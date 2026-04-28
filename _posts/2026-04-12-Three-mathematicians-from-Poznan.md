---
layout: single
title: "Three Mathematicians from Poznan"
date: 2026-04-12 08:00:00 +0100
categories: [Weather, HPC, History]
tags: [Enigma, Rejewski, Rozycki, Zygalski, Codebreakers, Poland, Turing, BletchleyPark, Computing]
header:
  teaser: /assets/images/header-enigma.jpg
  overlay_image: /assets/images/header-enigma.jpg
  overlay_filter: "0.6"
excerpt: "In 1932, a 27-year-old Polish mathematician cracked the German Enigma cipher using abstract algebra. He and two colleagues handed their secrets to the British five weeks before the invasion. Their contribution was suppressed for forty years. This story is personal."
---

This post is personal.

For thirteen posts I have been telling you about the machines that predicted the weather. About [Richardson](/weather/hpc/history/2026/03/24/The-man-who-forecasted-weather-with-a-pencil.html) and his pile of hay. About [ENIAC](/weather/hpc/history/2026/04/02/From-cables-to-chaos.html) and its 17 468 vacuum tubes. About [von Neumann's blueprint](/weather/hpc/history/2026/04/08/The-blueprint-von-Neumann-gave-away.html) and the machines that copied it. About a [Swedish magician](/weather/hpc/history/2026/04/04/The-magician-who-told-no-secrets.html) who cracked a German cipher with a pencil and a few sheets of paper, and how that act of genius led to BESK and the [world's first weather forecasts](/weather/hpc/history/2026/04/03/The-swedes-got-there-first.html).

But the same mathematics that predicted the weather also cracked codes. And the same machines that ran weather forecasts were born from the effort to break ciphers. [Charney's](/weather/hpc/history/2026/03/29/The-man-who-tamed-the-equations.html) quasi-geostrophic filtering and [Rejewski's](#marian-rejewski-19051980) permutation group theory are the same act: a mathematician applying abstract formalism to a problem everyone else said was impossible. Beurling cracked the Geheimschreiber in Stockholm; his work created FRA, which built BESK, which ran the world's first weather forecasts. At Bletchley Park, Colossus cracked the Lorenz SZ42 -- a machine from the same family as the Geheimschreiber. The people who built Colossus went on to build the Manchester Mark 1 and the Ferranti machines. Von Neumann, who had advised on both the ENIAC and the IAS machine, had one foot in weapons physics and the other in weather.

Computing, weather, and codebreaking are not three stories. They are one story, told in three voices.

Today: the Polish voice. And I will tell you now that I am Polish, and this story belongs to my people, and what was done to them -- what was hidden for forty years -- is something I take personally.

---

## The Cipher

The **Enigma** was an electromechanical cipher machine that looked like a typewriter in a wooden box. You pressed a key, electric current flowed through a **plugboard** (which swapped pairs of letters), then through three (later four) rotating **wheels** that substituted each letter, then through a **reflector** that sent the current back through the wheels along a different path, and finally through the plugboard again. A lamp lit up showing the enciphered letter. Each key press advanced the rightmost wheel by one position, changing the substitution for the next letter. The number of possible configurations was astronomical -- on the order of 10^23 for the three-rotor military Enigma.

![A military Enigma I machine with its plugboard cables visible at the front. The three rotors sit under the lid. Each rotor contained 26 contacts, and the plugboard added another layer of substitution. Photo: Museo Scienza e Tecnologia, Milan, via Wikimedia Commons (CC BY-SA 4.0).](/assets/images/Enigma_machine.jpg)

The German military adopted Enigma in the late 1920s, believing it was unbreakable. Most Western cryptanalysts agreed. The machine was too complex, the keyspace too vast, the daily settings too ephemeral. Even if you cracked today's key, tomorrow's was completely different.

The Poles disagreed.

---

## Marian Rejewski (1905-1980)

![Marian Rejewski in 1932, the year he cracked Enigma. He was 27 years old. Public domain.](/assets/images/Rejewski_portrait.jpg)

**Marian Adam Rejewski** was born on August 16, 1905, in Bromberg, Prussia -- now Bydgoszcz, Poland. His father Jozef was a tobacco merchant. His excellent German, a legacy of growing up in a formerly Prussian city, would prove useful.

He studied mathematics at the University of Poznan, attending a secret cryptology course organized by the Polish Cipher Bureau in January 1929. His classmates included two other young mathematicians: **Jerzy Rozycki** and **Henryk Zygalski**. After a year at the University of Gottingen -- then the world centre of mathematics -- Rejewski returned to Poznan and joined the Cipher Bureau's "Black Chamber" part-time.

On September 1, 1932, he began working full-time at the **Biuro Szyfrow** (Cipher Bureau) in Warsaw, under Captain Maksymilian Ciezki. Ciezki gave Rejewski a task that no one else had been able to solve: crack the German military Enigma I cipher.

Rejewski was 27 years old. He worked alone. And he had an idea no cryptanalyst had ever tried before.

### The Theorem That Won the War

The insight was mathematical. Rejewski realized that the Enigma's substitution could be described as a **permutation** -- a mathematical function that rearranges the 26 letters of the alphabet. The daily key settings determined which permutation the machine applied at each step. The plugboard, which swapped pairs of letters, was another permutation. And permutations obey the laws of **group theory**.

The critical observation: when you conjugate a permutation by another permutation -- wrap it inside and its inverse -- the **cycle structure is preserved**. The cycle lengths of XYX^{-1} are the same as the cycle lengths of Y, regardless of what X is. And the plugboard acted as exactly this kind of conjugating permutation.

This meant that the cycle structure of the rotor permutations was **invariant** under the plugboard. No matter what plugboard settings the Germans used, the cycle lengths stayed the same. Rejewski could strip away the plugboard's complexity -- which had defeated every other cryptanalyst -- by working with cycle lengths instead of individual letters.

He called this invariant the **"characteristic"** (charakterystyka).

There was one more piece he needed: the wiring of the rotors themselves. This is where intelligence came in. **Gustave Bertrand**, a French military intelligence officer, had been receiving Enigma documents from **Hans-Thilo Schmidt**, a German spy codenamed "Asche" who worked in the German cipher office. Schmidt had been selling secrets to the French since 1931, motivated by resentment and debts. Bertrand passed Schmidt's documents -- operating manuals, monthly key tables for September and October 1932 -- to the Poles.

Armed with the permutation theory and Schmidt's documents, Rejewski made one final assumption: that the military Enigma's entry drum was wired in simple alphabetical order (ABCDEFG...). This seemed too obvious. Dilly Knox at the British Government Code and Cypher School had considered and rejected the same possibility. As Knox's colleague Peter Twinn later said: "It was such an obvious thing to do, rather a silly thing to do, that nobody -- not Dilly Knox or Tony Kendrick or Alan Turing -- ever thought it worthwhile trying."[^1]

Rejewski tried it. It worked.

In his own words: "From my pencil, as by magic, began to issue numbers designating the connections in rotor N."[^2]

By the end of 1932, Rejewski had recovered the wiring of all three rotors and the reflector. He was reading German military Enigma traffic. He was 27 years old, and he had just broken what the entire Western intelligence establishment considered unbreakable.

Cipher historian Cipher A. Deavours called the underlying theorem **"the theorem that won World War II."**[^3]

---

## Jerzy Rozycki and Henryk Zygalski

Rejewski did not work alone for long. His two classmates from the 1929 Poznan cryptology course joined him in Warsaw.

![Jerzy Rozycki (1909-1942). The youngest of the three, he invented the "clock" method for determining Enigma rotor positions. He drowned at 32 when the SS Lamoriciere sank in the Mediterranean. Public domain.](/assets/images/Rozycki_portrait.jpg)

**Jerzy Rozycki** was born in 1909 in Olszana (now Vilshana, Ukraine). His father was a pharmacist. Rozycki earned a master's in mathematics from Poznan in 1932 and later a second master's in geography. He was the youngest of the three and the most inventive -- he developed the **"clock" method** (zegar), which could determine which of the three Enigma rotors was in the rightmost position on any given day, drastically reducing the search space.

![Henryk Zygalski (1908-1978). His perforated sheets were an elegant physical algorithm -- a Boolean AND operation performed with light, paper, and patience. He spent his post-war decades teaching statistics in England, forbidden from telling anyone what he had done. Public domain.](/assets/images/Zygalski_portrait.jpg)

**Henryk Zygalski** was born in 1908 in Poznan. His contribution came in late 1938, when the Germans increased Enigma's security by introducing new rotors. The old methods stopped working. Zygalski designed the **perforated sheets** (plachty Zygalskiego) -- 26 sheets of paper, each 26 by 26 cells, with holes punched at positions corresponding to a particular cryptographic pattern. When you stacked sheets from multiple intercepted messages on a light table and shifted them according to a defined procedure, the number of visible holes decreased. When only one hole remained -- that was the daily key.

The Zygalski sheets were, in effect, a **physical algorithm**: a Boolean AND operation performed with light, paper, and a human operator. They were a form of systematic computation decades before anyone used that phrase.

---

## The Bomba

In October 1938, Rejewski designed something more ambitious: the **bomba kryptologiczna** -- an electromechanical device that automated the search for Enigma daily settings. Six replicas of the Enigma machine were wired together and driven by electric motors, cycling through the 17 576 possible positions of three rotors. Each bomba "took the place of some one hundred workers." Six were built by the AVA Radio Manufacturing Company in Warsaw.

![A 3D reconstruction of the Polish bomba kryptologiczna. Six Enigma-replica rotor sets cycled through 17 576 positions automatically. The physical devices were destroyed before the German invasion. Image: Szymon Pilecki and Szymon Dąbrowski, via Wikimedia Commons (CC BY-SA 4.0).](/assets/images/Bomba_Polish.jpg)

The bomba was not a computer in the modern sense. It was a special-purpose electromechanical search engine. But it was a **precursor** to Turing's Bombe at Bletchley Park, which was directly inspired by the Polish device -- and named after it.

---

## Five Weeks Before the Invasion

By mid-1939, Poland was running out of time. Hitler had taken Czechoslovakia in March. German troops massed on the border. The Polish General Staff made a decision: share everything.

On **July 25-26, 1939** -- five weeks before Germany invaded Poland -- a secret conference was held in the Kabaty Woods at Pyry, south of Warsaw. The Polish Cipher Bureau hosted delegations from French and British intelligence.

**Commander Alastair Denniston**, head of the British Government Code and Cypher School, and **Dilly Knox**, Britain's chief Enigma cryptanalyst, arrived expecting a technical discussion of approaches and difficulties. Instead, the Poles announced that they had been reading German Enigma traffic since 1933. They revealed everything: the rotor wirings, the cyclometer, the bomba, the Zygalski sheets. They promised each delegation a Polish-reconstructed replica Enigma machine.

The British were stunned. They had been working on Enigma for years with limited success. The Poles had solved it **seven years earlier**.

Knox's reaction was complex. He was "furious that the solution was one he had rejected"[^5] -- the alphabetical entry drum wiring -- yet he "grasped everything very quickly, almost quick as lightning."[^5] He was, in the words of one observer, "chagrined -- but grateful."[^5]

Gordon Welchman, who would build Bletchley Park's Hut 6 Ultra operation, wrote later:

> **"Hut 6 Ultra would never have got off the ground if we had not learned from the Poles, in the nick of time, the details both of the German military version of the commercial Enigma machine, and of the operating procedures that were in use."**[^4]

The RUSI described the Pyry disclosure as "the most consequential intelligence-sharing arrangement of World War Two."[^6]

Alan Turing visited the Polish cryptologists at PC Bruno in France in January 1940, bringing completed sets of Zygalski sheets. On January 17, 1940, the Poles made the first break into wartime Enigma traffic. Turing's Bombe -- the electromechanical device that would break Enigma at industrial scale -- was developed from the Polish bomba and took its name from the Polish original. But Turing's key innovation was a change of method: where the Polish bomba had exploited the indicator repetition procedure (the Germans' habit of enciphering the message key twice), Turing's Bombe used **cribs** -- guesses of known plaintext phrases like "WETTERVORHERSAGE" (weather forecast). This made it robust against the procedural changes that had killed the Polish bomba in 1938. Gordon Welchman then added the **diagonal board**, which exploited the reciprocal property of the plugboard and dramatically reduced false stops. More than 340 Bombes were eventually built -- 211 British and 131 American. The Polish foundation made Bletchley Park possible.

---

## The Fates

What happened to the three mathematicians is a story of cruelty, injustice, and silence.

### Rozycki: Drowned at 32

After escaping Poland in September 1939, the three worked at the Franco-Polish cryptology centre PC Bruno (Chateau de Vignolles, near Paris), and later at Cadix (Chateau des Fouzes, near Uzes in Vichy France), reading German and Italian dispatches about Axis troop movements.

On January 6, 1942, the French passenger ship **SS Lamoriciere** departed Algiers bound for Marseille, carrying 272 passengers and 122 crew. Rozycki was aboard, returning from the Algiers branch office where he had been supervising the reading of encrypted German traffic.

The ship hit a severe storm. Short of proper fuel, the stokers were burning furniture to keep the boilers going. On the morning of January 9, the captain ordered abandonment. The Lamoriciere sank at 12:35. Of 394 people aboard, only 93 survived.

**Jerzy Rozycki** was not among them. He was 32 years old. The youngest of the three, the inventor of the clock method, the man with two master's degrees and a wife and a young son -- dead in the Mediterranean, on his way back from decrypting the messages that were helping the Allies track Axis forces in North Africa.

### Rejewski and Zygalski: Racehorses Pulling Wagons

After the fall of Vichy France in November 1942, Rejewski and Zygalski fled through southern France. They crossed the Pyrenees on foot in January 1943. Their guide pulled a pistol and robbed them near the summit. They were arrested in Spain and spent three months in prison before the Polish Red Cross secured their release. They reached London on August 3, 1943.

In Britain, the two men who had cracked Enigma seven years before Bletchley Park existed were inducted as **privates** in the Polish Armed Forces. They were assigned to a Polish signals unit at Stanmore Park and set to work cracking low-grade German hand ciphers.

British cryptanalyst Alan Stripp later said: **"Setting them to work on the Doppelkassetten system was like using racehorses to pull wagons."**[^7]

They were never brought to Bletchley Park.

### Rejewski: The Codebreaker as Accountant

Rejewski returned to Poland after the war. He chose not to go back to his university position, unwilling to separate from his remaining family -- his son Andrzej had died of polio in 1947, aged 11, after only five days' illness.

Instead, he took a job as sales director at a cable-manufacturing company. When his mathematician's eye discovered financial irregularities at the factory, it brought disfavour on **him** rather than on the perpetrators. Between 1949 and 1958, Poland's Office of Public Security repeatedly investigated him, suspecting membership in the Polish Armed Forces in the West. He never told them about Enigma.

The greatest cryptanalyst in Polish history spent his working life as a **mid-level bureaucrat and cost inspector**, moving between a succession of provincial cooperative associations, harassed by secret police, unable to tell anyone what he had done.

He received the Officer's Cross of the Order of Polonia Restituta in 1978, at age 72 -- the first formal recognition. He died of a heart attack on February 13, 1980, while returning from shopping in Warsaw. He was 74.

His posthumous 1981 paper in the *IEEE Annals of the History of Computing* -- "How Polish Mathematicians Deciphered the Enigma" -- was published more than a year after his death. The major recognitions all came later: the Grand Cross (2000, posthumous), the British War Medal (2005, received by his daughter), the Knowlton Award (2012, posthumous), the IEEE Milestone (2014).

He did not live to see the full reckoning.

### Zygalski: The Master Cryptanalyst Teaching Statistics

Zygalski chose to stay in England after the war. He could not return to communist Poland. He could not tell anyone what he had done.

He taught mathematics at the Polish University College in London, then transferred to Battersea Polytechnic in 1951. The institution was renamed Battersea College of Technology in 1957, then received a Royal Charter as the University of Surrey in 1966. Zygalski continued teaching through all three incarnations -- elementary statistics to undergraduate students who had no idea that the quiet lecturer with the round glasses had invented one of the most elegant cryptanalytic techniques in history.

The Official Secrets Act prevented him from publishing or even speaking about his wartime work. His colleagues were entirely unaware. He suffered a stroke in 1968 and retired.

In 1977, the Polish University in Exile awarded him an honorary doctorate -- the first formal recognition.

**Henryk Zygalski died on August 30, 1978.** Kozaczuk's *W kregu Enigmy* -- the first comprehensive account of the Polish Enigma achievement -- was published in 1979. Garlinski's English-language *Intercept* appeared the same year. Zygalski missed the full story reaching the world by **months**.

---

## The Forty-Year Silence

Why was the Polish contribution hidden for four decades?

**Churchill's secrecy ban (1945):** All Enigma intelligence (Ultra) was classified. Enigma-type machines were still in use by former colonies after the war, and GCHQ wanted to keep reading their traffic.

**Winterbotham's distortion (1974):** F.W. Winterbotham's *The Ultra Secret*, the first major English disclosure, attributed the original Enigma solution to information from a "Polish employee of the cipher machine factory" -- a fiction. As David Kahn wrote in the *New York Times*: the book **"cheats the Poles of credit for one of the great cipher solutions of history."**[^8]

**The Cold War:** Poland was behind the Iron Curtain. Polish scholars had limited access to Western publications. Western scholars had limited access to Polish sources. Rejewski was silenced not only by British classification but by the practical danger of attracting the attention of Poland's Soviet-controlled security services.

**The standard narrative:** For decades, the story was simply: "Alan Turing cracked Enigma." The 2014 film *The Imitation Game* reduced the Polish contribution to a single line.

---

## The Monument

![The Enigma Codebreakers Monument in Poznan, unveiled in 2007. Three bronze pillars for three mathematicians. The inscription reads: "To the memory of Marian Rejewski, Jerzy Rozycki, Henryk Zygalski -- mathematicians, Polish Army officers, who by breaking Enigma ciphers contributed to the victory over Nazi Germany." Photo: Radomil via Wikimedia Commons (GFDL 1.2).](/assets/images/Poznan_monument.jpg)

In 2007, a monument was unveiled in Poznan -- the city where three young mathematicians attended a secret cryptology course in 1929. Three bronze pillars, triangular in cross-section, each bearing the name of one of the three. The Poznan Enigma Cipher Centre now stands nearby, telling their story.

The inscription reads:

> **"To the memory of Marian Rejewski, Jerzy Rozycki, Henryk Zygalski -- mathematicians, Polish Army officers, who by breaking Enigma ciphers contributed to the victory over Nazi Germany."**[^9]

Contributed. The word is too modest. They made it possible. As Welchman said: without the Poles, Bletchley Park would never have gotten off the ground. The Bombe was named after the bomba. The methods were Polish. The mathematics was Polish. The foundation was Polish.

Rejewski, the quiet man with the elegant algebra, died thinking the world did not know his name. Rozycki drowned at 32 in a storm in the Mediterranean. Zygalski spent his last decades teaching statistics in Battersea, forbidden from saying who he was.

They cracked Enigma. They saved the world. And then the world forgot them for forty years.

This story is personal. I am Polish. And I do not forget.

---

## Footnotes
[^1]: Twinn, P. (1993). "The Abwehr Enigma." In Hinsley, F. H. & Stripp, A. (eds.), *Codebreakers: The Inside Story of Bletchley Park*. Oxford University Press, p. 125.
[^2]: Rejewski, M. (1981). "How Polish Mathematicians Deciphered the Enigma." *IEEE Annals of the History of Computing*, 3(3), 213-234. [IEEE](https://ieeexplore.ieee.org/document/4639752).
[^3]: Deavours, C. A. (1980s). Writings in *Cryptologia* on the Polish contribution to breaking Enigma. See also Deavours, C. A. & Kruh, L. (1985), *Machine Cryptography and Modern Cryptanalysis*, Artech House.
[^4]: Welchman, G. (1982). *The Hut Six Story: Breaking the Enigma Codes*. McGraw-Hill. Republished 1997 by M & M Baldwin with corrections.
[^5]: Kozaczuk, W. (1984). *Enigma: How the German Machine Cipher Was Broken, and How It Was Read by the Allies in World War Two*. Trans. C. Kasparek. University Publications of America. Knox's reactions to the Pyry disclosure are recorded in Kozaczuk's account of the Polish-French-British meeting.
[^6]: Royal United Services Institute (RUSI). Historical analyses of the Pyry conference and the Anglo-Polish-French intelligence-sharing arrangement. See RUSI journal articles on WWII signals intelligence.
[^7]: Stripp, A. (1993). "The Enigma Machine: Its Mechanism and Use." In Hinsley, F. H. & Stripp, A. (eds.), *Codebreakers: The Inside Story of Bletchley Park*. Oxford University Press.
[^8]: Kahn, D. (1974). Review of F. W. Winterbotham's *The Ultra Secret*. *New York Times Book Review*, December 29, 1974.
[^9]: Enigma Cipher Centre, Poznan. Inscription on the Enigma Codebreakers Monument (unveiled 2007). [centrum-szyfrow.pl](https://centrum-szyfrow.pl/en/).

## References
**Primary Sources:**
* Rejewski, M. (1981). How Polish Mathematicians Deciphered the Enigma. *IEEE Annals of the History of Computing*, 3(3), 213-234. (Posthumous.) [IEEE](https://ieeexplore.ieee.org/document/4639752)
* Rejewski, M. (1980). An Application of the Theory of Permutations in Breaking the Enigma Cipher. *Applicationes Mathematicae*, 16(4), 543-559.
* Rejewski, M. (1984). "Mathematical Solution of the Enigma Cipher." Appendix E in Kozaczuk (1984).

**Books:**
* Kozaczuk, W. (1984). *Enigma: How the German Machine Cipher Was Broken, and How It Was Read by the Allies in World War Two*. Trans. C. Kasparek. University Publications of America.
* Garlinski, J. (1979). *Intercept: The Enigma War*. J.M. Dent & Sons.
* Singh, S. (1999). *The Code Book*. Fourth Estate. (Chapter on Polish contribution.)
* Hodges, A. (1983). *Alan Turing: The Enigma*. Simon & Schuster.
* Kahn, D. (1996). *The Codebreakers* (revised ed.). Scribner.
* Welchman, G. (1982). *The Hut Six Story: Breaking the Enigma Codes*. McGraw-Hill. (Republished 1997, M & M Baldwin.)
* Hinsley, F. H. & Stripp, A., eds. (1993). *Codebreakers: The Inside Story of Bletchley Park*. Oxford University Press.
* Deavours, C. A. & Kruh, L. (1985). *Machine Cryptography and Modern Cryptanalysis*. Artech House.
* Kahn, D. (1974). Review of *The Ultra Secret* by F. W. Winterbotham. *New York Times Book Review*, December 29, 1974.

**Articles and Online Sources:**
* GCHQ. The Pyry Conference. [GCHQ](https://www.gchq.gov.uk/information/pyry-conference)
* JSTOR Daily. The Polish Codebreakers Who Cracked the Enigma Machine. [JSTOR](https://daily.jstor.org/the-codebreakers-who-saved-the-world/)
* Bauer, F.L. (2003). Review of *Codebreakers*. *Notices of the AMS*. [PDF](https://www.ams.org/notices/200308/rev-bauer.pdf)
* AMS Feature Column. Permutations and the Enigma Machine. [AMS](https://www.ams.org/publicoutreach/feature-column/fcarc-enigma)
* Enigma Cipher Centre, Poznan. [centrum-szyfrow.pl](https://centrum-szyfrow.pl/en/)
* SS Lamoriciere. [Wikipedia](https://en.wikipedia.org/wiki/SS_Lamoricière)

**Image Credits:**
* Rejewski portrait (1932). Public domain. [Wikimedia](https://commons.wikimedia.org/wiki/File:Marian_Rejewski_1932_small.jpg)
* Rozycki portrait. Public domain. [Wikimedia](https://commons.wikimedia.org/wiki/File:Jerzy_Rozycki.jpg)
* Zygalski portrait. Public domain. [Wikimedia](https://commons.wikimedia.org/wiki/File:Henryk_Zygalski.jpg)
* Enigma machine, Milan museum. [Wikimedia](https://commons.wikimedia.org/wiki/File:Enigma_(crittografia)_-_Museo_scienza_e_tecnologia_Milano.jpg)
* Bomba reconstruction. [Wikimedia](https://commons.wikimedia.org/wiki/File:Cryptology_Bomb.jpg)
* Poznan monument. [Wikimedia](https://commons.wikimedia.org/wiki/File:Pomnik_Kryptologow_RB1.jpg)

---

*Previously in this series: [The Man Who Forecasted Weather with a Pencil](/weather/hpc/history/2026/03/24/The-man-who-forecasted-weather-with-a-pencil.html) -- [The Number That Connects Turbulence to War](/weather/hpc/history/2026/03/25/The-number-that-connects-turbulence-to-war.html) -- [The Line That Models Cannot Draw (Part 1)](/weather/hpc/history/2026/03/26/The-line-that-models-cannot-draw.html) -- [Reading the Sky](/weather/hpc/history/2026/03/27/Reading-the-sky.html) -- [The Ghost in the Grid](/weather/hpc/history/2026/03/28/The-ghost-in-the-grid.html) -- [The Man Who Tamed the Equations](/weather/hpc/history/2026/03/29/The-man-who-tamed-the-equations.html) -- [The First Climate Model Had 5 KB of RAM](/weather/hpc/history/2026/03/30/The-first-climate-model-had-5KB-of-RAM.html) -- [The Butterfly That Broke the Forecast](/weather/hpc/history/2026/03/31/The-butterfly-that-broke-the-forecast.html) -- [From Cables to Chaos](/weather/hpc/history/2026/04/02/From-cables-to-chaos.html) -- [The Swedes Got There First](/weather/hpc/history/2026/04/03/The-swedes-got-there-first.html) -- [The Magician Who Told No Secrets](/weather/hpc/history/2026/04/04/The-magician-who-told-no-secrets.html) -- [The Blueprint Von Neumann Gave Away](/weather/hpc/history/2026/04/08/The-blueprint-von-Neumann-gave-away.html) -- [The Machine That Learned Too Early](/weather/hpc/history/2026/04/09/The-machine-that-learned-too-early.html) -- [The Machine That Built IBM](/weather/hpc/history/2026/04/10/The-machine-that-built-IBM.html)*
