# Arne Beurling -- Additional In-Depth Research

This file supplements `Beurling.md` with deeper material for a blog post where Beurling is the sole protagonist.

---

## 1. The Geheimschreiber Decryption Story -- Full Detail

### 1.1 The Siemens & Halske T52: What It Was and How It Worked

The T52, codenamed "Sturgeon" by British cryptanalysts, was an online cipher teleprinter manufactured by Siemens & Halske for high-level German military and diplomatic communications. Unlike the portable Enigma (used by field units), the T52 was a heavy fixed-circuit machine used by the Luftwaffe, the German Navy, and diplomatic services over landline and cable connections.

**Technical mechanism:**
- The machine processed characters as five parallel bits in Baudot code.
- It employed **ten pinwheels** of coprime sizes: 73, 71, 69, 67, 65, 64, 61, 59, 53, and 47. The cam patterns on these wheels could not be modified by the operator.
- Each of the five plaintext bits was XORed with the XOR sum of three taps from the pinwheels.
- Additionally, cyclically adjacent pairs of plaintext bits were swapped (or not) according to XOR sums of three different output bits.
- A plugboard allowed selection of which triplets of wheels controlled each XOR or swap operation.
- The pinwheels were stepped in a complex nonlinear way based on positions from various relays in the past, but arranged so they could never stall.
- This produced "a much more complex cipher than the Lorenz machine" and means the T52 was "not just a pseudorandom number generator-and-XOR cipher."

**Key space:** The ten wheels permitted approximately **893,622,318,929,520,960** different key configurations -- nearly one quintillion. For comparison, the military Enigma had roughly 158,962,555,217,826,360,000 settings (159 quintillion), but the Enigma's effective keyspace was much smaller because large portions could be eliminated through known structural weaknesses. The T52's multi-layered XOR-plus-swap architecture made it qualitatively harder to attack.

**Variants (mostly incompatible with each other):**
- **T52a/T52b** -- differed only in electrical noise suppression; both cryptologically weak
- **T52c** -- also cryptologically weak
- **T52d/T52e** -- more advanced; wheel movement was intermittent, controlled by logic circuits taking input from the wheels themselves. These eliminated "conceptual flaws, including very subtle ones" from earlier models.

Sources:
- Siemens and Halske T52, Wikipedia. https://en.wikipedia.org/wiki/Siemens_and_Halske_T52 Accessed: 2026-04-03
- "The Siemens and Halske Geheimschreiber T-52." http://www.quadibloc.com/crypto/te0302.htm Accessed: 2026-04-03
- Cryptomuseum, T52e Technical Description. https://www.cryptomuseum.com/crypto/siemens/t52/files/T52e_TechDesc_EN.pdf Accessed: 2026-04-03

### 1.2 The Timeline: From Intercepted Tape to Broken Cipher

**Background:** After Germany occupied Denmark and Norway in April 1940, German military communications between Berlin, Oslo, and German forces in Finland and Norway began passing through Swedish telegraph cables. The Swedes tapped the line.

**Key dates:**
- **25 May 1940:** The first 24-hour batch of intercepted T52 cipher traffic is collected and handed to Beurling.
- **27 May 1940:** Beurling verifies his initial assumptions against a second day of intercepted traffic.
- **Approximately two weeks from late May 1940:** Beurling reconstructs the complete cipher principles of the T52a/b, working from only cipher text on teleprinter tapes -- no plaintext, no captured machine, no documentation.
- **Autumn 1940:** Using Beurling's reconstruction, engineer Vigo Lindstein of LM Ericsson builds analogue decoding machines (essentially reverse-engineered T52s). These are installed at Karlaplan 4 in Stockholm, connected to teleprinters. Young women type intercepted ciphertext into the machines, which output German plaintext.
- **June 1940 -- late 1943:** Sweden continuously deciphers German traffic. At the peak (late 1942 -- early 1943), around 175 persons work on T52 traffic at FRA, nearly half the agency's workforce.
- **Total haul:** Sweden intercepted **500,000** German messages and successfully decrypted **350,000** of them over three years. Peak daily output reached 678 decrypted messages in a single day (October 1943).

Sources:
- Hans Hogman, "Swedish Military Cryptanalysis 1939-1945." https://www.hhogman.se/crypto-dept.htm Accessed: 2026-04-03
- "Arne Beurling," Cryptocellar. https://cryptocellar.org/Ulfving/node8.html Accessed: 2026-04-03

### 1.3 What Did He Have to Work With?

Beurling had **only** intercepted teleprinter tapes containing raw cipher text. He had:
- **No access to the machine** itself
- **No plaintext** cribs or known-plaintext pairs
- **No documentation** about the T52's design
- **No information** about the cipher mechanism's construction

He worked with **pen and paper** only. His method apparently involved:
- Identifying high-frequency and unusually long words in hypothesized German plaintext (classical frequency analysis)
- Forming hypotheses about the machine's internal structure
- Creating formulas and tables to test hypotheses against multiple messages
- Exploiting German operator errors -- operators frequently reused encryption key settings due to high message volume and time pressure, creating "depths" (multiple messages enciphered with identical settings)

Carl Gosta Borelius, who later worked at FRA and studied under Beurling at Uppsala, produced a reconstruction of Beurling's likely methodology. Borelius noted that Beurling used "threes and fives in the text" as structural markers to find weaknesses in the German remote printer system.

Sources:
- Carl-Gosta Borelius, Wikipedia. https://en.wikipedia.org/wiki/Carl-G%C3%B6sta_Borelius Accessed: 2026-04-03
- "Arne Beurling," Cryptocellar. https://cryptocellar.org/Ulfving/node8.html Accessed: 2026-04-03

### 1.4 "Two Weeks with Pen and Paper" -- Is This Verified?

The "two weeks" claim comes from multiple independent sources:
- **Bengt Beckman** -- former head of FRA's cryptanalysis department, who had access to FRA archives and interviewed surviving participants. His 2002 book *Codebreakers* (AMS) documents this timeline.
- **David Kahn** -- the foremost historian of cryptography, who called it "quite possibly the finest feat of cryptanalysis performed during the Second World War" in his classic *The Codebreakers* (1967).
- **The NSA** -- a declassified NSA Cryptologic Almanac document titled "The Breaking of Geheimschreiber" confirms the timeline.
- **Uppsala University** and **MacTutor History of Mathematics** both cite the two-week timeframe independently.
- **The intercepted traffic dates** (25 May first batch, 27 May verification) provide an objective lower bound. The reconstruction was complete by mid-June 1940.

The specific methods, however, remain unverified because Beurling refused to explain them. As Beckman wrote: "That secret Arne Beurling took with him to the grave."

Sources:
- Bengt Beckman, *Codebreakers: Arne Beurling and the Swedish Crypto Program During World War II*, AMS, 2002. https://bookstore.ams.org/SWCRY Accessed: 2026-04-03
- NSA, "The Breaking of Geheimschreiber." https://www.nsa.gov/portals/75/documents/news-features/declassified-documents/crypto-almanac-50th/The_Breaking_of_Geheimschreiber.pdf Accessed: 2026-04-03

### 1.5 What the Decrypted Traffic Revealed: Operation Barbarossa

From late 1940 through late 1943, Sweden could read 80-95% of all messages sent between Norway and Germany, including army-level staff reports, troop deployments, and strategic planning.

**Operation Barbarossa (June 1941):**
- In the spring of 1941, Sweden became **the first nation besides Germany** to possess intelligence about the planned invasion of the Soviet Union.
- In mid-June 1941, information about the coming German attack was leaked from Sweden to Great Britain through the Swedish naval attache.
- Britain passed the warning to the Soviet Union.
- However, Stalin and Soviet officials dismissed the warning, partly because the source could not be revealed without compromising Swedish signals intelligence.

Sources:
- Hans Hogman, "Swedish Military Cryptanalysis 1939-1945." https://www.hhogman.se/crypto-dept.htm Accessed: 2026-04-03
- Cryptocellar, "What happened later?" https://cryptocellar.org/Ulfving/node13.html Accessed: 2026-04-03

### 1.6 How the Source Was Exposed

**First leak -- Soviet espionage (August 1941):** Allan Emanuel Nyblad, a courier transporting decrypted messages between Karlaplan 4 and the military headquarters at Gra Huset, had been recruited as a Soviet agent on ideological grounds. He photographed messages during his regular route and passed them to Soviet representatives. His espionage was discovered in January 1942.

**Second and decisive leak -- Finnish channel (June 1942):** Colonel Stewen, the Finnish military attache in Stockholm, was given access to Swedish intelligence. After Finland allied with Germany in 1941, the Finns revealed to the Germans that Sweden had broken their ciphers. On 22 June 1942, Colonel Carl Bjornstjerna wrote: "The Germans have been warned by the Finns that we have succeeded in breaking their G-schreiber."

**The intercepted warning message:** On approximately 17 June 1942, the Swedes decrypted a German message that read: **"These messages are decrypted in Sweden."** Immediately after this, all German transmissions became unreadable due to enhanced security measures.

**German countermeasures:**
- **21 July 1942:** Introduction of the T52c ("Caesar") machine
- **October 1942:** Introduction of randomly chosen key words ("Wahlworter") and rerouting of traffic through Danish-Norwegian and Finnish-Baltic cables
- **1942:** Swedish cryptanalysts defeated the T52c security improvements
- **May 1943:** Radical keying changes made codebreaking nearly impossible, ending sustained decryption
- **1944:** Machines T52d, T52e, and a mysterious "Y-machine" appeared; none could be broken

Sources:
- Cryptocellar, "What happened later?" https://cryptocellar.org/Ulfving/node13.html Accessed: 2026-04-03

### 1.7 How FRA Used Beurling's Results

Swedish intelligence built an entire operational infrastructure around Beurling's breakthrough:
- **LM Ericsson** (specifically its subsidiary, Svenska Kassaregisteraktiebolaget -- the Swedish Cash Register Company) manufactured analogue T52 machines in great secrecy, designed by engineer Vigo Lindstein based on Beurling's reverse engineering.
- The machines were installed at Karlaplan 4, the crypto department's facility in central Stockholm. Operators typed intercepted ciphertext into teleprinters connected to the analogue machines.
- In 1940, operations expanded to villas at **Elfviks Udde on Lidingo island**, with additional collection sites established across Sweden.
- On 1 July 1942, the independent government agency **Forsvarsvasendets radioanstalt** (later FRA -- Forsvarets Radioanstalt) was formally established under the Swedish Ministry of Defence. Naval officer **Torgil Thoren** (1892-1982) served as FRA's first head from 1942 to 1957.
- In October 1943, FRA relocated to a secret facility at **Lovon**, approximately 15 km from Stockholm.

Sources:
- Hans Hogman, "Swedish Military Cryptanalysis 1939-1945." https://www.hhogman.se/crypto-dept.htm Accessed: 2026-04-03
- Siemens and Halske T52, Wikipedia. https://en.wikipedia.org/wiki/Siemens_and_Halske_T52 Accessed: 2026-04-03

### 1.8 Comparison with Bletchley Park and Turing

**The British struggle with T52 traffic:**
- Bletchley Park first detected T52 traffic in the summer and autumn of 1942 on a link between Sicily and Libya, codenamed "Sturgeon."
- Mathematician Michael Crum analysed operator depths (multiple messages with identical settings).
- Bletchley "broke into Sturgeon, although they did not break it as regularly as they broke Enigma or Tunny [Lorenz]."
- A key reason: "the T52 was by far the most complex cipher of the three."
- The Luftwaffe often retransmitted Sturgeon messages using weaker ciphers, reducing the urgency to attack the T52 directly.

**Key comparative points:**
- Beurling worked **alone**; Bletchley Park employed thousands.
- Beurling had **no captured machine or documentation**; the Poles had provided Bletchley with reconstructed Enigma machines before the war.
- Beurling used **only pen and paper**; Bletchley used bombes, Colossus, and extensive mechanical aids.
- Beurling completed his work in **two weeks**; Enigma decryption was an ongoing multi-year effort.
- The British themselves acknowledged the T52 was harder than Enigma.

**David Kahn's verdict:** "Quite possibly the finest feat of cryptanalysis performed during the Second World War."

An alternative formulation attributed to Kahn: "Perhaps the greatest triumph of cryptanalysis done during World War II was Arne Beurling's solution of the Geheimschreiber secret."

Sources:
- Siemens and Halske T52, Wikipedia. https://en.wikipedia.org/wiki/Siemens_and_Halske_T52 Accessed: 2026-04-03
- MacTutor, Arne Beurling biography. https://mathshistory.st-andrews.ac.uk/Biographies/Beurling/ Accessed: 2026-04-03

### 1.9 "A Magician Does Not Reveal His Secrets" -- Context

The exact quote is: **"A magician does not reveal his secrets."** (Variants: "A magician does not reveal his tricks.")

**Context:** When asked after the war to explain his cryptanalytic methods, Beurling consistently refused. The quote appears in Beckman's *Codebreakers* (2002) and is the canonical source. The refusal was not a single incident but a lifelong posture -- Beurling never explained his methods to anyone, including his students and colleagues at FRA.

**Lennart Carleson's elaboration:** "He took pride in presenting his results so that the way he discovered them was completely hidden. 'A magician does not reveal his tricks,' he used to say." This applied not only to his cryptanalysis but to his mathematics generally -- Beurling habitually polished proofs to conceal the path of discovery.

Sources:
- MacTutor, Arne Beurling biography. https://mathshistory.st-andrews.ac.uk/Biographies/Beurling/ Accessed: 2026-04-03
- Bengt Beckman, *Codebreakers*, AMS, 2002. https://bookstore.ams.org/SWCRY Accessed: 2026-04-03

---

## 2. Personality and Anecdotes

### 2.1 The Explosive Temperament

Beurling inherited his temperament from his father **Konrad Beurling** (1872-1959), a sea captain described as "a small hot-tempered man who often used to dress in knickerbockers." It was said that "when he fell out with someone he would tell them about the people he had shot."

Beurling's own temper was legendary. His success at Crypto Detail IV "created friction within the department" and his "hot temper" led to his **dismissal in the spring of 1942** -- ironically, the man who had achieved the greatest Swedish intelligence triumph of the war was fired for being too difficult to work with. He returned to his professorship at Uppsala.

### 2.2 The Hunting Expedition That Delayed a Thesis

Beurling proved the **Denjoy conjecture** (concerning asymptotic values of entire functions of finite order) in **1929**, while hunting alligators in Panama with his father. However, the combination of this South American expedition and his compulsory military service (1930-31) delayed his doctoral thesis by approximately five years.

During this delay, **Lars Ahlfors** independently proved the same conjecture and published first, receiving his doctorate earlier. Ahlfors later wrote: "Neither could I have known that Arne Beurling had found a different proof in 1929 while hunting alligators in Panama."

Despite this, Beurling's doctoral thesis of 1933 (*Etudes sur un probleme de majoration*) was immediately recognized as far more than a proof of one conjecture. Ahlfors and Carleson described it as "not a mere collection of interesting results, but...one of the most influential mathematical publications in recent times."

Sources:
- MacTutor, Arne Beurling biography. https://mathshistory.st-andrews.ac.uk/Biographies/Beurling/ Accessed: 2026-04-03

### 2.3 The Ahlfors Friendship: Fields Medal in a Pawn Shop

The friendship between Beurling and **Lars Ahlfors** (1907-1996) is one of the great mathematical friendships of the 20th century. Key moments:

**First meeting:** 1934, at the Scandinavian Congress of Mathematicians in Stockholm. Both were unmarried at the time.

**The pawn shop incident (1944):** When Ahlfors fled Finland during WWII, Finnish exit regulations permitted him to take only ten Swedish crowns -- not enough for train fare from Stockholm to Kungsbacka on the west coast, where his family waited. In desperation, Ahlfors pawned his **Fields Medal** (one of the first two ever awarded, in 1936). In his own words: "I smuggled out my Fields Medal, and I pawned it in the pawn shop and got enough money. I had no other way..." He added: "I'm sure that it's the only Fields Medal that has been in a pawn shop."

**Beurling's rescue:** Beurling immediately arranged a position for Ahlfors at Uppsala, providing him with housing, office space, and teaching duties. Once Ahlfors began receiving his Uppsala salary, he was able to reclaim the medal from the pawn shop. Ahlfors wrote: "I am forever indebted to Arne Beurling, who showed what true friendship can be."

**The death of Christoffer Ahlfors:** While in Sweden, Ahlfors' young son Christoffer died of an electric shock while playing at home. Ahlfors was on a lecture visit to Uppsala and heard the traumatic news first from Beurling. He later wrote: "Never in my life have I witnessed anybody handle such a difficult assignment with greater tact and compassion. It seemed to me that Arne's extraordinary sensitivity had raised our friendship to a level that I had not experienced before, and from that moment on, I have come to regard Arne as the personification of what true friendship can be."

**Forty years later:** When Beurling died in 1986, Ahlfors opened his eulogy at Princeton with the words: **"Arne Beurling was the best friend I ever had."**

**Ahlfors' final assessment:** "There was a streak of genius in everything he did."

Sources:
- "The Amazing Journey of Lars Ahlfors' Fields Medal." https://arxiv.org/html/2506.12850v5 Accessed: 2026-04-03
- "Ahlfors and Beurling," Yet Another Mathblog. https://yetanothermathblog.com/2012/07/28/ahlfors-and-beurling-14/ Accessed: 2026-04-03
- MacTutor, Arne Beurling biography. https://mathshistory.st-andrews.ac.uk/Biographies/Beurling/ Accessed: 2026-04-03

### 2.4 Early Cryptanalytic Feats: The Hagelin B-21

During his compulsory military service (1930-31), Beurling took a course in cryptology and cryptanalysis taught by **Captain Erik Anderberg**. Anderberg showed Beurling the **Hagelin B-21** -- a cipher machine newly purchased by the Swedish military, constructed by the Swedish inventor Boris Hagelin.

Anderberg encouraged Beurling to take the machine home over the weekend. After finding a weakness, Beurling asked Anderberg for a ciphertext containing "a not-too-short probable word." Anderberg enciphered a message starting with the word **overbefalhavaren** (Swedish for "supreme commander"). Beurling returned and showed the fully deciphered text to the astonished Anderberg. This incident made Anderberg remember Beurling's name, which later led to his recruitment for wartime cryptanalysis.

Before tackling the Geheimschreiber, Beurling also helped break **Soviet codes** prior to the Winter War (November 1939), enabling Sweden to provide Finland with valuable intelligence. He also decrypted several encrypted Czech telegrams despite not knowing the Czech language.

Sources:
- MacTutor, Arne Beurling biography. https://mathshistory.st-andrews.ac.uk/Biographies/Beurling/ Accessed: 2026-04-03
- Hans Hogman, "Swedish Military Cryptanalysis 1939-1945." https://www.hhogman.se/crypto-dept.htm Accessed: 2026-04-03

### 2.5 Secrecy About Methods

Beurling's secrecy was not limited to cryptanalysis. **Lennart Carleson** described his mathematical approach: "Beurling had a complicated and passionate relationship to mathematics...Only pure, beautiful theories were accepted: he had something of an artist's attitude when gauging his own work, and that of others. He took pride in presenting his results so that the way he discovered them was completely hidden."

He published selectively and "only when all details were resolved." This meant that much of his work was never published during his lifetime. Paradoxically, "his readiness to share his ideas was unselfish in the extreme" -- he would freely discuss his work with colleagues, simply declining to write it down until it met his exacting standards.

### 2.6 Work Habits and the Walking Mathematician

Carleson described Beurling's seminars at Uppsala as taking place **"every second Tuesday, 6-8 pm"** where Beurling "discussed only his own work."

Beurling's neighbours could observe his deep concentration: they would tell how "he walked back and forth...sometimes stopped!" -- the stopping being the alarming part, as it suggested he was so deep in thought that even his habitual pacing had frozen.

**John Wermer** (a Harvard mathematician) wrote that Beurling's lectures at Harvard (1948-49) were "like nothing else...Everything based on his own results." On one occasion, Beurling exclaimed to the Harvard students: **"You Harvard men seem to be afraid of integral signs."**

Sources:
- MacTutor, Arne Beurling biography. https://mathshistory.st-andrews.ac.uk/Biographies/Beurling/ Accessed: 2026-04-03

### 2.7 The Domar Assessment

**Yngve Domar**, one of Beurling's students in the 1940s, said: "If the label of genius is to be put on anybody, then the right thing is to put it on Beurling...He never based his results on what others did, but attacked new problems with fresh methods."

### 2.8 Why He Left Sweden

Beurling was unhappy at Uppsala. His girlfriend **Annette-Marie Yxkull** wrote to Ahlfors explaining the depth of Beurling's unhappiness. Ahlfors acted quickly, arranging a visiting position for Beurling at Harvard (1948-49). Before emigrating permanently, Beurling was offered the directorship of the **Mittag-Leffler Institute** -- Sweden's premier mathematical research centre -- but turned it down.

In 1954 he left Sweden permanently for the Institute for Advanced Study in Princeton, "no doubt with Ahlfors' strong recommendation."

Sources:
- "Ahlfors and Beurling," Yet Another Mathblog. https://yetanothermathblog.com/2012/07/28/ahlfors-and-beurling-14/ Accessed: 2026-04-03

---

## 3. Mathematical Contributions -- Detail

### 3.1 The Doctoral Thesis (1933): Extremal Length and the Denjoy Conjecture

Beurling's thesis *Etudes sur un probleme de majoration* introduced the concept of **extremal length** (later developed jointly with Ahlfors). A key result was his estimate for harmonic measure: if omega is harmonic measure and lambda is the extremal distance between a set and the boundary, then omega is bounded by exp(-pi * lambda). These inequalities were strong enough to yield a proof of the Denjoy conjecture independently of Ahlfors' earlier proof.

The Denjoy conjecture (1907): if an entire function has at least 2k distinct finite asymptotic values, its order must be at least k.

### 3.2 Beurling's Theorem on Invariant Subspaces (1949)

Published in "On two problems concerning linear transformations in Hilbert spaces," *Acta Mathematica* 81 (1949), pp. 239-255.

Beurling characterised the closed shift-invariant subspaces of the **Hardy space H^2** on the unit disc. Every such subspace has the form **uH^2** where u is an **inner function** (a bounded analytic function on the disc with boundary values of modulus 1 almost everywhere). This introduced the fundamental inner/outer factorization of Hardy space functions.

This result is considered one of the most influential theorems in 20th-century functional analysis and operator theory. It was later generalised by P. Lax to the vector-valued case (the **Beurling-Lax theorem**) and by H. Helson, D. Lowdenslager, and J. Wermer to broader settings.

Source:
- Beurling-Lax theorem, Encyclopedia of Mathematics. https://encyclopediaofmath.org/wiki/Beurling-Lax_theorem Accessed: 2026-04-03

### 3.3 Beurling Generalized Primes and the Beurling Zeta Function (1937)

Beurling introduced **generalized primes** as any increasing sequence of real numbers greater than 1, and defined **generalized integers** as products of these. The associated **Beurling zeta function** generalises the Riemann zeta function. He proved a generalized prime number theorem: if the counting function N(x) of generalized integers satisfies N(x) = Ax + O(x log^{-gamma} x) with gamma > 3/2, then the number of generalized primes less than x is asymptotic to x/log(x), just as for ordinary primes. He showed that if gamma = 3/2, this conclusion need not hold.

This work opened an entire subfield of analytic number theory that remains active to this day.

Source:
- Beurling zeta function, Wikipedia. https://en.wikipedia.org/wiki/Beurling_zeta_function Accessed: 2026-04-03

### 3.4 The Beurling-Malliavin Theorem (1961, published 1967)

In collaboration with **Paul Malliavin** at Princeton during the academic year 1960-61, Beurling solved two hard related problems: the characterisation of entire functions that can be written as quotients of two bounded entire functions of exponential type, and the computation of the "totality radius" of a given sequence.

**Malliavin** described their working methods: "We devoted half of the academic year 1960-1961 to this problem; very often I stayed at Beurling's house for a full night of cooperative work." Karin Beurling prepared meals during these marathon sessions. The results were known by 1961 but the final version was not completed until autumn 1966 and published in *Acta Mathematica* in 1967 ("On the closure of characters and the zeros of entire functions").

The **Beurling-Malliavin multiplier theorem** has been called "one of the most celebrated results of 20th-century one-dimensional harmonic analysis." It was later used by Bourgain and Dyatlov in the proof of the Fractal Uncertainty Principle.

Sources:
- MacTutor, Arne Beurling biography. https://mathshistory.st-andrews.ac.uk/Biographies/Beurling/ Accessed: 2026-04-03
- "The Beurling and Malliavin Theorem in several dimensions." https://arxiv.org/html/2306.12397v2 Accessed: 2026-04-03

### 3.5 Dirichlet Spaces and Potential Theory (with Deny, 1958-59)

Around 1959, Beurling and **Jacques Deny** introduced the theory of **Dirichlet spaces** -- an axiomatic framework for potential theory based on the Dirichlet integral. Beurling discovered that the essential property of the "Dirichlet norm" being diminished by normal contractions yields "very short and elegant demonstrations of fundamental results in potential theory" and leads to "profound theorems of spectral synthesis in harmonic analysis."

This axiomatic approach became one of the foundational frameworks of modern abstract potential theory.

Source:
- IAS Scholars page. https://www.ias.edu/scholars/arne-k-beurling Accessed: 2026-04-03

### 3.6 Quasiconformal Mappings (with Ahlfors, 1956)

In their joint paper "The boundary correspondence under quasi-conformal mappings" (*Acta Mathematica* 96, 1956), Beurling and Ahlfors established fundamental results on boundary values of quasiconformal mappings. Ahlfors stated that "the decisive idea was entirely due to Beurling."

### 3.7 Malliavin's Paradox

Paul Malliavin offered a reflection on Beurling's mathematical legacy: though Beurling always started with "hard concrete problems" and sought "elementary and transparent" proofs, he ultimately became "the key initiator of important theories" -- his search for simplicity repeatedly uncovered "basic general principles of universal applicability."

### 3.8 The Collected Works

Beurling's published output was small relative to his influence because of his perfectionism. After his death, the **Collected Works of Arne Beurling** was published by Birkhauser in 1989, in two volumes (Complex Analysis and Harmonic Analysis), edited by **Lennart Carleson, Paul Malliavin, John Neuberger, and John Wermer**. Much of the material had never been published during Beurling's lifetime.

Source:
- Collected Works of Arne Beurling, Springer. https://link.springer.com/book/9780817634124 Accessed: 2026-04-03

---

## 4. The FRA and BESK Connection

### 4.1 From Beurling to FRA

Beurling's wartime codebreaking created the institutional foundation for Swedish signals intelligence:
- His work at **Crypto Detail IV** (Kryptodetalj IV, established 1939 under commander **Sven Hallenborg** with ~50 employees) demonstrated Sweden's capacity for advanced signals intelligence.
- On 1 July 1942, this work was formalised into the independent agency FRA (Forsvarsvasendets radioanstalt, later Forsvarets Radioanstalt).
- Beurling himself was dismissed from the crypto department in spring 1942 due to personality conflicts, but his methods and the infrastructure he enabled continued operating.

### 4.2 FRA and BESK

After the war, FRA became one of the earliest and most important users of Swedish electronic computers:
- In 1953, FRA gained access to **BESK** (Binar Elektronisk SekvensKalkylator), Sweden's first electronic computer.
- **"During the nights Swedish National Defence Radio Establishment (FRA) used BESK for cracking encryption of radio messages"** (by Per-Erik Persson et al.).
- **Carl Gosta Borelius** -- who had studied mathematics under Beurling at Uppsala in 1940 and was placed at FRA's crypto department with Beurling's approval -- became one of the early users of both BARK and BESK at FRA. He later became head of FRA's data centre.

### 4.3 Beurling's Personal Connection to BESK

There is no evidence that Beurling ever used BESK himself. He had left Sweden for Princeton in 1954, just as BESK was becoming operational. The connection was purely institutional: Beurling's wartime work created FRA, and FRA became BESK's most important classified customer.

However, Beurling's years at the Institute for Advanced Study in Princeton (from 1952 as a member, from 1954 as faculty) overlapped exactly with von Neumann's Electronic Computer Project at the same institution. The IAS computer was the architectural ancestor of BESK -- Swedish engineers Carl-Erik Froberg and Erik Stemme had visited Princeton in 1947-48 to learn the design.

Sources:
- BESK, Wikipedia. https://en.wikipedia.org/wiki/BESK Accessed: 2026-04-03
- Carl-Gosta Borelius, Wikipedia. https://en.wikipedia.org/wiki/Carl-G%C3%B6sta_Borelius Accessed: 2026-04-03
- National Defence Radio Establishment, Wikipedia. https://en.wikipedia.org/wiki/National_Defence_Radio_Establishment Accessed: 2026-04-03

---

## 5. Princeton Years (1954-1986)

### 5.1 How He Got There

The path from Uppsala to Princeton was facilitated by Ahlfors:
1. Beurling's girlfriend Annette-Marie Yxkull wrote to Ahlfors about Beurling's unhappiness at Uppsala.
2. Ahlfors arranged a visiting position at Harvard (1948-49).
3. Beurling spent 1952-54 as a Member at the IAS School of Mathematics.
4. In September 1954, he was appointed to the permanent Faculty.
5. Before leaving Sweden, he declined the directorship of the Mittag-Leffler Institute.

### 5.2 Einstein's Office

In **1965**, Beurling was given **Albert Einstein's office, No. 115**, at the Institute for Advanced Study. Einstein had died in 1955. This was considered "a distinction granted very few people." Beurling occupied this office until his retirement.

Note: Some sources say he was given Einstein's office when he arrived in 1954, but the more precise dating (1965) comes from the Cryptocellar source based on Swedish research.

Sources:
- "Arne Beurling," Cryptocellar. https://cryptocellar.org/Ulfving/node8.html Accessed: 2026-04-03

### 5.3 Work at the Institute

At the IAS, Beurling continued his research in harmonic analysis, complex analysis, and potential theory. He was not known to have continued cryptographic work at Princeton.

Specific institutional roles:
- **Faculty member**, School of Mathematics: September 1954 -- June 1973
- **School Secretary** (Executive Officer), School of Mathematics: 1965-1966
- Organised the **Harmonic Analysis program** at IAS (1966-67)
- **Professor Emeritus**: September 1973 -- November 1986

Other emeritus mathematicians overlapping with Beurling at IAS included **Kurt Godel** (emeritus 1976) and **Andre Weil** (emeritus 1976).

### 5.4 Karin Beurling at Princeton

Beurling's second wife Karin Lindblad Beurling (1920-2006) worked in a **biochemistry laboratory at Princeton University** during their Princeton years. Malliavin described her as "a former distinguished PhD student at Uppsala University, where she had been president of the association of graduate students." During his collaborative sessions with Beurling, "Karin prepared meals" during their all-night working sessions.

### 5.5 Archival Papers

The **Arne Beurling papers** are preserved at the Shelby White and Leon Levy Archives Center of the Institute for Advanced Study, Princeton. They consist of administrative files documenting his work as Member and Faculty, arranged chronologically and covering 1955-1971. The collection is open for research access.

Source:
- IAS Archives. https://archives.ias.edu/repositories/2/resources/43 Accessed: 2026-04-03

### 5.6 Later Years and Death

Beurling retired in 1973 and remained at Princeton as professor emeritus. He died on **20 November 1986**, aged 81, in Princeton, New Jersey. His body was returned to Sweden for burial at **Norra begravningsplatsen** in Solna, near Stockholm -- the same cemetery where many notable Swedes are interred.

### 5.7 Personal Tragedy

Beurling's son from his first marriage, **Pehr-Henrik Konrad Beurling** (born 11 December 1936), died on **26 April 1962** at age 25. The circumstances are not detailed in available sources. His daughter from his first marriage, Christina (born 1938), survived him.

---

## 6. The Book by Bengt Beckman

### 6.1 Publication Details

**Title:** *Codebreakers: Arne Beurling and the Swedish Crypto Program During World War II*
**Author:** Bengt Beckman
**Translator:** Kjell-Ove Widman
**Publisher:** American Mathematical Society (AMS)
**Year:** 2002 (English translation; Swedish original published earlier)
**ISBN:** 978-0-8218-2889-2

### 6.2 About the Author

Bengt Beckman was **for many years the head of the cryptanalysis department of the Swedish signal intelligence agency** (FRA). He had direct access to FRA archives and interviewed many surviving participants in the wartime intelligence effort.

### 6.3 AMS Book Description

"One of the greatest accomplishments in the history of cryptography occurred in 1940 when a Swedish mathematician broke the German code used for strategic military communications. This story has all the elements of a classic thriller: a desperate wartime situation; a moody and secretive mathematical genius with a talent for cryptography; and a stunning mathematical feat, mysterious to this day."

### 6.4 Review by F.L. Bauer (Notices of the AMS, August 2003)

"This is an unforgettable book, even for those not addicted to cryptology."

F.L. Bauer praised Beckman for producing "a well-written, fascinating book showing the mathematician Arne Beurling...as well as the part-time cryptologist Beurling in the depressing atmosphere in Sweden during the Second World War."

### 6.5 EMS Review

The European Mathematical Society also reviewed the book favourably, noting Beckman's unique insider access to FRA's archives.

Sources:
- AMS Bookstore. https://bookstore.ams.org/SWCRY Accessed: 2026-04-03
- Goodreads reviews. https://www.goodreads.com/book/show/199401.Codebreakers Accessed: 2026-04-03

---

## 7. Lennart Carleson -- The Student Who Inherited the Tradition

### 7.1 The Mentor-Student Relationship

Lennart Carleson received his Ph.D. from Uppsala University in 1950, supervised by Beurling. His thesis was "On a Class of Meromorphic Functions and Its Exceptional Sets."

Carleson described the relationship: "It was my great fortune to have been introduced to mathematics by Arne Beurling; the tradition he, T. Carleman and Marcel Riesz initiated is very obviously responsible for the good standard of mathematics in our country. Personally I am very happy for this opportunity to express to Arne Beurling my gratitude for having guided me into a fruitful area of mathematics and for having given an example that only hard problems count."

### 7.2 Carleson's Abel Prize (2006)

Carleson was awarded the Abel Prize in 2006 "for his profound and seminal contributions to harmonic analysis and the theory of smooth dynamical systems." His work was a direct continuation of the tradition Beurling established.

### 7.3 Preserving Beurling's Legacy

Carleson, together with Malliavin, Neuberger, and Wermer, collected and published Beurling's unpublished works posthumously in the 1989 *Collected Works* -- an act of filial devotion to a teacher who had published too little during his lifetime.

Source:
- "Interview with Abel Prize Recipient Lennart Carleson," AMS Notices. https://www.ams.org/notices/200702/comm-carleson.pdf Accessed: 2026-04-03

---

## 8. Other Notable Details

### 8.1 First President of the Swedish Mathematical Society

Beurling served as the **first president of the Swedish Mathematical Society**.

### 8.2 The Opera: Krypto CEG

The 2005 short opera **"Krypto CEG"** (music by Jonas Sjostrand, libretto by Kimmo Eriksson) dramatises Beurling's cryptanalytic achievement.

### 8.3 Breaking Soviet Codes Before the Winter War

Before his famous Geheimschreiber work, Beurling helped break Soviet coded messages "just before the Soviet invasion of Finland in November 1939 (The Winter War)." At the outbreak of WWII in 1939, Beurling contacted **Captain Eskil Gester** at Military Intelligence's Cryptography Department and offered his services. He was immediately hired and given a position with signals collection at a secret address near **Karlaplan** in Stockholm.

### 8.4 Family Heritage: The Clockmaker

Beurling's great-grandfather **Pehr Henrik Beurling** (1758 or 1763-1806) founded a renowned clock factory in Stockholm in 1783, producing high-quality timepieces. Examples of "Beurling Stockholm" clocks still appear at auction.

### 8.5 The IAS Photograph

The IAS archives hold a photograph of Beurling at a blackboard, as well as a portrait photograph. A separate archival photograph shows "Christina and Karin Beurling, daughter and wife of Arne Beurling" at the Institute.

Sources:
- IAS Albert Digital Archive: https://albert.ias.edu/entities/archivalmaterial/da1c7c15-7853-4fd8-88f3-2b528c91fa05 (blackboard photo). Accessed: 2026-04-03
- IAS Albert Digital Archive: https://albert.ias.edu/entities/archivalmaterial/6aacb042-2f13-446a-82b2-c92efbdf5ad0 (Christina and Karin). Accessed: 2026-04-03

---

## 9. Collected Quotes

### By Beurling
- **"A magician does not reveal his secrets."** -- When asked about his cryptanalytic methods. (Beckman, *Codebreakers*, 2002)
- **"A magician does not reveal his tricks."** -- Variant, per Carleson, about concealing the path of mathematical discovery. (MacTutor)
- **"You Harvard men seem to be afraid of integral signs."** -- To students at Harvard, 1948-49. (John Wermer, via MacTutor)

### About Beurling
- **"Arne Beurling was the best friend I ever had."** -- Lars Ahlfors, opening his eulogy at Princeton, 1986.
- **"There was a streak of genius in everything he did."** -- Lars Ahlfors, in the Collected Works (1989).
- **"Never in my life have I witnessed anybody handle such a difficult assignment with greater tact and compassion."** -- Lars Ahlfors, on Beurling delivering the news of Christoffer's death.
- **"I am forever indebted to Arne Beurling, who showed what true friendship can be."** -- Lars Ahlfors.
- **"Quite possibly the finest feat of cryptanalysis performed during the Second World War."** -- David Kahn, *The Codebreakers* (1967).
- **"If the label of genius is to be put on anybody, then the right thing is to put it on Beurling...He never based his results on what others did, but attacked new problems with fresh methods."** -- Yngve Domar.
- **"Beurling had a complicated and passionate relationship to mathematics...Only pure, beautiful theories were accepted."** -- Lennart Carleson.
- **"It was my great fortune to have been introduced to mathematics by Arne Beurling...only hard problems count."** -- Lennart Carleson.
- **"Not a mere collection of interesting results, but...one of the most influential mathematical publications in recent times."** -- Ahlfors and Carleson, on Beurling's doctoral thesis.
- **"This is an unforgettable book, even for those not addicted to cryptology."** -- F.L. Bauer, reviewing Beckman's *Codebreakers* (Notices of the AMS, 2003).

---

## 10. Sources Master List

1. Arne Beurling, Wikipedia. https://en.wikipedia.org/wiki/Arne_Beurling Accessed: 2026-04-03
2. "Arne Beurling," MacTutor History of Mathematics. https://mathshistory.st-andrews.ac.uk/Biographies/Beurling/ Accessed: 2026-04-03
3. "Arne Beurling," Department of Mathematics, Uppsala University. https://www.uu.se/en/department/mathematics/about-us/department-history/arne-beurling Accessed: 2026-04-03
4. "Arne Beurling," Uppsala University prominent people. https://www.uu.se/en/about-uu/history/prominent-people/arne-beurling Accessed: 2026-04-03
5. Arne K. Beurling, Scholars, Institute for Advanced Study. https://www.ias.edu/scholars/arne-k-beurling Accessed: 2026-04-03
6. IAS Archives, Arne Beurling papers. https://archives.ias.edu/repositories/2/resources/43 Accessed: 2026-04-03
7. Siemens and Halske T52, Wikipedia. https://en.wikipedia.org/wiki/Siemens_and_Halske_T52 Accessed: 2026-04-03
8. Hans Hogman, "Swedish Military Cryptanalysis 1939-1945." https://www.hhogman.se/crypto-dept.htm Accessed: 2026-04-03
9. "Arne Beurling," Cryptocellar (Lars Ulfving). https://cryptocellar.org/Ulfving/node8.html Accessed: 2026-04-03
10. "What happened later? When and how was the unique source exposed?" Cryptocellar. https://cryptocellar.org/Ulfving/node13.html Accessed: 2026-04-03
11. "The Amazing Journey of Lars Ahlfors' Fields Medal," arXiv. https://arxiv.org/html/2506.12850v5 Accessed: 2026-04-03
12. "Ahlfors and Beurling," Yet Another Mathblog. https://yetanothermathblog.com/2012/07/28/ahlfors-and-beurling-14/ Accessed: 2026-04-03
13. Bengt Beckman, *Codebreakers: Arne Beurling and the Swedish Crypto Program During World War II*, AMS, 2002. https://bookstore.ams.org/SWCRY Accessed: 2026-04-03
14. David Kahn, *The Codebreakers: The Story of Secret Writing*, 1967/1996.
15. NSA, "The Breaking of Geheimschreiber," Cryptologic Almanac. https://www.nsa.gov/portals/75/documents/news-features/declassified-documents/crypto-almanac-50th/The_Breaking_of_Geheimschreiber.pdf Accessed: 2026-04-03
16. Carl-Gosta Borelius, Wikipedia. https://en.wikipedia.org/wiki/Carl-G%C3%B6sta_Borelius Accessed: 2026-04-03
17. National Defence Radio Establishment, Wikipedia. https://en.wikipedia.org/wiki/National_Defence_Radio_Establishment Accessed: 2026-04-03
18. BESK, Wikipedia. https://en.wikipedia.org/wiki/BESK Accessed: 2026-04-03
19. Beurling-Lax theorem, Encyclopedia of Mathematics. https://encyclopediaofmath.org/wiki/Beurling-Lax_theorem Accessed: 2026-04-03
20. Beurling zeta function, Wikipedia. https://en.wikipedia.org/wiki/Beurling_zeta_function Accessed: 2026-04-03
21. "Interview with Abel Prize Recipient Lennart Carleson," *Notices of the AMS*. https://www.ams.org/notices/200702/comm-carleson.pdf Accessed: 2026-04-03
22. Collected Works of Arne Beurling, Springer. https://link.springer.com/book/9780817634124 Accessed: 2026-04-03
23. Goodreads, *Codebreakers* reviews. https://www.goodreads.com/book/show/199401.Codebreakers Accessed: 2026-04-03
24. IVA (Royal Swedish Academy of Engineering Sciences), memorial publication (2022, PDF). https://www.iva.se/contentassets/e8436f25872e4bca8be92207871a0456/ivas-minnesskrift-2022-arne-beurling.pdf Accessed: 2026-04-03
25. "The Beurling and Malliavin Theorem in several dimensions," arXiv. https://arxiv.org/html/2306.12397v2 Accessed: 2026-04-03
