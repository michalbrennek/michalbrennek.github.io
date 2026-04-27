---
layout: single
title: "The Machine That Looked Like Furniture"
date: 2026-04-27 08:00:00 +0100
categories: [Weather, HPC, History]
tags: [Cray, SeymourCray, NCAR, ECMWF, WarrenWashington, VectorProcessing, MesaLab, Computing]
header:
  teaser: /assets/images/header-cray.jpg
  overlay_image: /assets/images/header-cray.jpg
  overlay_filter: "0.6"
excerpt: "On July 11, 1977, two refrigerated electronic vans pulled up at the Mesa Laboratory in Boulder. Inside one of them was a 5.5-ton C-shaped cylindrical computer that looked, when you put it in a room, less like a piece of office equipment than like a piece of furniture you could sit on. NCAR had paid 8.86 million dollars for it. It would change the temperature of the world."
---

There is a piece of furniture sitting in a glass display case at the NCAR-Wyoming Supercomputing Center in Cheyenne. It is a little under two metres tall and almost three metres across at its base. It is shaped like a hollow cylindrical "C" -- a column of vertical chassis bays curved around an inner court, with the open side of the C facing out, and a ring of leather-padded benches running around the outside of its base. The benches are the kind of thing you might put in a hotel lobby. The cabinet itself is a deep, matte off-white with vertical accent stripes. It is beautiful in the way industrial things from the late 1970s sometimes were, when industrial designers were still allowed to make computers look like sculptures rather than like beige boxes.[^1]

Inside the cabinet, when this object was operational, sat 1 662 circuit-board modules in 113 different varieties, holding roughly 200 000 emitter-coupled-logic gates wired through twisted-pair cables that had each been individually cut to a specific length to keep the signal-propagation timings within 12.5 nanoseconds of each other. Behind a removable panel at the bottom, paired stainless-steel pipes circulated liquid Freon at high pressure to dissipate the 115 kilowatts of heat that the gates produced when they were running. The bench around the outside was not just a place to sit. It was a structural cover for the power supplies and the cooling system. In a 1976 article for the trade press, the editor Steve Callahan called the resulting object "the world's most expensive love seat."[^2] Within five years it would be the most photographed computer in the world, and the de facto symbol of supercomputing for the rest of the twentieth century.

The machine was the **Cray-1**. The bench in question -- serial number 3 -- was the first one anybody paid for. NCAR took delivery of it on July 11, 1977, in two refrigerated electronic vans that arrived at the Mesa Laboratory in Boulder, Colorado, after a road trip from Cray Research's plant in Chippewa Falls, Wisconsin. The price tag was 8.86 million dollars: 7.9 million for the system itself and roughly a million more for sixteen DD-19 disk drives. Thirty construction workers, engineers, and helpers were needed to move the machine from the trucks into the building. Its acceptance test ran in December 1977. With acceptance, Cray Research became, for the first time in its short history, a revenue-generating company.[^3]

This post is about that machine, and about the man who designed it, and about the climate scientists who put it to work.

---

## The Hermit of Chippewa Falls

<figure class="align-center" style="width: 90%;">
  <img src="/assets/images/Seymour_Cray_portrait.jpg" alt="Seymour Cray, designer of the Cray-1 and the most influential computer architect of the late twentieth century.">
  <figcaption>Seymour Cray, designer of the Cray-1 and arguably the most influential computer architect of the late twentieth century. He worked, in his own description, with a number-three Ticonderoga pencil, a pad of graph paper, and an absolutely quiet office in rural Wisconsin. Photo: NOAA, public domain.</figcaption>
</figure>

Seymour Roger Cray was born on September 28, 1925, in Chippewa Falls, Wisconsin -- a small town on the Chippewa River about ninety minutes east of Minneapolis-Saint Paul. His father, also Seymour, was the city civil engineer; his mother Lillian kept house for the family. The elder Seymour was a builder of bridges and water mains. His son was, from the age of about eight, a builder of automatic telegraph machines from Erector Sets, and -- by the age when other boys were playing baseball -- a builder of a punched-tape-to-Morse-code device that won him a high-school science prize.[^4]

He graduated from Chippewa Falls High School in June 1943, was drafted six months later, and spent the second half of the Second World War as an Army radio operator -- first in Europe, then in the Pacific theatre, where his unit was reassigned to break Japanese naval codes. The work was the kind of cryptanalytic problem-solving that lives in the very narrow intersection of mathematics, electronics, and patience. Cray would never afterwards say much about his Pacific service, but the experience is the through-line that connects his career to American codebreaking. The lab he would join in 1950, Engineering Research Associates of Saint Paul, had been formed out of the same Navy codebreaking operation that ran his wartime unit. ERA's first big customer, throughout the early 1950s, would be the U.S. National Security Agency. NSA would buy two CDC 6600s and a 6400 from Cray during the 1960s, would acquire one of the early Cray-1s for cryptanalysis, and would eventually induct Cray into its Hall of Honor for what its declassified internal history calls "a profound effect on NSA's mission from the 1950s to the 1990s."[^5]

He returned from the Pacific in 1946, took a bachelor's degree in electrical engineering from the University of Minnesota in 1949, and a master's degree in applied mathematics from the same institution in 1951. By that point he was already at ERA, where he had been hired as a technical staff member in 1950. He was twenty-six years old. He would design, in 1953, the **ERA 1103** -- the first commercially successful scientific computer, a vacuum-tube system shipped to twenty installations including the Lawrence Livermore Laboratory and the Bureau of Ships. He would be promoted at ERA, then at Remington Rand after the corporate merger, then at Sperry Rand after the next merger, with each step amplifying his frustration at corporate bureaucracy.[^6]

In 1957, Cray and a small group of ERA colleagues left to co-found a startup called **Control Data Corporation**, with William Norris as president. Norris was forty-six and a businessman; Cray was thirty-two and an engineer. Their first product was the **CDC 1604**, a transistor-based scientific computer that came out in 1960 -- one of the first commercially successful transistorised machines, and a substantial commercial success. The 1604 was followed in 1964 by the **CDC 6600**, which was, on the day it shipped, the fastest computer in the world. It would hold the title for five years, until succeeded in 1969 by its own successor, the **CDC 7600**, which would hold it for another six years.[^7] Both machines were Cray's designs. Both were built by a small team of engineers (the 6600 team was thirty-four people) that Cray had moved from CDC's Minneapolis headquarters to a remote laboratory in rural Wisconsin -- Chippewa Falls, his hometown. The lab was deliberately remote so that nobody from corporate could come bother him.

This is where the famous Cray stories begin. He worked, by his own account, with a number-three Ticonderoga pencil and a pad of graph paper. (Asked once which side of the graph paper he preferred, he said the back, "so the lines weren't too bright.") He never used a computer-aided design tool. His progress reports to CDC management were occasionally one sentence long -- the legendary example, framed and hung in a colleague's office, read in its entirety: *Activity is progressing satisfactorily as outlined under the June plan. There have been no significant changes or deviations from the June plan.* When asked about the secrets of his success by a visiting French scientist, he said: *Well, we have elves here, and they help me.* He then showed his visitor the entrance to a tunnel he had dug under his Lake Wissota property, where, he said, the elves brought him solutions to his problems while he was digging. Years later, when winter approached, he was reputed to design and build a sailboat, sail it during the summer, and then burn it at a party so that next winter he could begin again "without being held back by last year's ideas."[^8]

These stories are, almost all of them, what former Cray Research employees came to call **Rollwagenisms**, after John Rollwagen, who became Cray Research's CEO and an enormously gifted storyteller. Cray did dig some kind of small tunnel beneath his Lake Wissota basement -- four or five yards, never to another building. He did burn a sailboat once, at a Lake Wissota party. The myths grew from kernels of truth into much larger sculptural objects, and Rollwagen polished them. The truer truth, by all accounts of the people who actually worked with Cray, was that he was a quiet, focused, painstaking engineer who valued an absolutely silent room, hated bureaucracy, hated meetings, and was so unsentimental about his own past designs that he was widely understood to mean it when he said he wanted to start each new project with a clean sheet of graph paper and no carry-over from the one before.[^9]

In 1972, he left CDC. The trigger was Norris's decision to cancel the **CDC 8600**, a brute-force multi-processor design Cray had been working on for years. The 8600 was supposed to be ten times faster than the 7600. It was running into intractable cooling and reliability problems. Norris pulled the plug. Cray walked. The story is that Norris invested 250 000 dollars in startup capital for the new venture, and asked his old engineer to put together a five-year plan. Cray's reply, on a single sheet of paper, was as follows:

*Five-year goal: Build the biggest computer in the world. One-year goal: One-fifth of the above.*

That was the founding plan of Cray Research, Inc.[^10]

---

## The Vector Idea

Two architectural ideas defined the Cray-1 and most of what supercomputing would do for the following twenty years.

The first was **vector processing**. A conventional scalar computer of the early 1970s -- the IBM 360/195 at GFDL, say, or the CDC 7600 at NCAR -- executed one arithmetic operation at a time on a single pair of operands. Add A to B; store result in C. To add a thousand pairs, you ran the loop a thousand times. Each iteration paid the same overhead: load the inputs from memory, route them through the arithmetic unit, write the result back, increment the loop counter. For a numerical model of the atmosphere -- which spends almost all its time in nested loops doing the same arithmetic at every point in a three-dimensional grid -- this overhead was the dominant cost.

A vector computer recognised that the loop was the fundamental unit of work, and made the loop the fundamental hardware operation. The Cray-1 had eight **vector registers**, each capable of holding 64 64-bit floating-point numbers. A single instruction could load 64 values into a register; a single instruction could add the contents of two such registers and produce a third; a single instruction could store the result back to memory. The arithmetic units themselves were pipelined, so the result of operation N appeared one cycle after operation N-1 even though the operations themselves took several cycles each. And the machine could **chain** operations together: the output of an addition could feed directly into a multiplication without first returning to memory, with the chained operations executing in parallel rather than sequentially. On a well-vectorised inner loop, the Cray-1 could sustain something like one floating-point operation per clock cycle per arithmetic unit, with multiple chained units running together, for a peak performance of around 160 million operations per second. On scalar code -- the kind of thing that does not vectorise -- the same machine ran roughly five times slower than its peak. The whole architecture was a bet that the world's most important programs were vectorisable.[^11]

The bet paid off precisely at the institutions that had been waiting for it. Atmospheric models, ocean models, lattice quantum-chromodynamics calculations, finite-element structural simulations, Monte Carlo radiation transport, every kind of large-scale scientific computing built around nested loops over a regular grid -- all of these were exactly the codes the vector hardware had been designed to accelerate. An Argonne National Laboratory benchmark in 1978 showed Cray-1 vectorised code running 2.5 to 10 times faster than the equivalent scalar code on the same machine. A canonical Fast Fourier Transform benchmark went from 47 milliseconds on an IBM 360/195 to 3 milliseconds on the Cray-1. For numerical weather prediction this was not an incremental improvement. It was the difference between running a ten-day forecast in the morning and running it overnight.[^12]

The second architectural idea, much less commonly discussed but in some ways more consequential, was **balance**. Cray had watched the failure of two earlier vector projects -- the **CDC STAR-100** delivered to Lawrence Livermore in 1974, and the abandoned 8600 he had walked away from in 1972 -- and concluded that pure vector performance was not enough. The STAR-100 had impressive vector throughput but very poor scalar performance, which meant that real codes (which always have some scalar parts) ran disappointingly slowly. The 8600 had pursued raw clock speed at the cost of reliability. Cray's design philosophy for the Cray-1 was, instead, to build an *all-around fast* machine -- excellent scalar performance combined with excellent vector performance, with neither sacrificed to the other. The 12.5-nanosecond clock cycle was aggressive but not record-breaking. The vector registers were large but not enormous. The memory bandwidth was substantial -- 16 interleaved memory banks each with a 50-nanosecond cycle time, providing an aggregate of 638 megabits per second -- but not extreme. What made the Cray-1 fast was not any one number being the largest. It was that no number was the smallest.

This is the architectural lesson that, in retrospect, separated Cray from his competitors and his successors. It is also the philosophical statement that he made most often in interviews. *Anyone can build a fast CPU,* he liked to say. *The trick is to build a fast system.*[^13]

---

## The Shape

<figure class="align-center" style="width: 90%;">
  <img src="/assets/images/Cray_1_museum.jpg" alt="A Cray-1 on display at the Computer History Museum in Mountain View, California.">
  <figcaption>A Cray-1 on display at the Computer History Museum in Mountain View, California. The C-shaped cabinet is structural: every chassis bay is wired to its neighbours through twisted-pair cables that have been individually cut to specific lengths to equalise signal-propagation times. The leather-padded bench around the base hides the power supplies and the Freon cooling system. Photo: Wikimedia Commons, CC BY-SA 4.0.</figcaption>
</figure>

The Cray-1's distinctive shape -- a C-shaped vertical cabinet bent around an inner court, two metres tall and three metres across at the base, surrounded by a leather-padded bench -- was not industrial-design whimsy. It was a structural choice that came directly from the timing constraints.

The 12.5-nanosecond clock cycle was, in 1976, very fast. Light travels about 3.75 metres in 12.5 nanoseconds. The machine had to fit into a volume small enough that no signal had to travel more than a few feet between any two functional units, because if a signal had to travel further, it would arrive too late for the next clock edge. To minimise the longest signal paths, Cray's team did two things. They folded the chassis into a "C" so that any module could communicate with any other module by a path running along the inner curve of the C, rather than across a longer chord. And they cut each twisted-pair cable individually to a specific length so that the propagation time from any sender to any receiver was within tolerance. There were 1 662 modules in 113 different varieties. Each module connected to roughly a dozen others. Each connection had a precise length specification. The wiring of the Cray-1 was, by the standards of any other commercial computer of the era, an absurd quantity of bespoke handwork.[^14]

The cooling was also bespoke. The CDC 7600 had famously failed at least once a day in normal operation, four or five times a day at the worst sites; reliability had been one of Cray's chief concerns when he started thinking about the Cray-1. His solution was a Freon-based liquid cooling system that ran chilled refrigerant through stainless-steel pipes in direct contact with the circuit boards. The boards were paired back-to-back with a sheet of copper between them; the copper drew heat to the pipes; the Freon carried it out. The cooling system was, on its own, the size of a small room. With its associated chiller and condenser, it consumed almost as much power as the computer itself -- the total power draw of a Cray-1 at full operation was around 230 kilowatts, half of which was the computation and half of which was the cooling.[^15]

The bench around the base of the cabinet was a structural cover for the power supplies and the Freon plumbing. The bench had to be there. Industrial designers at Cray Research turned it from a necessity into an aesthetic element: leather-padded, comfortable to sit on, vaguely reminiscent of a hotel lobby's circular settee. The 1976 *Computerworld* article that called it "the world's most expensive love seat" was not entirely joking. People sat on it. Visiting dignitaries sat on it. Photographs were taken with the visiting dignitary in the foreground and the gleaming cylindrical cabinet behind them. The Cray-1 was probably the first computer in history that anybody bothered to make beautiful, and it is not an accident that the photograph of it became the visual symbol of supercomputing for the rest of the century. IBM made boxes. Cray made furniture.

The aesthetic choice was not free. Cray's competitors at the time -- IBM, CDC, Burroughs, Univac -- shipped computers in rectilinear cabinets that fit standard data-centre tile patterns. Cray's customers had to renovate computer rooms to accommodate the C-shaped footprint. They did it anyway. They wanted the machine.

---

## Six Months of Freon

The first Cray-1 -- serial number 1 -- shipped to Los Alamos National Laboratory in early 1976 on a six-month free-trial basis. Cray Research, at that point, had no other customers and no revenue. The trial deployment did not begin well. The Freon cooling system, in the Los Alamos installation, developed leaks. The compressor lubricant from the cooling system mixed with the Freon and coated the circuit boards with a film of oil. The oil shorted out the boards. The boards had to be removed, cleaned, and reinstalled. The leaks recurred. Cray Research engineers spent six months on site at Los Alamos, redesigning the welds, retesting the system, repeatedly cleaning and reinstalling the boards. The episode nearly bankrupted the company. By the spring of 1977 it was unclear whether Cray Research would survive long enough to deliver a second machine.[^16]

The fix, when it finally came, was a new welding technique for the Freon pipework that eliminated the leak paths. By June 1977, serial number 1 at Los Alamos was running reliably for periods of nearly four days at a time -- by the standards of the CDC 7600 it had replaced, this was a transformative reliability improvement. ECMWF's later operational data, covering serial number 6 between 1978 and 1985, gave a mean time between hardware faults of 96 hours.[^17] The Cray-1 was, despite Cray's reputation for sacrificing reliability for speed, the most reliable supercomputer anyone had built up to that date.

By the time the Freon problem was resolved, NCAR -- whose serial number 3 had been ordered in 1976 for delivery in 1977 -- had agreed to be the first paying customer. The order was approved by the National Science Foundation, which funded NCAR. The contract included a discount for serving as the first commercial reference site. The machine arrived in Boulder on July 11, 1977.

---

## The Mesa Laboratory

<figure class="align-center" style="width: 90%;">
  <img src="/assets/images/NCAR_Mesa_Lab.jpg" alt="The NCAR Mesa Laboratory, designed by I.M. Pei.">
  <figcaption>The NCAR Mesa Laboratory, designed by I.M. Pei in 1961-67 as the home of NCAR's research program, sits below the Flatirons sandstone cliffs above Boulder, Colorado. Pei based the design on the Anasazi cliff dwellings of Mesa Verde. The Cray-1 lived in the basement of this building for almost twelve years. Photo: NCAR / UCAR, public domain.</figcaption>
</figure>

The building NCAR's serial number 3 went into is itself worth a paragraph.

The National Center for Atmospheric Research had been founded in 1960 by the University Corporation for Atmospheric Research, sponsored by the National Science Foundation. Its founding director, Walter Orr Roberts, was an astronomer who had built his career on solar observations from a high-altitude site in Climax, Colorado, and who had been the principal advocate for an institutionally independent NSF-funded national centre to do the kinds of long-term, mission-driven atmospheric research that no individual university could sustain. The Colorado state legislature appropriated 250 000 dollars to buy 500 acres of mesa-top land south of Boulder for the new centre, and in 1961 NCAR selected as its architect a young Chinese-American by the name of **I.M. Pei**.[^18]

Pei was forty-four. He had built nothing famous yet -- the Louvre Pyramid was almost three decades in the future, the Bank of China Tower in Hong Kong was thirty years away. NCAR's Mesa Laboratory was one of his first major projects. He visited the site, looked at the Flatirons -- the dramatic slabs of Permian sandstone that tilt up out of the foothills west of Boulder -- and modelled the building on the Anasazi cliff dwellings of Mesa Verde National Park, three hundred kilometres to the southwest. The Mesa Lab is two clusters of stepped, terracotta-coloured concrete towers, set into the side of the mesa, with deep window recesses that look like the natural shadow patterns of cliff alcoves. Construction began in April 1964. The building was completed in 1966 and dedicated in 1967. It is still, in 2026, one of the most photographed scientific buildings in the United States. Pei went on to design the John F. Kennedy Library, the East Building of the National Gallery, and the Louvre Pyramid; the Mesa Laboratory remains in his retrospective bibliography as one of the projects that he later said he was proudest of.

The Cray-1 arrived in 1977 and lived in the basement of the Mesa Laboratory until January 27, 1989, when it was decommissioned after eleven and a half years of operational service.[^19] During that time it ran the codes of essentially every major American atmospheric and climate research program. It produced the Penn State - NCAR Mesoscale Model -- which would, through its successors MM1 through MM5, become one of the most widely used regional weather models in the world. It produced the first three-dimensional ocean general-circulation simulations of the Antarctic Circumpolar Current under Albert Semtner and William Holland. It produced the first numerical simulations of the solar dynamo by Peter Gilman. It produced detailed thunderstorm models from research groups at Illinois, Colorado State, and Hawaii. And it produced, most importantly for the long-term influence of the institution, the first generations of the **Community Climate Model**.

---

## Warren Washington and the Climate Code

The principal scientist who put NCAR's Cray-1 to work for climate modelling was **Warren Morton Washington**, born August 28, 1936, in Portland, Oregon. He was the second of five sons of Edwin Washington, a Pullman porter on the Union Pacific Railroad, and a nurse mother. The elder Washington had wanted to be a schoolteacher; in 1920s Portland, the city would not hire Black men to teach in public schools, and so he had supported the family by waiting tables in Pullman cars on the run from Portland to Chicago.[^20]

The younger Washington was, by his own account, told by his Jefferson High School counsellor that he should consider a business school rather than college. He ignored the advice. He took a bachelor's degree in physics at Oregon State University in 1958, a master's degree in meteorology there in 1960, and a doctoral degree in meteorology at Pennsylvania State University in 1964. He thereby became the second African American in the history of the United States to earn a doctorate in meteorology. The first was **Charles E. Anderson** (1919-1994), a former Tuskegee Airman, whom Washington in later interviews credited as his role model.

He arrived at NCAR in 1963 -- one year before defending his PhD -- and stayed for sixty-one years. Through the 1960s, working with the Japanese-American meteorologist **Akira Kasahara**, he built one of the first three general circulation models of the atmosphere ever constructed (the other two were [Manabe's at GFDL](/weather/hpc/history/2026/04/13/The-forecast-that-reached-the-Nobel.html) and [Mintz and Arakawa's at UCLA](/weather/hpc/history/2026/04/22/The-fireman-and-the-visionary.html)). The Kasahara-Washington model used height as the vertical coordinate rather than pressure, ran on NCAR's CDC 3600 in the early 1960s, then on the CDC 6600, then on the CDC 7600, then on the Cray-1 from 1977 onward.

It was on the Cray-1 that Washington's work transitioned to what would become NCAR's most enduring scientific contribution: the **Community Climate Model**, designed not just for NCAR's internal use but as a tool for the broader university community served by UCAR. CCM0 was publicly released in 1982, CCM1 in 1987, CCM2 in 1992. The CCM evolved through CCM3 and CCM4 into the **Community Climate System Model** (CCSM) and then the **Community Earth System Model** (CESM), which is, in 2026, one of the three most widely used climate models in the world. Every coupled climate simulation in the IPCC's Sixth Assessment Report that runs on a CESM-family model -- and a substantial fraction do -- is the descendant, in lineage, of the codes that Washington and Kasahara first built on NCAR's Cray-1.

Washington served as scientific adviser to six U.S. presidential administrations from Carter to Obama. He was elected to the National Academy of Engineering in 2002. He chaired the National Science Board from 2002 to 2006. His research was part of the IPCC assessments that shared the 2007 Nobel Peace Prize with Al Gore. He received the National Medal of Science from President Obama in 2009 and the Tyler Prize for Environmental Achievement in 2019. He died at his home in Denver, Colorado, on October 18, 2024, age 88. The boy from Portland whose high-school counsellor had advised business school had spent six decades shaping the global understanding of climate, much of it through software running on the C-shaped machine in the basement of I.M. Pei's mesa.[^21]

---

## CFT and the Vectorised FORTRAN

There is a piece of software inside the Cray-1 story that connects it to the [Fortran trilogy](/weather/hpc/history/2026/04/21/The-language-that-refused-to-die.html) I wrote earlier in this series.

The Cray-1's hardware was useless without a compiler that could automatically generate vector code. Scientists were not going to rewrite their atmospheric models in vector assembly. Cray Research, in 1976-78, built the **Cray Fortran Translator** -- usually known as **CFT** -- which was the first commercial FORTRAN compiler that automatically vectorised inner loops. CFT took ANSI 1966 FORTRAN as input, identified the data dependencies inside DO loops, and where the analysis was conclusive, emitted vector instructions that operated on 64 elements at a time. Crucially, it did this without requiring any source modifications. A weather model that had been written for an IBM 360 in 1970 could, on a good day, be fed to CFT on a Cray-1 in 1978 and come out two-and-a-half to ten times faster.[^22]

CFT was a quietly important piece of software in the history of scientific computing. It is the reason the Cray-1's vector hardware was actually usable by atmospheric scientists in the 1970s, rather than usable in principle. It established the design pattern -- automatic vectorisation by the compiler rather than explicit vector instructions in the source code -- that every subsequent vector compiler from CDC, Fujitsu, Hitachi, NEC, and Cray Research itself would follow into the 1990s. It also, indirectly, shaped how scientists wrote FORTRAN in the 1980s. Loops with branches inside them did not vectorise. Subroutine calls inside inner loops did not vectorise. Array indices that depended on themselves through previous iterations -- recurrences -- did not vectorise. The scientific FORTRAN community, through the late 1970s and 1980s, gradually rewrote itself into a style that maximised vectorisation: cleaner loops, fewer branches, careful separation of innermost-loop work from outer-loop bookkeeping. The codes got faster on Cray hardware, and -- as a side effect -- they also got more readable.

The Bryan-Cox / MOM ocean code I wrote about in [the Bryan post](/weather/hpc/history/2026/04/23/The-man-who-fit-the-entire-ocean-in-half-a-megabyte.html), the [UCLA GCM](/weather/hpc/history/2026/04/22/The-fireman-and-the-visionary.html) descendants under James Hansen at GISS, the Manabe-Bryan coupled GFDL model, the Penn State - NCAR Mesoscale Model, the European IFS at ECMWF, and Washington's own Kasahara-Washington and CCM lineage -- every one of them spent some part of the 1980s being restructured for Cray vector processing. The discipline of writing for vectorisation is what made the modern operational weather and climate models capable of running on the next generation of parallel machines, because the same loop-level cleanliness that vectorisation rewards is also what parallelisation rewards. Cray's vector hardware is gone. The coding discipline it forced on the field is still there.

---

## Reading on October 24, 1978

The other big customer was European.

The **European Centre for Medium-Range Weather Forecasts** had been chartered in 1975 by a convention signed by ten European member states -- Belgium, Denmark, Germany, Spain, France, Greece, Ireland, Italy, the Netherlands, the United Kingdom, plus Switzerland, Sweden, Yugoslavia, Finland, and Austria as associate members -- with a mandate to do medium-range forecasting (three days to fifteen days ahead) at a scale and resolution that no national weather service in Europe could afford individually. The new centre's headquarters was at Shinfield Park in Reading, England, deliberately chosen for proximity to the UK Met Office and the University of Reading's meteorology department. The first director was **Aksel Wiin-Nielsen**, a Danish meteorologist who had trained under Carl-Gustaf Rossby in Stockholm in the early 1950s and who had participated in the [BESK forecasts in Stockholm in 1954](/weather/hpc/history/2026/04/03/The-swedes-got-there-first.html). Wiin-Nielsen served as ECMWF's first Director from January 1, 1974, through December 31, 1979. The first head of research, hired in 1975, was the Swedish meteorologist **Lennart Bengtsson**, who would become Director-General from 1982 to 1990 and would lead ECMWF into the position of world leadership in medium-range forecasting that it has held since.[^23]

ECMWF's first Cray-1A was installed at Shinfield Park on **October 24, 1978**. It was the first Cray installation in Europe and one of the very first commercial Cray installations outside the United States. Operational forecasting on an experimental basis began on **August 1, 1979**: ten-day forecasts, five days a week, at 210-kilometre horizontal resolution with fifteen vertical levels, using the so-called N48 spectral model. A single ten-day forecast required about five hours of CPU time on the Cray-1A. Full operational seven-day-a-week forecasting began on **August 1, 1980**. By the early 1980s the ECMWF medium-range forecast was, in skill measurements against radiosonde and satellite observations, the best operational forecast on Earth. The combination of multinational scientific staff, a state-of-the-art Cray, a focus on data assimilation that Bengtsson had insisted on, and the institutional independence to invest in long-term research rather than short-term operational service-delivery had made ECMWF, within five years of its founding, the global leader in numerical weather prediction.[^24]

This was a substantial shift. American NWP -- at GFDL, at NMC, at NCAR, at the Naval Research Laboratory -- had been the pace-setter through the 1950s, 1960s, and early 1970s. From roughly 1980 onwards, ECMWF was. The shift was substantially driven by the European Cray. The Americans had Crays too, of course; NCAR's serial number 3, the National Severe Storms Laboratory in Norman, the Naval Research Laboratory in Monterey, Lawrence Livermore. But ECMWF had a Cray dedicated entirely to medium-range forecasting research, with no operational service-delivery duty, no political constraints from a single national bureaucracy, and a mandate from sixteen governments to take long-term scientific risks. The Cray-1A in Reading was the European answer to the American supercomputing dominance of the 1960s. It worked.

---

## What Came Next

The Cray-1 dominated supercomputing until 1982, when its successor -- the **Cray X-MP**, designed not by Seymour Cray but by his colleague Steve Chen -- shipped with two processors and roughly five times the Cray-1's performance. Cray himself, by that point, had stepped down as CEO of Cray Research (1980) and had moved with a small team to Colorado Springs to start work on the **Cray-2**. The Cray-2 shipped in 1985. It was a four-processor machine with 256 megawords of memory (more than all previously delivered Cray hardware combined) and a Fluorinert immersion cooling system that immersed the entire computer in clear fluorinated liquid. Critics called it "the world's most expensive aquarium." It ran at 1.9 gigaflops peak, was the world's fastest computer from 1985 to 1987, and shipped about thirty units.[^25]

In 1989 Cray spun off his next project, the **Cray-3**, into a separate company called Cray Computer Corporation, which moved to Colorado Springs. The Cray-3 was supposed to use experimental gallium arsenide semiconductors instead of silicon, which would, in principle, allow much faster clock speeds. In practice, gallium arsenide chips of the necessary complexity could not be manufactured reliably. Only one production Cray-3 was ever delivered, in May 1993, to NCAR -- serial number S5, nicknamed "Graywolf" -- as a test and evaluation system. NCAR's first Cray, in 1977, and Cray's last commercial machine, in 1993, bookended the same institution. Cray Computer Corporation filed for Chapter 11 bankruptcy on March 24, 1995.[^26]

Cray himself did not survive the decade.

On Sunday, September 22, 1996, he was driving his Jeep Cherokee on Interstate 25 near the United States Air Force Academy, north of Colorado Springs. Another vehicle struck his Jeep while he was merging. The Jeep rolled three times. He suffered a broken neck, severe head injuries, and fractured ribs, and was taken by ambulance to Penrose Hospital in Colorado Springs, where he was hospitalised in critical condition. He died there on October 5, 1996, two weeks after the accident, at the age of seventy-one. The other driver was cited for careless driving.[^27]

His final company, **SRC Computers**, founded earlier in 1996, had not yet shipped a product. Cray's last published statement on what supercomputing should be -- captured in his 1996 SRC Computers founding statement -- summarised the design philosophy of his entire career: *Anyone can build a fast CPU. The trick is to build a fast system.*

---

## The Bench in Cheyenne

NCAR's serial number 3, after eleven and a half years of running the climate codes that defined a generation of American atmospheric science, was decommissioned on January 27, 1989. It was succeeded at NCAR by a Cray X-MP (1986), a Cray Y-MP (1989), a Cray T3D (1995), a Cray T3E (1997), and a long succession of subsequent machines through the 2024-era HPE Cray EX systems that NCAR runs in Cheyenne today. The original Cray-1A was kept in storage on the Mesa Lab campus for many years, then placed on permanent public display at the NCAR-Wyoming Supercomputing Center in Cheyenne in 2021, when the new facility was completed.[^28]

It is worth visiting if you are in the area. The bench is still in place. The leather is original. The cabinet is still gleaming off-white with vertical accent stripes. There is no cooling running, and the gates inside are no longer wired to anything, and the twisted-pair cables -- 1 662 modules' worth of them, each cut to a specific length -- are fixed in place in their original geometry. If you sit on the bench you can put your hand against the side of the cabinet and feel the slight curve where the cylindrical column wraps inward. This is what supercomputing looked like for fifteen years.

The machine was built by a man who worked with a number-three pencil and a pad of graph paper in a small office in Chippewa Falls, Wisconsin. He died in 1996 in a car accident. His machine, in the basement of a building designed to look like Anasazi cliff dwellings by an architect who would later design the Louvre Pyramid, ran the codes of a climate scientist whose father had been a Pullman porter and whose high-school counsellor had told him to attend business school. It produced the first generations of an American climate model whose descendants are, in 2026, projecting the temperature of the planet through the twenty-second century. It was the first paying customer's order for a Wisconsin startup that would go on to dominate scientific computing for a quarter of a century. It looked, at the same time, like a piece of furniture you could sit on.

This was not an accident. The look was the point. Cray and his industrial designers wanted the machine to be beautiful, because they understood that supercomputing was a category of work whose customers were unusual, whose budgets were enormous, and whose imagination was their most renewable resource. A machine that looked like a sculpture got photographed. A machine that got photographed got remembered. A machine that got remembered got bought. The eighty Cray-1s sold over the production run -- between, perhaps, a half-billion and a billion 1980 dollars in revenue, depending on how you count -- were sold partly because the machine was the fastest computer in the world and partly because the people writing the cheques wanted, deeply, to own one.

This is how an entire generation of weather and climate scientists, from Boulder to Reading to Princeton to Tokyo, ended up running their codes on the same C-shaped machine. The mathematics of the atmosphere did not require a beautiful computer. The career of the man who designed the computer did. Both got what they needed.

---

## Footnotes

[^1]: Description of the surviving NCAR Cray-1 (serial number 3) on display at the NCAR-Wyoming Supercomputing Center in Cheyenne. NCAR/CISL "Historic Cray-1A moved from Boulder to Cheyenne" article, [cisl.ucar.edu](https://www.cisl.ucar.edu/news/historic-cray-1a-moved-boulder-cheyenne); NCAR/CISL "CRI Cray-1A S/N 3" page, [cisl.ucar.edu](https://www.cisl.ucar.edu/ncar-supercomputing-history/c1).

[^2]: The "world's most expensive love seat" phrase is widely attributed to a 1976 *Computerworld* article; the attribution to the editor Steve Callahan at Auerbach is given in Richard M. Russell's contemporaneous reporting. [Cray-1 Wikipedia](https://en.wikipedia.org/wiki/Cray-1) discusses the phrase's history.

[^3]: NCAR/CISL Cray-1A serial #3 page, [cisl.ucar.edu](https://www.cisl.ucar.edu/ncar-supercomputing-history/c1). Two refrigerated electronic vans, July 11, 1977 delivery, $8.86 million ($7.9M for system, ~$1M for sixteen DD-19 disk drives), December 1977 acceptance test.

[^4]: [Seymour Cray -- Wikipedia](https://en.wikipedia.org/wiki/Seymour_Cray); [Britannica entry](https://www.britannica.com/biography/Seymour-R-Cray).

[^5]: NSA's declassified internal history of Cray's contribution: [Seymour Cray and NSA, NSA Cryptologic Heritage](https://www.nsa.gov/portals/75/documents/news-features/declassified-documents/history-today-articles/10%202018/05OCT2018%20SEYMOUR%20CRAY%20and%20NSA.pdf).

[^6]: [ERA 1103 -- Wikipedia](https://en.wikipedia.org/wiki/UNIVAC_1103); Cray's 1950-1957 ERA-Remington Rand-Sperry Rand career is summarised in the Britannica entry, [britannica.com/biography/Seymour-R-Cray](https://www.britannica.com/biography/Seymour-R-Cray).

[^7]: [CDC 1604](https://en.wikipedia.org/wiki/CDC_1604); [CDC 6600](https://en.wikipedia.org/wiki/CDC_6600); [CDC 7600](https://en.wikipedia.org/wiki/CDC_7600). Each of these machines was, on the date it shipped, the fastest computer in the world.

[^8]: The "Activity is progressing satisfactorily" status report quote is widely reproduced; one published source is the *Today in Science* compilation of Cray quotations at [todayinsci.com](https://todayinsci.com/C/Cray_Seymour/CraySeymour-Quotations.htm). The elves-and-tunnel quote and the burning-sailboat story are summarised in the Cray-History.net retrospective at [cray-history.net](https://cray-history.net/2023/12/16/jim-masoco-recalls-life-working-at-cray-research-and-seymour-stories/).

[^9]: Jim Masocco, a former Cray Research employee, on the relationship between the Cray myths and the actual man: [Cray-History.net interview](https://cray-history.net/2023/12/16/jim-masoco-recalls-life-working-at-cray-research-and-seymour-stories/). Masocco notes that Cray dug only four or five yards of basement excavation, never to another building, and that the burning-sailboat incident happened once rather than annually -- but that the underlying philosophy of designing each new project from a clean sheet was real.

[^10]: The "five-year goal" anecdote is quoted in the [HPCwire Cray obituary, 1996](https://www.hpcwire.com/1996/10/18/seymour-cray-and-lake-wissota/) and in numerous Cray Research retrospectives.

[^11]: Vector processing architecture and the Cray-1's design choices: Russell, R. M. (1978). "The CRAY-1 Computer System." *Communications of the ACM* 21(1), 63-72. [PDF copy at University of Wisconsin](https://pages.cs.wisc.edu/~markhill/restricted/cacm78_cray1.pdf).

[^12]: Argonne National Laboratory benchmark, 1978, summarised in the Cray-1 Wikipedia article. The FFT benchmark comparison (47 ms IBM, 3 ms Cray-1) is in [Cray-1 -- Wikipedia](https://en.wikipedia.org/wiki/Cray-1).

[^13]: The "anyone can build a fast CPU" quote is widely reproduced from interviews Cray gave in the early 1990s, including his SRC Computers founding statements.

[^14]: Russell 1978, same reference as footnote 11. The 1 662 modules and 113 module varieties figure is from the same source.

[^15]: Cray-1A power consumption and Freon cooling specifications: Russell 1978; supplemental detail in [Cray-1 -- Wikipedia](https://en.wikipedia.org/wiki/Cray-1).

[^16]: The Los Alamos Freon-leak episode and the welding fix: [Cray-1 -- Wikipedia](https://en.wikipedia.org/wiki/Cray-1); [Cray History at HPE](https://www.hpe.com/us/en/compute/hpc/cray.html).

[^17]: ECMWF's measured 96-hour mean time between hardware faults on the Cray-1A is cited in the Cray-1 Wikipedia article.

[^18]: NCAR's founding history and the Mesa Laboratory: [Mesa Laboratory -- Wikipedia](https://en.wikipedia.org/wiki/Mesa_Laboratory); [Walter Orr Roberts -- Wikipedia](https://en.wikipedia.org/wiki/Walter_Orr_Roberts).

[^19]: NCAR Cray-1A operational dates and decommissioning: [NCAR/CISL Cray-1A page](https://www.cisl.ucar.edu/ncar-supercomputing-history/c1).

[^20]: Warren Washington's biography, including the Pullman-porter detail and the high-school counsellor anecdote, is from [BlackPast.org](https://blackpast.org/african-american-history/warren-m-washington-1936/) and [the Oregon Encyclopedia](https://www.oregonencyclopedia.org/articles/washington-warren/).

[^21]: NCAR/UCAR's tribute on Washington's death: [news.ucar.edu](https://news.ucar.edu/132989/nsf-ncar-and-ucar-mourn-passing-distinguished-scholar-warren-washington).

[^22]: CFT and automatic vectorisation: Russell 1978 (footnote 11); Cray Research Inc., *CFT Reference Manual*, available at [Internet Archive](https://archive.org/details/cray-fortran).

[^23]: ECMWF's founding and the Wiin-Nielsen / Bengtsson directorships: [ECMWF history](https://www.ecmwf.int/en/about/who-we-are/history); the recent *Nature Communications* retrospective "50 years of weather forecasting at the ECMWF," [nature.com](https://www.nature.com/articles/s41467-025-65837-2).

[^24]: ECMWF Cray-1A installation date October 24, 1978 and the operational forecasting timeline beginning August 1, 1979: [ECMWF "40 years of operational medium-range forecasting" announcement, 2019](https://www.ecmwf.int/en/about/media-centre/news/2019/ecmwf-celebrates-40-years-operational-medium-range-forecasting).

[^25]: Cray-2 specifications: [Cray-2 -- Wikipedia](https://en.wikipedia.org/wiki/Cray-2).

[^26]: Cray-3 and Cray Computer Corporation history: [NCAR/CISL Cray-3 (Graywolf) page](https://www.cisl.ucar.edu/ncar-supercomputing-history/graywolf); [Cray-3 -- Wikipedia](https://en.wikipedia.org/wiki/Cray-3).

[^27]: Cray's death: [HPCwire Cray obituary, 1996](https://www.hpcwire.com/1996/10/18/seymour-cray-and-lake-wissota/); John Markoff's *New York Times* obituary, reproduced at [pages.cs.wisc.edu/~bezenek/cray.html](https://pages.cs.wisc.edu/~bezenek/cray.html).

[^28]: NCAR's supercomputer succession after the Cray-1A: [NCAR/CISL supercomputing history](https://www.cisl.ucar.edu/ncar-supercomputing-history).

---

## References

**Primary technical sources:**

* Russell, R. M. (1978). "The CRAY-1 Computer System." *Communications of the ACM* 21(1), 63-72. [PDF](https://pages.cs.wisc.edu/~markhill/restricted/cacm78_cray1.pdf).
* Cray Research Inc. *CFT Reference Manual.* [Internet Archive copy](https://archive.org/details/cray-fortran).
* Cray Research Inc. *CRAY-1 Computer System Hardware Reference Manual* (1979).

**Histories and retrospectives:**

* [Cray-1 -- Wikipedia](https://en.wikipedia.org/wiki/Cray-1).
* [Seymour Cray -- Wikipedia](https://en.wikipedia.org/wiki/Seymour_Cray).
* [Britannica: Seymour R. Cray](https://www.britannica.com/biography/Seymour-R-Cray).
* John Markoff, "Seymour R. Cray, Computer Industry Pioneer and Father of the Supercomputer, Is Dead," *New York Times*, October 6, 1996, [reproduced at University of Wisconsin](https://pages.cs.wisc.edu/~bezenek/cray.html).
* HPCwire, "Seymour Cray and Lake Wissota," October 18, 1996, [hpcwire.com](https://www.hpcwire.com/1996/10/18/seymour-cray-and-lake-wissota/).
* Cray-History.net, ["Jim Masocco recalls life working at Cray Research"](https://cray-history.net/2023/12/16/jim-masoco-recalls-life-working-at-cray-research-and-seymour-stories/), 2023.
* NSA, "Seymour Cray and NSA," declassified Cryptologic Heritage document, [PDF](https://www.nsa.gov/portals/75/documents/news-features/declassified-documents/history-today-articles/10%202018/05OCT2018%20SEYMOUR%20CRAY%20and%20NSA.pdf).

**NCAR and the Mesa Laboratory:**

* [NCAR/CISL "CRI Cray-1A S/N 3"](https://www.cisl.ucar.edu/ncar-supercomputing-history/c1).
* [NCAR/CISL Supercomputing History](https://www.cisl.ucar.edu/ncar-supercomputing-history).
* [Mesa Laboratory -- Wikipedia](https://en.wikipedia.org/wiki/Mesa_Laboratory).
* [Walter Orr Roberts -- Wikipedia](https://en.wikipedia.org/wiki/Walter_Orr_Roberts).
* NCAR News, ["The Cray-1: Not your ordinary supercomputer"](https://news.ucar.edu/3266/cray-1-not-your-ordinary-supercomputer).
* NCAR/CISL, ["Historic Cray-1A moved from Boulder to Cheyenne"](https://www.cisl.ucar.edu/news/historic-cray-1a-moved-boulder-cheyenne).

**Warren Washington:**

* NCAR News, ["NSF NCAR and UCAR mourn the passing of Distinguished Scholar Warren Washington"](https://news.ucar.edu/132989/nsf-ncar-and-ucar-mourn-passing-distinguished-scholar-warren-washington).
* [Warren M. Washington -- Wikipedia](https://en.wikipedia.org/wiki/Warren_M._Washington).
* [Warren Morton Washington (1936-2024) -- Oregon Encyclopedia](https://www.oregonencyclopedia.org/articles/washington-warren/).
* [Warren M. Washington -- BlackPast.org](https://blackpast.org/african-american-history/warren-m-washington-1936/).

**ECMWF:**

* [ECMWF -- Our History](https://www.ecmwf.int/en/about/who-we-are/history).
* ECMWF, ["ECMWF celebrates 40 years of operational medium-range forecasting" (2019)](https://www.ecmwf.int/en/about/media-centre/news/2019/ecmwf-celebrates-40-years-operational-medium-range-forecasting).
* "50 years of weather forecasting at the ECMWF," *Nature Communications* (2025), [nature.com](https://www.nature.com/articles/s41467-025-65837-2).

**Cray-2, Cray-3, and the later Cray history:**

* [Cray-2 -- Wikipedia](https://en.wikipedia.org/wiki/Cray-2).
* [Cray-3 -- Wikipedia](https://en.wikipedia.org/wiki/Cray-3).
* [NCAR/CISL Cray-3 "Graywolf" page](https://www.cisl.ucar.edu/ncar-supercomputing-history/graywolf).
* [Cray History -- HPE](https://www.hpe.com/us/en/compute/hpc/cray.html).

**Cross-references in this series:**

* [The Forecast That Reached the Nobel](/weather/hpc/history/2026/04/13/The-forecast-that-reached-the-Nobel.html) -- Manabe and the GFDL atmospheric modelling lineage; the GCM tradition that NCAR's Kasahara-Washington model parallels.
* [The Fireman and the Visionary](/weather/hpc/history/2026/04/22/The-fireman-and-the-visionary.html) -- Mintz and Arakawa at UCLA; the third of the three original GCM programmes.
* [The Man Who Fit the Entire Ocean in Half a Megabyte](/weather/hpc/history/2026/04/23/The-man-who-fit-the-entire-ocean-in-half-a-megabyte.html) -- Kirk Bryan and the GFDL ocean model.
* [The Language That Refused to Die](/weather/hpc/history/2026/04/21/The-language-that-refused-to-die.html) -- Modern Fortran, the language CFT compiled and the language that all current operational weather and climate models still use.
* [The Swedes Got There First](/weather/hpc/history/2026/04/03/The-swedes-got-there-first.html) -- BESK, Stockholm 1954, the European Cray story's pre-history; Wiin-Nielsen's training under Rossby.
