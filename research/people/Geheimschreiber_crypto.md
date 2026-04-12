# The Siemens & Halske T52 Geheimschreiber: Machine, Cryptanalysis, and Intelligence

## Research Notes — Deep Dive

---

## 1. The T52 Machine: Technical Details

### Overview

The Siemens & Halske T52, known as the **Geheimschreiber** ("secret writer") or formally as the **Schlüsselfernschreibmaschine** (SFM — "cipher teleprinter machine"), was a World War II German cipher machine and teleprinter produced by Siemens & Halske. It was one of Nazi Germany's most secret cryptographic systems, designed for high-level strategic communications. British cryptanalysts at Bletchley Park codenamed the T52 and its traffic **"Sturgeon"**, while the broader category of German teleprinter ciphers was collectively called **"Fish"**.

Between 600 and 1200 units were manufactured during the war.

- **Wikipedia — Siemens and Halske T52**: [https://en.wikipedia.org/wiki/Siemens_and_Halske_T52](https://en.wikipedia.org/wiki/Siemens_and_Halske_T52). Accessed: 2026-04-03.
- **Crypto Museum — T52e Technical Description**: [https://www.cryptomuseum.com/crypto/siemens/t52/files/T52e_TechDesc_EN.pdf](https://www.cryptomuseum.com/crypto/siemens/t52/files/T52e_TechDesc_EN.pdf). Accessed: 2026-04-03.
- **jproc.ca — Sturgeon**: [http://jproc.ca/crypto/sturg.html](http://jproc.ca/crypto/sturg.html). Accessed: 2026-04-03.

### How It Worked

The T52 was an **online cipher machine** — it encrypted teleprinter messages automatically during transmission, as opposed to Enigma which required manual letter-by-letter operation. The teleprinters of the day emitted each character as **five parallel bits** on five lines, encoded in **Baudot code** (International Telegraph Alphabet No. 2, ITA2). The machine operated at approximately **50 baud** (roughly 66 words per minute, or about 6 characters per second).

#### The Ten Pin-Wheels

The T52 had **ten pin-wheels** (also called code wheels), labeled A through K (omitting I). Each wheel had a different number of pins, chosen to be **coprime** to ensure non-periodic output when combined:

| Wheel | Number of Pins |
|-------|---------------|
| A     | 47            |
| B     | 53            |
| C     | 59            |
| D     | 61            |
| E     | 64            |
| F     | 65            |
| G     | 67            |
| H     | 69            |
| J     | 71            |
| K     | 73            |

The wheels were moulded in **Bakelite with fixed code patterns** — unlike the Lorenz SZ40/42 (Tunny), which had metal cams that could be set in active or inactive positions.

#### Encryption Process

The cipher operated through two cryptographic functions:

1. **Substitution (Subtractor):** Each of the five plaintext bits was XORed with the XOR sum of three taps from the pin-wheels.
2. **Transposition (Permutor):** Cyclically adjacent pairs of plaintext bits were swapped or not, according to XOR sums of three (different) output bits.

The triplets of bits controlling each XOR or swap were **selectable through a plugboard**, adding another layer of configurability.

This two-stage process — XOR followed by conditional transposition — meant the T52 was **not merely a pseudorandom number generator-and-XOR cipher** like the Lorenz. This had profound implications for cryptanalysis: a crib (known plaintext) did not directly yield the key, as it would on a pure Vernam cipher.

#### Keyspace

The T52 permitted approximately **893,622,318,929,520,960 different crypto key settings** — roughly 893 quadrillion (approximately 10^18) possible combinations per wheel order. The total keyspace, factoring in all configurations, reached approximately 10^27.

- **Rutherford Journal — "Bletchley Park's Sturgeon, the Fish that Laid No Eggs"**: [https://www.rutherfordjournal.org/article010106.html](https://www.rutherfordjournal.org/article010106.html). Accessed: 2026-04-03.

### Versions: T52a Through T52e

Siemens produced five versions with **increasing cryptographic sophistication**. The early models (T52a/b and T52c) were cryptologically weak; the later models (T52d and T52e) were far more resistant to attack.

#### T52a and T52b
- The earliest models. They differed **only in electrical noise suppression** (the T52b had better shielding).
- **Cryptologically weak**: All ten wheels advanced regularly (one position per character), producing a predictable keystream period.
- Wheel selection for the subtractor and permutor was done by **plugging cables into sockets**.
- These were the models Beurling broke in 1940.

#### T52c
- Introduced **simplified key settings** using a switch and relay assembly instead of plugboard cables.
- Used a **standard fixed configuration** of the transposition units (wired permanently in place).
- Still cryptologically weak. The critical vulnerability was the "Pentagon" — a wheel-combining circuit that produced only **60 possible cipher alphabets** instead of the theoretical 1024, because the subtractor character always maintained even parity.
- Bletchley Park first encountered this model (on Sicily-Libya traffic, 1942).

#### T52ca
- A modified T52c that **eliminated the Pentagon vulnerability**, increasing possible alphabets from 60 to 256.

#### T52d
- A major advance: introduced **irregular "stop-and-go" wheel movement**. The decision of whether or not to advance each wheel was controlled by logic circuits that took input data from the wheels themselves.
- Wheel selection still done via plugboard cables.
- Bletchley Park found this model extremely difficult: they required a year of analysis before reading a T52d (Halibut) message in June 1944.
- Captain Walter Fried's July 1944 assessment at Bletchley Park: **"The problem of solving current traffic seems completely hopeless."**

#### T52e
- Combined **T52c's usability** (switch-and-relay configuration) with **T52d's features** (irregular wheel movement).
- Featured improved wheel-combination logic and a switchable **autokey function** (KTF — *Klartextfunktion*), which used the plaintext itself to influence the cipher, making depth attacks far harder.
- Equipped the largest number of German teleprinter links by war's end.

### How It Differed from Enigma

| Feature | Enigma | T52 Geheimschreiber |
|---------|--------|---------------------|
| **Operation** | Manual, letter-by-letter | Online, automatic teleprinter |
| **Encoding** | 26-letter alphabet (substitution only) | 5-bit Baudot code (substitution + transposition) |
| **Rotors/Wheels** | 3-4 rotors (from set of 5-8) | 10 fixed pin-wheels |
| **Speed** | ~20 characters/minute (operator-limited) | ~400 characters/minute (50 baud) |
| **Deployment** | Portable, field units | Fixed installation, requiring landline circuits |
| **Users** | All branches, tactical level | Luftwaffe, Navy — strategic/high-level |
| **Complexity** | ~10^23 key combinations | ~10^27 key combinations |
| **Cipher type** | Polyalphabetic substitution | XOR + conditional transposition |

The T52 was **far more complex** than Enigma. It was also more complex than the Lorenz SZ40/42 — in particular, if two messages were sent with identical settings (a "depth of two"), this could be detected statistically but was **not immediately and trivially solvable** as it would be with the Lorenz.

### Where It Was Used

- Primarily used by the **Luftwaffe** (German Air Force) and **Kriegsmarine** (German Navy) for strategic communications.
- Required **fixed installations** with landline or cable circuits — unlike the portable Enigma.
- Key circuits included links between:
  - **Berlin and Oslo** (through Swedish cables)
  - **Berlin and other occupied territories** (Sicily, Libya, Norway)
  - **German embassies** (including Stockholm)
  - Inter-service communications between German high-command stations.

- **Wikipedia — Fish (cryptography)**: [https://en.wikipedia.org/wiki/Fish_(cryptography)](https://en.wikipedia.org/wiki/Fish_(cryptography)). Accessed: 2026-04-03.

---

## 2. Why Traffic Went Through Sweden

### The Cable Routes

When Germany invaded Denmark and Norway in April 1940 (Operation Weserübung), it needed reliable telecommunications between Berlin and the occupation forces in Norway. The most practical route was **via Swedish territory**: existing telegraph and telephone cables ran through Sweden, connecting Norway to the European continent.

Germany **demanded that Sweden keep these telephone and telegraph lines open** and hired the use of Swedish telephone lines for its military communications. After some deliberation, the Swedish government agreed — a pragmatic decision by a small neutral country surrounded by German-occupied or German-allied territory.

The Germans gradually hired lines in Sweden for multiple routes:
- **Oslo — Copenhagen — Berlin** (the primary strategic link)
- **Oslo — Trondheim**
- **Oslo — Narvik**
- **Oslo — Stockholm**
- **Stockholm — Berlin** (German embassy communications)
- **Stockholm — Helsinki** (communications with Finland)

These lines carried traffic encrypted with the Geheimschreiber.

- **Wikipedia — Sweden during World War II**: [https://en.wikipedia.org/wiki/Sweden_during_World_War_II](https://en.wikipedia.org/wiki/Sweden_during_World_War_II). Accessed: 2026-04-03.
- **Ulfving, Lars (trans. Weierud, Frode). "The Geheimschreiber Secret"**: [https://cryptocellar.org/Ulfving/ulfving.html](https://cryptocellar.org/Ulfving/ulfving.html). Accessed: 2026-04-03.

### Geopolitical Context: Sweden's "Neutrality"

Sweden declared neutrality in September 1939, but its position was precarious. After Germany occupied Denmark and Norway (April 1940) and allied with Finland, Sweden was **effectively surrounded** by Axis-controlled or Axis-aligned territory. Swedish neutrality was maintained through a combination of diplomatic concession and strategic flexibility.

Key concessions to Germany included:
- Allowing the transit of German troops through Sweden (most notably the **"Midsummer Crisis" of June 1941**, when Germany transported the 163rd Infantry Division by rail from Norway to Finland for Operation Barbarossa).
- Leasing telephone and telegraph lines for German military communications.
- Continued iron ore exports to Germany.

But Sweden was not passive. Its intelligence services saw the cable arrangement as a **golden opportunity**: the lines ran through Swedish territory, and Swedish engineers had physical access to them.

### FRA and the Interception

The Swedish General Staff's cryptanalytic unit, initially known as **Crypto Detail IV** (Kryptodetaljen IV), was established in 1939 under Sven Hallenborg's command with approximately 50 cryptanalysts. Its first facility was near Karlaplan in Stockholm.

When the German lines became active, Crypto Detail IV began **systematically tapping and recording** the encrypted teleprinter traffic. A set of teleprinters in a room at Karlaplan 4 were connected to the different leased lines, capturing the encrypted Baudot-code transmissions.

On **1 July 1942**, the intelligence operation was formalized as an independent government agency under the Swedish Ministry of Defence: the **Försvarets Radioanstalt (FRA)** — the National Defence Radio Establishment. It was led by naval officer **Torgil Thorén** (1942-1957). FRA relocated to Lovön (approximately 15 km from Stockholm) in October 1943.

- **Wikipedia — National Defence Radio Establishment**: [https://en.wikipedia.org/wiki/National_Defence_Radio_Establishment](https://en.wikipedia.org/wiki/National_Defence_Radio_Establishment). Accessed: 2026-04-03.
- **Hans Högman — Swedish Military Crypto Department**: [https://www.hhogman.se/crypto-dept.htm](https://www.hhogman.se/crypto-dept.htm). Accessed: 2026-04-03.

### Was the Interception Legal?

The legal and diplomatic situation was complex:

- **Sovereign territory**: The cables ran through Swedish soil. Under international law, Sweden had the right to monitor communications transiting its territory, particularly during wartime.
- **No explicit prohibition**: Germany leased the lines from Swedish telecom operators but did not negotiate any explicit guarantees of non-interception. The assumption of security rested entirely on the Geheimschreiber's encryption.
- **Wartime intelligence prerogative**: Sweden, while neutral, maintained the right to conduct signals intelligence for its own national security.
- **Diplomatic risk**: Had Germany discovered the interception (and the fact that Sweden could read the traffic), the consequences could have been severe. Sweden went to considerable lengths to protect the source.

The interception was not publicized and remained **classified for decades**. The modern FRA's legal framework (SFS 2008:717, the controversial "FRA law") has explicit statutory authorization for cable interception of international communications — a framework that can be seen as a distant descendant of the WWII-era practice.

---

## 3. Beurling's Cryptanalysis vs. Bletchley Park

### Arne Beurling Breaks the T52 (1940)

**Arne Beurling** (1905-1986), a professor of mathematics at Uppsala University, was on voluntary military service when he was assigned to work on the intercepted German teleprinter traffic in the spring/summer of 1940.

#### The Achievement

Working with only **pencil and paper** and a set of intercepted messages, Beurling **single-handedly deduced the internal workings of the T52a/b cipher machine and developed a method to decrypt its traffic** — all within approximately **two weeks**.

He had never seen a Geheimschreiber. He worked from **intercepted ciphertext alone** — specifically, messages in "depth" (multiple messages encrypted with the same key settings) intercepted on 25 and 27 May 1940 on the Berlin-Oslo circuit.

The key factors enabling his break:
1. **Operator errors**: German cipher clerks frequently sent **multiple messages using the same key settings**, creating depths that Beurling could exploit.
2. **Classical cryptanalytic technique**: Beurling identified high-frequency or unusually long German words, formed hypotheses, and tested them against other encoded messages.
3. **Mathematical intuition**: Beurling combined his knowledge of German, his analytical brilliance, and what contemporaries described as "intuition, feeling and aesthetics" rather than purely mechanical methods.

#### Beurling's Secrecy

Beurling **never described his exact method**. When asked how he cracked the code, his answer was famously evasive:

> **"A magician does not reveal his secrets."**

He took the secret to his grave in 1986. A partial reconstruction of his likely method was later made by **Carl-Gösta Borelius** at FRA.

- **Wikipedia — Arne Beurling**: [https://en.wikipedia.org/wiki/Arne_Beurling](https://en.wikipedia.org/wiki/Arne_Beurling). Accessed: 2026-04-03.
- **Uppsala University — Arne Beurling**: [https://www.uu.se/en/about-uu/history/prominent-people/arne-beurling](https://www.uu.se/en/about-uu/history/prominent-people/arne-beurling). Accessed: 2026-04-03.

#### The Ericsson Decryption Machines

Once Beurling had determined the machine's workings and the daily key-finding method, the telephone company **L.M. Ericsson** was commissioned to build **analog replicas** of the T52 — decryption machines known internally as **"APP"** (Apparat, plural "APPARNA"). These machines could **automatically decrypt intercepted messages** once the key settings had been found by hand.

This was Sweden's answer to what Bletchley Park achieved with Colossus — but built by a telephone manufacturer rather than a computing pioneer, and designed to replicate the cipher machine rather than statistically attack the cipher.

#### Beurling's Departure

Beurling was known for his **explosive temperament** and could be "stubborn and difficult" — he reportedly ended some arguments with his fists. He was **dismissed from the cryptanalytic unit in spring 1942** due to interpersonal conflicts, despite being the genius behind their greatest achievement. He later returned to academic mathematics, served as a visiting professor at Harvard (1948-1949), and from 1954 held a professorship at the **Institute for Advanced Study in Princeton**, occupying Albert Einstein's former office.

- **Weierud, Frode. "Sweden: Cryptographic Superpower" (book review, Cryptologia, 1998)**: [https://cryptocellar.org/pubs/beckrevw.pdf](https://cryptocellar.org/pubs/beckrevw.pdf). Accessed: 2026-04-03.

#### Sweden's Continuing Breaks

Beurling made the initial break, but other Swedish cryptanalysts continued the work:

- A team of **Carl-Gösta Borelius, Tufve Ljunggren, and Bo Kjellberg**, under the leadership of **Lars Carlbom**, continued breaking new T52 variants as Germany introduced them.
- They broke the **T52c** and **T52ca** models.
- On **9 April 1943**, the same group broke **Lorenz SZ40 traffic** passing through Swedish cables — making Sweden the **first nation besides Britain to break the Lorenz cipher**.
- In June and September 1943, they also broke SZ40 and SZ42 **radio** traffic.
- The Lorenz machine was simulated using a "Heath Robinson" machine with **twelve bicycle chains of different lengths**.
- When the **T52d** was introduced in December 1943, the improved German keying practices and the intermittent wheel movements proved too much. The Swedes had to accept defeat.

**All Swedish breaks were performed by hand.** They only automated the deciphering (not the key-finding) by building machine replicas.

- **Weierud, Frode. "Sweden: Cryptographic Superpower"**: [https://cryptocellar.org/pubs/beckrevw.pdf](https://cryptocellar.org/pubs/beckrevw.pdf). Accessed: 2026-04-03.

### Bletchley Park Attacks the T52 (1942-1944)

#### Bletchley Park's Encounter with Sturgeon

Bletchley Park (BP) first detected T52 traffic in **summer/autumn 1942** on radio links between **Sicily and Libya**. The German operators on this link transmitted numerous messages using identical machine settings — creating the depths that were essential for cryptanalytic attack.

Mathematician **Michael Crum** exploited these depths to analyse the machine's structure. BP discovered the machine used ten fixed code wheels and exploited the "Pentagon" vulnerability of the T52c (only 60 possible cipher alphabets instead of 1024, due to even parity in the subtractor).

#### BP's Progression Through Variants

- **T52c ("Pentagon machine")**: Encountered first. The wheel-combining logic was the critical weakness. BP could read depths of four or five messages once daily wheel settings were recovered.
- **T52a/b ("Salmon" link)**: Simpler construction, but reportedly **more difficult** than the Pentagon machine despite its simplicity — producing 960 alphabets instead of 60.
- **T52d ("Halibut" link)**: Introduced irregular stop-and-go wheel movement. A depth of only four to five messages in July 1943 proved insufficient. BP required **a year of analysis** before reading a Halibut message in **June 1944** — deriving the complete motor-wheel logic from a single message, an "outstanding achievement."
- **T52e**: Featured improved wheel-combination logic and autokey function.

#### Why BP Abandoned Sturgeon

Despite breaking multiple T52 variants, BP decided to **abandon Sturgeon traffic in 1944**. Reasons included:
1. **Cryptanalytic difficulty**: Each new variant was harder than the last.
2. **Limited traffic**: Most T52 traffic went over landlines (inaccessible to British intercept stations); only a small amount was transmitted by radio.
3. **Poor intelligence yield**: Most intercepted Sturgeon messages consisted of "operator chat" rather than high-level strategic intelligence.
4. **The Luftwaffe retransmission habit**: The Luftwaffe very often retransmitted Sturgeon messages using easier-to-attack (or already broken) ciphers, making the effort to break Sturgeon itself less worthwhile.

Captain Walter Fried's July 1944 assessment proved prescient: **"The problem of solving current traffic seems completely hopeless."** BP's own analysis confirmed that once Germans implemented proper keying (no depths, autokey activated, no wheel-reset mechanism), Sturgeon traffic became intractable. Properly used, the T52d would have been "highly unlikely to have been broken."

- **Rutherford Journal — "Bletchley Park's Sturgeon, the Fish that Laid No Eggs"**: [https://www.rutherfordjournal.org/article010106.html](https://www.rutherfordjournal.org/article010106.html). Accessed: 2026-04-03.

### Turing, Tutte, and the Lorenz SZ40/42 (Tunny)

The Lorenz SZ40/42, codenamed **Tunny** at Bletchley Park, was a different teleprinter cipher machine used by the **German Army** (Wehrmacht/OKH/OKW) for high-level communications. It was also in the "Fish" category but used a fundamentally different cipher design.

#### Tutte's Deduction

**William Tutte** (Bill Tutte), a Cambridge mathematician at Bletchley Park, deduced the complete internal structure of the Lorenz machine by **January 1942** — without ever having seen one. (A Lorenz machine was not captured until 1945.) Tutte's analysis was based on a single long stretch of key material extracted by **Brigadier John Tiltman** from two messages sent with the same key settings on 30 August 1941.

Tutte wrote out bit patterns by hand and discovered a period of 41 in the first channel — revealing the structure of the chi and psi wheel systems. This was described, when Tutte was inducted as **Officer of the Order of Canada** in October 2001, as *"one of the greatest intellectual feats of World War II."*

#### Turing's Contribution

In July 1942, **Alan Turing** developed **"Turingery"** (Turing's Method), a hand codebreaking technique for finding the wheel settings of the Lorenz cipher.

#### Colossus

The statistical methods needed to break Tunny traffic required enormous computation. This led to:
1. **Heath Robinson** machines (1943) — electro-mechanical devices that were slow and unreliable.
2. **Colossus** (operational February 1944) — designed by **Tommy Flowers**, the world's first electronic programmable digital computer. It used 1500 to 2400 thermionic valves (vacuum tubes) and processed ciphertext at 5000 characters per second (Mark 2 versions reached an effective 25000 characters per second through parallel processing). **Ten Colossus machines** were operational by war's end, with approximately 90% of selected Tunny messages being decrypted.

- **Wikipedia — Cryptanalysis of the Lorenz cipher**: [https://en.wikipedia.org/wiki/Cryptanalysis_of_the_Lorenz_cipher](https://en.wikipedia.org/wiki/Cryptanalysis_of_the_Lorenz_cipher). Accessed: 2026-04-03.
- **Wikipedia — Lorenz cipher**: [https://en.wikipedia.org/wiki/Lorenz_cipher](https://en.wikipedia.org/wiki/Lorenz_cipher). Accessed: 2026-04-03.

### Comparison: Beurling vs. Bletchley Park

| Dimension | Beurling (Sweden, 1940) | Tutte/Turing (BP, 1941-42) | BP Sturgeon Team (1942-44) |
|-----------|------------------------|---------------------------|---------------------------|
| **Target machine** | Siemens T52a/b | Lorenz SZ40/42 | Siemens T52c/d/e |
| **Codename** | (no codename — Swedish effort) | Tunny | Sturgeon |
| **Method** | Pen and paper, solo | Pen and paper (Tutte), then machine-assisted | Pen and paper, some mechanization |
| **Time to first break** | ~2 weeks | ~5 months (Tutte, Aug 1941 - Jan 1942) | Months (1942 onwards) |
| **Machine assistance** | Ericsson APP replicas (decryption only) | Colossus (key-finding) | None for key-finding |
| **Team size** | Beurling alone (initial break) | Team effort (Tiltman, Tutte, Turing, Flowers) | Team effort (Crum and others) |
| **Cipher complexity** | Higher (XOR + transposition) | Lower (XOR only, pure Vernam) | Higher (same as T52) |
| **Success duration** | June 1940 — May 1943 | 1942 — May 1945 | Limited, abandoned 1944 |
| **Messages read** | ~350,000 of ~500,000 intercepted | Thousands (high strategic value) | Far fewer ("far slimmer" results) |

#### How Cryptographers Compare the Difficulty

The T52 produced a **much more complex cipher than the Lorenz machine**. The key difference: the Lorenz was a pure Vernam XOR cipher, meaning that if you could find the key, you could directly XOR it with the ciphertext to get plaintext. The T52's addition of **conditional transposition** made this impossible — a crib on the T52 does not directly yield key material, requiring permutation analysis on top of the XOR attack.

However, the Lorenz was used on a far larger scale and carried far more strategically important traffic (Hitler's communications with his generals). The British devoted vastly more resources to Tunny because the intelligence payoff was enormous.

Beurling's achievement is often considered **more individually impressive** — one man, two weeks, pen and paper, against a more complex cipher — while the Tunny effort was a greater **institutional and technological** achievement, culminating in the invention of the electronic computer.

### Did the British Know About Beurling's Work?

**Yes.** The evidence strongly suggests Bletchley Park knew about Sweden's success **before** they began their own attack on the T52.

The key connection was **Colonel Ragnvald Alfred Roscher Lund**, Norway's military attaché in Stockholm and chief intelligence officer. Roscher Lund maintained close contacts with both Swedish and British intelligence:

- In **November 1941**, Roscher Lund explicitly informed a BP cryptanalyst (during a meeting at the Royal Automobile Club in London, arranged through Captain Howard) that *"the Germans were sending masses of messages to their troops in the north of Norway by teleprinter"* and that Ericsson had *"built a machine which decyphered these messages."*
- Roscher Lund was a close friend of **Yves Gyldén**, described as Scandinavia's (or Europe's) greatest cryptanalyst, and had extensive contacts with the Swedish and Finnish cipher bureaux.

Despite this knowledge, there is **no evidence of direct operational cooperation** between BP and FRA on the T52 during the war. The Swedish operation was run independently, and Sweden guarded its source jealously. Intelligence from the decrypts was shared with the Allies indirectly — reportedly through the **Polish resistance movement**.

Frode Weierud's review notes that Beurling broke the T52a/b in **June 1940**, while BP's first break of Lorenz SZ40 came in **January 1942** and their first break of Sturgeon (T52) not until **1942**. He concludes: *"It is probably safe to say that Sweden was the first ever to break modern, on-line teleprinter ciphers."*

- **Weierud, Frode. "Sweden: Cryptographic Superpower"**: [https://cryptocellar.org/pubs/beckrevw.pdf](https://cryptocellar.org/pubs/beckrevw.pdf). Accessed: 2026-04-03.
- **Rutherford Journal — "Bletchley Park's Sturgeon, the Fish that Laid No Eggs"**: [https://www.rutherfordjournal.org/article010106.html](https://www.rutherfordjournal.org/article010106.html). Accessed: 2026-04-03.

---

## 4. What the Decrypted Traffic Revealed

### Scale of the Intelligence Take

Between June 1940 and May 1943, Sweden intercepted approximately **500,000 German messages** and successfully decrypted approximately **350,000** (a remarkable 70% success rate). A figure of approximately **296,000** is given in some sources (this may reflect a different counting method or a subset of the traffic).

The traffic came from teleprinters connected to the various leased lines between Germany and Norway, Finland, and the German embassy in Stockholm. German briefings and compilations had **great intelligence value** for Sweden.

- **Wikipedia — National Defence Radio Establishment**: [https://en.wikipedia.org/wiki/National_Defence_Radio_Establishment](https://en.wikipedia.org/wiki/National_Defence_Radio_Establishment). Accessed: 2026-04-03.

### Operation Barbarossa

The most strategically significant intelligence derived from the Geheimschreiber decrypts was **advance knowledge of Operation Barbarossa** — the German invasion of the Soviet Union, launched on 22 June 1941.

The decrypted traffic revealed German army-level staff reports and troop deployments, including the massive eastward movement of forces. Sweden became **"the first nation, besides Germany, to possess information about the forthcoming German attack on the Soviet Union."**

#### Did Sweden Warn Stalin?

Sweden did pass warnings to the Soviet Union, but the Soviets **dismissed the information** because Sweden refused to disclose its intelligence source. This was one of over a hundred warnings Stalin received from various sources between January and June 1941 — all of which he rejected, believing them to be British provocations designed to draw the USSR into the war.

The Soviet ambassador in Stockholm was **Alexandra Kollontai**, one of the USSR's most experienced diplomats, but even she could not persuade Moscow to take the Swedish warnings seriously.

### Other Intelligence Gathered

The decrypted traffic provided Sweden with:
- **German military dispositions** in Norway and Finland — force strengths, deployments, and strategic intentions.
- **Diplomatic communications** between Berlin and the German embassy in Stockholm — giving Sweden insight into Germany's diplomatic strategy and its "red lines," helping Sweden calibrate its neutrality policy to avoid provoking an invasion.
- **Operational intelligence** about German military activities across Scandinavia.
- Knowledge of German military planning that **"helped keep Sweden out of the war"** by allowing Swedish leaders to understand precisely how far they could push back against German demands without triggering a military response.

### How Long Did Sweden Read the Traffic?

The timeline of Swedish access:

| Period | Status |
|--------|--------|
| **May-June 1940** | Beurling breaks T52a/b. Decryption begins. |
| **June 1940 — mid-1942** | Steady reading of T52a/b traffic. |
| **August 1941** | **First leak**: Courier Allan Emanuel Nyblad, recruited by the Soviet Union on ideological grounds, photographs decrypted messages while transporting them between Swedish military facilities. Discovered January 1942. |
| **June 1942** | **Second leak**: Finnish military attaché Colonel Stewen reveals Swedish codebreaking capability to the Germans. On 22 June 1942, Swedish Colonel Björnstjerna reports: *"The Germans have been warned by the Finns that we have succeeded in breaking their G-schreiber."* |
| **17 June 1942** | Germans initiate communications security upgrades. |
| **21 July 1942** | T52c ("Caesar") introduced. Swedish cryptanalysts break it by exploiting German reuse of older wheel components. |
| **October 1942** | Germans reroute some teleprinter traffic through non-Swedish cables. "Wahlwörter" (random word prefixes) implemented. |
| **April 1943** | Swedes break Lorenz SZ40 traffic on their cables. |
| **May 1943** | Radical keying procedure changes make T52 decryption nearly impossible. |
| **December 1943** | T52d introduced. The Swedes never break it. |
| **1943-1944** | T52d, T52e, and T52y appear. Intelligence capability significantly diminished. |

- **Ulfving/Weierud — "The Geheimschreiber Secret" (Source Exposure)**: [https://cryptocellar.org/Ulfving/node13.html](https://cryptocellar.org/Ulfving/node13.html). Accessed: 2026-04-03.
- **Hans Högman — Swedish Military Crypto Department**: [https://www.hhogman.se/crypto-dept.htm](https://www.hhogman.se/crypto-dept.htm). Accessed: 2026-04-03.

---

## 5. Assessments of Beurling's Achievement

### David Kahn (The Codebreakers, 1967)

The most widely cited assessment comes from **David Kahn**, the dean of cryptographic historians, in his landmark work *The Codebreakers: The Story of Secret Writing* (1967):

> **"Quite possibly the finest feat of cryptanalysis performed by the Swedes, and the most far-reaching, was Arne Beurling's solution of the German Siemens machine."**

This quote appears on p. 482 of the original 1967 edition and has been widely reproduced. Weierud's 1998 review in *Cryptologia* uses it as the opening line to frame the significance of Beurling's work.

- **Kahn, David. *The Codebreakers*. Macmillan, 1967.**
- **Weierud, Frode. "Sweden: Cryptographic Superpower." *Cryptologia* 22(1): 25-28, January 1998.**: [https://cryptocellar.org/pubs/beckrevw.pdf](https://cryptocellar.org/pubs/beckrevw.pdf). Accessed: 2026-04-03.

### Bengt Beckman (Codebreakers, 2002)

**Bengt Beckman**, former chief of FRA's cryptanalytical department, published *Codebreakers: Arne Beurling and the Swedish Crypto Program During World War II* (American Mathematical Society, 2002; English translation by Kjell-Ove Widman). The original Swedish edition, *Svenska kryptobedrifter*, was published in 1996.

Beckman's assessment:

> The cracking of the code from the Geheimschreiber device is **"every bit as impressive as the breaking of the Enigma code by the Poles and English."**

The book, based on extensive use of Swedish intelligence archives and interviews with participants, is the definitive account of the Swedish cryptanalytic effort. Weierud's review describes it as placing Sweden **"in the same league as the other cryptographic 'superpowers' at the time: Poland, England and USA."**

- **Beckman, Bengt. *Codebreakers: Arne Beurling and the Swedish Crypto Program During World War II*. American Mathematical Society, 2002. ISBN 0-8218-2889-4.**: [https://bookstore.ams.org/SWCRY](https://bookstore.ams.org/SWCRY). Accessed: 2026-04-03.
- **Amazon listing**: [https://www.amazon.com/Codebreakers-Beurling-Swedish-Crypto-Program/dp/0821828894](https://www.amazon.com/Codebreakers-Beurling-Swedish-Crypto-Program/dp/0821828894). Accessed: 2026-04-03.

### Friedrich Bauer (AMS Notices review, 2003)

Mathematician **Friedrich Bauer** reviewed Beckman's book for the *Notices of the American Mathematical Society* (August 2003) and described Beurling's solution of the Geheimschreiber as **"one of the most magnificent achievements of cryptanalysis of that time."**

- **Bauer, Friedrich. Review of *Codebreakers*. *Notices of the AMS*, 50(8), August 2003.**: [https://www.ams.org/notices/200308/rev-bauer.pdf](https://www.ams.org/notices/200308/rev-bauer.pdf). Accessed: 2026-04-03.

### Frode Weierud (Cryptologia, 1998)

Cryptographic historian **Frode Weierud** (CERN), in his review of Beckman's original Swedish edition for *Cryptologia*:

> "Arne Beurling was clearly a genius, just like Alan Turing, he worked from first principles, however the similarity ends there."

> "The Swedish cryptanalytical achievements are top class and therefore it is only appropriate to put Sweden in the same league as the other cryptographic 'superpowers' at the time: Poland, England and USA."

> "It is probably safe to say that Sweden was the first ever to break modern, on-line teleprinter ciphers."

Weierud also notes the remarkable fact that the Swedes went on to break the Lorenz SZ40 as well — *independently* of Bletchley Park.

### NSA Assessment

The U.S. National Security Agency's declassified **"Cryptologic Almanac"** includes an entry titled *"The Breaking of Geheimschreiber"* (DOCID: 3719064). This document acknowledges Beurling's achievement as a significant cryptanalytic milestone and provides the NSA's assessment of the technical details.

- **NSA. "The Breaking of Geheimschreiber." Cryptologic Almanac (50th Anniversary Series). Declassified.**: [https://www.nsa.gov/portals/75/documents/news-features/declassified-documents/crypto-almanac-50th/The_Breaking_of_Geheimschreiber.pdf](https://www.nsa.gov/portals/75/documents/news-features/declassified-documents/crypto-almanac-50th/The_Breaking_of_Geheimschreiber.pdf). Accessed: 2026-04-03.

### Uppsala University

Uppsala University, where Beurling held his professorship, describes his achievement as:

> "Using only teleprinter tapes and cipher text, he deciphered the code that the Germans believed impossible to crack — in two weeks."

And notes that his work was driven by **"intuition, feeling and aesthetics"** rather than purely logical methods.

- **Uppsala University — Arne Beurling**: [https://www.uu.se/en/about-uu/history/prominent-people/arne-beurling](https://www.uu.se/en/about-uu/history/prominent-people/arne-beurling). Accessed: 2026-04-03.

### IVA Memorial (2022)

The Royal Swedish Academy of Engineering Sciences (IVA) published a memorial to Beurling in 2022, describing how he "performed the ingenious feat of solving the G-writer's encryption so that Sweden could stay informed of Germany's activities and plans during three years of the Second World War."

- **IVA. "Arne Beurling Memorial." 2022.**: [https://www.iva.se/contentassets/e8436f25872e4bca8be92207871a0456/ivas-minnesskrift-2022-arne-beurling.pdf](https://www.iva.se/contentassets/e8436f25872e4bca8be92207871a0456/ivas-minnesskrift-2022-arne-beurling.pdf). Accessed: 2026-04-03.

### Comparison with Tutte's Recognition

Bill Tutte's deduction of the Lorenz machine structure was described, when he was inducted as Officer of the Order of Canada in October 2001, as *"one of the greatest intellectual feats of World War II."*

Both Beurling (T52, 1940) and Tutte (Lorenz, 1941-42) performed extraordinary individual intellectual achievements — deducing the workings of complex cipher machines they had never seen, from intercepted traffic alone. The key difference: Tutte's work was followed by the massive institutional effort of Colossus; Beurling's achievement remained a solo performance, and Sweden automated only the decryption (not the key-finding).

---

## 6. Post-War Legacy

### Post-War Use of the T52

After the war, the T52 attracted interest from multiple nations:
- **Norway**: Modified approximately 50 T52d and T52e machines left behind by the Germans. Used by the Norwegian Security Police and Intelligence Service for internal communications (from 1946 onwards, under Captain Nils Stordahl).
- **France**: Acquired over 235 units (1949-1953) for military communications.
- **Netherlands**: The Dutch Navy employed T52 machines in the 1950s.
- **East Germany**: Explored manufacturing T52e machines, though success is undocumented.

This sustained post-war interest suggests American and British cryptanalytic organizations remained concerned about T52 security implications — and also that the machine, when properly used, was considered cryptographically strong.

### Swedish-Norwegian Intelligence Cooperation

At the beginning of 1946, Sweden and Norway began a close intelligence cooperation that continued into the 1960s. Norway intercepted Russian military radio traffic and telegram traffic; Sweden provided most of the cryptanalytical work — drawing on the expertise built up during the Geheimschreiber era.

### Operation Stella Polaris (1944)

In September 1944, Sweden received the **complete Finnish cryptographic and signals intelligence organization** — 750 people (staff and families) plus 700 crates of equipment. This "Operation Stella Polaris" brought Finnish expertise in Russian cryptosystems to Sweden, though the expected continued intelligence cooperation largely failed to materialize. FRA purchased technical material for 252,875 Swedish kronor and employed about 15 Finnish cryptographers.

---

## Complete Source List

### Primary Sources and Key References

1. **Beckman, Bengt.** *Codebreakers: Arne Beurling and the Swedish Crypto Program During World War II.* American Mathematical Society, 2002. ISBN 0-8218-2889-4. [https://bookstore.ams.org/SWCRY](https://bookstore.ams.org/SWCRY). Accessed: 2026-04-03.

2. **Kahn, David.** *The Codebreakers: The Comprehensive History of Secret Communication from Ancient Times to the Internet.* Macmillan, 1967 (revised edition Scribner, 1996). ISBN 0-684-83130-9.

3. **NSA.** "The Breaking of Geheimschreiber." Cryptologic Almanac (50th Anniversary Series). DOCID: 3719064. Declassified. [https://www.nsa.gov/portals/75/documents/news-features/declassified-documents/crypto-almanac-50th/The_Breaking_of_Geheimschreiber.pdf](https://www.nsa.gov/portals/75/documents/news-features/declassified-documents/crypto-almanac-50th/The_Breaking_of_Geheimschreiber.pdf). Accessed: 2026-04-03.

4. **Ulfving, Lars (trans. Weierud, Frode).** "The Geheimschreiber Secret: Arne Beurling and the Success of Swedish Signals Intelligence." (Originally published 1992; English translation 1997.) [https://cryptocellar.org/Ulfving/ulfving.html](https://cryptocellar.org/Ulfving/ulfving.html). Accessed: 2026-04-03.

5. **Weierud, Frode.** "Sweden: Cryptographic Superpower — A Book Review." *Cryptologia* 22(1): 25-28, January 1998. [https://cryptocellar.org/pubs/beckrevw.pdf](https://cryptocellar.org/pubs/beckrevw.pdf). Accessed: 2026-04-03.

### Encyclopedia and Reference Articles

6. **Wikipedia.** "Siemens and Halske T52." [https://en.wikipedia.org/wiki/Siemens_and_Halske_T52](https://en.wikipedia.org/wiki/Siemens_and_Halske_T52). Accessed: 2026-04-03.

7. **Wikipedia.** "Arne Beurling." [https://en.wikipedia.org/wiki/Arne_Beurling](https://en.wikipedia.org/wiki/Arne_Beurling). Accessed: 2026-04-03.

8. **Wikipedia.** "National Defence Radio Establishment." [https://en.wikipedia.org/wiki/National_Defence_Radio_Establishment](https://en.wikipedia.org/wiki/National_Defence_Radio_Establishment). Accessed: 2026-04-03.

9. **Wikipedia.** "Sweden during World War II." [https://en.wikipedia.org/wiki/Sweden_during_World_War_II](https://en.wikipedia.org/wiki/Sweden_during_World_War_II). Accessed: 2026-04-03.

10. **Wikipedia.** "Fish (cryptography)." [https://en.wikipedia.org/wiki/Fish_(cryptography)](https://en.wikipedia.org/wiki/Fish_(cryptography)). Accessed: 2026-04-03.

11. **Wikipedia.** "Lorenz cipher." [https://en.wikipedia.org/wiki/Lorenz_cipher](https://en.wikipedia.org/wiki/Lorenz_cipher). Accessed: 2026-04-03.

12. **Wikipedia.** "Cryptanalysis of the Lorenz cipher." [https://en.wikipedia.org/wiki/Cryptanalysis_of_the_Lorenz_cipher](https://en.wikipedia.org/wiki/Cryptanalysis_of_the_Lorenz_cipher). Accessed: 2026-04-03.

### Specialist Articles and Reviews

13. **Rutherford Journal.** "Bletchley Park's Sturgeon, the Fish that Laid No Eggs." [https://www.rutherfordjournal.org/article010106.html](https://www.rutherfordjournal.org/article010106.html). Accessed: 2026-04-03.

14. **jproc.ca.** "Sturgeon." [http://jproc.ca/crypto/sturg.html](http://jproc.ca/crypto/sturg.html). Accessed: 2026-04-03.

15. **Hans Högman.** "Swedish Military — Crypto Department." [https://www.hhogman.se/crypto-dept.htm](https://www.hhogman.se/crypto-dept.htm). Accessed: 2026-04-03.

16. **Uppsala University.** "Arne Beurling." [https://www.uu.se/en/about-uu/history/prominent-people/arne-beurling](https://www.uu.se/en/about-uu/history/prominent-people/arne-beurling). Accessed: 2026-04-03.

17. **IVA (Royal Swedish Academy of Engineering Sciences).** "Arne Beurling Memorial." 2022. [https://www.iva.se/contentassets/e8436f25872e4bca8be92207871a0456/ivas-minnesskrift-2022-arne-beurling.pdf](https://www.iva.se/contentassets/e8436f25872e4bca8be92207871a0456/ivas-minnesskrift-2022-arne-beurling.pdf). Accessed: 2026-04-03.

18. **Ulfving/Weierud.** "What happened later? When and how was the unique source exposed?" [https://cryptocellar.org/Ulfving/node13.html](https://cryptocellar.org/Ulfving/node13.html). Accessed: 2026-04-03.

19. **Ulfving/Weierud.** "Breaking of the German encrypted telex traffic." [https://cryptocellar.org/Ulfving/node4.html](https://cryptocellar.org/Ulfving/node4.html). Accessed: 2026-04-03.

20. **Bauer, Friedrich.** Review of *Codebreakers*. *Notices of the AMS* 50(8), August 2003. [https://www.ams.org/notices/200308/rev-bauer.pdf](https://www.ams.org/notices/200308/rev-bauer.pdf). Accessed: 2026-04-03.

### Academic and Springer References

21. **Ulfving, Lars.** "The Geheimschreiber Secret." In *Coding Theory and Cryptography*. Springer, 2000. [https://link.springer.com/chapter/10.1007/978-3-642-59663-6_5](https://link.springer.com/chapter/10.1007/978-3-642-59663-6_5). Accessed: 2026-04-03.

22. **"Sturgeon, The FISH BP Never Really Caught."** SpringerLink. [https://link.springer.com/chapter/10.1007/978-3-642-59663-6_3](https://link.springer.com/chapter/10.1007/978-3-642-59663-6_3). Accessed: 2026-04-03.

23. **Science Museum Group Collection.** "Siemens and Halske T52e Cipher Machine, 1940s." [https://collection.sciencemuseumgroup.org.uk/objects/co60815/siemens-and-halske-t52e-cipher-machine-1940s](https://collection.sciencemuseumgroup.org.uk/objects/co60815/siemens-and-halske-t52e-cipher-machine-1940s). Accessed: 2026-04-03.

### Machine Learning / Modern Analysis

24. **KTH Thesis (2019).** "Decyphering the Geheimschreiber, a Machine Learning Approach." DiVA Portal. [https://www.diva-portal.org/smash/get/diva2:1337816/FULLTEXT01.pdf](https://www.diva-portal.org/smash/get/diva2:1337816/FULLTEXT01.pdf). Accessed: 2026-04-03.

25. **Kopal, Nils.** "Invited Talk: Special Session on Arne Beurling — Modern Codebreaking of T52." 2018. [https://ep.liu.se/ecp/149/006/ecp18149006.pdf](https://ep.liu.se/ecp/149/006/ecp18149006.pdf). Accessed: 2026-04-03.
