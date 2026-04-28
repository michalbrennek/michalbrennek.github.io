# Review Batch 4: Posts 14-18

**Reviewer:** Claude (Opus 4.7, 1M context)
**Review date:** 2026-04-27
**Posts under review:**
1. `2026-04-10-The-machine-that-built-IBM.md` (IBM 701) — Post 14
2. `2026-04-12-Three-mathematicians-from-Poznan.md` (Polish codebreakers) — Post 15
3. `2026-04-13-The-forecast-that-reached-the-Nobel.md` (Manabe / Nobel) — Post 16
4. `2026-04-16-The-man-who-caught-the-computer-disease.md` (Frankel / LGP-30) — Post 17
5. `2026-04-17-The-decade-the-forecast-got-good.md` (1960s NWP) — Post 18

**Method:** Cross-referenced each post against per-post reviews (POST15-POST19_REVIEW.md, POLISH_TURING_FACTCHECK.md), people files, and computer files. Verified that prior corrections "stuck."

---

## POST 14 — "The Machine That Built IBM" (2026-04-10)

### Factual

Spot-checks against research files for Watson Jr., IBM 701, and Smagorinsky:

- **Watson Jr. "win this one or fail" quote (line 64, line 297)**: Verified verbatim against `Watson_Jr.md` line 40. Correct: *"We thought in those early days that we either had to win this one or fail as a company -- and that's why I think everybody put such effort into it."*
- **Birkenstock pitch quote (line 56)**: Quote tracks the Hurd oral-history record; "three-million-dollar gamble" is consistent.
- **18 orders out of expected 5 (line 102, line 106)**: Verified. The April 28, 1953 stockholders' meeting quote is verbatim.
- **Watson Jr.'s autobiography line "Customers wanted computers so badly..." (line 108)**: Verified verbatim from `Watson_Jr.md` line 56.
- **Five-eighteen as origin of Watson-Sr. apocrypha (line 110)**: Wikipedia IBM 701 article confirms this; consistent.
- **April 7, 1953 dedication and Oppenheimer "tribute to the mind's high splendor" (line 134)**: Verified — quote is from Goldstine, *The Computer from Pascal to von Neumann* (1972), p. 332. Footnote correctly cites this.
- **Oppenheimer clearance suspended December 21, 1953; revoked June 29, 1954 (lines 130, 134)**: Correct.
- **Speedcode (Backus, January 1953, six-person team)**: Names and dates check out. The footnote 50–75% cost claim and "10 to 20 times slower" are consistent with Backus's 1954 paper.
- **Samuel checkers — February 24, 1956 broadcast, Will Rogers Jr., 15-point stock rise (line 178–180)**: All check out. The 1962 Nealey win and 1966 Hellman/Oldbury 8-game loss are correctly framed as IBM hype/rout.
- **Samuel 1959 paper quote (line 188)**: Verbatim from the paper.
- **Georgetown-IBM January 7, 1954 demonstration**: All names verified — Hurd, Watson Sr., Sheridan, Garvin, Dostert. Cast list correct.
- **Russian sample sentences and translations (lines 216–218)**: Reproduced consistently with Hutchins (2004) account.
- **Dostert biography (line 206)**: Born 1904 Longwy, France; Eisenhower's interpreter; Nuremberg simultaneous-interpretation booth system. Verified.
- **Dostert "five years" prediction (line 226)**: Correctly cited from IBM January 8, 1954 press release.
- **CIA/NSF Georgetown funding (line 230)**: Specific figures ($411,000 NSF, $305,000 CIA, $1,314,869 direct, $9.7M in 2014 dollars) are from Gordin (2016). The post correctly attributes this to Gordin.
- **ALPAC report November 1966 chair John R. Pierce (line 234)**: Correct.
- **JNWPU established July 1, 1954 (line 246)**: Verified against `IBM_701_NWP_detail.md` line 17. (The research file notes some sources give 1953 — planning vs. formal establishment.)
- **Cressman 1919–2008 (line 244)**: Correct.
- **Cressman ran NMC from 1965 to 1979 (line 248)**: ⚠️ This says he ran the National Weather Service "from 1965 to 1979." This is the same Cressman date issue flagged in POST18: he was named director of National Meteorological Services in **1964**, then NWS director when ESSA formed in 1965. The post's "1965 to 1979" for "running the NWS itself" is technically defensible (NWS dates from 1965), but the same factual fragment appears in Post 18 as "1965" for leaving NMC, which POST18_REVIEW correctly flags as wrong (he left NMC in 1964). So Post 14's phrasing here is OK as written but should be re-checked: the sentence reads "lead the JNWPU for a decade, then run the National Weather Service itself from 1965 to 1979" — and 1965 is correct for the NWS specifically, since it dates from 1965. **No correction strictly required**, but if the user has decided "1964" is the canonical year for Cressman leaving NMC, this should be made consistent across the series.
- **First operational forecast May 6, 1955 (line 260)**: Verified.
- **Shuman 1989 retrospective quote (line 266)**: Verbatim from Shuman 1989 paper.
- **EMC quote "very disappointing and not usable by forecasters" (line 268)**: Verified.
- **Fred Shuman as JNWPU chief modeler, 1951 MIT doctorate (line 264)**: Verified — `Shuman.md` confirms 1951 D.Sc. MIT.
- **IBM 701 MTBF "about 30 minutes" (line 270)**: Verified against `IBM_701_NWP_detail.md` line 54.
- **NMC formed January 1, 1958, FOB 4 Suitland, moved 1999 to Bowie (line 276)**: Consistent with research files.
- **Watson Sr. died June 1956 (line 180)**: Correct (he died June 19, 1956).
- **Smagorinsky family on Lower East Side**: Not mentioned in this post — it was the post-16 Bronx error. ✓ This post correctly avoids it.
- **IBM 701: 19 units, 1071 vacuum tubes, 36-bit words, 12 µs memory cycle, 10 tons (lines 78–82)**: All match `IBM_701.md`.

**Minor / Not strictly errors:**
- Line 134 says "Goldstine, who had been a principal architect of the IAS machine and who was in the room, preserved the quote in his 1972 book." Whether Goldstine was "in the room" at the April 7, 1953 dedication is not directly sourced — Goldstine was a senior IAS figure but was no longer with the IAS machine project by that date. Recommend softening to "preserved the quote in his 1972 book" without claiming he was in the room, unless the user has a specific source. **Low priority.**
- Line 76 calls Rochester "MIT-trained electrical engineer who had spent World War II at the MIT Rad Lab working on radar." Standard Rochester biography. Verified.
- Line 110: "Wikipedia's IBM 701 article makes the correction explicit." Confirmed.
- Footnote 13 (Persson 2005) is cited at line 256 ("`tremendously successful`" results). The Persson source is in `IBM_701_NWP_detail.md`. ✓

### Language

- The post uses em-dash style consistently (` -- `), no curly quotes, no ellipses. ✓
- A few rhetorical/stylistic flourishes that may or may not be wanted:
  - Line 68: "Win or fail. No middle ground." — punchy, works.
  - Line 90: "They did. Eventually." — works.
  - Line 282: "The first forecast was disappointing. Every forecast since is descended from it." — works.
  - Line 312: "Three firsts. Three disappointments. Three worlds transformed." — works.
- Line 314: "And that was the machine that quietly -- one disappointing demonstration at a time -- invented the future." — slightly purple but fine.
- Line 24 uses bold sparingly and effectively.

No language issues.

### Forward-looking phrases

- Line 318+: The footnotes mention many things that come "later" but in past tense ("Backus would go on to give the world FORTRAN" at line 290 — back-projecting from 701 era to FORTRAN/704 is fine because FORTRAN is in the past relative to today, not the future relative to the post). ✓
- The post does not tease any upcoming posts in the series. ✓ The "Previously in this series" footer at line 387 lists posts already published.

### Character

- Watson Jr., Rochester, Haddad, Backus, Samuel, Dostert, Cressman, Shuman, Oppenheimer, von Neumann — all introduced with brief biographical setup; cross-references work.
- Dostert biography section (line 206) is colorful and well-judged.
- Line 36–40 sets up Watson Sr./Watson Jr. tension nicely.

### Verdict

**APPROVED with one minor optional fix.** The post is solid. The only thing worth checking is whether Goldstine was actually "in the room" at the April 7, 1953 dedication. If the source doesn't support this, soften the wording. Otherwise the post is publication-ready and consistent with the research files and the corrections applied to Post 18 (Cressman 1964 vs 1965 — Post 14 says NWS "1965–1979" which is correct for NWS specifically, separate from the NMC departure date).

---

## POST 15 — "Three Mathematicians from Poznan" (2026-04-12)

This is the most sensitive post in the batch. Verified line-by-line against `POLISH_TURING_FACTCHECK.md` and `POST15_REVIEW.md`.

### Factual

**Critical Bombe count fix — VERIFIED CORRECTED.** POLISH_TURING_FACTCHECK.md flagged "224 British and over 130 American = ~355 total" as INCORRECT and recommended "More than 340 -- 211 British and 131 American." The current post (line 118) reads:

> "More than 340 Bombes were eventually built -- 211 British and 131 American."

✓ **The correction stuck. This matches the Bletchley Park Trust / TNMOC consensus.**

**Other corrections from POLISH_TURING_FACTCHECK.md:**
- ✓ **Claim 7 — Bombe vs bomba operating principle (line 118):** Now reads "Turing's key innovation was a change of method: where the Polish bomba had exploited the indicator repetition procedure (the Germans' habit of enciphering the message key twice), Turing's Bombe used **cribs** -- guesses of known plaintext phrases like 'WETTERVORHERSAGE' (weather forecast). This made it robust against the procedural changes that had killed the Polish bomba in 1938. Gordon Welchman then added the **diagonal board**..." — this is exactly the clarification the fact-check requested. ✓
- ✓ **Claim 6 — "early 1940" → "January 1940":** Line 118 says "Alan Turing visited the Polish cryptologists at PC Bruno in France in January 1940, bringing completed sets of Zygalski sheets. On January 17, 1940, the Poles made the first break into wartime Enigma traffic." This is more specific than "early 1940" and includes the January 17, 1940 first break date. ✓
- ✓ **Claim 1 — "directly inspired" softening:** The post still uses "directly inspired by" at lines 96 and 118. POLISH_TURING_FACTCHECK marked this as "optional — soften to 'developed from'." Not strictly required, and in context the post immediately explains what was different (the crib method, the diagonal board). Acceptable as written.
- ✓ **Claim 3 — Pyry dates "July 25-26, 1939":** GCHQ uses 25–26; Denniston's diary says 26–27. The post's choice (25–26) aligns with GCHQ. POLISH_TURING_FACTCHECK marked this "no correction strictly required." ✓

**Other key claims verified against research files and POST15_REVIEW:**

- **Rejewski born August 16, 1905 in Bromberg/Bydgoszcz (line 42)**: ✓
- **Began full-time at Cipher Bureau September 1, 1932, under Captain Ciężki (line 46)**: ✓
- **Rejewski was 27 (line 48)**: Correct (born Aug 1905, recovered wirings Dec 1932).
- **Permutation theory / characteristic insight (lines 52–58)**: Mathematically correct description of the cycle-structure-invariance argument; standard formulation.
- **Hans-Thilo Schmidt "Asche" selling secrets to French since 1931 (line 60)**: Verified — first meeting Nov 1, 1931 Verviers.
- **Bertrand passed September and October 1932 key tables (line 60)**: Verified.
- **"From my pencil, as by magic" (line 66)**: Verbatim Rejewski 1981 quote, footnote 2 correct.
- **Twinn quote (line 62)**: Verbatim from Hinsley & Stripp (1993).
- **Deavours "theorem that won World War II" (line 70)**: Verified — appears in I.J. Good and Cipher A. Deavours afterword to Rejewski's 1981 IEEE paper.
- **Rożycki born 1909 in Olszana (Vilshana, Ukraine) (line 80)**: Verified.
- **Zygalski born 1908 in Poznań (line 82)**: Verified.
- **Zygalski sheets — 26 sheets, 26×26 cells, late 1938 development (line 84)**: ✓
- **Bomba designed October 1938, six built by AVA Radio Manufacturing (line 92)**: Verified.
- **17576 positions of three rotors (line 92)**: 26³ = 17576. ✓
- **Pyry conference July 25–26, 1939, Kabaty Woods south of Warsaw (line 104)**: GCHQ-aligned date; defensible.
- **Reading German Enigma traffic since 1933 (line 106)**: ✓ Confirmed by Kozaczuk.
- **Welchman quote "Hut 6 Ultra would never have got off the ground..." (lines 112–114)**: Verbatim from *The Hut Six Story* (1982). The "got" vs. "gotten" choice (British vs American edition) is fine.
- **RUSI "the most consequential intelligence-sharing arrangement of World War Two" (line 116)**: POST15_REVIEW noted this quote could not be traced to a specific RUSI document. The footnote (line 214) reads: "Royal United Services Institute (RUSI). Historical analyses of the Pyry conference and the Anglo-Polish-French intelligence-sharing arrangement. See RUSI journal articles on WWII signals intelligence." This is appropriately vague rather than asserting a specific URL. ⚠️ **Optional improvement**: If the user has access to the original RUSI article, cite it specifically. Otherwise, current attribution is defensible.
- **SS Lamoricière January 6, 1942 from Algiers; sank January 9 at 12:35; 272 passengers + 122 crew = 394; 93 survivors (lines 130–132)**: All verified. ✓
- **Rożycki was 32 when he drowned (line 134)**: Born 1909, died Jan 1942 = 32. ✓
- **Crossed Pyrenees on foot January 1943; reached London August 3, 1943 (line 138)**: Verified.
- **Stripp "racehorses to pull wagons" quote (line 142)**: Verbatim from Hinsley & Stripp (1993).
- **Rejewski's son Andrzej died of polio in 1947, aged 11 (line 148)**: Verified. The "after only five days' illness" detail is in the research file but not in the post — fine.
- **Office of Public Security investigations 1949–1958 (line 150)**: Verified.
- **Officer's Cross of Polonia Restituta 1978; died February 13, 1980 of heart attack age 74 (lines 154)**: Verified. The "returning from shopping" detail (line 154) was flagged in POST15_REVIEW Claim 8 as appearing in Polish_codebreakers.md / Kozaczuk but unverifiable from web sources. Defensible.
- **Posthumous 1981 IEEE Annals paper (line 156)**: Verified.
- **Zygalski stayed in England, taught at Polish University College → Battersea Polytechnic (1951) → Battersea College of Technology (1957) → University of Surrey (1966) (line 164)**: Verified.
- **1968 stroke, retired (line 166)**: Verified.
- **1977 honorary doctorate from Polish University in Exile (line 168)**: Verified.
- **Zygalski died August 30, 1978 (line 170)**: Verified — multiple sources agree.
- **Kozaczuk's *W kręgu Enigmy* (1979) and Garliński's *Intercept* (1979) (line 170)**: ✓
- **Winterbotham's *Ultra Secret* (1974) and Kahn quote (line 180)**: Kahn 1974 NYT review — verified.
- **2007 Poznań monument unveiled (line 192)**: ✓
- **Inscription verbatim (line 196)**: Footnote 9 cites Enigma Cipher Centre Poznań — appropriate source.

**Possible minor issues:**

- Line 18 says "Bert Bolin had been at IAS with Charney and von Neumann and then returned to Sweden to help run the BESK forecasts." Bolin's IAS connection is correct; "help run the BESK forecasts" is shorthand but accurate.
- Line 18 mentions "Aksel Wiin-Nielsen and Geirmundur Arnason walked directly from Rossby's Stockholm group to JNWPU in Suitland." Both names appear in the IBM_701_NWP_detail.md (Wiin-Nielsen explicitly; Arnason consistent with Stockholm-to-Suitland flow). ✓
- Line 22: "I am Polish, and this story belongs to my people, and what was done to them — what was hidden for forty years — is something I take personally." This is the post's emotional spine. Per memory file `user_blogger.md`, this matches the user's heritage and intent.

### Language

- Em-dashes consistent ` -- `. ✓
- No curly quotes. ✓
- No ellipses misuse. ✓
- Line 14: "This post is personal." Strong opening. ✓
- Line 22: "I am Polish, and this story belongs to my people..." personal voice is consistent.
- Line 204: "I am Polish. And I do not forget." ending is bold.

No language issues.

### Forward-looking phrases

- The post does not tease upcoming posts. ✓
- Line 18: "Charney's quasi-geostrophic filtering and Rejewski's permutation group theory are the same act" — this is a thematic claim about the past, not a forward-looking promise. ✓

### Character

- Strong Polish-personal framing maintained throughout without becoming polemical until the closing.
- Cross-references to Beurling, Charney, Richardson, ENIAC, von Neumann, Swedish forecasts all work as labeled hyperlinks.
- The Pyry meeting passage (line 104+) is dramatic and well-constructed.
- The "Fates" structure works: Rożycki's drowning (line 126); Rejewski/Zygalski "racehorses pulling wagons" (line 136); Rejewski as accountant (line 146); Zygalski in Battersea (line 160).

### Verdict

**APPROVED.** All major fact-check corrections from POLISH_TURING_FACTCHECK.md and POST15_REVIEW.md have stuck. The Bombe count (211 British + 131 American = 340+) is correct. The Bombe-vs-bomba operating-principle clarification is in place. The "January 1940" specificity is in place. The post is publication-ready.

Optional follow-ups (low priority): (1) traceable RUSI source citation if user has access; (2) "directly inspired by" → "developed from" softening if the user prefers more neutral language. Neither is required.

---

## POST 16 — "The Forecast That Reached the Nobel" (2026-04-13)

Verified against POST16_REVIEW.md and `Manabe.md` / `Smagorinsky.md`.

### Factual

POST16_REVIEW.md flagged three HIGH priority errors. Checked whether they stuck:

- ✓ **Bronx → Lower East Side / NYC**: Line 28 now reads: "settled on the Lower East Side, where he worked first as a house painter, then built a paint store into a hardware business." And the section heading at line 24 is "The Boy from New York City" (not "The Boy from the Bronx"). Line 14 says "a 26-year-old weather observer from New York City named Joseph Smagorinsky." ✓ **CORRECTION STUCK.**
- ✓ **Smagorinsky age 29 → 31 at GFDL founding**: Line 51 says: "They chose Smagorinsky. He was 31 years old." ✓ **CORRECTION STUCK.**
- ✓ **Carbon Brief URL**: Line 200 in references reads `[Carbon Brief](https://www.carbonbrief.org/the-most-influential-climate-change-papers-of-all-time/)`. ✓ **CORRECTION STUCK.** No more The Conversation URL misattribution.

LOW priority items:
- ✓ **Daily News building "top" → "lobby"**: Line 30 now says "would visit the lobby of the **Daily News building** on East 42nd Street to look at the weather instruments displayed there." ✓ **CORRECTION STUCK.**

**Other key claims verified:**

- **Smagorinsky born January 29, 1924 NYC (line 28)**: ✓
- **Parents Nathan and Dina Azaroff from Gomel, Belarus (line 28)**: ✓ Matches `Smagorinsky.md` line 13. (The post says "Nathan and Dina Azaroff" which presents Azaroff as her surname; `Smagorinsky.md` confirms Dina née Azaroff.)
- **Stuyvesant High School (line 30)**: ✓
- **Brown University then MIT during WWII; Lorenz his instructor (line 32)**: ✓ POST16_REVIEW confirmed Lorenz was instructor (himself ~25 at the time). Optional parenthetical not added — fine.
- **NYU degrees: B.S. 1947, M.S. 1948, Ph.D. 1953 under Bernhard Haurwitz (line 34)**: ✓ Matches `Smagorinsky.md`.
- **April 1950 ENIAC team: Charney, Fjørtoft, Freeman, Platzman, Smagorinsky (line 38)**: ✓ Matches research file.
- **Margaret Smagorinsky née Knoepfel — first female statistician hired by Weather Bureau (line 40)**: ✓ POST16_REVIEW Section "CLAIMS VERIFIED CORRECT" confirms this.
- **General Circulation Research Section 1955 → renamed 1959 → GFDL 1963 (line 54)**: ✓
- **GFDL moved to Princeton's Forrestal Campus 1968 (line 54)**: ✓
- **Smagorinsky ran GFDL for 28 years (1955–1983) (line 56)**: ✓
- **1963 paper "General Circulation Experiments with the Primitive Equations: I" in *Monthly Weather Review*; nine-level hemispheric primitive-equation GCM on IBM Stretch (line 60)**: ✓
- **Smagorinsky subgrid-scale turbulence model — Smagorinsky-Lilly (line 62)**: ✓
- **Manabe born September 21, 1931, Shinritsu Village, Ehime Prefecture (line 72)**: ✓ Matches `Manabe.md` line 6.
- **D.Sc. University of Tokyo 1958 (line 76)**: ✓
- **Smagorinsky read paper, invited 1958, formally joined 1959 (lines 78, 80)**: ✓
- **"25 times" salary multiplier (line 80)**: POST16_REVIEW noted this is unverifiable from mainstream sources but appears in IPRC Climate Vol 5 No 2 (2005). Not corrected with inline citation; defensible as research-file-attested. Low priority.
- **Manabe quotes about complementarity, Japanese culture, "I don't want to go back" (lines 82–86)**: All verified verbatim from `Manabe.md` "Personality and Working Style" section.
- **Briefly returned Japan 1997–2001, Princeton 2002 onward (line 88)**: ✓ Matches `Manabe.md`.
- **1967 Manabe-Wetherald paper in *J. Atmos. Sci.* — "most influential climate research paper of all time" (line 94)**: ✓ Carbon Brief survey, correctly cited.
- **Doubling CO2 from 300 to 600 ppm → 2.36 °C surface warming (line 100)**: POST16_REVIEW confirmed correct. ✓
- ⚠️ **"+2.3 C climate sensitivity" claim from task instructions**: The user's task specifies "+2.3 C climate sensitivity for doubled CO2." The post says "2.36 degrees C." The 1967 paper Table 5 gives 2.36 °C. The task brief seems to round to 2.3 — the post's 2.36 is more precise and matches `Manabe.md` line 48 which gives "2.3 to 2.93" range. **No correction needed.**
- **Observed sensitivity ~2.57 °C, "less than 10% higher" (line 102)**: POST16_REVIEW confirmed this math: (2.57 − 2.36) / 2.57 = 8.2% — less than 10%. ✓
- **Stratosphere cools while troposphere warms — distinctive fingerprint (line 102)**: ✓ Confirmed.
- **1969 Manabe-Bryan first coupled ocean-atmosphere GCM (line 108)**: ✓
- **Kirk Bryan recruited 1961 (line 108)**: ✓
- **1975 Manabe-Wetherald: ~3 °C warming, Arctic amplification first prediction, intensified hydrological cycle (line 112)**: ✓
- **1979 Charney Report: NAS Ad Hoc Study Group on CO2 and Climate, Charney chair, ~3 °C ± 1.5 °C climate sensitivity (lines 116–118)**: ✓
- **Wetherald 1936–2011, died October 9, 2011 in Trenton NJ age 75 (line 132)**: ✓ POST16_REVIEW confirmed.
- **Nobel Prize October 5, 2021 (lines 16, 140)**: ✓
- **Manabe 90 years old (line 142)**: 2021 − 1931 = 90 ✓
- **Manabe quote "I did these experiments out of pure scientific curiosity..." (line 144)**: ✓ Verified verbatim from `Manabe.md` line 82.
- **Smagorinsky died Hillsborough NJ age 81 in 2005 (line 163)**: Matches `Smagorinsky.md` (died Sept 21, 2005, age 81, Hillsborough NJ). ✓ Note Smagorinsky died on September 21, the same date as Manabe's birthday — interesting coincidence not exploited in the post.
- **1979 Charney Report, ENIAC connection (lines 154, 162)**: ✓ All chain timeline dates check out.
- **Hasselmann shared 2021 Nobel; Parisi other half (line 140)**: ✓

**Optional enhancements not yet applied (POST16_REVIEW Section "SUGGESTED ENHANCEMENTS"):**
- Bryan was Lorenz's PhD student (1957) — not added; optional.
- Margaret Smagorinsky's role as pre-computer of equations (vs. just "operator") — not changed; minor.
- Lorenz was ~25 when instructing Smagorinsky — no parenthetical added; minor.

None of these are required.

### Language

- Em-dashes consistent. ✓
- No curly quotes, no problematic ellipses. ✓
- Line 22 timeline framing: "Seventy-one years. Two men. One chain." — works.
- Line 167+: "And the planet is warmer by exactly the amount they said it would be." — strong, factual.

No language issues.

### Forward-looking phrases

- No teasing of future posts. ✓
- Line 174: "The most important forecast in the history of science started with curiosity. It ended with a Nobel Prize. And it began -- as everything in this series begins -- with a computer and a dream of predicting the weather." — closes the post; not forward-looking.

### Character

- Strong dual-protagonist structure (Smagorinsky / Manabe).
- Wetherald's "man without the prize" interlude (line 124+) is well-handled — gives him due credit without disrupting the main narrative.
- Cross-references to ENIAC, Charney, Lorenz, JNWPU all functional.

### Verdict

**APPROVED.** All HIGH priority corrections from POST16_REVIEW.md have stuck (Bronx → NYC/Lower East Side; age 29 → 31; Carbon Brief URL; Daily News "top" → "lobby"). The post is publication-ready.

---

## POST 17 — "The Man Who Caught the Computer Disease" (2026-04-16)

Verified against POST17_REVIEW.md and `Frankel.md`.

### Factual

POST17_REVIEW.md flagged three Priority 1 errors. Checked whether they stuck:

- ✓ **Margaret Hamilton → Ellen Fetter at Lorenz's chaos discovery**: Lines 144–166 describe Lorenz at MIT and the chaos discovery moment, but **the post does not name a programmer at all**. It says simply "a meteorologist named **Edward Lorenz** was running a simple weather model on a computer" (line 144) and "One day in the winter of 1961, Lorenz wanted to rerun a simulation from a point partway through" (line 148). **Margaret Hamilton is not named anywhere in the post.** This avoids the POST17 error entirely. ✓ **CORRECTION STUCK by removal.**

- ✓ **"Early 1950s" → "early 1949" for clearance revocation**: Line 84 reads: "**In early 1949**, Stanley Frankel lost his security clearance." ✓ **CORRECTION STUCK.**

- ✓ **"A million" → "Half a million" punch cards**: 
  - Line 54 section heading: "## A Million Punch Cards" → ⚠️ **STILL READS "A Million Punch Cards" as section heading**.
  - Line 68 body text: "**Roughly half a million punch cards** of data flowed through the machine." ✓
  
  ⚠️ **PARTIAL CORRECTION**: Body text now correctly says "half a million," but the section heading still reads "A Million Punch Cards." This is the heading the user noted in the task brief: "'roughly half a million punch cards' (NOT 'a million')." The body text is fixed but the heading creates a contradiction. **RECOMMEND**: Change section heading from "A Million Punch Cards" to "Half a Million Punch Cards" to match the corrected body text. **Priority: medium.**

**Other claims verified:**

- **Born June 6, 1919, Los Angeles (line 34)**: ✓
- **Rochester graduate study; Berkeley PhD; postdoc under Oppenheimer (line 34)**: ✓
- **Recruited to Los Alamos 1943, age 24 (line 36)**: ✓
- **Group T-5 with desk calculators including wife Mary Frankel (line 42)**: ✓ POST17_REVIEW noted T-5 (desk calculators) vs T-6 (IBM) distinction — the post smooths this slightly but does not say T-5 was the IBM group. Acceptable.
- **Feynman computer disease story (lines 16–24)**: Phrasing is paraphrase rather than exact quote. POST17_REVIEW noted: "the blog presents a condensed version in quotation marks that is not the verbatim Feynman text." Checked the post: Line 20 reads:
  > 'Frankel, he said, had caught "the computer disease" -- the irresistible delight of seeing how much you can make a machine do.'
  
  The phrase "the computer disease" is a verbatim Feynman phrase. The rest is **outside the quotation marks** — described as paraphrase ("the irresistible delight of seeing how much you can make a machine do"). ✓ This is correct quotation hygiene now — POST17_REVIEW concern addressed.
- **War ended August 1945; Frankel and Metropolis traveled to Moore School (line 56)**: ✓
- **Edward Teller's hydrogen bomb / "Super" (line 62)**: ✓
- **ENIAC: 30 tons, 40 panels, 17468 vacuum tubes, 70000 resistors, 10000 capacitors (line 66)**: Matches research files.
- **Calculation ran weeks beginning November 1945, results December (line 68)**: ✓ `Frankel.md` line 50: "ran for approximately six weeks beginning in late November or early December 1945. Results were available by early 1946." Post says "the program ran for weeks. The results were available by December." Slight tension — research file says "results available by early 1946" while post says "by December." The H-bomb calculations continued through February 1946. The post's "December" is consistent with results emerging early but most analysis happened in early 1946. **Minor.**
- **Teller's spring 1946 report (line 70)**: ✓
- **Teller-Ulam radiation implosion 1952 working H-bomb (line 70)**: ✓
- **Berni Alder Monte Carlo molecular dynamics (line 78)**: ✓
- **1950 trip to Manchester to run Alder calculations on Manchester Mark 1 (line 78)**: ✓
- **JCP paper 1955 (line 78)**: ✓
- **Oppenheimer clearance suspended December 21, 1953; revoked June 29, 1954 (line 86)**: ✓
- **MINAC 1954, 113 vacuum tubes, germanium diodes from Hughes Aircraft, magnetic drum (lines 102–104)**: ✓
- **LGP-30 first manufactured 1956 (line 122)**: ✓
- **6.5 inches diameter, 7 inches long magnetic drum, 4096 words 32-bit, 64 tracks of 64 words, 2.34 ms time between adjacent addresses (line 126)**: ✓ Matches `Frankel.md` lines 119–123.
- **Flexowriter typewriter, 800 lbs, $47000, 500+ units (lines 126–132)**: ✓
- **LGP-21 transistorized successor (line 136)**: ✓
- **Lorenz's 12-variable model (line 144)**: ✓
- **Rounding from 6 to 3 decimal places (line 148)**: ✓
- **1963 "Deterministic Nonperiodic Flow" *J. Atmos. Sci.* (line 154)**: ✓
- **Frankel died May 1978 age 58 (line 174)**: ✓ Matches `Frankel.md` line 4.
- **Feynman lived to 1988, Metropolis to 1999, Lorenz to 2008 (line 174)**: ✓

### Language

- Em-dashes consistent. ✓
- No curly quotes. ✓
- Line 16 starts a story narrative; works. ✓
- Line 162: "From nuclear weapons to the butterfly effect, through a single forgotten man." — punchy.
- Line 168: "On a shared mainframe, Lorenz would never have had the idle time to notice a discrepancy in the fourth decimal place." — strong causal claim, well-supported by the framing.
- Line 188: "And one of those machines changed everything we thought we knew about prediction." — fine.

No language issues.

### Forward-looking phrases

- No teasing of future posts. ✓

### Character

- Frankel introduced through Feynman's eyes (the arctangent table) — strong opening.
- Cross-reference to "Post 8 of this series" at line 158 ("I wrote about Lorenz's discovery in detail in [Post 8 of this series, 'The Butterfly That Broke the Forecast.']") — reflective, not forward-looking. ✓
- Cross-reference to "Post 12 of this series" at line 110 ("the IAS machine at Princeton, which von Neumann had designed and which we met in [Post 12 of this series]") — same. ✓

### Verdict

**APPROVED with one fix needed.** Two of three Priority 1 corrections from POST17_REVIEW stuck cleanly (Margaret Hamilton removal; "early 1949" clearance date). The third correction (punch cards) is partially applied: body text correctly says "half a million," but the section heading at line 54 still says "## A Million Punch Cards." 

**Required edit:** Change section heading at line 54 from `## A Million Punch Cards` to `## Half a Million Punch Cards`.

---

## POST 18 — "The Decade the Forecast Got Good" (2026-04-17)

Verified against POST18_REVIEW.md.

### Factual

POST18_REVIEW.md flagged three corrections. Checked whether they stuck:

- ✓ **Cressman left NMC in 1965 → 1964**: Line 162 now reads: "[George Cressman] had left the NMC directorship in **1964** to become head of the Weather Bureau (later the National Weather Service under NOAA, which was created in 1970)." ✓ **CORRECTION STUCK.**

- ✓ **TIROS-1 height 19 inches → 22 inches**: Line 90 now reads: "It was small -- about the size of a washing machine drum, 42 inches in diameter, **22 inches high**." ✓ **CORRECTION STUCK.**

- ✓ **Watson memo paraphrase fix**: Line 144 now reads: "Thomas Watson Jr.** reportedly fired off an angry memo lamenting that IBM had lost 'our industry leadership position' to a lab of '34 people, including the janitor.'" The phrase "world's largest computer company" is gone. ✓ **CORRECTION STUCK.** Note the wording uses "lamenting that IBM had lost 'our industry leadership position'" — this is a slight paraphrase but the quote-marked phrase is now Watson's actual words ("our industry leadership position"). ✓

**Other claims verified:**

- **First operational forecast May 6, 1955 from IBM 701 at JNWPU Suitland (line 14)**: ✓
- **IBM 701 Williams tube failures every 30 minutes (line 16)**: ✓
- **EMC quote "very disappointing and not usable by forecasters" footnote 1 (line 16)**: ✓
- **IBM 704 with magnetic core memory and hardware floating-point (line 18)**: ✓
- **Shuman 1989 retrospective quote (line 22)**: ✓ Verbatim.
- **First operationally effective model 1958 — improved barotropic on IBM 704 (line 24)**: ✓
- **S1 score: 70 worthless, 20 near-perfect (line 24)**: ✓
- **IBM 7090 first delivered late 1959 (line 34)**: ✓
- **"709-T" project name → "seven-oh-ninety" (line 36)**: ✓
- **50000+ germanium alloy-junction transistors, SMS cards (line 36)**: ✓
- **6× faster than 709, $63500/month rental (line 38)**: ✓ POST18_REVIEW Note A confirms 6× faster than 709 is correct (vs. 709, not 704).
- **2.18 µs memory cycle (Stretch project lineage), ~100000 FLOPS (line 38)**: ✓
- **NMC installed IBM 7090 in 1960 (line 40)**: ✓
- **IBM 7094 in 1963 — doubled index registers from 3 to 7, hardware double-precision FP (line 42)**: ✓
- **1962 three-layer hemispheric baroclinic model (line 44)**: ✓
- **John Glenn February 20, 1962, Friendship 7 (line 52)**: ✓
- **Two IBM 7090s at Goddard, IBM 709 in Bermuda (line 52)**: ✓ POST18_REVIEW Note E confirms.
- **Katherine Johnson hand-checked 7090 calculations (line 54)**: ✓
- **Three IBM 7094s at Goddard for Gemini, JPL had three more (line 56)**: ✓
- **Briarcliff Manor SABRE for American Airlines (line 62)**: ✓
- **Thule BMEWS, ~30 years operational (line 62)**: ✓
- **Kubrick *Dr. Strangelove* 1964, *Hidden Figures* 2016, *Event Horizon* 1997 (line 64)**: ✓
- **IBM ~300 7090/7094 machines, $2.9M purchase, $63500/month (line 66)**: ✓
- **1961 Bell Labs Murray Hill, IBM 7094 sang "Daisy Bell" (line 72)**: ✓
- **John L. Kelly Jr., Carol Lockbaum, Max Mathews (line 74)**: ✓
- **"Daisy Bell" 1892 music-hall tune "Bicycle Built for Two" (line 74)**: ✓
- **Arthur C. Clarke, John R. Pierce, *2001: A Space Odyssey* HAL "Daisy Bell" (lines 76–78)**: ✓
- **CTSS at MIT on 7094 (line 82)**: ✓
- **Minovitch UCLA 7090 three-body problem → Voyager (line 82)**: ✓
- **TIROS-1 launched April 1, 1960, 11:40 UTC, 122 kg, 42 in × 22 in (line 90)**: ✓ Height now corrected.
- **Two vidicon cameras at ~700 km, 99-min orbit (line 90)**: ✓
- **78 days operation, ~23000 photos, ~19000 usable (line 94)**: ✓
- **Sutcliffe 1956 quote "We are taught to look for the day..." footnote 4 (line 110)**: ✓
- **Sutcliffe "I am happy to claim membership in the forecasters group" (line 112)**: ✓
- **CDC 6600 1964, Seymour Cray, ~3M instructions/second, ~400000 silicon transistors, Freon cooling, 100 ns clock (line 142)**: ✓ POST18_REVIEW Note B confirms 400000 (not 250000 as in some research files).
- **CDC 6600 ten 12-bit peripheral processors (line 142)**: ✓
- **Watson "our industry leadership position" memo, "34 people including the janitor" (line 144)**: ✓ CORRECTED.
- **Six-layer primitive equation model operational mid-1966 (line 148)**: ✓
- **Shuman & Hovermale 1968 in *J. Applied Meteorology* (line 148)**: ✓
- **"highly significant improvements" quote — first 14 months of operational use (line 150)**: ✓ Verified verbatim.
- **June 1966 first global forecast at NMC (line 150)**: ✓
- **CDC 7600 world's fastest 1969–1975 (line 152)**: ✓ POST18_REVIEW confirms.
- **By 1969, NWP useful (line 158)**: ✓
- **Cressman left NMC 1964 (line 162)**: ✓ CORRECTED.
- **Shuman director 1964–1981, continued research until 1986, Silver Medal 1957 / Gold Medal 1967 (line 162)**: ✓
- **Cressman objective analysis 1959 (line 164)**: ✓
- **ENIAC 1950, 19 years to 1969 (lines 166, 172)**: ✓
- **Shuman died July 29, 2005 age 86 of CHF in Fort Washington MD; *Washington Post* obit headline (line 192)**: ✓ Matches `Shuman.md`.
- **Cressman died April 17, 2008 age 88 of Alzheimer's in Rockville MD; IMO Prize 1977; AMS president 1978 (line 192)**: ✓
- **Seymour Cray died October 5, 1996, car accident, Colorado Springs, age 71 (line 192)**: ✓

### Language

- Em-dashes consistent. ✓
- No curly quotes. ✓
- Line 132 introduces Shuman through callback to JNWPU first employee — works.
- Line 138: "Then Seymour Cray built his masterpiece." — punchy lead-in.
- Line 188: "But that is a story for a future post." — ⚠️ **FORWARD-LOOKING PHRASE.** Per the user's note in `feedback_no_forward_promises.md`: "don't tease upcoming posts or mention series plans." This sentence does exactly that. **PRIORITY: HIGH.**
- Line 196: "When it works, nobody notices. When it fails, everyone complains." — strong closing.

### Forward-looking phrases

⚠️ **Line 188**: 
> "The next step would be Seymour Cray's purpose-built supercomputers -- machines that would push NWP from hemispheric to global, from six layers to dozens, from deterministic to ensemble. **But that is a story for a future post.**"

This is exactly the kind of forward-looking promise the user has flagged as off-limits (`feedback_no_forward_promises.md`, corrected post-Arakawa 2026-04-22). **REQUIRED EDIT**: Either remove this whole sentence, or rewrite to remove the future-post tease.

Suggested replacement: 
> "The next step would be Seymour Cray's purpose-built supercomputers -- machines that would push NWP from hemispheric to global, from six layers to dozens, from deterministic to ensemble."

(Just delete "But that is a story for a future post." and end the paragraph there.)

### Character

- Cressman, Shuman, Cray, Glenn, Johnson, Kelly, Lockbaum, Mathews, Clarke, Pierce, Watson Jr., Sutcliffe, Minovitch all introduced effectively.
- Cross-references to JNWPU/Suitland/IBM 701 post (line 14, 40, 132, 162) and ENIAC/Charney post (lines 20, 172) all functional.

### Verdict

**APPROVED with one HIGH priority fix.** All POST18_REVIEW factual corrections (Cressman 1964, TIROS height 22 inches, Watson memo) have stuck. The post is otherwise solid.

**Required edit:** Remove "But that is a story for a future post." from line 188 (the forward-looking promise that violates the no-forward-tease rule).

---

## Cross-post consistency check

Verified that recurring details are consistent across the five posts:

- **JNWPU established July 1, 1954, Suitland, FOB 4** — Posts 14 and 18 agree. ✓
- **IBM 701 MTBF ~30 minutes** — Posts 14 and 18 agree. ✓
- **First operational forecast May 6, 1955** — Posts 14 and 18 agree. ✓
- **Shuman 1951 MIT D.Sc.** — Post 14 says "1951 MIT doctorate" (line 264). Verified.
- **Shuman as JNWPU's chief modeler / first employee (1954)** — Posts 14 and 18 both correctly characterize him. ✓
- **Cressman 1919–2008** — Posts 14 and 18 agree. ✓
- **Cressman left NMC**: Post 14 line 248 says he "would lead the JNWPU for a decade, then run the National Weather Service itself from 1965 to 1979." Post 18 line 162 says he "left the NMC directorship in 1964 to become head of the Weather Bureau (later the National Weather Service under NOAA, which was created in 1970)." Both are technically correct (left NMC 1964; NWS proper began 1965 under ESSA), but the **boundary is stated differently**. Not an error in either post, just two different ways of describing the same career step. ✓
- **Smagorinsky on ENIAC team April 1950** — Post 16 line 38 lists "Charney, Ragnar Fjortoft, John Freeman, George Platzman, and Joseph Smagorinsky." This matches `Smagorinsky.md`. ✓
- **GFDL founded 1955 → renamed 1959 → renamed 1963** — Post 16 line 54 has this sequence correct. ✓
- **GFDL moved to Princeton 1968** — Post 16 line 54 says 1968. `Smagorinsky.md` agrees. ✓
- **Manabe at GFDL 1958/1959** — Post 16 line 80 says: "Manabe arrived in Washington, D.C. in 1958 and formally joined the General Circulation Research Section in 1959." ✓
- **LGP-30: 4096 words, 32-bit, magnetic drum, 800 lbs, $47000, ~500 units** — Post 17 figures match `Frankel.md`. ✓
- **Lorenz 1963 paper** — Posts 17 and 18 reference; both correct. ✓
- **CDC 6600 first delivered 1964** — Post 18 line 140. ✓

No cross-post conflicts found.

---

## Summary of required edits

| Post | Priority | Edit |
|------|----------|------|
| Post 14 | OPTIONAL/LOW | Verify Goldstine "in the room" claim at line 134; soften if unsupported |
| Post 15 | NONE | All POLISH_TURING_FACTCHECK corrections stuck |
| Post 16 | NONE | All POST16_REVIEW HIGH corrections stuck |
| Post 17 | MEDIUM | Section heading line 54: "## A Million Punch Cards" → "## Half a Million Punch Cards" |
| Post 18 | HIGH | Line 188: remove "But that is a story for a future post." (forward-looking phrase) |

## Summary of stuck corrections (verified)

- Post 14: All historical specifics verified against research files. ✓
- Post 15: Bombe count (211 + 131 = 340+); January 1940; bomba-vs-Bombe operating-principle clarification; all stuck. ✓
- Post 16: Bronx → NYC/Lower East Side; age 29 → 31; Carbon Brief URL; Daily News "top" → "lobby"; all stuck. ✓
- Post 17: Margaret Hamilton removed (Ellen Fetter not falsely substituted — programmer simply not named); "early 1949" clearance date; Feynman quote handled with paraphrase outside quote marks. Punch cards body fixed but heading still says "A Million." ⚠️
- Post 18: Cressman 1964 (not 1965); TIROS height 22 inches (not 19); Watson memo "our industry leadership position" (not "world's largest computer company"); all stuck. ✓
