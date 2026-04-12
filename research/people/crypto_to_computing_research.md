# From Ciphers to Computers: Research Notes for Blog Post

## The Argument

Cryptanalysis was one of the primary drivers of early electronic computing. The same machines, people, and mathematical techniques that broke enemy ciphers in WWII became the foundation of the computers that predicted the weather. The pipeline runs:

- **Poland:** Rejewski's permutation group theory (1932) -> bomba kryptologiczna (1938) -> Pyry handover (1939)
- **Britain:** Polish bomba -> Turing's Bombe (1940) -> Colossus (1943) -> Newman at Manchester (1948) -> Turing at NPL (1945) -> Ferranti Mark 1 (1951)
- **Sweden:** Beurling's Geheimschreiber break (1940) -> FRA -> BESK (1953) -> operational NWP (1954)
- **USA:** ENIAC (ballistics, 1946) -> von Neumann/Charney weather forecast (1950) -> IAS machine -> IBM 701 -> JNWPU (1955)

---

## 1. The Bomba Kryptologiczna

### What It Was Physically

The bomba kryptologiczna was an electrically powered aggregate of six interconnected Enigma replicas (lacking plugboards). Each replica incorporated three rotors -- duplicates of Enigma wheels I, II, and III -- a reflector, and associated wiring. The six units were linked in three pairs to form "double-Enigmas." An electric motor drove the rotors to advance in unison through all 17576 possible starting positions (26^3). The machine was housed within a supporting framework and produced a "characteristic muffled noise" during operation.

### How Many Were Built

Exactly **six** bombas were built in Warsaw by the **AVA Radio Manufacturing Company** before September 1939. Each corresponded to one of the six possible orderings of the three available rotors.

### How It Worked

The bomba exploited a critical German procedural flaw: operators encrypted the three-letter message key twice at the start of each message (e.g., typing "ABCABC" which encrypted to six seemingly random letters). This double encipherment meant that positions 1 and 4, 2 and 5, 3 and 6 encrypted the same plaintext letter. The bomba mechanized the testing of all 17576 possible starting positions, looking for settings where unchanged individual letters appeared (as opposed to the earlier "grill" method which required unchanged letter pairs). Each bomba "took the place of some one hundred workers" and could reconstruct the daily key in approximately two hours.

The "bomb method" required only that the plug connections in the plugboard did not change all the letters -- which was the case when there were between five and eight plug connections.

### Design Timeline

- Designed by Rejewski probably in **October 1938**, after the Germans changed their indicator procedure on 15 September 1938 (eliminating the usefulness of the earlier card catalog/cyclometer method)
- By **mid-November 1938**, machines were operational
- All six destroyed or evacuated before the German invasion of **September 1939**

### Name Origin

Rejewski stated the device was dubbed a "bomb" "for lack of a better idea." The apocryphal story that Rozycki named it after an ice-cream dessert (bombe glacee) was dismissed by Rejewski as improbable since the source of that story (Tadeusz Lisicki) had not known Rozycki.

### Was It a Precursor to Turing's Bombe?

Yes, directly. The British Bombe's name was derived from the Polish original. Turing visited the Polish cryptologists at PC Bruno (near Paris) in early 1940 to confer about Enigma decryption. Turing specified a machine that could break Enigma "more effectively than the Polish bomba kryptologiczna." RUSI described the Polish contribution: "it was the Polish use of electromechanical technology that moved cryptanalysis into the industrial age."

**Sources:**
- [Bomba (cryptography) - Wikipedia](https://en.wikipedia.org/wiki/Bomba_(cryptography))
- [The Polish Connection -- TNMOC](https://www.tnmoc.org/bh-3-the-polish-connection)
- [Resurrecting Bomba Kryptologiczna - ResearchGate](https://www.researchgate.net/publication/255338633_Resurrecting_Bomba_Kryptologiczna_Archaeology_of_Algorithmic_Artefacts_I)

---

## 2. Turing's Bombe at Bletchley Park

### Evolution from the Polish Bomba

The fundamental difference: the Polish bomba exploited a specific procedural vulnerability (double encipherment of the message key). When the Germans changed procedures, the bomba became useless. Turing realized this and designed his Bombe on a completely different principle: the assumption of a "crib" (known or predicted plaintext) at a defined point in the message text itself. This made the method independent of any particular indicator procedure.

Key technical differences:

| Aspect | Polish Bomba | Turing's Bombe |
|--------|-------------|----------------|
| Design principle | Exploited indicator repetition | Based on known plaintext (cribs) |
| Flexibility | Required fixed rotor order (6 machines for 6 orders) | Could test multiple rotor orders on single machine |
| Plugboard handling | Limited (5-8 connections) | Designed to work with full 10-lead plugboard |
| Adaptability | Rendered obsolete by procedural changes | General principle allowed continuous adaptation |
| Scale | 6 machines total | 211+ British machines, 121 US Navy, 10 US Army |

### Cribs and Menus

Cribs were sections of suspected plaintext -- standard German military phrases, weather reports (which followed rigid formats), or known expressions. "Finding cribs was not at all straightforward; it required considerable familiarity with German military jargon and the communication habits of the operators."

Once a crib was identified, operators created a graphical "menu" showing letter relationships between plaintext and ciphertext. These formed "loops" or "cycles." The more loops, the more candidate settings the Bombe could eliminate. Turing estimated an 11-letter menu with 3 loops would produce approximately 0.14 false stops per rotor order.

### Gordon Welchman's Diagonal Board

Welchman, a mathematician who headed Hut 6, devised the diagonal board in 1940. It exploited the **reciprocal property** of the Enigma plugboard: if letter A was plugged to letter R, then R was also plugged to A.

**Technical structure:** A square lattice of 26 x 26 electrical terminals, where 26 rows represent letters A-Z that may occur on a menu and 26 columns represent the 26 possible plugboard partners. Pairs of terminals were permanently connected to encode the symmetry -- the terminal at (row F, column J) was connected to (row J, column F). Each such wire ran diagonally across the board -- hence the name.

**Effect:** The diagonal board increased feedback into the Bombe's circuits, dramatically reducing false "stops." With the improvement, it became possible to use menus with only a single loop, or in special cases, no loops at all. This vastly expanded the number of usable cribs. Turing acknowledged Welchman's contribution as immensely important.

The first Bombe, "Victory," was installed at Bletchley Park on **18 March 1940** -- it lacked the diagonal board. The second Bombe, "Agnes," incorporating Welchman's diagonal board, became operational on **8 August 1940** and immediately proved superior.

### How Many Were Built

By war's end:
- **224 British bombes** (73 standard, 14 Jumbo, 57 Mammoth, 12 Cobra, 68 "new" standard)
- **121 US Navy bombes**
- **10 US Army bombes**
- Total: approximately **355 Bombes**
- Operated by 1676 female WRNS and 263 male RAF personnel

### Physical Specifications

- 7 feet wide x 6 feet 6 inches tall x 2 feet deep
- Approximately 1 ton
- 36 Enigma equivalents, each with 3 drums (108 total drums)
- Each drum had 104 wire brushes making contact with terminal plates
- Speed: 50.4 rpm (early), 120 rpm (later); approximately 20 minutes to test all 17576 positions
- US Navy Bombe: 10 ft x 7 ft x 2 ft, 2.5 tons, drums at 1725 rpm -- 34 times faster than early British models

### Were They Computers?

The Bombes were electromechanical devices -- special-purpose cryptanalytic machines, not general-purpose computers. They performed fixed logical operations within their design parameters. Wikipedia categorizes them under "Electro-mechanical computers" and "1930s computers," but they lacked programmability in the modern sense. They could not be reprogrammed for a different task.

**Sources:**
- [Bombe - Wikipedia](https://en.wikipedia.org/wiki/Bombe)
- [The Turing-Welchman Bombe -- TNMOC](https://www.tnmoc.org/bombe)
- [Enter Turing and Welchman -- bombe.org.uk](https://bombe.org.uk/enter-turing-and-welchman/)
- [The Turing bombe in Bletchley Park -- Rutherford Journal](https://rutherfordjournal.org/article030108.html)
- [How the Bombe was Plugged-Up](http://www.ellsbury.com/bombe3.htm)
- [Bombe -- Britannica](https://www.britannica.com/topic/Bombe)

---

## 3. Colossus

### Tommy Flowers and the Design

Tommy Flowers was a senior electrical engineer and Head of the Switching Group at the Post Office Research Station at Dollis Hill. Alan Turing recommended him to Newman after being impressed by his Bombe improvement work (Flowers had been working at Bletchley since February 1941).

Flowers had a crucial insight from pre-war experience: most thermionic valve (vacuum tube) failures occurred during power-up thermal stress. By keeping machines powered continuously and slowly ramping up heater voltage, he achieved very low failure rates. This made building a 1600-2400 valve machine feasible when many considered it impossible.

Flowers took Newman's blueprint and spent ten months turning it into Colossus, delivering it to Bletchley Park on **8 December 1943**. Newman's memo dated 18 January 1944 records: "Colossus arrives today."

### Max Newman's Section (The Newmanry)

Max Newman was a Cambridge mathematician who headed the "Newmanry" at Bletchley Park -- the section responsible for machine methods against the Lorenz SZ40/42 cipher (codenamed "Tunny"). Newman conceived the idea of using electronic machines to automate the breaking of Lorenz, and Flowers implemented the design.

### The Number Built

- **10 Colossi** were operational by V-E Day, with an **11th being assembled**
- The first Mark 1 Colossus arrived December 1943
- The first Mark 2 arrived 1 June 1944 -- just in time for D-Day
- 4 Mark 2 machines ordered March 1944, increased to 12 by late April
- 7 were used for "wheel setting," 3 for "wheel breaking"

### Technical Specifications

- **Mark 1:** 1600 thermionic valves (vacuum tubes)
- **Mark 2:** 2400 thermionic valves plus relays and stepping switches
- Operating speed: 5000 characters per second (40 feet/second paper tape)
- Tested up to 9700 characters/second before tape disintegrated
- Effective throughput via parallelism: 25000 characters/second
- Power consumption: 8.5 kilowatts
- Read data from paper tape loops (up to 20000 x 5-bit characters)
- Programmed using switches and plug panels
- No internal RAM storage
- Output via electric typewriter

### First Programmable Electronic Digital Computer?

Colossus is "regarded as the world's first programmable, electronic, digital computer" (compared to Zuse's Z3, the first electromechanical computer, completed in Berlin 1941).

**Caveats:**
- **NOT Turing-complete** -- it was special-purpose for cryptanalysis
- **NOT a stored-program computer** -- programs were set via switches and jack panel connections
- However, Benjamin Wells demonstrated that all ten Colossus machines arranged in a specific cluster could theoretically simulate a universal Turing machine, making the collection Turing-complete

### The Lorenz SZ40/42 and Its Relation to the Geheimschreiber

The Lorenz SZ40/42 and the Siemens & Halske T52 (Geheimschreiber) were **both German teleprinter cipher machines** in the same family of devices, codenamed "Fish" by Bletchley Park. The T52 was called "Sturgeon" and the Lorenz was called "Tunny."

Key distinction: the T52 was **considerably more complex** than the Lorenz. The T52 had ten pinwheels stepped in a complex nonlinear way, with both XOR substitution and conditional transposition stages. The Lorenz had twelve wheels (5 chi, 5 psi, 2 mu motor wheels) using Vernam ciphering (XOR of plaintext with keystream).

**The connection to Beurling:** Beurling cracked the T52 (Sturgeon) in two weeks with pen and paper in 1940. Bill Tutte performed the theoretical break of the Lorenz (Tunny) in about four months in 1941-42, also essentially by hand. Both feats have been called among "the greatest intellectual achievements of World War II." But Tutte's break led to Colossus being built; Beurling's led to FRA and eventually BESK.

### Fate After the War

- All but two Colossus machines were **dismantled "into such small parts that their use could not be inferred"**
- Two were retained and moved to GCHQ at Eastcote (1946), then Cheltenham (1952-54)
- "Colossus Blue" dismantled in 1959; the other in the 1960s
- Some sanitized parts transferred to Newman's Computing Machine Laboratory at Manchester
- Tommy Flowers was ordered to destroy all documentation: "That was a terrible mistake. I was instructed to destroy all the records, which I did... put it in the boiler fire. And saw it burn."
- A fully functional Mark 2 reconstruction was completed 1993-2008 by Tony Sale

### The Secrecy Problem

Colossus was kept secret until the mid-1970s (Winterbotham's *The Ultra Secret*, 1974). Because of this, it was excluded from computing history for decades, and Flowers' team received no recognition. Professor Brian Randell argued: "the COLOSSUS project was an important source of this vitality, one that has been largely unappreciated."

It had "little direct influence on the development of later computers; it was EDVAC that was the seminal computer architecture of the time." But a small group who knew Colossus was feasible -- Turing, Newman, Harry Huskey -- played significant roles in early computer development.

**Sources:**
- [Colossus computer - Wikipedia](https://en.wikipedia.org/wiki/Colossus_computer)
- [Colossus -- TNMOC](https://www.tnmoc.org/colossus)
- [IEEE Spectrum -- Hidden Figures Behind Colossus](https://spectrum.ieee.org/the-hidden-figures-behind-bletchley-parks-codebreaking-colossus)
- [Siemens and Halske T52 - Wikipedia](https://en.wikipedia.org/wiki/Siemens_and_Halske_T52)
- [GCHQ celebrates 80 years of Colossus](https://www.gchq.gov.uk/news/colossus-80)

---

## 4. The Computing Pipeline from Crypto to Weather

### Bletchley Park -> Manchester

**Max Newman** headed the Newmanry (Colossus section) at Bletchley Park. In 1945, he moved to the University of Manchester as Fielden Professor of Pure Mathematics. He secured a 30000 GBP Royal Society grant in July 1946 to found the **Computing Machine Laboratory**. Some sanitized Colossus components were transferred to Manchester. The result: the **Manchester Baby** (June 1948) -- the world's first stored-program electronic computer.

**Alan Turing** joined Newman at Manchester in October 1948 after leaving NPL. He worked on programming the **Manchester Mark 1** (which evolved from the Baby). Turing introduced teleprinter tape programming and sourced a paper tape reader -- "probably borrowed from Bletchley."

The Manchester Mark 1 was commercialized by Ferranti as the **Ferranti Mark 1** (February 1951) -- the world's first commercially available general-purpose electronic computer. Turing wrote its programming manual.

### Bletchley Park -> NPL (Turing -> ACE)

After the war, Turing joined the **National Physical Laboratory** on **1 October 1945**. By year's end, he completed his design for the **Automatic Computing Engine (ACE)** -- "the first complete specification of an electronic stored-program all-purpose digital computer." His report included detailed logical circuit diagrams and a cost estimate of 11200 GBP.

But NPL thought the engineering too difficult. Turing grew disillusioned by slow progress and left for Manchester. A smaller version, the **Pilot ACE**, became operational on **10 May 1950**. English Electric later commercialized it as **DEUCE**.

### FRA (Beurling) -> BESK -> Swedish NWP

Beurling's 1940 Geheimschreiber break created **FRA** (formally established 1 July 1942). FRA became the most urgent institutional customer for Swedish computing. **Stig Comet** -- simultaneously BESK project leader and FRA bureau chief -- ran nightly code-breaking sessions on BESK under strictest secrecy.

**BESK** (Binar Elektronisk SekvensKalkylator) was completed in 1953. It was a 40-bit vacuum tube machine, briefly the world's fastest computer (addition in 56 microseconds, multiplication in 350 microseconds). During daytime, it was used by meteorologists and SAAB engineers. During nights, FRA used it for cryptanalysis.

In **December 1954**, the Royal Swedish Air Force Weather Service began the **world's first routine operational NWP** on BESK -- a full year before the Americans.

The chain: **Beurling's pencil -> FRA -> BESK -> the weather.**

### ENIAC -> H-bomb and Weather

**ENIAC** was built at the University of Pennsylvania starting in 1943 for ballistics calculations at Aberdeen Proving Ground. It was later used for hydrogen bomb calculations.

In **spring 1950**, at Aberdeen Proving Ground, Jule Charney, Ragnar Fjortoft, and John von Neumann performed the **first numerical weather forecast by electronic computer** on the ENIAC. The team worked for 33 days and nights. Result: "Numerical Integration of the Barotropic Vorticity Equation" (1950). It took 24 hours of processing time to calculate a 24-hour forecast.

### Von Neumann -> IAS -> IBM 701 -> JNWPU

Von Neumann designed the **IAS machine** at Princeton. He persuaded IAS to move from theory to building a real computer, with meteorology as a key test of scientific value.

The **IBM 701** (first commercial scientific computer, 1952) was based on the IAS architecture. On **1 July 1953**, the **Joint Numerical Weather Prediction Unit (JNWPU)** was created. Early models were developed on an IBM 701 at IBM headquarters in late 1954. A dedicated IBM 701 was installed for JNWPU in 1955, beginning operational American NWP.

**Sources:**
- [Alan Turing in Manchester -- Science and Industry Museum](https://www.scienceandindustrymuseum.org.uk/objects-and-stories/alan-turing-in-manchester)
- [Max Newman -- Digital 60](https://curation.cs.manchester.ac.uk/digital60/www.digital60.org/about/biographies/maxnewman/index.html)
- [Automatic Computing Engine - Wikipedia](https://en.wikipedia.org/wiki/Automatic_Computing_Engine)
- [BESK - Wikipedia](https://en.wikipedia.org/wiki/BESK)
- [Ferranti Mark 1 - Wikipedia](https://en.wikipedia.org/wiki/Ferranti_Mark_1)
- [The First Compute Arms Race -- arxiv](https://arxiv.org/html/2506.21816v1)
- [ENIAC Forecasts -- Peter Lynch](https://maths.ucd.ie/~plynch/Publications/ENIAC-BAMS-08.pdf)
- [IBM 701 - Wikipedia](https://en.wikipedia.org/wiki/IBM_701)

---

## 5. The Mathematical Parallel: Rejewski and Charney

### Rejewski's Permutation Group Theory (1932)

In December 1932, Rejewski cracked the German military Enigma by applying **permutation group theory** to cryptanalysis -- the first time anyone had used pure mathematics for code-breaking.

**The method:** Rejewski modeled the Enigma machine as a composition of permutations. Each component -- entry drum, rotors, reflector, plugboard -- was a permutation on the 26-letter alphabet. The complete encryption at any position was a product of these permutations.

**The key insight (conjugation and invariance):** In group theory, if X and Y are permutations, the product XYX^{-1} is the conjugate of Y by X. A fundamental theorem: **the disjoint cycle structure of a permutation and any of its conjugates has the same shape.** Rejewski realized the plugboard acted as a conjugating permutation. This meant the plugboard changed which letters appeared in the cycles but **did not change the number and lengths of cycles.** The cycle structure was therefore an **invariant** -- independent of the unknown, daily-changing plugboard settings. He called this invariant the **"characteristic" (charakterystyka)**.

By collecting enough message indicators from a single day, Rejewski determined the characteristic without knowing the plugboard settings. The characteristic constrained possible rotor positions to a small number of candidates.

**The six equations:** Rejewski formulated six equations modeling permutations at six consecutive Enigma positions:

A = S H P N P^{-1} M L R L^{-1} M^{-1} P N^{-1} P^{-1} H^{-1} S^{-1}

where S = plugboard, H = entry drum, P, N = rotor settings, M, L = reflector, R = rightmost rotor.

**The alphabetical insight:** The British had assumed the military Enigma used keyboard order (QWERTZU) for the entry drum. Rejewski tried straight alphabetical order (ABCDEFG...). It worked. As Peter Twinn said: "It was such an obvious thing to do, rather a silly thing, that nobody -- not Dilly Knox or Tony Kendrick or Alan Turing -- ever thought it worthwhile trying." Rejewski recalled: **"from my pencil, as by magic, began to issue numbers designating the connections in rotor N."**

**Cipher A. Deavours**, co-editor of *Cryptologia*, called the conjugation theorem Rejewski applied **"the theorem that won World War II."**

### Charney's Quasi-Geostrophic Equations (1948)

In 1948, Jule Charney derived the **quasi-geostrophic prediction equations** -- a mathematical simplification that made numerical weather prediction computationally feasible.

**The problem:** Lewis Fry Richardson had attempted NWP by hand in 1922 and failed catastrophically: his forecast predicted a pressure change of 145 millibars in 6 hours (actual change: nearly zero). The failure was caused by computational instability -- the primitive equations contained fast-moving sound waves and gravity waves that overwhelmed the slow meteorological signal.

**Charney's solution:** Using scale analysis, Charney simplified the primitive equations by assuming a geostrophic and hydrostatic atmosphere. He reduced the system to a single equation involving only air pressure, from which sound and gravity wave solutions were **completely eliminated.** The resulting equations predicted only the slow, large-scale motions relevant to weather.

**The parallel:** Both Rejewski and Charney faced problems that everyone considered computationally impossible. Both applied abstract mathematical techniques (group theory / scale analysis) to transform the problem into something tractable. Both were initially working in relative obscurity (a Polish cipher bureau / a PhD student at UCLA). Both were dismissed by the establishment until their results proved undeniable. Both changed the world.

The difference: Rejewski's breakthrough was immediate and operational (reading Enigma within weeks). Charney's required a computer to implement -- which is why the two stories converge when the crypto-driven computers became available for weather.

**Sources:**
- [Marian Rejewski and the First Break into Enigma -- AMS](https://www.ams.org/publicoutreach/feature-column/fcarc-enigma)
- [Cryptanalysis of the Enigma - Wikipedia](https://en.wikipedia.org/wiki/Cryptanalysis_of_the_Enigma)
- [Rejewski's equations -- ResearchGate](https://www.researchgate.net/publication/320658732_Rejewski's_equations_Solving_for_the_entry_permutation)
- [Charney and the Revival of NWP -- SpringerLink](https://link.springer.com/chapter/10.1007/978-1-944970-35-2_4)
- [Jule Gregory Charney - Wikipedia](https://en.wikipedia.org/wiki/Jule_Gregory_Charney)

---

## 6. Hans-Thilo Schmidt ("Asche")

### Background

**Hans-Thilo Schmidt** (13 May 1888 -- 19 September 1943), codenamed **Asche** (also "Source D"), was a German spy who sold Enigma secrets to French intelligence during the 1930s.

He held a civilian post at Germany's Chiffrierabteilung (Cipher Office / Cryptographic Agency). His brother, **Rudolf Schmidt**, was a Wehrmacht general who had secured the position for him. Hans-Thilo had been forced to leave the army after suffering gas injuries during World War I.

### What He Sold

Over several years, Schmidt met with French agents at various European cities and supplied:
- Copies of the Enigma machine's **instruction manual**
- **Operating procedures**
- Lists of **key settings** (monthly tables)
- Rotor wiring information

These materials were critical. Rejewski's system of equations had too many unknowns to solve with intercept data alone. The key settings lists from Schmidt "proved in practice crucial" -- they reduced the unknowns enough for Rejewski to determine the rotor and reflector wirings.

Rejewski acknowledged: "the intelligence material furnished to us should be regarded as having been decisive to solution of the machine." He also noted he could have broken the code without the French materials, "but it would have taken much longer and would instead have been based on chance."

### How the Documents Reached Rejewski

1. **Schmidt** approached French intelligence through **Rodolphe Lemoine** (born Friedrich Rudolf Stallmann, 1871-1946), a German-born French agent codenamed "Rex."

2. On **1 November 1931**, at the Grand Hotel in Verviers, Belgium, Schmidt met with Lemoine and French intelligence officer. He provided the first Enigma documents.

3. Lemoine, taking advantage of Schmidt's gambling debts and financial difficulties, maintained the relationship over years, meeting at various European cities.

4. **Captain Gustave Bertrand**, chief of Section D (Decryptement) within French military intelligence, received the materials from Lemoine.

5. Bertrand first offered the materials to the **British** (Dilly Knox and GC&CS). They were unable to make use of them.

6. In **December 1932**, Bertrand shared the intelligence with the **Polish Cipher Bureau** (specifically with chief Gwido Langer).

7. Rejewski, who had already set up his system of permutation equations, now had enough data to solve for the unknowns.

### His Tragic End

After the Battle of France (1940), the chain of betrayal began:

1. **Rodolphe Lemoine** was arrested by the Gestapo (or defected to them) in late 1942/early 1943, possibly on **27 February 1943**, after attempting to sell an Italian secret code to the Germans.

2. During Gestapo interrogation in Berlin, Lemoine **betrayed Schmidt** as one of his intelligence sources.

3. Schmidt was **arrested on 1 April 1943**.

4. In **September 1943**, Schmidt's daughter Giselle was called to identify his body. Her account suggests Schmidt **committed suicide in prison** on **19 September 1943**. His cause of death is listed ambiguously as "Execution or Suicide."

5. Lemoine died in his cell in Germany in **1946**, after being arrested by French troops following the Nazi surrender.

### His Brother

**Rudolf Schmidt** (1886-1957) was a German general who commanded the 2nd Panzer Group and later the Second Panzer Army on the Eastern Front. He was stripped of his rank in 1943 -- possibly in connection with his brother's espionage, though the exact circumstances remain debated.

**Sources:**
- [Hans-Thilo Schmidt - Wikipedia](https://en.wikipedia.org/wiki/Hans-Thilo_Schmidt)
- [The Spy in Hitler's Inner Circle -- USF Digital Commons](https://digitalcommons.usf.edu/cgi/viewcontent.cgi?article=1639&context=jss)
- [queerplaces - Friedrich Rudolf Stallmann](http://www.elisarolle.com/queerplaces/fghij/Friedrich%20Rudolf%20Stallmann.html)

---

## 7. Gustave Bertrand

### Biography

**Gustave Bertrand** (1896-1976) was a French military intelligence officer. He joined the military as a private in 1914 and was wounded at the Dardanelles in 1915. From 1926, he worked in radio intelligence. By 1930, he became chief of **Section D (Decryptement)** within France's Deuxieme Bureau, overseeing all French radio intelligence and cryptanalytic operations.

### His Role as Broker

Bertrand was the critical link between Schmidt's espionage and Rejewski's mathematics:

1. Bertrand's network (through Lemoine/Stallmann) recruited Schmidt as an agent.
2. In **December 1932**, then-Captain Bertrand delivered Schmidt's Enigma materials to Polish Cipher Bureau chief Major Gwido Langer.
3. The Poles gave Bertrand the codename **"Bolek."**
4. Rejewski confirmed: the documents "proved in practice crucial" to solving the Enigma.

Bertrand first offered the materials to the British. When Knox and GC&CS could not use them, Bertrand turned to the Poles.

### The Pyry Meeting (July 1939)

Bertrand learned of Poland's success against Enigma only at the **tripartite Polish-French-British conference** held in the Kabaty Woods, south of Warsaw, on **25-26 July 1939** -- five weeks before war began.

**The delegations:**

**Polish:** Lt. Col. Gwido Langer (Cipher Bureau chief), Major Maksymilian Ciezki (BS-4 chief), Col. Stefan Mayer (intelligence chief), Marian Rejewski, Jerzy Rozycki, Henryk Zygalski, engineers Antoni Palluth and Czeslaw Betlewski (AVA).

**French:** Major Gustave Bertrand, Captain Henri Braquenie (Air Force).

**British:** Commander Alastair Denniston (head of GC&CS), Alfred Dillwyn "Dilly" Knox (chief cryptanalyst), Commander Humphrey Sandwith (Royal Navy signals).

**What was revealed:** The Poles revealed everything: their methods for breaking Enigma, the internal wiring, the cyclometer, the bomba kryptologiczna, the Zygalski sheets. They promised each delegation a Polish-reconstructed replica Enigma machine.

**Reactions:** Knox was "chagrined -- but grateful" to learn how simple the entry ring solution was (alphabetical order). He "grasped everything very quickly, almost quick as lightning," Rejewski observed. Knox threw a tantrum -- not at the Poles but at himself, for having dismissed the alphabetical wiring. After the meeting, Knox sent the Polish cryptologists "a very gracious note in Polish" on official British stationery, along with a scarf featuring a picture of a Derby winner and a set of paper "batons."

Gordon Welchman later wrote: **"Hut 6 Ultra would never have got off the ground if we had not learned from the Poles, in the nick of time, the details both of the German military version of the commercial Enigma machine, and of the operating procedures that were in use."**

RUSI called it **"the most consequential intelligence-sharing arrangement of World War Two."**

### Wartime Activities

After Poland fell, Bertrand sponsored continued Cipher Bureau work in France:
- **PC Bruno** (Chateau de Vignolles, near Paris) from October 1939
- **Cadix** (Chateau des Fouzes, near Uzes, southern France) from October 1940 to November 1942

On **5 January 1944**, Germans captured Bertrand at Sacre Coeur basilica. He pretended cooperation, was allowed to return to Vichy, and went into hiding. On **2 June 1944** -- four days before D-Day -- he, his wife, and a Polish Resistance courier escaped by Lysander aircraft to England.

### Later Life

Retired from French Secret Service in 1950. Became mayor of Theoule-sur-Mer. In 1973, published *Enigma ou la plus grande enigme de la guerre 1939-1945*, providing "a detailed account of the some eleven years of Franco-Polish collaboration."

**Sources:**
- [Gustave Bertrand - Wikipedia](https://en.wikipedia.org/wiki/Gustave_Bertrand)
- [GCHQ -- The Pyry Forest Meeting](https://www.gchq.gov.uk/information/the-pyry-forest-meeting)
- [UK National Archives -- Polish cryptologists, July 1939](https://history.blog.gov.uk/2019/07/26/whats-the-context-polish-cryptologists-reveal-they-have-cracked-the-enigma-code-26-july-1939/)
- [Enigma -- Poland In Exile](https://polandinexile.com/article/enigma/)
- [Alastair Denniston's Account of Pyry -- Cryptologia](https://www.tandfonline.com/doi/abs/10.1080/01611190600920944)

---

## Key Quotes for the Blog Post

1. Rejewski on the breakthrough: **"from my pencil, as by magic, began to issue numbers designating the connections in rotor N."**

2. Peter Twinn on the alphabetical insight: **"It was such an obvious thing to do, rather a silly thing, that nobody -- not Dilly Knox or Tony Kendrick or Alan Turing -- ever thought it worthwhile trying."**

3. Cipher Deavours on Rejewski's mathematics: **"the theorem that won World War II"** (referring to the conjugation invariance of cycle structure).

4. David Kahn on Rejewski: **"The solution was Rejewski's own stunning achievement, one that elevates him to the pantheon of the greatest cryptanalysts of all time."**

5. Gordon Welchman: **"Hut 6 Ultra would never have got off the ground if we had not learned from the Poles, in the nick of time."**

6. Rejewski's noble statement: **"It was not cryptological difficulties of ours that prompted us to work with the British and French, but only the deteriorating political situation."**

7. Alan Stripp on the wartime mistreatment of Rejewski and Zygalski: **"Setting them to work on the Doppelkassetten system was like using racehorses to pull wagons."**

8. Tommy Flowers on destroying Colossus documentation: **"That was a terrible mistake. I was instructed to destroy all the records, which I did... put it in the boiler fire. And saw it burn."**

9. Brian Randell on Colossus's hidden influence: **"the COLOSSUS project was an important source of this vitality, one that has been largely unappreciated."**

10. Rejewski on the role of intelligence: **"the intelligence material furnished to us should be regarded as having been decisive to solution of the machine."**

---

## The Narrative Thread for the Blog Post

The post should follow this arc, connecting to the existing series:

1. **Open with the promise** from the Beurling post: "In Poland, three other magicians are waiting for their story to be told properly. Soon."

2. **Schmidt and Bertrand** -- the spy and the broker who made it all possible. A German aristocrat selling secrets out of resentment and debt. A French intelligence officer who brokered the documents to the only people who could use them -- not the British (who tried and failed), but the Poles.

3. **Rejewski's mathematics** -- the permutation group theory breakthrough of 1932. Emphasize: this was the first time anyone used pure mathematics for code-breaking. The parallel with Charney: abstract mathematics applied to an "impossible" practical problem.

4. **The bomba** -- the first electromechanical cryptanalytic machine (1938). Six machines built by AVA in Warsaw. The direct ancestor of Turing's Bombe.

5. **The Pyry handover** -- July 1939. Five weeks before war. Knox's reaction. The most consequential intelligence sharing of the war.

6. **Turing's Bombe** -- how it evolved from the Polish bomba. Welchman's diagonal board. 355 machines built. The industrial scale of British code-breaking.

7. **Colossus** -- from Enigma (Bombes) to Lorenz (Colossus). Tommy Flowers and Max Newman. The first programmable electronic computer. Built for codebreaking. The Lorenz SZ40/42 was the same family as Beurling's Geheimschreiber.

8. **The computing pipeline** -- show how the people and institutions flowed from crypto to computers to weather:
   - Newman -> Manchester Baby -> Ferranti Mark 1
   - Turing -> NPL ACE -> DEUCE
   - Beurling -> FRA -> BESK -> Swedish NWP (1954)
   - ENIAC (ballistics/H-bomb) -> Charney/von Neumann weather (1950) -> IAS -> IBM 701 -> JNWPU (1955)

9. **The mathematical parallel** -- Rejewski (permutation group theory, 1932) and Charney (quasi-geostrophic equations, 1948). Both applied abstract mathematics to problems everyone said were impossible. Both were initially dismissed. Both changed the world. The crypto broke the ciphers; the math broke the weather.

10. **Close** -- from Rejewski's pencil to the weather forecast on your phone. The chain runs through ciphers, through vacuum tubes, through equations, to the atmosphere.
