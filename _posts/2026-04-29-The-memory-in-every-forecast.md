---
layout: single
title: "The Memory in Every Forecast"
date: 2026-04-29 08:00:00 +0100
categories: [Weather, HPC, History]
tags: [Whirlwind, Forrester, Wang, Papian, Olsen, Everett, Aiken, MIT, Harvard, SAGE, CoreMemory, Computing]
header:
  teaser: /assets/images/header-whirlwind.jpg
  overlay_image: /assets/images/header-whirlwind.jpg
  overlay_filter: "0.6"
excerpt: "On 29 June 1948, walking through Harvard Yard, a young Chinese physicist named An Wang wrote in his notebook the principle that would make computer memory practical. Twelve months later, on 13 June 1949, on the other side of Cambridge, an MIT engineer named Jay Forrester wrote down the architecture that would make Wang's invention scale. The IBM patent dispute that followed was one of the formative IP cases of early computing. The memory technology they invented powered every weather and climate machine for the next twenty-five years."
---

In the late spring of 1948, on the second floor of an undistinguished brick building on the northern edge of Harvard Yard, a twenty-eight-year-old Chinese applied physicist named **An Wang** sat at a workbench staring at a small ferrite ring. The ring -- a magnetic donut roughly the size of a pencil eraser -- had two stable states: magnetized clockwise or magnetized counterclockwise. With the right pulse of electric current it would switch from one state to the other and stay there indefinitely without further power. Wang had been thinking about computer memory for three weeks. The Mark IV computer that his employer Howard Aiken was building for the U.S. Air Force used rotating magnetic drums for memory, which were slow and mechanical. Williams electrostatic tubes had random access but lost their bits in milliseconds. Mercury delay lines were one-dimensional. What Wang had in mind was different: read a bit by flipping the core to a known reference state, then immediately rewrite the original bit back into the same core. The read would be destructive, but the act of destroying the bit would tell you what it had been.

On **29 June 1948** Wang wrote the idea out in his lab notebook. "It is very possible," he noted, "that the information can stay there ... and be transferred many times before the information [is lost or muddied]."[^1]

Twelve months later, on **13 June 1949**, in a different basement on the other side of Cambridge -- at MIT's Servomechanisms Laboratory in the Barta Building on Massachusetts Avenue -- a thirty-year-old electrical engineer named **Jay Forrester** scribbled a different version of the same problem in his own notebook. Forrester was running a computer project the Navy had originally commissioned to be a flight simulator. By 1949 the simulator part had been quietly dropped and the computer itself, called Whirlwind, was running on Williams-style electrostatic storage tubes that failed roughly every fifteen minutes. Forrester had just seen an advertisement in *Electrical Engineering* magazine for a magnetic alloy called Deltamax, ordered samples, formed them into rings, and confirmed that they switched between two stable states under modest electrical drive. His notebook entry sketched a three-dimensional array: every ring would sit at the intersection of two perpendicular wires, and only the unique ring at the intersection of two simultaneously-energized wires would see enough current to flip. The math was elegant. To address X-times-Y rings you needed only X-plus-Y drivers.[^2]

What Wang had captured in 1948 was the *principle* of magnetic-core memory: that a destructive read followed by an immediate rewrite was practical. What Forrester invented in 1949 was the *architecture*: a three-dimensional array selected by coincident half-currents on perpendicular wires. Both inventions were necessary. Neither alone was sufficient. The technology that emerged from them -- magnetic-core random-access memory -- would dominate computing from August 1953 through roughly 1976 and would, in particular, be the working memory of every machine that performed numerical weather prediction during that period: the IBM 704 that ran Norman Phillips's first general circulation experiment, the IBM 7090 and 7094 that ran the early GFDL climate models, the CDC 1604 and 6600 and 7600 at NCAR, the UNIVAC 1108 on which Suki Manabe and Kirk Bryan first coupled an ocean to an atmosphere, the DEC VAX 11/780 on which Mark Cane and Stephen Zebiak ran [the first El Nino forecast](/weather/hpc/history/2026/04/28/The-forecast-on-a-VAX.html). None of those machines would have been possible without memory that worked. Memory that worked, in 1953, meant magnetic cores. Magnetic cores, in 1953, meant Wang's principle and Forrester's architecture.

The two notebooks, twelve months apart, are the centre of this post.

## The memory problem of 1948

The early stored-program computer was, until about 1953, a machine without reliable memory. The arithmetic worked. The vacuum-tube logic worked. Operations could be performed at speeds approaching one microsecond. What did not work was the place where you put the bits between operations.

Three families of memory technology had been tried by 1948.

The first was the **mercury delay line**, an idea that came out of wartime radar work and was carried into computing by J. Presper Eckert and John Mauchly. The principle was acoustic. A pulse generator at one end of a sealed glass tube of liquid mercury fired ultrasonic pulses into the column; piezoelectric transducers at each end detected and regenerated them. The bit pattern propagated through the mercury at the speed of sound -- about 1450 metres per second -- and looped back to the generator every millisecond or so. EDVAC, EDSAC, BINAC, and UNIVAC I all used delay-line memory. It worked, in the sense that you got your bits back. But the access pattern was strictly sequential: if you wanted bit number 327 of a 1024-bit line, you waited for it to come around. Mercury was toxic; the tubes were heavy; the apparatus was mechanically fragile; and the speed of sound shifted noticeably with temperature.[^3]

The second was the **Williams tube**, a memory technology that came out of the same Manchester laboratory where Alan Turing's group had built the Mark I codebreaking machine. F. C. Williams and Tom Kilburn had figured out in 1947 that a modified cathode-ray tube would hold a charge pattern on its phosphor screen for a few hundred microseconds, long enough to be read out by a sensing plate held against the outside of the glass. Bits could be addressed at random by deflecting the electron beam to the appropriate spot on the screen. The Williams tube was the random-access memory of the Manchester Baby (the world's first stored-program computer), the IAS machine, the IBM 701 (IBM's first commercial scientific computer), the BESK in Stockholm, and -- briefly and unhappily -- of Whirlwind. The trouble was that the read operation was destructive (the electron beam erased what it had detected), the charge pattern decayed and had to be refreshed every few hundred microseconds, the screens drifted with use and aging, and most installations had to be hand-tuned. A good Williams tube might run for a few minutes between failures. A bad one might fail every few seconds. The IBM 701 in production ran with a mean time between memory faults of about fifteen minutes. Whirlwind in 1951 to 1953 ran on similarly afflicted electrostatic storage tubes -- of MIT's own design, with two electron guns per tube to address bits more reliably than the Manchester original -- that the project reportedly spent on the order of thirty-two thousand dollars per month replacing, close to forty per cent of the project's running costs going to memory tubes alone.[^4]

<figure class="align-center" style="width: 70%;">
  <img src="/assets/images/Williams_tube.jpg" alt="Williams electrostatic storage tube on display at The National Museum of Computing.">
  <figcaption>A Williams-Kilburn electrostatic storage tube. The phosphor screen on the front held bit patterns as charge; a sense plate against the outside of the glass detected them. Williams tubes were the random-access memory of the world's first stored-program computers but were famously unreliable. Whirlwind ran on a related electrostatic-tube design in 1951 to 1953 before magnetic cores replaced it. <em>Source: BadgersCP / Wikimedia Commons. License: CC0.</em></figcaption>
</figure>

The third was the **drum memory**, a rotating cylinder coated in magnetic material onto which bits could be written and read by stationary heads. The British computer scientist Andrew Booth at Birkbeck had built one in 1947; the Engineering Research Associates 1101 and 1103, the IBM 650, and the LGP-30 (the machine on which [Edward Lorenz would later discover deterministic chaos](/weather/hpc/history/2026/03/31/The-butterfly-that-broke-the-forecast.html)) all used drum storage. Drums were cheap, dense, and non-volatile. They were also strictly sequential within a track and access times averaged half a revolution -- typically several milliseconds.

By the summer of 1948 the field had reached an impasse. The mercury delay line was reliable but slow and sequential. The Williams tube was random-access but unreliable. The drum was sequential. Whatever came next would have to be random-access (you needed to fetch any bit at any time), fast (microseconds, not milliseconds), reliable (mean time between failures measured in months, not hours), and non-volatile (it should not lose its bits when the power blinked).

The list of requirements is, with hindsight, a list of the properties of magnetic-core memory.

## A flight simulator that wasn't

The MIT computer that would force the issue had not been designed as a computer at all. In late 1944, Captain Luis de Florez of the U.S. Navy's Bureau of Aeronautics, head of the Special Devices Division, was tired of the Link Trainer. The Link, in production since the 1930s, was an electromechanical flight simulator that simulated one specific airplane. De Florez wanted a "universal" trainer -- one machine that could be reprogrammed to mimic any aircraft type, even ones not yet built. He called the proposed system the Aircraft Stability and Control Analyzer, or ASCA.

In November 1944 the Navy approached MIT's Servomechanisms Laboratory under Gordon Brown to take on the project. Brown handed it to a young research associate named **Jay Forrester**.

Forrester at twenty-six already had a reputation. He had been born on **14 July 1918** on a cattle ranch in the Sand Hills of central Nebraska. The family property had no electricity. As a high-school senior, Forrester had wired the ranch himself -- building a wind-driven twelve-volt generator out of old car parts and putting his parents' home on its first electric grid. He had earned his bachelor's at the University of Nebraska in 1939, his master's at MIT in 1945 under Brown, and through the war years had built hydraulic gun-control servomechanisms for radar-stabilized shipboard gun mounts. He was, by every contemporary account, an engineer who would set goals his team thought impossible and then expect them to be met.[^5]

The original ASCA design was analog. Vacuum-tube amplifiers would drive electromechanical servos; the equations of motion would be solved continuously in real time, the same way a radar gun-aiming computer worked. By the spring of 1945 it was clear the analog approach was not going to work. Aircraft equations of motion were too nonlinear for the available analog hardware to solve with sufficient precision over the required range of flight conditions.

The pivot came from a young Navy engineer named **Perry O. Crawford Jr.**, an MIT alumnus who had moved to the Special Devices Center in 1942 and was advocating digital techniques across the department. Crawford witnessed a demonstration of ENIAC in 1945 and immediately understood the implication: a sufficiently fast digital computer could solve aerodynamic equations as fast as a real airplane could fly through them. He pushed Forrester to abandon analog. Forrester, who had been thinking about the same problem from a different angle, was persuaded.[^6]

By March 1946 Forrester had convinced the Navy to redirect the contract from a Navy flight simulator with a computer inside it into a general-purpose digital computer. The flight simulator goal never quite disappeared from the contract paperwork; it just stopped driving the design. The machine itself was renamed Whirlwind.

Construction began in 1947 in a brick building on the corner of Massachusetts Avenue and Vassar Street -- the **Barta Building**, MIT designation N42. By peak Forrester had a team of roughly one hundred and seventy-five people: about seventy engineers and technicians, the rest support staff. The first equations were solved on Whirlwind in the third quarter of 1949, displaying simple integration test results on an oscilloscope. Full operation came on **20 April 1951**, by which time the contract paperwork had been quietly rewritten -- the machine was now described as having "successfully accomplished digital computation of interception courses." By 1951 the Air Force, not the Navy, was paying the bills. The reason for that change is the next section of this story.[^7]

The architecture of Whirlwind I, as it stood in 1951, was distinctive in three ways. The word length was sixteen bits, which was short by the standards of contemporaries (EDVAC had forty-four, the IAS machine forty). The processing was **bit-parallel** -- all sixteen bits of a word handled simultaneously by sixteen arithmetic slices -- whereas EDVAC, EDSAC, BINAC, and most other early machines were bit-serial, processing one bit at a time. And the design target was real-time response: the machine had to keep up with a pilot's control inputs at tens of milliseconds per loop, which it did at roughly twenty thousand single-address operations per second. Memory was 1024 sixteen-bit words, initially in a pair of MIT-designed electrostatic storage tube banks. The machine drew over a hundred kilowatts of power, occupied two thousand square feet of floor space, weighed ten tons, and ran on roughly five thousand vacuum tubes. The original 1947 design specification called for memory access in six microseconds; the storage tubes Whirlwind actually got delivered roughly twenty-five microseconds, four times slower than spec, and they kept failing.[^7]

<figure class="align-center" style="width: 70%;">
  <img src="/assets/images/Whirlwind_register.jpg" alt="Surviving Whirlwind register module at the Computer History Museum.">
  <figcaption>A surviving Whirlwind register module at the Computer History Museum in Mountain View. Whirlwind ran on roughly five thousand vacuum tubes, drew over a hundred kilowatts of power, and occupied two thousand square feet of floor space at MIT's Barta Building (N42) on Massachusetts Avenue. The bit-parallel architecture -- sixteen arithmetic slices working simultaneously -- was unique among 1951 machines and was driven by Whirlwind's real-time design target. <em>Source: Marcin Wichary / Wikimedia Commons. License: CC BY 2.0.</em></figcaption>
</figure>

## How a flight simulator became air defense

By 1948 the Office of Naval Research had taken over Whirlwind's funding from the Bureau of Aeronautics. ONR was a research funder, not a procurement office, and Whirlwind's growing budget began to alarm them. By 1948 the project had spent over 1.9 million dollars and was consuming an estimated **twenty per cent** of ONR's entire research budget. There was no flight simulator. There was no clear date for one. There was an enormous, expensive, half-working digital computer that the engineers wanted to develop into something general.[^8]

The mathematical sciences division of ONR was headed from February 1949 by **Mina Rees**, a topologist who had spent the war administering applied mathematics for the Office of Scientific Research and Development. Rees was sympathetic to Whirlwind's potential and personally admired Forrester. But the budget arithmetic was unsustainable. Rees later wrote that "the imposition on Project Whirlwind of budgetary constraints necessitated by the size of the ONR research budget" had made her job extremely difficult. Through 1949 ONR cut Whirlwind's funding twice. By early 1950 ONR was preparing to cut the project entirely.[^9]

Whirlwind was rescued by a Soviet bomb test.

On **29 August 1949**, in the steppe of eastern Kazakhstan, the USSR detonated its first nuclear device. Within weeks American policymakers were asking how the United States would defend its airspace against Soviet long-range bombers. The existing radar networks of 1949 were a patchwork of stations with no unified picture; tracking even one bogey required phone calls between operators reading paper plots. **George Valley**, an MIT physics professor and Air Force Scientific Advisory Board member, was tasked in late 1949 with examining the air defense problem. The **Air Defense Systems Engineering Committee** -- ADSEC, sometimes called the Valley Committee -- began weekly meetings on **20 January 1950**.[^10]

Valley needed a computer that could fuse radar data from many stations into a single picture in real time. He did not have one. The technology to do so did not exist anywhere in the world. The closest approach to the problem was being run six months from cancellation in a brick building on Massachusetts Avenue.

Late in January 1950, Jerome Wiesner of MIT (later JFK's science advisor) brought Valley and Forrester together for lunch at the MIT Faculty Club. Valley described ADSEC's needs; Forrester offered Whirlwind. The two men toured the machine afterward. Maud Rozee, in a 2015 senior thesis at Barnard, called it one of the most consequential meals in American computing history. There is no transcript.[^11]

By March 1950 the MIT provost was meeting with ONR representatives to discuss "more centralized control" of Whirlwind, diplomatic language for transferring the project to a new sponsor. The Air Force convened **Project Charles** -- a summer study group on continental air defense, formal letter contract on 30 January 1951 -- and the recommendation came back in October that MIT host a permanent Air Force-funded laboratory dedicated to air defense. **MIT Lincoln Laboratory** was founded in 1951 in Lexington, Massachusetts, on the basis of the Project Charles recommendation. Whirlwind was effectively transferred from ONR to Lincoln Lab. The Air Force became its primary patron.

The Korean War, which had begun in June 1950, increased the urgency. By the time Lincoln Lab was up and running, the Whirlwind that had been six months from cancellation in early 1950 was the centrepiece of the U.S. continental air defense research program.

## Wang's notebook -- the principle

Across the Charles River from MIT, at Harvard, a parallel story was unfolding under the wartime mathematician **Howard Aiken**, builder of the Harvard Mark I (delivered to the U.S. Navy in 1944), the Mark II (1947), and now the Mark IV. Aiken's Computation Laboratory occupied a two-story brick building near the Yard with the original Mark I still on the ground floor. The lab consisted, in 1948, of Aiken, five or six research fellows, and a handful of assistants.

In June 1948 a twenty-eight-year-old Chinese applied physicist named **An Wang** walked across Harvard Yard to ask whether the Computation Laboratory had openings.

Wang's path to that morning was not typical of Aiken's other research staff. He had been born in Shanghai on **7 February 1920**, the eldest son of a teacher of English and traditional Chinese medicine. He had begun school in the third grade because his elementary school did not offer the first two grades, and had thereafter been permanently two years younger than his classmates. He had earned his bachelor's at Chiao Tung University in Shanghai in 1940 -- "the MIT of China," the institution his father had briefly attended -- with the highest entrance examination scores of his class. From 1941 to 1944, with the Japanese occupation tightening, Wang and a group of eight young engineers had slipped through Japanese lines from Shanghai to Hong Kong, then through the French concession of Kuan Chou Wan and overland to Nationalist-held Kweilin three hundred miles inside China, where the twenty-one-year-old Wang was put in charge of scrounging parts and improvising designs for radio transmitters for Chinese Nationalist troops. He arrived in the United States in June 1945 on a Nationalist government scholarship for two years of advanced training, took a master's at Harvard in 1946, finished his doctorate in nonlinear mechanics in June 1948, daunted by the security paperwork required by Hughes Aircraft walked across the Harvard campus to ask Aiken for a job, and was hired as a research fellow effective 1 July 1948. (One persistent error in the popular literature should be flagged: Wang's PhD adviser at Harvard was not Aiken. Wang had earned his doctorate under a different advisor and walked across campus *after* the doctorate, looking for a job.)[^12]

On **18 May 1948**, before Wang had formally started at the lab, Aiken posed the central problem. How could one record and read magnetically stored information without mechanical motion? Computer designers across the small early-computing community agreed in principle that a toroidal core of high-remanence magnetic material -- a small magnetic donut with two stable polarizations -- could store one bit. The trouble was that reading the stored information disturbed it.

Wang struggled with the problem for about three weeks. The solution came to him while walking through Harvard Yard. He could not remember afterwards which day. The insight: it did not matter that reading was destructive, provided the read circuit immediately rewrote the original bit back into the same core. As Wang later put it, "by destroying the information -- I know it." His notebook entry for **29 June 1948** records: "It is very possible that the information can stay there [in the core in the form of a particular magnetic direction] and be transferred many times before the information [is lost or muddied]."[^1]

To realize the idea, Wang found a U.S. Navy publication describing a German wartime magnetic material called Permanorm 5000-Z; the U.S. equivalent, sold under the trade name **Deltamax** by Arnold Engineering, a subsidiary of Allegheny-Ludlum, had similar properties. Working with his Harvard colleague **Way-Dong Woo** -- a fellow Shanghai native and Chiao Tung graduate -- Wang strung the toroids in series to form a magnetic-core delay line, which became the memory in Aiken's Mark IV. Wang and Woo's paper "Static Magnetic Storage and Delay Line" appeared in the *Journal of Applied Physics* on 1 January 1950.[^13]

Wang first discussed patenting the device with his fiancee Lorraine Chiu in June 1949. Chiu encouraged him to file. Harvard at that time only reserved patent rights to itself for inventions related to public health; the administrator Wang consulted advised him to file at his own expense and recommended Harvard's own patent firm, Fish, Richardson and Neave -- the same firm that would later represent IBM against him. The IEEE Computer Pioneer biography of Wang notes the irony that Harvard and the University of Pennsylvania, both of which discouraged staff patents, "quickly lost and never regained their original computing eminence," while MIT, which actively pursued them, has been "at the forefront of computing research" ever since.[^14]

On **21 October 1949** Wang filed his patent application, titled "Pulse Transfer Controlling Devices," with thirty-four claims, most directed at "an information delay line." The patent issued as **U.S. Patent 2,708,722** on **17 May 1955**. Claim 24 -- the broad concept of destructive-read-with-immediate-rewrite in a magnetic core -- ultimately controlled later patents in the field by virtue of its priority and breadth. Every magnetic-core memory cell that ever shipped, including every cell in every Forrester-style array, fundamentally implements Claim 24 of Wang's 1949 application.[^15]

After filing, Wang suffered a sleepless night before telling Aiken. To his surprise, Aiken did not react at all and later gave Wang a substantial raise.

<figure class="align-center" style="width: 50%;">
  <img src="/assets/images/An_Wang.jpg" alt="An Wang in 1979.">
  <figcaption>An Wang in 1979, photographed during the peak of Wang Laboratories' commercial success. Wang's 29 June 1948 notebook entry at Harvard's Computation Laboratory captured the principle of destructive-read-with-immediate-rewrite that made magnetic-core memory practical. He filed his patent on 21 October 1949 -- nineteen months before Forrester filed at MIT. <em>Source: Wikimedia Commons. License: Public Domain (US, no copyright notice).</em></figcaption>
</figure>

## Forrester's notebook -- the architecture

Across the Charles River, at MIT, Forrester was working on the same problem from the other end.

By the spring of 1949, Whirlwind's electrostatic storage tubes were costing the project on the order of thirty-two thousand dollars per month to keep running. The tubes had a mean time between memory faults of perhaps fifteen minutes -- three or four reboots per shift, every shift. The 1947 design spec of six microseconds memory access had become a standing joke. Forrester had been thinking for several months about whether something better was possible.

The catalyst, as Forrester told it in a 1975 oral history, was an advertisement. He told the story this way: "I was reading a technical journal one evening, just leafing through the advertisements in the magazine *Electrical Engineering*," and saw an ad for a magnetic alloy called Deltamax. It was the same alloy Wang had been using at Harvard for almost a year, although the two men did not yet know each other's work. Forrester ordered samples, formed them into rings, and confirmed in his MIT lab that the rings flipped between two stable magnetization states under modest current and held those states without further power. Deltamax itself ultimately proved too slow and too pressure-sensitive for production memory; the Whirlwind team eventually settled on small ceramic ferrite toroids about two millimetres in diameter. But Deltamax was the proof of principle.[^16]

The conventional dating for the moment of invention is **15 June 1949** -- the date of Forrester's notebook entry sketching what he called the "coincident-current" addressing scheme. The Computer History Museum's archival page on the notebook gives the date as **13 June 1949**; EDN and most other secondary sources say 15 June 1949. The two-day discrepancy may reflect different cataloguing of when Forrester drafted versus dated the entry. The entry itself records his first written formulation of "applying half currents on two wires to select one core at the intersection."[^2]

The conceptual breakthrough was the **three-dimensional coincident-current selection scheme**. In a Forrester-style core array, every ferrite ring sits at the intersection of two perpendicular wires -- an X (row) wire and a Y (column) wire -- with two further wires threaded through every core in a plane: a sense wire to detect the readout pulse, and an inhibit wire used during writing. To address a single core, the X driver and Y driver each send a current pulse equal to half the core's switching threshold; only the unique core sitting at the intersection of the two energized wires sees the full switching current and flips. The read is destructive; immediately afterwards the inhibit wire is used during a write-back cycle to restore the original data.

The genius of the scheme was that it required only X-plus-Y drivers to address X-times-Y cores. A 32-by-32 plane needed 64 drivers, not 1024. This is what made array-architecture core memory economically practical at scale -- and it is the difference between Wang's invention, which had been implemented in Aiken's Mark IV as a *delay line* with one driver per cell, and Forrester's invention, which scaled.

The two inventions, Wang's of 1948 and Forrester's of 1949, are both genuine; both are necessary; neither alone is sufficient. Wang invented the principle of how a magnetic-core cell could be made to work. Forrester invented the architecture by which many such cells could be addressed cheaply. The patent dispute that followed in the 1950s wrestled with the question of which of the two had priority over which scope. The answer, in retrospect, is that both did. Wang got there first chronologically; Forrester's architecture was the one that scaled to economic viability.

## Building the cores

The four years between Forrester's notebook entry of June 1949 and the first installation of working core memory in Whirlwind on **8 August 1953** were spent on hardware. The conceptual architecture took an evening. The ferrite chemistry, the threading geometry, the drive electronics, and the sense electronics took an MIT graduate student and his thesis committee.

The student was **William N. Papian**, recruited by Forrester in the autumn of 1949 to test individual cores. Papian's MIT master's thesis, "A Coincident-Current Magnetic Memory Unit," was filed in August 1950. He published the foundational engineering paper, "A Coincident-Current Magnetic Memory Cell for the Storage of Digital Information," in the *Proceedings of the IRE* in April 1952. He presented the working memory to the world at the AIEE-IRE Eastern Joint Computer Conference in December 1953. Without Papian there is no working core memory in 1953; Forrester provided the coincident-current concept and the political shield, Papian provided the materials science and the circuitry.[^17]

The materials side of the project was hard. Deltamax was too soft, too pressure-sensitive, and switched too slowly. The team tested sample after sample of candidate ferrite formulations from Bell Labs, General Electric, and several smaller suppliers. The production-grade cores Whirlwind eventually used were small ceramic toroids of manganese-magnesium-zinc ferrite, roughly two millimetres in outer diameter and one millimetre across, with sharp magnetic hysteresis. (RCA's Jan Rajchman, working independently on a different magnetic-core scheme, wound his first cores using a converted aspirin press in 1949.) Each core was strung on four tiny wires by hand. A 32-by-32 plane held 1024 cores. A sixteen-bit word required sixteen stacked planes. The complete Whirlwind core memory was a 32-by-32-by-16 array, 16 384 bits, on which the wiring alone required several thousand hand-soldered connections.[^18]

The patent on the architecture was filed by Forrester on **11 May 1951** as application 225 879. It eventually issued as **U.S. Patent 2,736,880**, "Multicoordinate Digital Information Storage Device," on **28 February 1956**. The patent was assigned to MIT. It would become the single most lucrative patent MIT ever owned.[^19]

The first core memory bank was installed in Whirlwind on **8 August 1953**, replacing one of the two electrostatic storage tube banks. Whirlwind ran for several months in a hybrid configuration; both banks were core by the autumn of 1954. The transformation was visible in three numbers.

Memory **access time** dropped from approximately twenty-five microseconds for the storage tubes to approximately nine microseconds for the cores. Whirlwind's overall throughput approximately doubled, from twenty thousand single-address operations per second to roughly forty thousand. Memory was no longer the binding constraint on the machine.[^20]

Memory **reliability**, which had been the project's nightmare for two years, was transformed even more dramatically. The most-cited figure is from Papian himself: maintenance time on the memory dropped from **four hours per day to two hours per week**. In mean-time-between-failures terms, that is a fifty- to one-hundred-fold improvement, depending on how you count. Memory had been Whirlwind's fragility; now it was Whirlwind's reliability. The first generation of cores installed in August 1953 outlasted Whirlwind itself; the same banks were operating in May 1959 when the machine was decommissioned.[^21]

The **operating cost** that mattered most to MIT's accountants was the line item for storage tubes. It went away. The thirty-two thousand dollars per month in tube replacements, which had eaten almost forty per cent of Whirlwind's running costs in 1952, simply vanished from the books. Cores -- once strung -- did not fail.

<figure class="align-center" style="width: 70%;">
  <img src="/assets/images/Whirlwind_core_memory.jpg" alt="The 1951 Whirlwind core memory unit on loan from MIT Museum.">
  <figcaption>The 1951 Whirlwind core memory unit, on loan from the MIT Museum to the Charles River Museum of Industry. Each ceramic ferrite ring stores one bit by being magnetized in one of two directions; the X-Y wires that thread through the cores select individual cells through coincident half-currents. The full Whirlwind core memory was a 32-by-32-by-16 array of 16 384 bits installed on 8 August 1953. Maintenance time on the memory dropped from four hours per day under storage tubes to two hours per week. <em>Source: Daderot / Wikimedia Commons. License: Public Domain.</em></figcaption>
</figure>

<figure class="align-center" style="width: 70%;">
  <img src="/assets/images/core_memory_closeup.jpg" alt="Close-up of magnetic core memory with woven wires through ferrite rings.">
  <figcaption>Close detail of magnetic-core memory: each ferrite ring is the size of a pencil eraser, threaded with four hand-soldered wires (X address, Y address, sense, inhibit). By the late 1950s industrial production was assembling cores at scale; by the late 1960s IBM was producing roughly twenty billion cores per year and the unit cost had fallen from thirty-three cents to three-hundredths of a cent. <em>Source: Wikimedia Commons. License: CC BY-SA.</em></figcaption>
</figure>

## SAGE: the memory goes continental

By the time core memory was installed in Whirlwind, the machine itself was no longer the most important deployment of the technology. The Air Force had decided in late 1952 that the Whirlwind architecture, scaled up and rebuilt by an industrial contractor, would become the heart of a continental air defense computer system. The system was named **SAGE** -- Semi-Automatic Ground Environment -- and IBM was selected as prime contractor in October 1952. The first production contract was awarded in February 1954.

SAGE was a vast project. The Air Force eventually deployed twenty-four SAGE direction centers, each with its own computer, plus three combat centers. Each direction center received feeds from multiple radar stations, fused them into a unified picture of the airspace, tracked individual aircraft (friendly or otherwise) on circular CRT displays, and could direct interception by friendly fighters via voice and data link. Each center ran around the clock. The consequences of unscheduled downtime were considered unacceptable -- a missed bomber stream might mean a Soviet first strike succeeding -- so each center had two computers, one active and one hot spare.

The computer was the **IBM AN/FSQ-7 Combat Direction Central**. By the standards of any era it is the largest computer ever built. Each AN/FSQ-7 contained 49 000 vacuum tubes (60 000 if peripherals are counted), weighed 250 to 275 tons, occupied 2000 square metres of floor space (roughly half an acre), drew up to three megawatts of power, and ran at about 75 000 instructions per second. Including the hot spare, each direction center had two of these machines. The total tube count of the network was not far below two and a half million. The network was built on top of magnetic-core memory descended directly from Forrester's Whirlwind design.[^22]

The first operational SAGE direction center went live at McGuire AFB, New Jersey, on **1 July 1958**. The full network of twenty-four direction centers was operational across North America by 1963. By that time SAGE was already technologically obsolete -- the threat had shifted from Soviet bombers to Soviet ballistic missiles, against which a bomber-defense system was largely irrelevant -- but the network remained in continuous service. The last AN/FSQ-7 systems were not decommissioned until the early 1980s; the Q7 at Luke Air Force Base was demolished in February 1984. Twenty-five years of vacuum-tube continental air defense had run on machines whose direct intellectual ancestor was Whirlwind I.[^22]

The total program cost across the deployment cycle is most often given as eight to twelve billion dollars in then-year currency, which is roughly the equivalent of eighty to one hundred billion dollars today. The Manhattan Project cost two billion dollars in WWII-era dollars. SAGE was four to six times the Manhattan Project. It was almost entirely paid for by the U.S. taxpayer, almost entirely under-discussed in the public record, and almost entirely premised on a memory technology that did not exist when the original Whirlwind contract was signed in December 1944.[^23]

<figure class="align-center" style="width: 90%;">
  <img src="/assets/images/SAGE_blue_room.png" alt="Interior of a SAGE Sector Control Center.">
  <figcaption>Inside a SAGE Sector Control Center: the blue-lit command post with its projection display showing a Cape Cod radar picture. Each direction center had two AN/FSQ-7 computers (one active, one hot spare), 49 000 vacuum tubes per machine, and a magnetic-core memory descended directly from Forrester's 1953 Whirlwind installation. Twenty-four such centers were deployed across North America. SAGE was almost entirely premised on a memory technology that did not exist when the Whirlwind contract was signed in December 1944. <em>Source: U.S. Air Force, via Wikimedia Commons. License: Public Domain.</em></figcaption>
</figure>

## The patent dispute -- IBM pays twice

The IBM patent dispute that followed Whirlwind's success and Wang's prior application stretched from 1953 to 1964 and produced two separate settlements: a smaller one with Wang, a larger one with MIT.

IBM was, by 1953, simultaneously the prime contractor for SAGE production (and therefore needing to ship core memory in volume), the manufacturer of the new IBM 702 and 704 commercial computers (which were also being designed around core memory), and a litigant facing two pending patents that arguably covered everything they were doing.

IBM and Wang signed an interim consulting agreement in November 1953 under which Wang would consult for IBM at one thousand dollars per month and IBM would receive a three-year option on a non-exclusive license to his still-unissued patent. Wang later wrote that he believed IBM was less interested in the specific consulting projects than in cultivating access to his thinking on magnetic-core applications.

When the Wang patent finally issued on 17 May 1955, IBM opened formal negotiations. Wang opened by offering to sell the patent outright for two and a half million dollars; IBM countered that "even half of that is too high." In October 1955, IBM offered five hundred thousand dollars in cash plus seventy per cent of all royalties from third-party licensing.

Wang was prepared to accept but objected to language regarding patent validity and interference proceedings. After Wang answered fifty-eight questions attacking the patent from "every conceivable angle," IBM revealed that it had located a 1947 patent application by Frederick W. Viehe, a Los Angeles public works inspector, which IBM believed would "certainly lead to an interference."

Under this pressure, Wang assigned the patent to IBM on **4 March 1956** under the October terms, with provisions allowing one hundred thousand dollars of the payment to be withheld in case of an interference declaration. Two weeks before the deadline, in May 1956, the U.S. Patent Office did declare an interference with the Viehe application. In November 1957, mid-litigation, IBM bought the Viehe application outright -- reportedly for one million dollars -- and hired Viehe as a consultant. The interference proceeding then continued as IBM versus IBM. The eventual decision awarded Viehe only one minor claim. Wang forfeited the contingent one hundred thousand dollars and harboured a lifelong grudge against IBM. (When Viehe died in 1960 he left a six-hundred-twenty-five-thousand-dollar estate; his son later confirmed that the buyer of his father's patent had been IBM.)[^24]

The bigger settlement, separately negotiated, was between IBM and MIT for Forrester's array-architecture patent. MIT and IBM disagreed for several years about the royalty rate IBM should pay on the millions of bits of Forrester-style core memory it was shipping in the IBM 704, 705, 709, 7090, 7094, and the AN/FSQ-7 SAGE machines. Negotiations ran from about 1961 to 1964. In **1964** IBM agreed to pay MIT **thirteen million dollars**, then "the largest patent settlement to that date" and the largest MIT had ever received. Forrester personally received one and a half million dollars; the rest went to MIT for educational programs.[^25]

The two settlements together fairly capture the parallel-invention story. Wang invented the underlying principle first, in 1948, and his patent issued first, in May 1955. Forrester invented the array architecture nine months later, in June 1949, but his patent issued nine months after Wang's, in February 1956. IBM paid Wang half a million dollars; it paid MIT twenty-six times as much. Wang got the priority; MIT got the volume.

Wang, in his autobiography *Lessons*, called Forrester's array scheme "brilliant" and said he always regretted not thinking of it himself. Forrester, on the rare occasions he was asked, returned the compliment.

## The diaspora -- Olsen, DEC, and the VAX

Whirlwind's most consequential alumnus was not Forrester, who left engineering for the Sloan School in 1956 and spent the next sixty years building the discipline of system dynamics. It was a working-class graduate student from Connecticut who joined the project in 1950 and noticed that small fast computers might be a business.

**Kenneth Harry Olsen** was born on 20 February 1926 in Bridgeport, Connecticut, into a Norwegian-American family of evangelical Protestants. His father Oswald was a machine-tool designer with several patents to his name; the household was strict, and Olsen took his Christianity seriously his whole life -- he never drank, smoked, or swore. He served in the U.S. Navy as an electronics technician from 1944 to 1946, enrolled at MIT on the GI Bill, earned his bachelor's in 1950 and his master's in 1952. He joined the Whirlwind project in 1950 while still a graduate student, working in Lincoln Lab's Division 6 on the magnetic-core memory subsystem -- the same circuitry Papian was building. Olsen helped construct the **Memory Test Computer** (MTC), a smaller machine designed specifically to test core-memory ideas before they were committed to Whirlwind itself. He then moved to the **TX-0**, the first transistorized research computer, completed at Lincoln Lab in 1955-56 as a follow-on to Whirlwind. The TX-0 experience -- a fast, interactive, transistor-based machine that researchers used hands-on rather than through batch operators -- became the template for everything Olsen built afterward.[^26]

In 1957 Olsen and his Lincoln Lab colleague **Harlan Anderson**, joined later by Olsen's brother Stanley, decided to leave MIT and build interactive computers commercially. They approached **Georges Doriot's American Research and Development Corporation** -- the pioneering Boston venture-capital firm. ARD's offer was seventy thousand dollars in equity for seventy per cent of the company plus a thirty-thousand-dollar loan. Doriot insisted they not call themselves a "computer" company -- the conventional wisdom in 1957 was that the computer market was saturated by IBM and a handful of mainframe makers. They incorporated as **Digital Equipment Corporation**, leased the second floor of an abandoned nineteenth-century woolen mill in Maynard, Massachusetts, fifteen miles from Lincoln Lab, and started building digital logic modules. ARD's seventy-thousand-dollar stake in DEC eventually grew to three hundred and fifty-five million dollars by 1971 -- the founding success story of American venture capital.[^27]

The Maynard mill never grew its doors. There were no doors on the cubicles because doors were considered too expensive in the early years and the practice stuck. Decades later, when DEC had become briefly the second-largest computer company in the world after IBM, executives still worked in doorless cubicles. Olsen drove an old Ford Fairlane to the office, refused a company car, listed his profession on his IRS forms as "engineer" rather than CEO, and never moved out of the modest house in Lincoln, Massachusetts, that he and his wife Aulikki had bought in the 1950s. The frugality was real and it was a culture.

DEC shipped the **PDP-1** in late 1959 (the production model was 1960) at a price of about one hundred and twenty thousand dollars -- roughly one-twentieth the price of an IBM mainframe and the first commercial computer designed for interactive use rather than batch operation. MIT's Tech Model Railroad Club acquired one in 1961 and used it to write *Spacewar!* in 1962, the first widely played digital video game. Only fifty-three PDP-1s were built but their influence was enormous; the machine is generally credited as the spark of hacker culture. The **PDP-8** (1965, eighteen thousand five hundred dollars) was the first true minicomputer in commercial volume, eventually selling more than fifty thousand units across many variants. The **PDP-11** (1970) became the most ubiquitous minicomputer of the 1970s, with over six hundred thousand units sold, and its instruction set influenced the design of the C programming language and Unix at Bell Labs.[^28]

The **VAX 11/780** shipped in October 1977 at about two hundred thousand dollars -- a thirty-two-bit superminicomputer with virtual memory and the operating system VMS. The VAX line dominated mid-range scientific computing through the 1980s. This is the machine that ran the [Cane-Zebiak coupled ocean-atmosphere model](/weather/hpc/history/2026/04/28/The-forecast-on-a-VAX.html) at Lamont-Doherty for the 1986 ENSO forecast covered in the previous post: Whirlwind to Olsen to DEC to the VAX 11/780 to the first successful seasonal forecast of an El Nino event. A lineage of forty years and one direct line of professional descent from Papian's core-memory bench at MIT to a basement office on the New York side of the Hudson.

<figure class="align-center" style="width: 50%;">
  <img src="/assets/images/Ken_Olsen.jpg" alt="Kenneth Olsen in 1986.">
  <figcaption>Kenneth Olsen in 1986. Olsen joined the Whirlwind project in 1950 as a graduate student working on the magnetic-core memory subsystem; in 1957 he founded Digital Equipment Corporation with seventy thousand dollars from Georges Doriot's American Research and Development Corporation. The 1977 DEC VAX 11/780 -- the machine on which Cane and Zebiak ran their 1986 El Nino forecast -- is a direct descendant of the Whirlwind core memory architecture. <em>Source: RIT News and Events (1986), via Wikimedia Commons. License: Public Domain (US, no copyright notice).</em></figcaption>
</figure>

The most-quoted thing Ken Olsen ever said is something he probably did not exactly say and certainly did not mean the way it is now used. The standard version is: "There is no reason for any individual to have a computer in their home." It is invariably cited as a forecasting blunder by the man who refused to see the personal-computer revolution coming. The actual record is murkier. The remark is attributed to a presentation Olsen gave at the World Future Society convention in Boston in 1977. The earliest known published source is the April 1980 issue of *Creative Computing* magazine, in a recollection by editor David Ahl, who had previously had professional disagreements with Olsen at DEC. No transcript of the original talk has surfaced. What Olsen was actually arguing against, in 1977, was the then-fashionable idea of the "home computer" as a single central computer that would automate every aspect of household life -- the lights, the heating, the meal-planning, the entertainment, the food inventory. He objected that a household ought not be run by an automation system. By 1977 his own family already used networked DEC time-sharing terminals at home: his wife played Scrabble against the office mainframe, and his son was networking MIT and DEC machines together. The quote is a famous misreading. Olsen lost the historical PR battle but he was not predicting that nobody would ever want a desktop machine.[^29]

## The memory in every forecast

The second consequential alumnus of the magnetic-core invention story was a machine, not a person.

The **IBM 704** was announced in May 1954 and first shipped at the end of 1954. It was the first general-purpose commercial computer to ship with magnetic-core memory as standard equipment. It used a thirty-six-bit word, supported floating-point hardware (the first commercial machine to do so), and shipped initially with a four-thousand-word core memory expandable to eight and then to thirty-two thousand words. It executed up to about twelve thousand floating-point additions per second. IBM produced one hundred and twenty-three type-704 systems between 1955 and 1960. **FORTRAN** was first developed on the 704 (the [first compile was on 19 April 1957 at Westinghouse-Bettis](/weather/hpc/history/2026/04/19/God-is-real-unless-declared-integer.html), the subject of an earlier post in this series); LISP was developed on the 704 at MIT; the SAP assembler was the standard programming tool for the machine.[^30]

Whatever else the IBM 704 was, it was the bridge between Whirlwind core memory and numerical weather prediction.

In April 1956, **Norman Phillips** at the Princeton Institute for Advanced Study completed the experiment that is generally regarded as [the first general circulation simulation in atmospheric science](/weather/hpc/history/2026/03/30/The-first-climate-model-had-five-kilobytes-of-RAM.html): a thirty-day numerical integration of a two-layer quasi-geostrophic model on a five-thousand-kilometre square representation of one hemisphere. The IAS machine itself was running on Williams tubes -- not core memory. But by 1956 the IBM 704 was shipping in volume and the IAS-clone machines were nearly all being decommissioned in favour of commercial successors. Within two or three years of Phillips's experiment, every active centre of atmospheric general circulation modelling -- the [Geophysical Fluid Dynamics Laboratory](/weather/hpc/history/2026/04/13/The-forecast-that-reached-the-Nobel.html) at Princeton, the National Center for Atmospheric Research in Boulder, [UCLA's Department of Meteorology](/weather/hpc/history/2026/04/22/The-fireman-and-the-visionary.html), the Joint Numerical Weather Prediction Unit at Suitland -- was running on machines whose working memory was magnetic core. The IBM 704 led to the IBM 7090 (1959), the 7094 (1962), the System/360 (1964), and through that line ran the entire generation of American climate models from Manabe-Strickler at GFDL to Mintz-Arakawa at UCLA to Kasahara-Washington at NCAR.

On the CDC side of the supercomputing world, every one of [Seymour Cray's](/weather/hpc/history/2026/04/27/The-machine-that-looked-like-furniture.html) machines from the **CDC 1604** of 1960 through the **CDC 6600** of 1964 to the **CDC 7600** of 1969 used magnetic-core working memory. The same was true of the UNIVAC 1108 on which [Manabe and Bryan first coupled an ocean to an atmosphere](/weather/hpc/history/2026/04/23/The-man-who-fit-the-entire-ocean-in-half-a-megabyte.html) in 1969, and of the DEC VAX 11/780 on which Cane and Zebiak ran their first El Nino forecast in 1986. By the time the VAX shipped in 1977 the technology was being displaced.

The displacement was semiconductor. **Intel's 1103 DRAM**, introduced in October 1970, was the first commercially successful semiconductor RAM chip: 1024 bits in an eighteen-pin DIP using a p-MOS three-transistor cell, fast enough to compete with core, and -- decisively -- on a Moore's-law cost curve that core could not match. The 1103 launched at about sixty dollars per chip; production improvements drove the price below four dollars per chip by 1973, less than one per cent of the equivalent core cost. By the end of 1971 the 1103 was the best-selling semiconductor in the world; within two years fourteen of the eighteen major computer manufacturers, including HP, DEC, Honeywell, and CDC, had adopted it.[^31]

By the late 1970s essentially every new computer was shipping with semiconductor RAM. Magnetic core lingered for another decade in two specialized markets: military and aerospace systems, where its inherent radiation-hardness and non-volatility were difficult to replicate (the Apollo Guidance Computer used a special variant called core rope memory, in which programs were *physically woven* into the threading of the cores -- the famous Apollo "1201" and "1202" alarms during the 1969 lunar descent were generated by code running out of core rope ROM and writing scratch values into core RAM); and a handful of legacy minicomputer lines that were still cheaper to build with cores than to redesign. The last shipping new-build core memories disappeared from the catalog in the early 1980s.

The terminology survives. The Unix command for writing the contents of a process's memory to disk after a crash is *core dump*; the resulting file is called a *core file*. Programmers in 2026 still type the same words that William Papian's Whirlwind technical reports used in 1953.

## Coda: what survived

Whirlwind itself ran from April 1951 to **29 May 1959**, when MIT formally shut it down. By that point all the work the machine could do for Lincoln Laboratory was being done better by the AN/FSQ-7 systems in SAGE deployments. The machine was about to be scrapped. Two former engineers refused to let it go.

Robert Everett, by then Technical Director at MITRE, intervened on the institutional side. **Ken Olsen**, by then running his year-old Digital Equipment Corporation across town in Maynard, intervened on the commercial side. They negotiated, separately, to preserve the hardware. **Wolf Research and Development Corporation** of Concord, Massachusetts, leased the entire machine from the U.S. Navy for one dollar per year from 30 June 1959 through 1974, paid two hundred and fifty thousand dollars to relocate the system, ran customer jobs on it for fifteen years, and earned a modest profit. The remaining racks went to museums in 1974. Three Whirlwind racks are on display at the Computer History Museum in Mountain View today; core memory units survive at the MIT Museum, the Charles River Museum of Industry, the Stanford collection, and the Smithsonian. The fact that any of Whirlwind survives in physical form is because two former engineers, in 1959, refused to let it be scrapped.[^32]

**An Wang** built **Wang Laboratories** out of the IBM patent settlement and a steady stream of consulting contracts. The first major product was the LOCI-2 desktop calculator in January 1965, the first desktop calculator to compute logarithms and the machine that effectively created the desk-calculator market. Wang followed with the 700-series scientific calculators in 1970 and, most consequentially, the Wang word processors of 1972 onward, which dominated the office market. By the mid-1970s Wang Labs controlled an estimated eighty per cent of the office word-processing market. Revenue reached one billion dollars in 1982, two billion in 1984, and approximately three billion at its peak in the mid-1980s, with thirty-three thousand employees. Wang was awarded the Medal of Liberty by President Reagan in 1986. He took leave for cancer treatment that same year, handed the company to his son Frederick, removed his son in 1989, and died of esophageal cancer on **24 March 1990** at age seventy. Wang Laboratories filed for Chapter 11 bankruptcy two and a half years later, in August 1992, undone by the same desktop computers that Doriot's seed money to Olsen had helped to make possible.[^33]

**Jay Forrester** left engineering in 1956 for MIT's Sloan School of Management and spent the next sixty years building the discipline of system dynamics. *Industrial Dynamics* (1961) introduced the field. *World Dynamics* (1971) presented WORLD2, a global model of population, food, industrial output, pollution, and non-renewable resources, which his student Donella Meadows expanded into WORLD3 -- the basis of *The Limits to Growth* (1972), a book that sold thirty million copies in thirty languages and triggered the modern debate over planetary boundaries. Forrester held the IEEE Medal of Honor (1972), the National Medal of Technology (1989, presented by President George H. W. Bush), and a permanent seat on the Digital Equipment Corporation board at Ken Olsen's invitation. He died on **16 November 2016**, in Concord, Massachusetts, aged ninety-eight.[^34]

**Robert Everett** ran MITRE Corporation as President from 1969 to 1986, building it from the SAGE engineering shop into one of the principal Federally Funded Research and Development Centers in the United States. He shared the National Medal of Technology with Forrester in 1989 and was named an IEEE Computer Pioneer in 1987. He died on **15 August 2018** at Cape Cod, Massachusetts, aged ninety-seven. There is no public-domain photograph of him in any archive that I have been able to find.

**Ken Olsen** was forced out of DEC in July 1992 after the company posted its first quarterly losses. DEC was eventually bought by Compaq in 1998 and absorbed into HP in 2002. Olsen retired from technology and devoted his last two decades primarily to philanthropy, particularly to Gordon College in Wenham, Massachusetts. He died on **6 February 2011** in Indianapolis, aged eighty-four.

The cores survive. They are quiet now, in glass cases at the MIT Museum and the Computer History Museum and the Smithsonian. The wires that thread through them are oxidized; the ferrite has lost none of its remanence. If they were powered up tonight, every bit set into them in 1953 -- the bits that ran the AN/FSQ-7 air defense computers, the bits that ran Phillips's first GCM in the spring of 1956, the bits that ran the first ocean-atmosphere coupling experiment on a UNIVAC 1108 in 1969 -- would still be there. Magnetic-core memory is non-volatile. Cores do not forget.

The two notebooks survive too. Wang's June 1948 entry is preserved at Wang's archive in Massachusetts; Forrester's June 1949 entry is at the Computer History Museum in Mountain View, behind glass. Twelve months apart, on opposite sides of Cambridge, two engineers wrote down the principle and the architecture of the memory technology that powered every weather and climate computer for twenty-five years.

Every forecast that ran from 1953 through the early 1970s -- every operational analysis of pressure fields, every retrospective integration of the equations of motion, every climate model whose results made it into the IPCC's first round of attribution studies -- ran out of memory invented in those two notebooks.

## Footnotes

[^1]: An Wang IEEE Computer Pioneer biography, ed. T. M. Smith, IEEE Computer Society. Wang's notebook entry of 29 June 1948 is reproduced and discussed in Wang's autobiography, with Eugene Linden, *Lessons* (Addison-Wesley, 1986). The "by destroying the information -- I know it" formulation appears in Wang's later interviews and in the IEEE biography.

[^2]: Forrester's notebook entry: the Computer History Museum gives the date as 13 June 1949; EDN ("Forrester records a proposal for core memory in his notebook, June 15, 1949") and most secondary sources give 15 June 1949. The two-day discrepancy reflects different cataloguing of when Forrester drafted versus dated the entry. CHM holds the original notebook and a high-resolution scan is available at the Computer History Museum's Revolution exhibit, "Memory and Storage" gallery.

[^3]: "Delay-line memory," Wikipedia. The Eckert-Mauchly mercury delay line and its use on EDSAC, EDVAC, BINAC, UNIVAC I.

[^4]: "Williams tube," Wikipedia; "Whirlwind I," Wikipedia. The thirty-two-thousand-dollar-per-month storage tube replacement figure is widely cited from the project's running cost records and appears in the standard histories.

[^5]: MIT News obituary, "Professor Emeritus Jay Forrester, digital computing and system dynamics pioneer, dies at 98," 16 November 2016; ETHW, "Jay W. Forrester," Engineering and Technology History Wiki; Concord Free Public Library, "Concord Oral History Program -- Jay Forrester."

[^6]: "Whirlwind I" and "Perry O. Crawford Jr.," Wikipedia; Forrester oral history, MIT, with Forrester's own account of Crawford's role in the Navy fundraising and the digital pivot. See also chapter 7.2 of *Bit by Bit*, "The Whirlwind Project," at Haverford College.

[^7]: Architecture and operational details from "Whirlwind I," Wikipedia; "Project Whirlwind: Reports and Technical Memoranda" via MIT Dome and MIT ArchivesSpace; Kent C. Redmond and Thomas M. Smith, *Project Whirlwind: The History of a Pioneer Computer* (Bedford, MA: Digital Press, 1980), the canonical scholarly history.

[^8]: "The Rise and Fall of Project Whirlwind," MIT Archival History of Computing; "Tales of Discovery: Project Whirlwind," Office of Naval Research History.

[^9]: "Mina Rees," Wikipedia and IEEE Computer Society Computer Pioneers profile; Mina Rees, "The Mathematical Sciences and World War II," *American Mathematical Monthly* (1980).

[^10]: "Project Charles," Wikipedia; "MIT Lincoln Laboratory," Wikipedia; "ADSEC, Final Report 24 October 1950," Internet Archive; Maud Rozee, *The Air Force Goes Digital*, senior thesis, Barnard College, 2015.

[^11]: Maud Rozee, *The Air Force Goes Digital* (2015), citing Redmond and Smith (1980); "Foundation of MIT's Lincoln Laboratory and SAGE," History of Information.

[^12]: Wang biographical material from An Wang IEEE Computer Pioneer biography (cited above); Wang and Linden, *Lessons* (1986); "An Wang," Wikipedia. The Kweilin radio-transmitter story and the path through Hong Kong are recounted in *Lessons*.

[^13]: An Wang and Way-Dong Woo, "Static Magnetic Storage and Delay Line," *Journal of Applied Physics* 21:49 (1 January 1950).

[^14]: An Wang IEEE Computer Pioneer biography; the Harvard / Penn / MIT comparison appears explicitly in the IEEE biography of Wang.

[^15]: An Wang, "Pulse Transfer Controlling Devices," U.S. Patent 2,708,722, filed 21 October 1949, issued 17 May 1955, available at patents.google.com/patent/US2708722.

[^16]: Forrester 1975 oral history, cited via secondary sources including *They Create Worlds* historical-interlude series and the Computer History Museum's Magnetic-Core Memory exhibit. The "leafing through the advertisements" wording is reproduced widely from the oral history; the *Electrical Engineering* journal in which the Deltamax ad appeared was the AIEE's main professional publication.

[^17]: William N. Papian, "A Coincident-Current Magnetic Memory Unit," MS thesis, MIT Department of Electrical Engineering, August 1950; W. N. Papian, "A Coincident-Current Magnetic Memory Cell for the Storage of Digital Information," *Proceedings of the IRE* 40 (April 1952); W. N. Papian, "The MIT Magnetic-Core Memory," *Papers and discussions presented at the December 8-10, 1953 Eastern Joint AIEE-IRE Computer Conference* (1953).

[^18]: "Magnetic-core memory," Wikipedia; Emerson W. Pugh, *Memories That Shaped an Industry: Decisions Leading to IBM System/360* (MIT Press, 1984), the standard reference on the early history of computer memory.

[^19]: Jay W. Forrester, "Multicoordinate Digital Information Storage Device," U.S. Patent 2,736,880, filed 11 May 1951, issued 28 February 1956, available at patents.google.com/patent/US2736880A.

[^20]: Computer History Museum, "1953: Whirlwind computer debuts core memory," Storage Engine timeline; "Magnetic-core memory," Wikipedia, citing Papian.

[^21]: Bit by Bit, chapter 7.2; Computer History Museum Storage Engine; the four-hours-per-day to two-hours-per-week figure is from the Whirlwind operations records as reported in the standard histories.

[^22]: "AN/FSQ-7 Combat Direction Central," Wikipedia; "Semi-Automatic Ground Environment," Wikipedia; "SAGE: Semi-Automatic Ground Environment Air Defense System," MIT Lincoln Laboratory historical materials.

[^23]: "Semi-Automatic Ground Environment," Wikipedia, with cost estimates from sage.mitre.org. The Manhattan Project comparison is from the standard secondary literature; the eight-to-twelve-billion-dollar range covers the deployment cycle as variously accounted.

[^24]: An Wang IEEE Computer Pioneer biography; Computer History Museum, "March 4: An Wang Sells Core Memory Patent to IBM"; the Viehe interference details from Wang and Linden, *Lessons*, and from contemporaneous IBM technical histories.

[^25]: "IBM Paying MIT In Patent Dispute," *The Harvard Crimson*, 15 April 1964; "Magnetic-core memory," Wikipedia, citing the same settlement.

[^26]: "Ken Olsen," Wikipedia; The DEC Connection, "Ken Olsen, Founder," decconnection.org; ANBHF biography; Glenn Rifkin and George Harrar, *The Ultimate Entrepreneur: The Story of Ken Olsen and Digital Equipment Corporation* (Contemporary Books, 1988).

[^27]: "American Research and Development Corporation," Wikipedia; Computer History Museum Revolution, "Digital Equipment Corporation"; Rifkin and Harrar (1988) on the Doriot meeting and the Maynard mill.

[^28]: "PDP-1," "PDP-8," "PDP-11," Wikipedia. The PDP-1 and *Spacewar!* connection is documented in Eric S. Raymond, "A Brief History of Hackerdom: The Early Hackers."

[^29]: Quote Investigator, "There is No Reason for Any Individual To Have a Computer in Their Home," 14 September 2017, with David Ahl's *Creative Computing* (April 1980) cited as the earliest publication; Snopes, "Ken Olsen" fact-check; Olsen 1982 and 2003 clarification interviews cited via Quote Investigator.

[^30]: "IBM 704," Wikipedia. Architecture, memory, FORTRAN/LISP/SAP, 123 systems shipped 1955-1960. The 19 April 1957 Westinghouse-Bettis FORTRAN delivery is the subject of an earlier post in this series.

[^31]: "Intel 1103," Wikipedia. October 1970 introduction, p-MOS, sixty-dollar launch price falling to four dollars by 1973.

[^32]: "Project Whirlwind comes home," MIT News, 22 May 2009; Computer History Museum collection records; Wolf Research and Development Corporation lease terms from secondary sources cited in the project research file.

[^33]: "Wang Laboratories," Wikipedia; Charles C. Kenney, *Riding the Runaway Horse: The Rise and Decline of Wang Laboratories* (Little, Brown, 1992); An Wang and Eugene Linden, *Lessons* (1986).

[^34]: MIT News obituary 2016; Forrester, *World Dynamics* (Wright-Allen Press, 1971); Donella H. Meadows, Dennis L. Meadows, Jorgen Randers, and William W. Behrens III, *The Limits to Growth* (Universe Books, 1972).

## References

**Primary scholarly histories:**

* Kent C. Redmond and Thomas M. Smith, *Project Whirlwind: The History of a Pioneer Computer* (Bedford, MA: Digital Press, 1980). The canonical scholarly history.
* Kent C. Redmond and Thomas M. Smith, *From Whirlwind to MITRE: The R&D Story of the SAGE Air Defense Computer* (MIT Press, 2000).
* Emerson W. Pugh, *Memories That Shaped an Industry: Decisions Leading to IBM System/360* (MIT Press, 1984). The standard reference on the early history of computer memory.
* Charles J. Bashe, Lyle R. Johnson, John H. Palmer, and Emerson W. Pugh, *IBM's Early Computers* (MIT Press, 1986).
* Glenn Rifkin and George Harrar, *The Ultimate Entrepreneur: The Story of Ken Olsen and Digital Equipment Corporation* (Contemporary Books, 1988).
* M. Mitchell Waldrop, *The Dream Machine: J.C.R. Licklider and the Revolution That Made Computing Personal* (Viking, 2001). Whirlwind chapters.
* Charles C. Kenney, *Riding the Runaway Horse: The Rise and Decline of Wang Laboratories* (Little, Brown, 1992).

**Primary technical sources:**

* W. N. Papian, "A Coincident-Current Magnetic Memory Unit," MS thesis, MIT Department of Electrical Engineering, August 1950.
* W. N. Papian, "A Coincident-Current Magnetic Memory Cell for the Storage of Digital Information," *Proceedings of the IRE* 40 (April 1952).
* W. N. Papian, "The MIT Magnetic-Core Memory," *Papers and discussions presented at the December 8-10, 1953 Eastern Joint AIEE-IRE Computer Conference* (1953).
* Jay W. Forrester, "Multicoordinate Digital Information Storage Device," U.S. Patent 2,736,880, filed 11 May 1951, issued 28 February 1956.
* An Wang, "Pulse Transfer Controlling Devices," U.S. Patent 2,708,722, filed 21 October 1949, issued 17 May 1955.
* An Wang and Way-Dong Woo, "Static Magnetic Storage and Delay Line," *Journal of Applied Physics* 21:49 (1 January 1950).

**Autobiographical:**

* An Wang with Eugene Linden, *Lessons: An Autobiography* (Addison-Wesley, 1986).
* Forrester oral history, MIT (1975 and later interviews), via the Computer History Museum and IEEE Computer Society.

**Web archives consulted (accessed 2026-04-29):**

* "Whirlwind I," "AN/FSQ-7 Combat Direction Central," "Magnetic-core memory," "Project Charles," "Semi-Automatic Ground Environment," "MIT Lincoln Laboratory," "An Wang," "Wang Laboratories," "Ken Olsen," "Robert Everett (computer scientist)," "Jay Wright Forrester," and "Williams tube" -- Wikipedia.
* Computer History Museum: Storage Engine timeline ("1953: Whirlwind computer debuts core memory"; "March 4: An Wang Sells Core Memory Patent to IBM"); Revolution exhibits on memory and storage.
* "IBM Paying MIT In Patent Dispute," *The Harvard Crimson*, 15 April 1964.
* "Project Whirlwind comes home," MIT News, 22 May 2009.
* "Forrester records a proposal for core memory in his notebook, June 15, 1949," EDN.
* MIT Sloan and MIT News obituary of Jay Forrester, 16 November 2016.
* Maud Rozee, *The Air Force Goes Digital*, senior thesis, Barnard College, 2015.
* IEEE Computer Society Computer Pioneers biographies of Forrester, Everett, Olsen, Wang, and Rees.
* Quote Investigator, "There is No Reason for Any Individual To Have a Computer in Their Home" (14 September 2017).
