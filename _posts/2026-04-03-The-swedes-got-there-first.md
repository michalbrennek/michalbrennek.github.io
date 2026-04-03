---
layout: single
title: "The Swedes Got There First"
date: 2026-04-03 08:00:00 +0100
categories: [Weather, HPC, History]
tags: [BESK, Sweden, Rossby, Bolin, NWP, Operations, SMHI, Computing]
header:
  teaser: /assets/images/header-cyclone.jpg
  overlay_image: /assets/images/header-cyclone.jpg
  overlay_filter: "0.6"
excerpt: "In December 1954, Sweden began running the world's first routine numerical weather forecasts — on a computer named after bitter schnapps, built because the Americans wouldn't sell them one."
---

A full disclosure before we begin. Sweden holds a special place in my heart. If the Swedish Chef from the Muppets has taught us anything, it's that you can accomplish great things in a kitchen — or a computer room — while being completely incomprehensible to everyone around you. "Bork bork bork!" as the man said, right before something exploded. Also what better way to spend a weekend — except maybe messing around in boats — than to build a good adult LEGO set from IKEA. There is nothing you cannot accomplish after a proper portion of köttbullar with lingonberry jam (my kids' favourite). Debug a climate model? Build a computer from vacuum tubes? Beat the Americans to operational weather forecasting? Just add lingonberry jam and anything becomes possible.

As it turns out, the Swedes were also doing something in the 1950s that nobody else quite understood at the time. And unlike the Swedish Chef, they got it exactly right.

Every history of numerical weather prediction tells the same story. Charney's [ENIAC forecast](/weather/hpc/history/2026/03/29/The-man-who-tamed-the-equations.html) in 1950. Phillips' [climate simulation](/weather/hpc/history/2026/03/30/The-first-climate-model-had-5KB-of-RAM.html) in 1956. The Joint Numerical Weather Prediction Unit in Suitland, Maryland, beginning operational forecasts in May 1955. The narrative is American. The machines are American. The heroes speak English.

There's a problem with this story.

**Sweden got there first.**

In **December 1954** — a full year before the Americans — the Royal Swedish Air Force Weather Service in Stockholm began producing routine, real-time numerical weather forecasts. Three times a week. For the North Atlantic. Using a barotropic model developed at Stockholm University. Running on a computer called **BESK** — a machine whose name means "bitter" in Swedish, built because the United States refused to sell Sweden a computer.

This is the story of how a small Scandinavian country, a returning emigrant, and a machine named after schnapps beat the world's superpower to the most important advance in weather forecasting since [Richardson's pile of hay](/weather/hpc/history/2026/03/24/The-man-who-forecasted-weather-with-a-pencil.html).

### The Man Who Came Home

![Carl-Gustaf Rossby in 1939, when he was appointed Assistant Chief of the U.S. Weather Bureau. The Swedish-born meteorologist would later return to Stockholm and bring numerical weather prediction with him. Harris & Ewing, Library of Congress, public domain.](/assets/images/Rossby_1939_LOC.jpg)

Readers who follow this series have met **Carl-Gustaf Rossby** before. He passed through the [Bergen School](/weather/hpc/history/2026/03/26/The-line-that-models-cannot-draw.html) at age 20, built the MIT meteorology department, ran the University of Chicago department during the war, founded the *Journal of Meteorology*, trained thousands of military weather cadets, and discovered the planetary waves that bear his name. By 1947, he was arguably the most influential meteorologist alive.

And then he went home.

The Swedish government created a personal professorship at Stockholm University to lure him back. Rossby accepted. He became the first professor at the newly established **Department of Meteorology (MISU)** and created the **International Meteorological Institute (IMI)** — a research centre funded by the Swedish Parliament, designed to attract leading scientists from around the world.

Why did he leave? The Chicago department was in turmoil. Chester Newton recalled that "when Rossby was in town, the department was in tumult... it was exciting but exhausting." But more than that, Rossby wanted to build something international. He had spent two decades constructing American meteorology. Now he wanted to construct **world** meteorology.

He did not fully abandon the US. He divided his time between Stockholm, Chicago, and Woods Hole. As he said: **"Communications are the alpha and omega of meteorology."**

But Stockholm became his base. And Stockholm had a problem.

It didn't have a computer.

### The Americans Said No

In the late 1940s, the Swedish Board for Computing Machinery — the **Matematikmaskinnämnden**, or MMN — tried to buy an American computer. They had a budget of 2 million Swedish kronor. They sent engineers to study the technology.

The US State Department said no. **Cold War export controls** blocked the sale of computing technology to all but the closest allies. Sweden was neutral. No computer for Sweden.

So Sweden built its own.

![The BESK computer — console, operator panel, and memory units. 2 400 vacuum tubes, 40-bit words, briefly the fastest computer in the world. Wikimedia Commons, CC BY-SA 4.0.](/assets/images/BESK_console_memories.jpg)

### BARK and BESK: Bitter Machines

The first machine was **BARK** — the *Binär Automatisk Relä-Kalkylator* (Binary Automatic Relay Calculator). It used 8 000 telephone relays and 80 kilometres of cable. It was already obsolete when completed in April 1950 — similar relay machines had existed a decade earlier. Howard Aiken reportedly visited and said: "This is the first computer I have seen outside Harvard that actually works."

The BARK team had wanted to call it **CONIAC** — *Conny Integrator And Calculator*, after project leader **Conny Palm**. Officials blocked the name. Too close to "cognac." Too alcoholic for a government project.

So when the electronic successor needed a name, the team chose **BESK** — *Binär Elektronisk SekvensKalkylator*. "Besk" means "bitter" in Swedish, evoking the traditional bitter schnapps. The pun was intentional. The officials apparently didn't notice.

### Conny Palm: The Visionary Who Didn't Live to See It

![Conny Palm standing before BARK, Sweden's first computer, which he designed using 8 000 telephone relays. Palm died in December 1951 at the age of 44, just as work on BESK was beginning. Photo: Tekniska museet, CC BY 2.0.](/assets/images/Conny_Palm_BARK.jpg)

**Conrad "Conny" Palm** was the driving force behind Swedish computing. A brilliant statistician at L.M. Ericsson, he had made foundational contributions to queueing theory — the mathematics of waiting lines, telephone traffic, and network congestion. His thesis advisor characterized him as "a bohemian and brilliant statistician." An anecdote captures him perfectly: his Ericsson salary was withheld unless he passed monthly exams — he typically appeared days before payday requesting oral examinations.

In 1947, Palm organized a study mission to America. Five young Swedish engineers were sent across the Atlantic: two to **von Neumann at Princeton** (including **Erik Stemme** and **Carl-Erik Fröberg**), two to **Howard Aiken at Harvard**, and one to IBM. They came back with drawings, ideas, and the conviction that Sweden could build its own electronic computer.

Palm drove the project forward — BARK first, then the electronic BESK. But on **27 December 1951**, at the age of 44, Conny Palm died. The cause was never publicly documented. He never saw BESK run.

**Stig Comet** took over the project. Comet had a remarkable double life: he was simultaneously head of the BESK project and bureau chief at **FRA** — Sweden's signals intelligence agency, the equivalent of the NSA. During the day, BESK computed weather and wing profiles. At night, under Comet's personal supervision, it **cracked encrypted radio messages**. The strictest secrecy separated the two roles.

![BESK's control panel — the interface through which operators entered programs and monitored the machine. Wikimedia Commons, CC BY-SA 4.0.](/assets/images/BESK_control_panel.jpg)

### Five Engineers and a Trip to Princeton

The machine BESK became was shaped by that 1947 American study mission. **Erik Stemme**, one of the five engineers, worked in Jan Rajchman's group at the RCA laboratory near Princeton on the **Selectron tube** — the memory technology von Neumann originally wanted for the IAS machine. When the Selectron proved impractical, Stemme pivoted: he read a 1948 paper on Williams tube memory, visited **Frederic Williams** in Manchester, England, and had a Williams tube working by 1949.

Stemme became, without formal appointment, the de facto leader of BESK's hardware construction. He designed the binary adder with an innovation: the carry flag between each of the 40 stages "went through the whole way without inversion," making BESK's adder faster than the IAS machine's.

**Carl-Erik Fröberg**, the other Princeton visitor, returned to Lund University and later built **SMIL** — a simplified BESK derivative. He also founded what may be the world's first university course in numerical analysis (spring 1956) and created the journal **BIT Numerical Mathematics** in 1961.

**Gösta Neovius** and **Olle Karlqvist** designed BESK's architecture and instruction set. Karlqvist, while developing BESK's magnetic drum memory, discovered an electromagnetic phenomenon in ferromagnetic layers that became known as the **Karlqvist gap** — a result still fundamental to hard drive design today. A computer project in 1950s Sweden yielded a discovery that matters every time your laptop reads a file.

### The Specs

| | BESK | IAS Machine | IBM 701 |
|---|---|---|---|
| **Word length** | 40 bits | 40 bits | 36 bits |
| **Memory** | 512 words (Williams tubes) | 1 024 words (Williams tubes) | 2 048 words (Williams tubes) |
| **Addition time** | **56 μs** | 62 μs | 60 μs |
| **Multiplication** | **350 μs** | 713 μs | 456 μs |
| **Vacuum tubes** | 2 400 | ~3 400 | ~4 000 |
| **Operational** | 1953 | 1952 | 1952 |

BESK was closely modelled on the IAS machine — the Swedish team brought back drawings from Princeton — but it was not a slavish copy. It was **faster**. For a few weeks in late 1953, BESK held the title of **fastest computer in the world**. A small neutral country, locked out of American technology by export controls, had built a machine that outperformed the original.

At the time, Swedish officials seriously debated whether the country needed **two or three computers total** for all national computing needs.

![BESK's Williams tube memory rack — cathode-ray tubes storing data as electric charges on phosphor screens. Each tube held a few hundred bits. Unreliable, requiring daily 30-minute calibration, they were replaced by ferrite core memory in 1956. Wikimedia Commons, CC BY-SA 4.0.](/assets/images/BESK_williams_tube.jpg)

### Five Minutes and a Prayer

In its early days, BESK averaged about **five minutes** of continuous operation before a vacuum tube failed. Programs had to be designed with breakpoints so computation could resume after repairs, rather than starting from scratch.

By 1954, reliability improved dramatically. The Williams tube memory required 30-minute daily calibration. In 1956, it was replaced by **ferrite core memory** — the same technology Jay Forrester had invented for [Whirlwind](/weather/hpc/history/2026/04/02/From-cables-to-chaos.html). The core memory was built by engineer **Carl-Ivar Bergman**, who had only weeks to deliver. To meet the deadline, he hired **"housewives with knitting experience"** (*hemmafruar med erfarenhet av att sticka*) to thread the tiny ferrite cores. The dexterity needed to weave hair-thin wires through hundreds of cores was, it turned out, analogous to knitting. When one bit failed in the finished memory, it was "easily cut out and replaced."

### Rossby and the Weather

Now: the weather.

Rossby had returned to Stockholm in 1947. He had watched [Charney's ENIAC forecast](/weather/hpc/history/2026/03/29/The-man-who-tamed-the-equations.html) from across the Atlantic. He knew BESK was being built. He immediately saw the opportunity.

He approached **SMHI** — the Swedish Meteorological and Hydrological Institute, Sweden's weather service. SMHI's leadership was **skeptical**. They felt NWP was too experimental and should be left to universities.

Rossby, being Rossby, went around them.

He found **Oskar Herlin**, head of the **Military Weather Central** under the Royal Swedish Air Force. Herlin was "a practical man" who had observed stagnation in conventional forecasting techniques. The cost was modest compared to military budgets. Herlin said yes. The Swedish Air Force would fund operational NWP.

### The Bridge Figure: Bert Bolin

The technical work required someone who understood both the American NWP effort and the Swedish computing environment. That person was **Bert Bolin**.

Bolin was born in 1925 in Nyköping, Sweden. During military service in Stockholm in 1947, he met Professor Rossby — a chance encounter that shaped the rest of his career. He became Rossby's student. In **1950-51**, Rossby sent Bolin to Princeton, where he worked at the Institute for Advanced Study with **Charney and von Neumann** on the ENIAC forecast computations. Bolin was present for the founding moment of numerical weather prediction.

Then he came home to Stockholm.

Bolin understood both the mathematics (Charney's filtered equations, the barotropic vorticity equation) and the machines (he had seen the ENIAC, he had worked alongside the IAS machine). He was the perfect person to translate the American research into Swedish operations.

In autumn 1953, Rossby brought another crucial visitor to Stockholm: **Norman Phillips** — readers who follow this series [already know him](/weather/hpc/history/2026/03/30/The-first-climate-model-had-5KB-of-RAM.html) from the first climate simulation. Phillips came to Stockholm specifically to **port the ENIAC weather forecast code to BESK**. This technology transfer — American code, rewritten for a Swedish machine — was the foundation of the operational system.

### The Moment: September 1954

In **September 1954**, 45 000 Swedish troops conducted military exercises in central Sweden. The manoeuvres tested nuclear protection equipment — and real-time upper-air forecasts predicting simulated nuclear fallout trajectories would be critical.

Rossby's group produced real-time NWP forecasts during the six-week exercise, running the barotropic model on BESK.

The results were dramatic: **the NWP forecasts were tremendously successful compared to subjective human forecasts.**

This was the validation moment. Not a research experiment in a university. Not a printout compared after the fact. Real forecasts, for real troops, in real time, that were **better** than what human forecasters could produce.

### December 1954: The World's First

Starting in **December 1954**, the Royal Swedish Air Force Weather Service in Stockholm began producing routine NWP forecasts for the **North Atlantic region, three times a week**. The model was barotropic — the same type of equation Charney had used on the ENIAC in 1950. The forecast area was roughly 9 000 × 12 000 km. BESK could deliver a 3-day forecast in about one hour of computation time.

By 1955, Bolin had extended the forecast range to **72 hours**. His paper in *Tellus* (1955) reported correlations between computed and observed changes of **0.85 for 24 hours, 0.82 for 48 hours, and 0.70 for 72 hours** over Western Europe. These were good numbers. These were *useful* numbers.

The workflow required military precision:

1. The Air Force Weather Service prepared observation data and upper-air charts
2. Weather maps were sent by **military couriers** to BESK at Drottninggatan 95A in Stockholm
3. Data was entered, the model ran
4. Forecast output returned to the weather service
5. Three times per week

BESK was not dedicated to weather. It also calculated wing profiles for the Saab Lansen jet fighter, ran statistics for Televerket (the Swedish telecom authority), computed highway profiles for the road authority, and — during night shifts — cracked codes for FRA. Weather had to share. This is why forecasts ran three times a week, not daily: there wasn't enough machine time.

### Meanwhile, in America

The **Joint Numerical Weather Prediction Unit (JNWPU)** opened in Suitland, Maryland, in 1954 — the same year the Swedes began their exercises. An **IBM 701** was installed in March 1955. The first routine American operational forecast was produced on **6 May 1955**.

And it was **"very disappointing and not usable by forecasters."**

Let that sink in. Sweden had been running useful forecasts since December 1954. The first American operational forecasts, produced five months later on a much more expensive machine, were disappointing.

The IBM 701 at JNWPU had a mean time between failure of roughly **30 minutes**. BESK, by 1954, was more reliable. The 701 used Williams tube memory — the same technology BESK had started with, but BESK upgraded to core memory in 1956, while the 701 kept its unreliable tubes.

It took the Americans until 1958, when the improved barotropic model ran on the **IBM 704** with core memory and hardware floating point, to match the forecast skill the Swedes had achieved in 1955.

### Why Nobody Knows This

If Sweden beat America to operational NWP by a full year, why isn't this common knowledge? Anders Persson of SMHI, one of the few historians to document the Swedish NWP story in detail, identifies several reasons:

1. **The narrative is American.** The history of computing and NWP is usually told as an American story: ENIAC, von Neumann, Charney, JNWPU. The Swedish results were published in *Tellus*, not American journals.

2. **Institutional ambiguity.** The Swedish forecasts were produced by an ad hoc collaboration between the Air Force and a university department — not a permanent national agency. SMHI didn't take over until 1961. JNWPU, by contrast, was a clearly defined operational unit.

3. **Scale.** America built a permanent, well-funded organisation that ran forecasts twice daily on dedicated hardware. Sweden ran three forecasts a week on shared time, on a machine that also calculated wing profiles and cracked codes.

4. **Rossby's death.** Rossby collapsed from a heart attack during a conference in Stockholm on **19 August 1957**. He was 58. Close friends knew he had suffered from rheumatic fever as a boy and had a weak heart. His death removed the charismatic advocate who might have championed the Swedish achievement more forcefully on the world stage.

5. **Swedish modesty.** The Swedes simply didn't make much noise about it.

### The Legacy: From BESK to the Nobel Prize

The Stockholm NWP group didn't just produce weather forecasts. It produced **institutions**.

**Aksel Wiin-Nielsen**, a Danish meteorologist who trained under Rossby in Stockholm and participated in the 1954 BESK forecasts, became the **first Director of ECMWF** — the European Centre for Medium-Range Weather Forecasts (1974-1979). The organisation that now produces the best medium-range weather forecasts on Earth traces its leadership lineage directly to Rossby's Stockholm seminar room.

**Bo Döös**, integral to the 1954 forecasts, later directed the **Global Atmospheric Research Programme (GARP)** from 1971 to 1982 — the international programme that laid the groundwork for ECMWF's mission.

**Bert Bolin** succeeded Rossby as director of IMI, became the first permanent professor of meteorology at Stockholm University, and in 1988 was appointed the **first Chairman of the Intergovernmental Panel on Climate Change (IPCC)**. The IPCC shared the **2007 Nobel Peace Prize** with Al Gore. Bolin was too ill to attend the ceremony. He died on 30 December 2007.

And here is perhaps the most extraordinary connection of all. In **1959**, a young man named **Paul Crutzen** arrived at MISU — Rossby's department — as a computer programmer. He had no PhD. He had no particular plan. He got involved in running weather models. Bert Bolin supervised his doctoral work. Crutzen went on to discover the mechanisms of stratospheric ozone depletion — and won the **1995 Nobel Prize in Chemistry**.

A computer programmer who came to run weather models on BESK's successors ended up with a Nobel Prize. The thread runs from Rossby's return to Stockholm, through BESK, through Bolin, to Crutzen and the ozone layer.

![BESK's operator panel — where engineers monitored the machine's internal state during computation. Wikimedia Commons, CC BY-SA 4.0.](/assets/images/BESK_operator_panel.jpg)

### The Machine That Cracked Codes, Designed Jets, and Discovered Primes

BESK did far more than weather. It calculated wing profiles for the **Saab 32 Lansen** — the first aircraft in which every mould line was mathematically computed. Saab consumed so much BESK time that they eventually built **SARA**, their own BESK copy, twice as fast.

In 1957, **Hans Riesel** used BESK during nights and weekends to hunt for large primes. His self-checking machine-language routine, fed by punched paper tape, found the **18th Mersenne prime**: 2^3217 - 1, a number with 969 digits — the largest known prime at the time.

In 1960, engineers at Nordisk ADB realised they had all the coordinates for a planned Stockholm motorway. They created what may be the **world's first computer-generated film** — a 30-second driver's-eye-view animation at 110 km/h, captured frame by frame from a specially designed digital oscilloscope. It was broadcast on Swedish television on 9 November 1961. The surviving copy at Tekniska museet bears the inscription: "the first computer-drawn film in the world."

And always, at night, the code-breaking. FRA's classified cryptanalysis sessions, personally supervised by Stig Comet, continuing the tradition of **Arne Beurling** — the legendary Swedish mathematician who, in 1940, single-handedly deciphered the German Geheimschreiber cipher **in two weeks using only pen and paper**. Beurling's cryptanalysis was considered more complex than cracking Enigma. When asked how he did it, he replied: **"A magician does not reveal his secrets."** Beurling later moved to the Institute for Advanced Study in Princeton, where he took over **Einstein's old office**. He was not directly involved in BESK — but the signals intelligence agency his wartime work had created was BESK's most urgent customer.

### The BESK Boys

In spring 1956, Stemme and 17 other BESK engineers left MMN for **Facit** (formerly Åtvidabergs Industrier) to build commercial computers. The group became known as **"the BESK Boys."** They produced the **Facit EDB** (1957-58), Sweden's first mass-produced computer — software-compatible with BESK.

The exodus was devastating for MMN. Their best engineers walked out the door carrying the knowledge of how to build and maintain BESK's hardware. But it also seeded a Swedish computer industry — one that would ultimately fail when US export controls were relaxed in the 1960s and IBM competition intensified.

The irony is circular. American export controls forced Sweden to build its own computer. That computer's success created Swedish expertise. That expertise left for the private sector. And then American technology came back in and rendered it moot.

### The First — and the Forgotten

Let me put the timeline side by side one more time.

| Date | Sweden | United States |
|---|---|---|
| **Autumn 1953** | Phillips ports ENIAC code to BESK | — |
| **March 1954** | First forecasts completed ahead of valid time | — |
| **September 1954** | Six-week operational trial, 45 000 troops | JNWPU established (no computer yet) |
| **December 1954** | **Routine 3x/week operational NWP begins** | — |
| **March 1955** | — | IBM 701 installed at JNWPU |
| **May 1955** | — | First US operational forecast ("very disappointing") |
| **1955** | Bolin extends forecasts to 72 hours | JNWPU struggles with reliability |

Sweden was first. By a year. On a machine that also designed fighter jets, cracked codes, hunted primes, and made films. A machine named after bitter schnapps, built because the Americans wouldn't sell them one.

The two-week wall that [Lorenz](/weather/hpc/history/2026/03/31/The-butterfly-that-broke-the-forecast.html) proved existed? The Swedes hit it before anyone else had even started running.

---

### References

**Swedish NWP:**
* Persson, A. (2005). Early operational Numerical Weather Prediction outside the USA: an historical Introduction. Part 1: Internationalism and engineering NWP in Sweden, 1952-69. *Meteorological Applications*, 12, 135-159. [Cambridge Core](https://www.cambridge.org/core/journals/meteorological-applications/article/abs/early-operational-numerical-weather-prediction-outside-the-usa-an-historical-introduction-part-1-internationalism-and-engineering-nwp-in-sweden-195269/62B132A2DB529EA0C02AD169EB678938)
* Staff Members, Institute of Meteorology, University of Stockholm (1954). Results of forecasting with the barotropic model on an electronic computer (BESK). *Tellus*, 6, 139-149.
* Bolin, B. (1955). Numerical forecasting with the barotropic model. *Tellus*, 7, 27-49. [Semantic Scholar](https://www.semanticscholar.org/paper/Numerical-Forecasting-with-the-Barotropic-Model-Bolin/98e25abd71a4eefaebe3cff8c7f7c8494741c27e)
* Bergthorsson, P. & Döös, B. (1955). Numerical weather map analysis. *Tellus*, 7, 329-340.
* Bauer, P., Thorpe, A. & Brunet, G. (2015). The quiet revolution of numerical weather prediction. *Nature*, 525, 47-55. [Nature](https://www.nature.com/articles/nature14956)
* Persson, A. (2014). Fifty Years Later. *History of Meteorology*, 6, 7-13. [PDF](https://journal.meteohistory.org/index.php/hom/article/download/39/39/57)

**BESK:**
* Petersson, T. (2005). Facit and the BESK Boys: Sweden's computer industry (1956-1962). *IEEE Annals of the History of Computing*, 27, 23-30. [IEEE](https://ieeexplore.ieee.org/document/1549794/)
* Lundin, P., ed. (2006). *Att arbeta med 1950-talets matematikmaskiner* (Working with the Computing Machines of the 1950s). KTH. [PDF](http://kth.diva-portal.org/smash/get/diva2:10842/FULLTEXT01.pdf)
* Dahlquist, G. (1958). *Kodning för BESK* (2nd ed.). Matematikmaskinnämnden. [PDF](http://user.it.uu.se/~foy/Documents/Kodning_for_BESK_2a_uppl_1958-05-02_HELA.pdf)
* Kaijser, A. et al. (2024). Bark och Besk -- datorerna där allting började. In *Maktens maskiner*, pp. 29-52. [PDF](https://arkiv.nu/wp-content/uploads/9789179243883.pdf)
* Yang, C. (2025). The First Compute Arms Race: the Early History of Numerical Weather Prediction. [arXiv](https://arxiv.org/html/2506.21816v1)

**Rossby:**
* Carl-Gustaf Rossby: Theorist, institution builder, bon vivant. *Physics Today*. [Link](https://physicstoday.aip.org/features/carl-gustaf-rossby-theorist-institution-builder-bon-vivant)
* Carl-Gustaf Rossby: The Stockholm period 1947-1957. *Tellus B*, 51 (1999). [Tellus](https://b.tellusjournals.se/articles/10.3402/tellusb.v51i1.16255)

**Bolin:**
* Bert Bolin (1925-2007) -- a world leading climate scientist and science organiser. *Tellus B*, 65 (2013). [Tellus](https://b.tellusjournals.se/articles/10.3402/tellusb.v65i0.20583)
* Stockholm University. Bert Bolin -- founder of the climate panel and world-leading scientist. [SU](https://www.su.se/english/about-the-university/cultural-heritage-and-history/the-history-of-stockholm-university/bert-bolin-founder-of-the-climate-panel-and-world-leading-scientist-1.531330)

**Beurling:**
* Beckman, B. (2002). *Codebreakers: Arne Beurling and the Swedish Crypto Program During World War II*. AMS.

**JNWPU / US NWP:**
* Harper, K. C. (2008). *Weather by the Numbers: The Genesis of Modern Meteorology*. MIT Press. [Publisher](https://mitpress.mit.edu/9780262083782/weather-by-the-numbers/)
* Cressman, G. P. (1996). The Origin and Rise of Numerical Weather Prediction. In *Historical Essays on Meteorology 1919-1995*, AMS, 21-39.
* NOAA. The History of Numerical Weather Prediction. [NOAA](https://celebrating200years.noaa.gov/foundations/numerical_wx_pred/welcome.html)

**Museum:**
* Tekniska museet. From Computing Machines to IT. [Tekniska museet](https://www.tekniskamuseet.se/en/collections/research/from-computing-machines-to-it/)
* History of Information. The Royal Swedish Air Force Weather Service Computes the First Routine Real-Time Numerical Weather Forecasting. [Link](https://historyofinformation.com/detail.php?id=2073)

**Image Credits:**
* BESK console and memories: Tekniska museet. CC BY-SA 4.0. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:BESK_Computer_Console_and_Memories.jpg)
* BESK control panel: Ellinor Algin / Tekniska museet. CC BY-SA 4.0. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:BESK_Control_Panel.jpg)
* BESK Williams tube rack: Tekniska museet. CC BY-SA 4.0. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:BESK_Williams_tube_rack.jpg)
* BESK operator panel: Peter Hall. CC BY 4.0. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:BESK_Operator_Panel.jpg)
* Carl-Gustaf Rossby, 1939: Harris & Ewing / Library of Congress (LCCN2016875745). Public domain. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Carl_G._A._Rossby_LCCN2016875745_(cropped).jpg)
* Conny Palm with BARK: Tekniska museet. CC BY 2.0. [Flickr](https://www.flickr.com/photos/tekniskamuseet/6979247547)

---

**Current status:**
- BESK: Decommissioned 1966. Console survives at Tekniska museet, Stockholm.
- Sweden's first operational NWP: December 1954. One year before the Americans. On shared time. Between wing profiles and code-breaking.
- The Swedes: Still modest about it. Still first.
- My cluster: 0.54 TFLOPS. Roughly 9×10⁹ times faster than BESK. Still can't predict next Tuesday.

Yours Truly
