# Fact-Check: Polish Codebreakers and Turing's Bombe

**Post:** `_posts/2026-04-12-Three-mathematicians-from-Poznan.md`
**Date of review:** 2026-04-16
**Reviewer method:** Cross-referencing post claims against Wikipedia, Britannica, GCHQ, RUSI, TNMOC, Bletchley Park Trust, Erskine (Cryptologia 2006), Dermot Turing (X Y Z, 2018), Welchman (The Hut Six Story, 1982), and multiple scholarly sources.

---

## Claim 1: "Turing's Bombe was directly inspired by the Polish bomba, from which its name was derived"

**Post text (line 96-97):**
> "a precursor to Turing's Bombe at Bletchley Park, which was directly inspired by the Polish device -- and named after it."

**Also (line 118):**
> "His Bombe -- the electromechanical device that would break Enigma at industrial scale -- was directly inspired by the Polish bomba."

### Verdict: LARGELY CORRECT but needs nuance

### Evidence:

**The name derivation** is well-supported. Wikipedia (Bombe article) states: "The British bombe was developed from the Polish bomba." Britannica states: "The Bombe was derived from a device called the bomba -- Polish for 'bomb' -- that was invented in Poland during the 1930s." This is the scholarly consensus: the British machine's name derives from the Polish original.

**"Directly inspired"** is more complicated. Turing knew about the Polish bomba from the Pyry handover (July 1939) and from visiting PC Bruno (January 1940). He specified a machine that could break Enigma "more effectively than the Polish bomba kryptologiczna" (Wikipedia, citing Rejewski). However, Turing's design was fundamentally different in its operating principle (see Claim 7 below). The concept of using an electromechanical machine to automate cryptanalysis was inherited from the Poles, but the actual design logic was Turing's own innovation.

Peter Calvocoressi (head of the Luftwaffe section at Bletchley Park) offered a measured view: the Polish contribution "accelerated the breaking of Enigma by perhaps a year. The British did not adopt Polish techniques but they were enlightened by them." (Wikipedia, Cryptanalysis of the Enigma)

**What Turing actually took from the Poles:**
- The concept that an electromechanical machine could automate Enigma cryptanalysis
- Knowledge of the Enigma's rotor wiring (critical)
- Knowledge of German operating procedures
- The name
- The Zygalski sheets (which Turing personally delivered completed sets of to PC Bruno)

**What was new in Turing's design:**
- The crib-based approach (known-plaintext attack) instead of indicator exploitation
- The ability to work regardless of indicator procedures
- The diagonal board (Welchman's addition) that exploited plugboard reciprocity
- Far greater scale (36 Enigma equivalents vs 6 in the Polish bomba)

### Recommendation:
The phrase "directly inspired by" is defensible but slightly overstates the mechanical continuity. The post already says the bomba was "a precursor to" (line 96), which is more precise. Consider changing line 118 from "directly inspired by the Polish bomba" to "built on the foundation of the Polish bomba" or "developed from the Polish bomba" to match the Wikipedia/Britannica phrasing. The current wording could be read as implying Turing copied or closely adapted the Polish design, when in fact he redesigned the approach from scratch while inheriting the concept and the intelligence.

**NO CORRECTION REQUIRED** -- the claim is within acceptable bounds for a blog post, but the post could note that the operating principle was different (see Claim 7).

---

## Claim 2: The name "Bombe" -- is it really derived from "bomba"?

**Post text (line 96-97):**
> "a precursor to Turing's Bombe at Bletchley Park, which was directly inspired by the Polish device -- and named after it."

### Verdict: CORRECT -- the British "Bombe" name derives from the Polish "bomba"

The scholarly consensus is clear that the British Bombe was named after the Polish bomba. This is stated by Britannica, Wikipedia, TNMOC, and virtually all scholarly sources.

The more interesting question is where the *Polish* name "bomba" came from. Multiple competing theories exist, and there is **no scholarly consensus** on the etymology of the *Polish* original:

1. **Rejewski's own account:** He said the device was dubbed a "bomb" "for lack of a better idea." (Wikipedia, Bomba article, citing Rejewski)
2. **The ice cream theory:** Tadeusz Lisicki claimed Rozycki named it after the bombe glacee (an ice cream dessert). However, Rejewski dismissed this as "implausible" since Lisicki had not known Rozycki. (Wikipedia, Bomba article)
3. **The ticking/noise theory:** Cipher Bureau technician Czeslaw Betlewski suggested workers called it a "bomb" because of "the characteristic muffled noise that it produced when operating." (Wikipedia, Bomba article)
4. **A 1945 US Army report** claimed a mechanical part fell off with a "loud noise," but this is described as "both vague and inaccurate." (Wikipedia)

### Recommendation:
The post's claim that the British Bombe was "named after" the Polish bomba is correct. The post does NOT claim why the *Polish* device was called "bomba," which is good, because that remains genuinely uncertain. No correction needed.

---

## Claim 3: The Pyry meeting -- July 25-26, 1939

**Post text (line 104):**
> "On July 25-26, 1939 -- five weeks before Germany invaded Poland -- a secret conference was held in the Kabaty Woods at Pyry"

### Verdict: DISPUTED -- the exact dates vary by source. The post's dates are one of two credible options.

### Evidence:

The dates of the Pyry conference are genuinely uncertain, with primary sources disagreeing:

- **Denniston's account** (from his pocket diary, published by Ralph Erskine in Cryptologia 2006): states **26 and 27 July 1939**. This is the only British first-hand account.
- **GCHQ official page** ("The Pyry Forest Meeting"): states **25 and 26 July 1939**.
- **UK Government History Blog** (history.blog.gov.uk): titles the post "26 July 1939."
- **Bertrand and Rejewski's** later accounts: give **25-26 July**, but both were writing more than 30 years later.
- **Wikipedia (Cryptanalysis of the Enigma):** gives "26 and 27 July 1939."
- **Dermot Turing (X, Y & Z, 2018):** The meeting spanned multiple days.

Ralph Erskine, who published Denniston's account in Cryptologia (2006), notes that Denniston derived the dates from his pocket diary written in May 1948, while Bertrand and Rejewski were writing over 30 years later. Erskine appears to favor 26-27 July based on Denniston's diary.

### Recommendation:
**CONSIDER CORRECTING.** The post says "July 25-26" but the most authoritative primary source (Denniston's diary, published by Erskine) gives July 26-27. GCHQ's own page gives 25-26 July. Given the genuine uncertainty, the safest option is either:
- Change to "July 25-26, 1939" and add a footnote noting the date discrepancy, OR
- Change to "in late July 1939" to avoid the dispute entirely, OR
- Keep "July 25-26" since GCHQ uses these dates (an authoritative institutional source)

The current text aligns with GCHQ and several Polish sources. It is defensible but not uncontested.

---

## Claim 4: Gordon Welchman's quote

**Post text (lines 112-114):**
> "Hut 6 Ultra would never have got off the ground if we had not learned from the Poles, in the nick of time, the details both of the German military version of the commercial Enigma machine, and of the operating procedures that were in use."

### Verdict: CORRECT -- the wording matches the standard citation

### Evidence:

This quote appears consistently across multiple authoritative sources:

- **Wikipedia (Cryptanalysis of the Enigma)** quotes Welchman as: "Hut 6 Ultra would never have gotten off the ground if we had not learned from the Poles, in the nick of time, the details both of the German military version of the commercial Enigma machine, and of the operating procedures that were in use."
- **RUSI article** on Poland's decisive role cites the same quote.
- **IEEE AESS** history column cites the same quote.
- **The research file** Polish_codebreakers.md cites the same quote.

The source is **Gordon Welchman, *The Hut Six Story: Breaking the Enigma Codes* (McGraw-Hill, 1982)**. The exact page number could not be confirmed via web search (reported as p. 289 in some secondary sources, but this could not be independently verified without access to the book).

Note: Wikipedia uses "gotten" while the post uses "got." Both forms appear in different citations of the same passage. The original British edition likely uses "got" (British English); the American edition may use "gotten." The post's use of "got" is appropriate.

### Recommendation:
**NO CORRECTION NEEDED.** The quote is accurately reproduced. Adding the source (Welchman, *The Hut Six Story*, 1982) in the references is good practice, which the post already does.

---

## Claim 5: "More than 350 Bombes were eventually built -- 224 British and over 130 American"

**Post text (line 118):**
> "More than 350 Bombes were eventually built -- 224 British and over 130 American."

### Verdict: INCORRECT -- the numbers need correction

### Evidence:

**British Bombes:** Multiple authoritative sources consistently give **211** as the number of British Bombes:
- TNMOC (The National Museum of Computing): "211 Bombe machines"
- Bletchley Park Trust: "211 bombe machines"
- bombe.org.uk: "211 Bombe machines"
- The figure of 211 is the most widely cited and authoritative number.

However, the research file crypto_to_computing_research.md gives a different breakdown: "73 standard, 14 Jumbo, 57 Mammoth, 12 Cobra, 68 'new' standard" = 224 total. This appears to come from the Wikipedia Bombe article's detailed production table, which lists different *types* of Bombes ordered/built. The discrepancy between 211 and 224 may reflect the difference between machines that were *operational at war's end* (211) versus total machines *ordered or constructed* over the entire war (224, which may include machines that were damaged, dismantled, or cannibalized for parts).

**American Bombes:**
- US Navy: **121 bombes** -- this is consistently documented across NSA, Wikipedia, NPS, and the Dayton Codebreakers site. Production stopped in September 1944.
- US Army: **10 bombes** (a physically different design, built by Bell Labs). These were relay-based, not drum-based.
- Total American: **131** (121 Navy + 10 Army)

**Grand total:**
- If using 211 British + 131 American = 342
- If using 224 British + 131 American = 355
- The post says "more than 350" with "224 British and over 130 American" = approximately 355

### Recommendation:
**CORRECT THE NUMBERS.** The most defensible figures are:
- British: **211** operational machines (the consensus figure from Bletchley Park, TNMOC, and multiple authoritative sources). Using 224 requires explaining it includes all types ever built, not just operational at war's end.
- American: **121 US Navy + 10 US Army = 131 American** (this is well-documented)
- Total: approximately **342** (using 211) or **355** (using 224)

Suggested correction: "More than 340 Bombes were eventually built -- 211 British and 131 American (121 US Navy, 10 US Army)."

Alternatively, if using the 224 figure: "More than 350 Bombes were ordered or built during the war -- up to 224 British (of various types) and 131 American."

---

## Claim 6: "Turing visited Polish cryptologists in France in early 1940"

**Post text (line 118):**
> "Alan Turing visited the Polish cryptologists in France in early 1940."

### Verdict: CORRECT

### Evidence:

This is well-documented across multiple sources:

- **Wikipedia (Marian Rejewski):** "In January 1940 Alan Turing spent several days at PC Bruno conferring with his Polish colleagues."
- **Wikipedia (Cryptanalysis of the Enigma):** "on 17 January 1940, the Poles made the first break into wartime Enigma traffic" using Zygalski sheets that had been completed on 7 January 1940.
- **Wikipedia (Zygalski sheets):** "The remaining Zygalski sheets were completed on 7 January 1940, and were couriered by Alan Turing to France shortly thereafter."
- **turing.org.uk** has a dedicated page titled "Alan Turing's mission to France, January 1940."
- **Rejewski** later wrote about Turing's visit to PC Bruno.

**What happened:** Turing traveled to PC Bruno (Chateau de Vignolles, near Paris) in January 1940. He brought completed sets of Zygalski sheets that had been punched at Bletchley Park by John Jeffreys using Polish-supplied specifications. On 17 January 1940, using these sheets, the Poles at PC Bruno made the first break into wartime Enigma traffic (specifically traffic from 28 October 1939). Turing conferred with the Polish cryptologists about Enigma decryption methods.

The post says "early 1940" which is correct -- it was January 1940. The post does not specify PC Bruno by name in this sentence (though it does mention PC Bruno later in the "Fates" section).

### Recommendation:
**NO CORRECTION NEEDED.** The claim is accurate. For added specificity, the post could say "January 1940" instead of "early 1940" and mention that Turing brought completed Zygalski sheets, but this is optional enrichment, not a factual correction.

---

## Claim 7: Did the Polish bomba work on the same principle as Turing's Bombe?

**Post does not explicitly conflate them, but the proximity of "directly inspired" could mislead readers.**

**Post text (lines 96-97 and 118):**
> "a precursor to Turing's Bombe at Bletchley Park, which was directly inspired by the Polish device -- and named after it."
> "His Bombe -- the electromechanical device that would break Enigma at industrial scale -- was directly inspired by the Polish bomba."

### Verdict: The post does NOT explicitly claim they used the same method, but it does NOT make the difference clear either. This is an OVERSIMPLIFICATION that could mislead readers.

### Evidence:

The two machines worked on **fundamentally different cryptanalytic principles:**

**Polish bomba (1938):**
- Exploited the **indicator repetition procedure** -- the German practice of encrypting the three-letter message key twice at the start of each message
- Searched for rotor positions that produced specific permutation patterns in the doubled indicator
- Became **useless** when the Germans changed the indicator procedure on 1 May 1940 (dropping the double encipherment)
- Required that the number of plugboard connections be relatively small (5-8)
- Required only three available rotors (six possible orderings)

**Turing's Bombe (1940):**
- Based on **cribs** (known or suspected plaintext) -- a known-plaintext attack
- Searched for rotor/plugboard settings consistent with an assumed crib-to-ciphertext relationship
- **Independent of any indicator procedure** -- worked on message body text
- Could handle full 10-connection plugboards (especially after Welchman's diagonal board)
- Could be adapted to new rotor combinations

As Wikipedia states: "Alan Turing designed the British bombe on a more general principle, the assumption of the presence of text, called a crib, that cryptanalysts could predict was likely to be present at a defined point in the message."

The TNMOC notes: "The Polish Bomba searched for matches in indicators. Turing began thinking about a machine that worked, not with the indicators, but with assumed text."

Peter Calvocoressi summarized: "The British did not adopt Polish techniques but they were enlightened by them."

### Recommendation:
**ADD A CLARIFYING SENTENCE.** The post should make clear that while Turing's Bombe inherited the concept and name from the Polish bomba, it used a fundamentally different cryptanalytic approach. This is important because:
1. It gives proper credit to Turing's genuine innovation
2. It explains why the British Bombe was vastly more powerful and adaptable
3. It prevents the reader from thinking the British simply scaled up the Polish design

Suggested addition after "was directly inspired by the Polish bomba" (line 118):
"Though Turing's machine used a fundamentally different cryptanalytic approach -- known-plaintext attack rather than the indicator exploitation of the Polish original -- the concept of automating the search with an electromechanical device, and the knowledge of Enigma's internals, came from the Poles."

---

## Claim 8: "The Polish foundation made Bletchley Park possible"

**Post text (line 118):**
> "The Polish foundation made Bletchley Park possible."

**Also (line 198):**
> "They made it possible. As Welchman said: without the Poles, Bletchley Park would never have gotten off the ground."

### Verdict: SUPPORTED BY WELCHMAN AND RUSI; CONTESTED BY CALVOCORESSI; THE POST'S STRONG PHRASING IS DEFENSIBLE BUT NOT UNIVERSALLY ACCEPTED

### Evidence:

**Sources that support the strong claim:**

1. **Gordon Welchman** (Hut 6 architect, *The Hut Six Story*, 1982): "Hut 6 Ultra would never have got off the ground if we had not learned from the Poles, in the nick of time, the details both of the German military version of the commercial Enigma machine, and of the operating procedures that were in use." This is a very strong statement -- "never" -- from the man who built the operation.

2. **RUSI** (2019): Described the Pyry disclosure as "the most consequential intelligence-sharing arrangement of World War Two." RUSI also stated: "Enigma was broken at Bletchley Park because of the Polish decision in 1939 to share all they knew."

3. **Dermot Turing** (*X, Y & Z*, 2018): Appears to be the source of the "most consequential intelligence-sharing" characterization, extensively documents the Polish contribution as foundational.

4. **GCHQ Director** (2019 commemoration): GCHQ officially commemorated the Pyry meeting, acknowledging the Polish contribution.

**Sources that offer a more measured view:**

1. **Peter Calvocoressi** (head of Bletchley Park's Luftwaffe section): The Polish contribution "accelerated the breaking of Enigma by perhaps a year. The British did not adopt Polish techniques but they were enlightened by them." This acknowledges major importance but stops short of "made it possible" -- implying the British would have gotten there eventually.

2. **Harry Hinsley** (official historian of British Intelligence): Initially underemphasized the Polish contribution in Volumes 1-2 of *British Intelligence in the Second World War*. Was criticized by both Rejewski and Welchman for inaccuracies. A revised account was included as Appendix 30 in Volume 3, Part 2 (1988), written by Joan Murray (nee Clarke). Hinsley estimated that Enigma decryption shortened the war by one to four years but did not specifically quantify the Polish contribution separately.

3. **Rejewski himself** addressed Hinsley's suggestion that cryptological difficulties prompted the Poles to share: "It was not cryptological difficulties of ours that prompted us to work with the British and French, but only the deteriorating political situation."

### Assessment:

The claim "The Polish foundation made Bletchley Park possible" is a strong interpretive statement. It is directly supported by Welchman (who was there and built Hut 6) and by RUSI (a major defense institution). Calvocoressi's "perhaps a year" suggests the British would have broken Enigma eventually without the Poles, just later. The truth is that the specific knowledge the Poles provided -- rotor wiring, operating procedures, the concept of electromechanical attack -- was indispensable to the *timing* of Bletchley Park's success. Whether "possible" or "accelerated by a year" is the right framing depends on how one defines "possible."

### Recommendation:
**NO CORRECTION STRICTLY REQUIRED** -- the claim is supported by Welchman and RUSI, both authoritative. However, the post could acknowledge the range of scholarly opinion. Calvocoressi's "accelerated by perhaps a year" is worth noting as a counterpoint, since it suggests the British might have gotten there without the Poles, just more slowly. The post's passionate tone ("They made it possible") is appropriate for a personal essay but readers should know that not all historians use language quite this strong.

---

## Summary of Recommended Corrections

| # | Claim | Verdict | Action |
|---|-------|---------|--------|
| 1 | Bombe "directly inspired by" Polish bomba | Largely correct | Optional: soften to "developed from" or "built on the foundation of" |
| 2 | Name derived from Polish bomba | Correct | No change needed |
| 3 | Pyry meeting July 25-26 | Disputed (some sources say 26-27) | Keep as-is (GCHQ uses 25-26) or note uncertainty |
| 4 | Welchman quote | Correct | No change needed |
| 5 | "224 British and over 130 American" Bombes | **INCORRECT** -- should be 211 British, 131 American | **CORRECT to "More than 340 Bombes -- 211 British and 131 American"** |
| 6 | Turing visited France early 1940 | Correct | Optional: specify "January 1940" |
| 7 | Bomba vs Bombe operating principle | Not wrong but oversimplified | **ADD a sentence clarifying the different principles** |
| 8 | "Polish foundation made Bletchley Park possible" | Supported by Welchman/RUSI; contested by Calvocoressi | No correction required; optionally note range of views |

### Priority corrections:
1. **FIX Bombe numbers** (Claim 5) -- the figure of 224 British Bombes is not the standard count. Use 211.
2. **ADD clarification** (Claim 7) -- note that the Bombe used a different cryptanalytic method than the bomba.

### Optional improvements:
3. Specify "January 1940" for Turing's visit (Claim 6)
4. Soften "directly inspired" to "developed from" (Claim 1)

---

## Sources Consulted

- [Bombe - Wikipedia](https://en.wikipedia.org/wiki/Bombe)
- [Bomba (cryptography) - Wikipedia](https://en.wikipedia.org/wiki/Bomba_(cryptography))
- [Cryptanalysis of the Enigma - Wikipedia](https://en.wikipedia.org/wiki/Cryptanalysis_of_the_Enigma)
- [Bombe - Britannica](https://www.britannica.com/topic/Bombe)
- [Bomba - Britannica](https://www.britannica.com/topic/Bomba-code-breaking-machine)
- [The Turing-Welchman Bombe - TNMOC](https://www.tnmoc.org/bombe)
- [Historical Background - TNMOC](https://www.tnmoc.org/bh-1-bombe-historical-background)
- [6 Facts About the Bombe - Bletchley Park Trust](https://www.bletchleypark.org.uk/our-story/6-facts-about-the-bombe/)
- [The Pyry Forest Meeting - GCHQ](https://www.gchq.gov.uk/information/the-pyry-forest-meeting)
- [Poland's Decisive Role - RUSI](https://www.rusi.org/explore-our-research/publications/commentary/polands-decisive-role-cracking-enigma-and-transforming-uks-sigint-operations)
- [UK Government History Blog - Pyry 26 July 1939](https://history.blog.gov.uk/2019/07/26/whats-the-context-polish-cryptologists-reveal-they-have-cracked-the-enigma-code-26-july-1939/)
- Erskine, Ralph. "The Poles Reveal their Secrets: Alastair Denniston's Account of the July 1939 Meeting at Pyry." *Cryptologia* 30, no. 4 (2006): 294-305.
- [US Naval Computing Machine Laboratory - Wikipedia](https://en.wikipedia.org/wiki/United_States_Naval_Computing_Machine_Laboratory)
- [US Navy Bombes - NPS](https://www.nps.gov/articles/000/-h-our-history-lesson-navy-waves-building-decryption-bombes-in-dayton-ohio.htm)
- [Historical Background - bombe.org.uk](https://bombe.org.uk/historical-background/)
- [Harry Hinsley - Wikipedia](https://en.wikipedia.org/wiki/Harry_Hinsley)
- [Marian Rejewski - Wikipedia](https://en.wikipedia.org/wiki/Marian_Rejewski)
- Welchman, Gordon. *The Hut Six Story: Breaking the Enigma Codes*. McGraw-Hill, 1982.
- Dermot Turing. *X, Y & Z: The Real Story of How Enigma Was Broken*. The History Press, 2018.
