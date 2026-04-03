---
layout: single
title: "The Magician Who Told No Secrets"
date: 2026-04-04 08:00:00 +0100
categories: [Weather, HPC, History]
tags: [Beurling, Cryptography, Sweden, FRA, BESK, Enigma, Poland, Geheimschreiber]
header:
  teaser: /assets/images/header-cyclone.jpg
  overlay_image: /assets/images/header-cyclone.jpg
  overlay_filter: "0.6"
excerpt: "In 1940, a Swedish mathematician cracked the German Geheimschreiber cipher in two weeks with pen and paper. When asked how, he replied: 'A magician does not reveal his secrets.' His work created the agency that made BESK its most urgent customer."
---

[Yesterday](/weather/hpc/history/2026/04/03/The-swedes-got-there-first.html) I told you about BESK — the bitter schnapps computer that ran the world's first operational weather forecasts. I told you that FRA, Sweden's signals intelligence agency, was BESK's most urgent customer, running classified cryptanalysis sessions every night while meteorologists and aircraft engineers used the machine by day.

But I didn't tell you **why** FRA existed in the first place.

This is the story of the man who created the need for Swedish code-breaking computers — and who did it with nothing but a pencil.

### The Son of a Sea Captain

![Arne Beurling in the 1940s — around the time of his cryptanalytic triumph. Photo: TT News Agency, public domain.](/assets/images/Beurling_1940s.jpg)

**Arne Carl-August Beurling** was born on 3 February 1905 in Gothenburg, Sweden. His father, Konrad Beurling, was a sea captain. His mother, Baroness Elsa Raab, came from Swedish nobility. From his father, Arne inherited an explosive temperament, a love of hunting and sailing, and an absolute refusal to explain himself to anyone.

His great-grandfather, Pehr Henrik Beurling, had founded a prestigious clock factory in Stockholm in 1783. Precision instruments ran in the blood.

Beurling studied mathematics at Uppsala University. His doctoral thesis was delayed by **five years** because his father took him on a hunting expedition to South America before he could finish it. When he finally submitted it in 1933, it became "one of the most influential mathematical publications of its time."

His approach to mathematics was unlike anyone else's. Colleagues noted that "he had a dimension to his thinking that was not logical but guided by intuition, feeling and aesthetics." For Beurling, "the world of mathematics seemed to be integrated with the real world and with life itself."

He was charismatic, generous with his friends, and loyal to a fault. He was also, by all accounts, impossible. He had "no sense for public relations" and an explosive temperament that could fill a room with debris — intellectual or otherwise. He did not publish his results until every detail was perfect, which meant that much of his work was never published during his lifetime. Paradoxically, "his readiness to share his ideas was unselfish in the extreme" — he would talk freely about his mathematics with anyone who cared to listen. He just wouldn't write it down.

A magician, in other words. In every sense.

### The Machine Nobody Could Read

In April 1940, Germany invaded Norway. Suddenly, German military communications between Norway and Berlin needed to travel through cables on **Swedish territory**. The traffic was encrypted using the **Siemens & Halske T52**, known as the **Geheimschreiber** — the "secret writer."

![A Siemens T-52D Geheimschreiber on display at the National Cryptologic Museum, Fort Meade — on loan from the Swedish government. This is the type of machine Beurling broke with pen and paper. Public domain.](/assets/images/Geheimschreiber_T52D_NSA.jpg)

The T52 was not the Enigma. It was **worse**.

The Enigma was a portable, manual cipher machine — an operator typed a letter, a lamp lit up, you wrote down the encrypted letter. Three or four rotors, a plugboard. Complex, but fundamentally a souped-up substitution cipher.

The T52 was an **online teleprinter cipher**. It encrypted messages automatically during transmission at roughly 66 words per minute. It used **ten cipher wheels** (not three), each with a different coprime number of pins (from 47 to 73), creating a keyspace of approximately 10^18 combinations per wheel setting — and roughly **10^27** total possible configurations. The encryption operated in two stages: first an XOR substitution, then a conditional transposition of bit pairs controlled by a plugboard. This two-stage process meant that even knowing the plaintext didn't directly reveal the key.

The British codenamed it **"Sturgeon."** Bletchley Park would struggle with it for years.

The Germans considered it unbreakable.

### Two Weeks, One Pencil

In the summer of 1940, Sweden's Defence Cryptography Agency recruited Beurling. He was a professor of mathematics at Uppsala. He was 35 years old.

They gave him intercepted teleprinter tapes — nothing but streams of cipher text. No captured machine. No documentation. No "cribs" (known plaintext). Just encrypted noise on paper tape.

As a warm-up, Beurling had already cracked the **Hagelin B-21** cipher — a different machine — over a weekend. FRA knew what he could do.

The first intercepted T52 traffic arrived on **25 May 1940**. Beurling sat down with the tapes and a pencil. By **27 May**, he had verified his first results.

**Two weeks later, he had reverse-engineered the entire machine** — deduced the internal wiring, the wheel structure, the encryption process — and could read the German traffic.

Alone. With pen and paper. In two weeks.

David Kahn, the dean of cryptographic historians, called it **"quite possibly the finest feat of cryptanalysis"** performed by the Swedes. Friedrich Bauer called it **"one of the most magnificent achievements of cryptanalysis."** Bengt Beckman, later head of FRA's cryptanalytical section, wrote that it was **"every bit as impressive as the breaking of the Enigma code."**

And here's the comparison that matters: at Bletchley Park, cracking the related **Lorenz SZ40/42** cipher (codenamed "Tunny") required a team of brilliant mathematicians working for months, plus the construction of **Colossus** — the world's first programmable electronic computer. Bill Tutte performed the theoretical break; Tommy Flowers built the machine to make it operational. It was a monumental team effort across years.

Beurling did something comparable. Alone. In a fortnight. With a pencil.

![The Lorenz SZ42 on display at Bletchley Park — the Geheimschreiber's more complex cousin. Breaking Tunny required building Colossus, the world's first programmable electronic computer. Beurling broke the T52 with pen and paper. Photo: Matt Crypto, public domain.](/assets/images/Lorenz_SZ42.jpg)

### "A Magician Does Not Reveal His Secrets"

In later years, when colleagues and historians asked Beurling how he had accomplished the feat, he gave his legendary reply:

> **"A magician does not reveal his secrets."**

He never explained his method. Not in writing, not in conversation, not on his deathbed. His approach apparently combined linguistic analysis (identifying high-frequency German words in the underlying plaintext) with systematic mathematical hypothesis testing, guided by what colleagues described as "an almost preternatural intuition."

He took the secret to his grave.

### 350 000 Messages

Beurling's breakthrough was not a one-time curiosity. It opened a floodgate.

Between June 1940 and late 1943, Sweden's signals intelligence operation read approximately **350 000 of 500 000** intercepted German messages. Swedish authorities gained advance knowledge of **Operation Barbarossa** — the German invasion of the Soviet Union in June 1941 — before it happened. They monitored German troop movements through Scandinavia. The intelligence helped Sweden maintain its precarious neutrality.

FRA — the Försvarets radioanstalt, formally established in 1942 — built on Beurling's work. They constructed **Ericsson APP machines** to automate the decryption process. And when the T52 was upgraded to more secure versions (the T52c, T52ca, T52d), Swedish cryptanalysts — building on Beurling's foundation — cracked several of these too. In **April 1943**, FRA even broke the **Lorenz SZ40** — the same family of cipher that Bletchley Park needed Colossus to crack.

The secret eventually leaked through two channels — a Soviet agent named Allan Nyblad, and a Finnish colonel named Stewen who told the Germans. FRA intercepted a German message that read, with chilling clarity: **"These messages are decrypted in Sweden."** By late 1943, the Germans had changed their methods and the window closed.

But Beurling himself was not there to see the end of it. In spring 1942, his explosive temperament caught up with him. Conflicts with FRA management led to his dismissal from the code-breaking effort. The magician was shown the door.

### The Poles Who Did It First

Beurling was not the first mathematician to break an "unbreakable" cipher with a pencil. Eight years before his triumph, three Polish mathematicians at the Biuro Szyfrów (Cipher Bureau) in Warsaw had done something even more extraordinary.

In **December 1932**, **Marian Rejewski** — a 27-year-old from Bydgoszcz — cracked the German military Enigma. He applied **permutation group theory** to cryptanalysis, the first time anyone had used pure mathematics for code-breaking. Together with **Jerzy Różycki** and **Henryk Zygalski**, he read German Enigma traffic through most of the 1930s. They built the **bomba kryptologiczna** — the first electromechanical cryptanalytic machine in history — and in **July 1939**, five weeks before Germany invaded their country, they handed everything to the British and French at a secret meeting in the Pyry forest near Warsaw. Turing's Bombe was directly inspired by the Polish bomba.

The Biuro Szyfrów made one revolutionary decision that enabled all of this: they recruited **mathematicians** from Poznań University rather than linguists. Every code-breaking bureau in the world hired language experts. The Poles hired mathematicians. That single choice changed the course of the war.

The parallels with Beurling are haunting. Small countries. Pure mathematics. Pencils before machines. And both stories were buried for decades — overshadowed by Bletchley Park, which got all the credit.

But that is a story that deserves its own post. The Polish codebreakers — Rejewski, Różycki, Zygalski — and the price they paid for being right too early and too quietly. That one is personal for me. It's coming.

### From Ciphers to Computers

After his dismissal from FRA, Beurling continued his mathematical career at Uppsala. In 1948-49 he was a visiting professor at Harvard. Then, in 1954, the Institute for Advanced Study at Princeton offered him a permanent professorship.

He accepted. He moved to New Jersey. And eventually, he moved into **Albert Einstein's former office — Room 115**.

Think about that for a moment. The man who cracked the Geheimschreiber with a pencil, sitting in the office where Einstein had worked out general relativity. Two minds that saw the world differently from everyone else, separated by a generation, connected by a room.

Beurling remained at Princeton until his death on 20 November 1986. His most famous student, **Lennart Carleson**, won the **Abel Prize** in 2006. Carleson said: **"It was my great fortune to have been introduced to mathematics by Arne Beurling."**

Beurling's closest friend was **Lars Ahlfors**, the Finnish Fields Medal winner. When Ahlfors was in financial difficulty, Beurling arranged a position for him at Uppsala. Ahlfors had been forced to **pawn his Fields Medal** — as Ahlfors himself later said, **"I'm sure that it's the only Fields Medal that has been in a pawn shop."** With the salary Beurling arranged, he was able to recover it. At Beurling's memorial, Ahlfors opened with: **"Arne Beurling was the best friend I ever had."**

### The Thread to BESK

And here is where the story connects back to [yesterday's post](/weather/hpc/history/2026/04/03/The-swedes-got-there-first.html).

Beurling's wartime code-breaking created FRA. FRA needed computing power for continued cryptanalysis after the war. FRA became the most urgent institutional customer driving the creation of BARK and then **BESK**. Stig Comet — who was simultaneously BESK project leader and FRA bureau chief — personally ran the nightly code-breaking sessions on BESK under the strictest secrecy.

And BESK, running during the daytime, produced the world's first operational numerical weather forecasts.

The chain runs: **Beurling's pencil → FRA → BESK → the weather.**

A mathematician who cracked ciphers with intuition and aesthetics created the institutional demand for the computer that predicted the weather. He never touched BESK himself — by 1954 he was at Princeton, in Einstein's office. But without his two weeks in 1940, Sweden might not have built the machine at all.

### The Magician's Grave

![Memorial to Arne Beurling in Uppsala. Photo: Joshua06, CC BY-SA 4.0.](/assets/images/Beurling_memorial_Uppsala.jpg)

Beurling died in Princeton in 1986. He was buried at Norra begravningsplatsen in Solna, Sweden — home. His unpublished mathematical works were collected and published posthumously by Carleson and others in 1989.

There is a memorial to him in Uppsala. There is a short opera about him (*Krypto CEG*, 2005). Bengt Beckman, the former head of FRA's cryptanalytical section, told the full story in his 2002 book *Codebreakers: Arne Beurling and the Swedish Crypto Program During World War II*.

But mostly, there is silence. The magician does not reveal his secrets. And the world has mostly not asked.

Some magicians are forgotten. Some are remembered too late. And some — like Beurling — changed the world with a pencil and were thanked with silence.

In Poland, three other magicians are waiting for their story to be told properly. Soon.

---

### References

**Beurling:**
* Beckman, B. (2002). *Codebreakers: Arne Beurling and the Swedish Crypto Program During World War II*. AMS. [Bookstore](https://bookstore.ams.org/SWCRY)
* Ahlfors, L. & Carleson, L. (1988). Arne Beurling in memoriam. *Acta Mathematica*, 161. [PDF](https://projecteuclid.org/journals/acta-mathematica/volume-161/issue-none/Arne-Beurling-in-memoriam/10.1007/BF02392292.pdf)
* Uppsala University. [Arne Beurling](https://www.uu.se/en/about-uu/history/prominent-people/arne-beurling)
* Institute for Advanced Study. [Arne K. Beurling](https://www.ias.edu/scholars/arne-k-beurling)
* IVA. Arne Beurling memorial publication (2022). [PDF](https://www.iva.se/contentassets/e8436f25872e4bca8be92207871a0456/ivas-minnesskrift-2022-arne-beurling.pdf)

**Geheimschreiber:**
* Kahn, D. (1996). *The Codebreakers* (revised ed.). Scribner.
* Bauer, F. L. (2003). Review of *Codebreakers*. *Notices of the AMS*. [PDF](https://www.ams.org/notices/200308/rev-bauer.pdf)
* Weierud, F. [Rebirth of a Sturgeon](https://www.rutherfordjournal.org/article010106.html). *Rutherford Journal*.
* Crypto Museum. [Siemens T52e Technical Description](https://www.cryptomuseum.com/crypto/siemens/t52/files/T52e_TechDesc_EN.pdf)
* Wikipedia. [Siemens and Halske T52](https://en.wikipedia.org/wiki/Siemens_and_Halske_T52)

**Polish Codebreakers:**
* Rejewski, M. (1981). How Polish Mathematicians Deciphered the Enigma. *IEEE Annals of the History of Computing*, 3(3), 213-234.
* Kozaczuk, W. (1984). *Enigma: How the German Machine Cipher Was Broken, and How It Was Read by the Allies in World War Two*. University Publications of America.
* Singh, S. (1999). *The Code Book*. Fourth Estate. (Chapter on Polish contribution.)
* Hodges, A. (1983). *Alan Turing: The Enigma*. Simon & Schuster. (Turing's acknowledgment of Polish work.)
* JSTOR Daily. [The Polish Codebreakers Who Cracked the Enigma Machine](https://daily.jstor.org/the-codebreakers-who-saved-the-world/)
* Enigma Cipher Centre, Poznań. [centrum-szyfrów.pl](https://centrum-szyfrow.pl/en/)

**Image Credits:**
* Beurling portrait (1940s): TT News Agency. Public domain in Sweden. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Arne_Beurling,_foto_TT_1940-tal.jpg)
* Geheimschreiber T-52D: National Cryptologic Museum, on loan from Sweden. Public domain. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:STURGEON.jpg)
* Lorenz SZ42: Matt Crypto, Bletchley Park. Public domain. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Lorenz-SZ42-2.jpg)
* Beurling memorial, Uppsala: Joshua06. CC BY-SA 4.0. [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Arne_Beurling_Uppsala_maj_2019_cropped.jpg)

---

**Current status:**
- The Geheimschreiber: Cracked in two weeks. With a pencil. By one man.
- The Enigma: Cracked by three Polish mathematicians in 1932. That story is coming.
- Bletchley Park: Built Colossus and the Bombe. Got all the credit. As usual.
- The magician: Died in Einstein's office. Room 115. Still not explaining how he did it.
- My cluster: Still can't crack anything. But it runs weather models. And that's Beurling's fault too.

Yours Truly
