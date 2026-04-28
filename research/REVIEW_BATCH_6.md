# REVIEW BATCH 6 -- Posts 22 through 25 (Arakawa, Bryan, Bjerknes, Cray-1)

Reviewed 2026-04-27 against the research base in `research/people/`,
`research/computers/`, and the four post sources in `_posts/`. Punchline-
quality is high across all four; factual accuracy is good with several
specific corrections recommended below.

---

## POST 1 -- 2026-04-22 -- "The Fireman and the Visionary"

### Factual

**HIGH-STAKES facts that hold:**
- Arakawa born 20 July 1927; died 21 March 2021 at 93. **PASS** (matches
  Arakawa.md; not 2020 or 2022).
- Mintz born 30 March 1916, Manhattan; died 27 April 1991, Jerusalem. **PASS**.
- Mintz BA Dartmouth 1937, MS Columbia 1942 geology, PhD UCLA 1949 under
  Jacob Bjerknes; second PhD ever awarded by UCLA Meteorology. **PASS**.
- Mintz Rossby Medal 1990 (post says "the year before his death, in 1990"
  -- correct; 1991 death). **PASS**.
- Arakawa Jacobian: 1966 J. Comp. Phys. (paper cited as 1(1), 119-143 in
  footnote 11). **PASS**.
- Arakawa-Lamb 1977 grids paper: Methods in Comp. Phys. 17, 173-265.
  **PASS**.
- Arakawa-Schubert 1974: J. Atmos. Sci. 31(3), 674-701. **PASS**.
- Charney Report 1979: only Arakawa from the modelling community on the
  panel; Mintz not on it; Manabe and Hansen briefed as outside experts;
  3 +/- 1.5 C climate sensitivity; Woods Hole, July 23-27 1979. **PASS**
  (matches Arakawa.md verbatim).

**ERRORS / inconsistencies to fix:**

1. **"Duane Johnson"** (line 48) -- the 1996 J. Climate tribute was
   co-authored by **D. R. Johnson** (Donald R. Johnson, University of
   Wisconsin atmospheric sciences). Both research files (Arakawa.md
   line 197, Yale_Mintz.md line 298) cite "Johnson, D. R." There is no
   "Duane Johnson" in the meteorological record consistent with this
   tribute. Recommend "Donald Johnson" or simply "D. R. Johnson".

2. **UCLA I machine claim** (line 130) -- the post says the prototype
   ran on "an IBM 709 and then on an IBM 360". The UCLA_GCM.md research
   file (line 113) says the production UCLA I "Ran on IBM mainframes
   (709 then 7094)". The post is internally consistent with later UCLA
   history (IBM 360 came later), but the prototype-era machine
   succession was 709 -> 7094, not 709 -> 360. Recommend "IBM 709 and
   then on an IBM 7094" or simply "an IBM 709 and successor IBMs".

3. **"Nozaki's singular-value decomposition"** (line 194) -- there is
   no "Nozaki SVD" in the canonical computational-science roll call.
   The SVD has multiple historical attributions (Beltrami, Jordan,
   Sylvester analytically; Golub-Kahan-Reinsch computationally). This
   reads like a misremembered name. Recommend either deleting this
   item or substituting "Golub's singular-value decomposition" or
   another well-attested example. **HIGH PRIORITY**: a confidently
   stated wrong name in the closing list undermines the post's
   credibility.

4. **JCP paper "twenty-nine-page"** -- the 1969 Bryan paper (which is
   discussed in the next post, not this one) is 347-376 = 30 pages.
   N/A here.

**Cross-references:**
- Links to Phillips post and Bergen School posts: **PASS** (consistent
  with the existing series).
- "[the Fortran series](/weather/.../God-is-real-unless-declared-integer.html)":
  consistent.

### Language

- Em-dashes / curly quotes / ellipses: **NONE detected** (clean ASCII).
- Tone is punchy but factual; the closing "make sure nothing else he
  built would break under pressure" reads well.
- "headstrong American collaborator named Yale Mintz" (line 18) -- the
  research portrays Mintz as voluble and visionary rather than
  "headstrong"; minor stylistic note, not a factual issue.

### Forward-looking

**ONE forward-looking phrase remains** (line 200):

> "The first two legs we have covered in other posts of this series and
> **will cover again**."

This is a mild forward-looking promise. Recommend deleting "and will
cover again" so the sentence becomes: "The first two legs we have
covered in other posts of this series." Backwards-looking only.

### Character

- Arakawa as "the fireman" framing: holds (the fire-station service
  during 1944-45 is documented).
- Mintz as "the visionary" framing: replaces the previous
  "Brooklyn-Romantic" framing per the redirect at line 7-8 of the
  front-matter. Mintz was Manhattan-born, not Brooklyn, so the new
  title is correct. **Self-disavowed-framing concern is RESOLVED**.
- "Manhattan-born Dartmouth humanist who never learned to program" --
  consistent with research.

### Verdict

**Publish after three small fixes**: replace "Duane Johnson" with
"Donald Johnson" or "D. R. Johnson"; reconsider the IBM 360 mention or
clarify the prototype/UCLA I succession; replace "Nozaki's SVD" or
delete the example. Drop "and will cover again" from the closing
section. After these, the post is in strong shape.

---

## POST 2 -- 2026-04-23 -- "The Man Who Fit the Entire Ocean in Half a Megabyte"

### Factual

**HIGH-STAKES facts that hold:**
- Bryan is **alive, 96, on Princeton AOS roster**. Post is unambiguous
  ("He is ninety-six years old, still listed on the Princeton faculty
  roster"). **PASS**. The pre-2026 confusion with his geologist father
  Kirk Bryan Sr. (1888-1950) does not appear here.
- PhD MIT 1957 under **Edward N. Lorenz**. **PASS** (line 44, "MIT
  between 1953 and 1957", "under Edward N. Lorenz"). Confirmed in
  Kirk_Bryan.md by three independent sources.
- Father Kirk Bryan Sr.: Harvard geologist, heart attack on field trip
  August 1950. Post says "August 1950" (line 28). Kirk_Bryan.md line 22
  confirms "22 August 1950 of a heart attack while leading a geology
  field trip in Colorado". **PASS** (post does not give the exact day,
  only the month -- consistent).
- Pre-MIT Woods Hole 1951-53 with Stommel. **PASS** (line 30).
- 1969 Manabe-Bryan coupled paper, four pages. **PASS** (line 126).
- UNIVAC 1108, half-megabyte, twenty minutes per model day. **PASS**
  (lines 130-131).
- Manabe-Bryan 1969 J. Atmos. Sci. 26(4), 786-789. **PASS**.
- Bryan 1969 J. Comput. Phys. 4(3), 347-376. **PASS**.
- Mike Cox (1941-1989) died of cancer at 48. **PASS** (line 156).
- Rigid-lid `w(z=0)=0` in Bryan 1969. **PASS** (line 104).
- Bryan accepted Agassiz Medal 30 April 2023, age 93. **PASS**
  (line 211, "April 30, 2023", "He was ninety-three").

**ERRORS / inconsistencies to fix:**

1. **"Walter Munk's 1950 theory of the Sverdrup transport"** (line 54)
   -- the **Sverdrup transport** is named after Harald Sverdrup, who
   derived it in 1947 (not Munk). Munk's 1950 paper used the Sverdrup
   transport in his wind-driven gyre solution. Ocean_GCM_origins.md
   line 27 explicitly says "Sverdrup (1947): Interior ocean transport
   balances wind-stress curl (the Sverdrup relation)" and line 29 says
   "Munk (1950): Wind-driven gyres with lateral friction." Recommend
   either rewording as "Walter Munk's 1950 wind-driven gyre solution
   (which used Sverdrup's 1947 transport relation)" or simply "Walter
   Munk's 1950 wind-driven-circulation theory". **HIGH PRIORITY**.

2. **"a twenty-nine-page paper"** (line 20) -- pages 347-376 of JCP
   4(3) is 30 pages inclusive. Minor; could read "thirty-page" or just
   "long" without losing the rhetorical point.

3. **Stommel 1948 paper "three pages and one equation"** (line 34) --
   the paper occupies *Trans. AGU* 29(2), pages 202-206, which is 5
   pages inclusive. The Stommel research file (Henry_Stommel.md line
   47, line 142) and the post itself's reference list (line 301) cite
   "202-206". The "three pages" descriptor is wrong. Even Stommel's
   own usual descriptor of the paper in his autobiographical
   reflections is "four pages" or simply "short." Recommend "five
   pages" or "a few pages" or just "a short paper, with one equation".

4. **"Stommel, at that point thirty-one years old"** (line 34) -- if
   Stommel was born 27 September 1920, and Bryan arrived at WHOI in
   roughly 1951 (post-Yale 1951 BS), Stommel would have been 30 going
   on 31. Defensible (depends on which month of 1951 Bryan started),
   but the phrasing implies Stommel was 31 throughout the formative
   period 1951-53 -- in 1951 he was usually 30. Could be reworded as
   "Stommel, then in his early thirties" to remove the precision.
   Minor.

5. **"Adrian Gill" (footnote 20, line 264)** -- post claims a 1971
   "Bryan and Gill" paper "A note on the heat transport by fluctuating
   currents". Kirk_Bryan.md line 87 describes Bryan-Gill 1971 as
   "the first set of primitive-equation simulations of Southern Ocean
   dynamics". The two descriptions don't match: was the 1971 paper
   about heat transport or Southern Ocean dynamics? This may be a
   mis-titled reference. Recommend verifying the title.

6. **"Pascale Delecluse spent time at GFDL in the late 1980s"**
   (line 186) -- Ocean_GCM_origins.md line 117 says "Pascale Delecluse
   spent time at GFDL in the 1980s" (no specific decade-half). The
   post is consistent if read loosely; minor.

**Cross-references:**
- "[the UCLA GCM I wrote about yesterday](/weather/.../2026/04/22/...)"
  on line 54 -- consistent (post 22 was published on 22 April 2026,
  this post is 23 April).
- Cross-link to Manabe Nobel post (line 178, line 328): **PASS**.
- Lorenz post link (line 44): **PASS**.

### Language

- Em-dashes / curly quotes / ellipses: **NONE detected** (clean ASCII).
- Voice is restrained and effective; the "It is four pages. It ran on
  half a megabyte." closing is strong.
- "Bryan's entire career, in print, has this quality: papers so spare
  that the magnitude of what they invent is invisible unless you know
  what they invented" (line 116) -- excellent line.

### Forward-looking

- **No forward-looking promises detected.** The post is anchored in
  the past and present.

### Character

- "Kirk Bryan" framing: matches the personality records (modest,
  soft-spoken, "gentleman" in the Princeton AOS phrase).
- Stommel as "the founding theorist of modern dynamical oceanography"
  matches Henry_Stommel.md.
- Mike Cox subplot: detailed, accurate, and emotionally resonant.

### Verdict

**Publish after the Munk/Sverdrup correction**, the Stommel page-count
correction, and the Gill 1971 title verification. The "twenty-nine-
page" can stand if "twenty-nine" is loose for 30. The post is
otherwise factually clean and well-paced.

---

## POST 3 -- 2026-04-24 -- "He Made Walker Right"

### Factual

**HIGH-STAKES facts that hold:**
- Born 2 November 1897, Stockholm; died 7 July 1975, Los Angeles.
  **PASS** (lines 22-23, line 30).
- Wife Hedvig Borthen, children Vil (1931) and Kirsten (1934).
  **PASS** (line 20, line 206).
- 1939 family departure from Norway in **July** for an "eight-month
  lecture tour". **PASS** (line 42, "the family would sail from
  Bergen in July"; consistent with Jacob_Bjerknes.md line 161).
- April 9 1940 German invasion of Norway and April 9 1951 Vilhelm's
  death (eleven years to the day). **PASS** (lines 16, 50).
- Three deaths of 1957: Rossby Aug 19, Sverdrup Aug 21,
  Helland-Hansen April 22. **PASS** (line 78). Matches the research
  file's verification (Jacob_Bjerknes.md line 232).
- 1966 Tellus paper title and volume 18(4), 820-829. **PASS**
  (line 122, "vol 18(4), 820-829").
- 1969 MWR paper "Atmospheric teleconnections..." 97(3), 163-172.
  **PASS** (line 130).
- The "chain reaction" phrasing on p. 171 of MWR. **PASS** (line 248,
  footnote 17, "The 'chain reaction' phrasing appears on p. 171").
- Cane-Zebiak 1986 Nature paper. **PASS** (line 164).
- El Chichon volcano masking 1982-83 El Nino satellite signal.
  **PASS** (lines 167-168).
- Gilbert Walker died 4 November 1958 in Coulsdon, Surrey. **PASS**
  (footnote 12, line 238).

**ERRORS / inconsistencies to fix:**

1. **"[on Tuesday]"** (line 60) -- the post is dated 24 April 2026
   (Friday), and references the UCLA GCM post dated 22 April 2026.
   Per the calendar, **22 April 2026 was a Wednesday**, not a Tuesday.
   Recommend either "[on Wednesday]" or, more safely (since the day
   reference adds little), simply "[two days ago]" or "[earlier this
   week]" or remove the parenthetical and let the link speak for
   itself. **MEDIUM PRIORITY**: a wrong day-of-week is a small
   trip-up but is verifiably wrong.

2. **ECMWF first director claim** -- The post does not claim
   anything about ECMWF director Wiin-Nielsen vs Bengtsson; it
   doesn't appear here, so this is a non-issue. (Note for the
   Cray-1 post separately.)

3. **"Jorgen Holmboe ... Holmboe's 1945 paper on baroclinic
   instability (known to every graduate student as the Eady-Holmboe
   analysis)"** (line 58) -- the **Eady-Holmboe** name combination is
   non-standard. The canonical analysis is "Eady (1949)" or "Charney
   (1947)" for baroclinic instability. Holmboe's 1945 contribution
   is sometimes called the **Holmboe instability** but for stratified
   shear flow, not for baroclinic eddies. Could be conflating two
   different "Holmboes"/instabilities. Recommend verifying the
   1945 Holmboe paper and removing the "Eady-Holmboe" attribution
   unless solidly sourced.

4. **"first American department of meteorology at a civilian
   university"** (line 22) -- this overstates. MIT had a meteorology
   department from the early 1930s under Carl-Gustaf Rossby; NYU and
   Chicago also had programmes pre-1940. UCLA was a major early
   civilian programme but was not the first. Recommend softening to
   "one of the first" or specify "first West Coast department".

5. **"Mintz defended his PhD under Jacob in 1949. It was the second
   doctorate the UCLA Meteorology Department ever awarded."**
   (line 60) -- consistent with research files. **PASS**. (Charney
   1946 was the first; Holmboe was Charney's adviser, with Bjerknes
   co-supervising, per Jacob_Bjerknes.md line 213.)

6. **The Stommel age claim** does not appear here.

7. **Yule-Walker equations attribution** (line 98) -- post says
   "named jointly after Walker and the British statistician Udny
   Yule". This is correct; Yule was British, the equations are
   Yule-Walker. **PASS**.

8. **"Klaus Wyrtki ... had settled at Scripps and then at the
   University of Hawaii"** (line 116) -- Yale_Mintz.md and other
   research describe Wyrtki as initially at Scripps and then at
   Hawaii. **PASS**.

9. **Schopf-Suarez "delayed-oscillator" theory dated 1988**
   (line 152) -- both research and ENSO_discovery_history.md
   confirm 1988. **PASS**. (Note: the post mentions Cane-Zebiak
   formalised in 1985 -- the canonical paper is 1986 in Nature
   reporting on 1985 work; ENSO_discovery_history.md line 244-247
   uses 1985-86 framing. Acceptable.)

**Cross-references:**
- Bergen School posts (line 16, line 30): **PASS**.
- The Fireman and the Visionary (line 20, line 60, line 306):
  **PASS**.
- The Man Who Fit the Entire Ocean (line 192, line 307): **PASS**.

### Language

- Em-dashes / curly quotes / ellipses: **NONE detected**.
- Pacing is excellent; the "He died seventeen months after the
  International Geophysical Year began collecting the data that would
  vindicate him -- and eleven years before Jacob Bjerknes ... published
  the paper that would do the explaining" closure on Walker is
  particularly strong.
- "The Pacific told him. He listened." closing line (line 210) is
  punchy.

### Forward-looking

- **No forward-looking promises detected.**

### Character

- Bjerknes as the second-act hero who reinvents himself in his
  sixties: holds (the 1957 deaths trigger the Pacific work; 1966 and
  1969 papers come at ages 69 and 71).
- Walker as posthumous vindicatee: holds; tragic-symmetry framing in
  ENSO_discovery_history.md anecdote (3) and the post's main argument
  align.
- "He Made Walker Right" title: works as a tribute. Walker died Nov
  1958; Bjerknes 1969 paper made the case. The retitle from the
  earlier "The Man Who Coupled the Pacific" (per redirect_from line
  8) is a meaningful improvement -- it foregrounds the relationship
  to Walker rather than a generic "coupling" metaphor.

### Verdict

**Publish after the day-of-week fix** ("Tuesday" -> "Wednesday" or
remove), the **Eady-Holmboe verification** (likely needs deletion),
and the "first American department of meteorology" correction. The
post is otherwise factually solid and stylistically the strongest of
the four.

---

## POST 4 -- 2026-04-27 -- "The Machine That Looked Like Furniture"

### Factual

**HIGH-STAKES facts that hold:**
- Cray born September 28, 1925, Chippewa Falls. **PASS** (line 31).
- Cray died October 5, 1996 at 71. **PASS** (line 159; "September 22,
  1996" accident, "two weeks after the accident" died Oct 5).
- Sept 22 1996 was a Sunday. Verified by `cal`. **PASS**.
- I-25 near Air Force Academy, Jeep Cherokee, rolled three times.
  **PASS** (line 159).
- NCAR took delivery serial #3 on July 11, 1977 in two refrigerated
  freight trucks. **PASS** (line 18, "July 11, 1977", "two
  refrigerated freight trucks"; Cray-1.md line 96 confirms "two
  refrigerated electronic vans").
- Price $8.86M ($7.9M + ~$1M for disks). **PASS** (line 18; Cray-1.md
  line 97-98 confirms).
- Decommissioned January 27, 1989. **PASS** (line 167).
- I.M. Pei selected 1961, ground broken April 1964, completed 1966,
  dedicated 1967, modeled on Anasazi cliff dwellings of Mesa Verde.
  **PASS** (lines 105-107; Cray-1.md line 113-114 confirms).
- Walter Orr Roberts founding director NCAR 1960. **PASS** (line 105).
- Warren Washington Aug 28, 1936 - Oct 18, 2024; second Black PhD in
  meteorology after Charles E. Anderson. **PASS** (lines 115, 117,
  123).
- ECMWF first Cray-1A installed October 24, 1978. **PASS** (line 145;
  Cray-1.md line 165 confirms).
- Wiin-Nielsen first ECMWF director (1974-1979). **PASS** (line 143).

**ERRORS / inconsistencies to fix:**

1. **"five-year goal" anecdote attribution** (line 47) -- post says
   "Norris invested 250 000 dollars in startup capital ... asked his
   old engineer to put together a five-year plan." Seymour_Cray.md
   line 70 confirms the $250000 figure and the famous reply but is
   careful: "According to one account, Norris reportedly invested..."
   The post presents it as fact; consistent with the dominant
   tradition. **OK**.

2. **"Cray-3 spun off into a separate company called Cray Computer
   Corporation"** (line 155) -- post says "In 1989 Cray spun off his
   next project". Seymour_Cray.md line 96 says Cray relocated in
   1988 to Colorado Springs with the Cray-3 project, and CCC was the
   spinoff entity (1989). The post is consistent.

3. **"only one production Cray-3 was ever delivered, in May 1993"**
   (line 155) -- Seymour_Cray.md line 104 says "Delivered to NCAR on
   May 24, 1993". Consistent.

4. **"Cray Computer Corporation filed for Chapter 11 bankruptcy on
   March 24, 1995"** (line 155) -- Seymour_Cray.md line 106 confirms
   exact date. **PASS**.

5. **"Cray Research, in 1976-78, built the **Cray Fortran
   Translator** -- usually known as **CFT**"** (line 131) -- this is
   correct. **PASS**.

6. **The 1976 'world's most expensive love seat' attribution to
   Steve Callahan** (line 17) -- the research (Cray-1.md line 57)
   says the phrase has been attributed to *Computerworld* and to
   "Richard M. Russell's editor at Auerbach, Steve Callahan." The
   post phrases it as "the editor Steve Callahan" but does not state
   that he was at Auerbach (a publisher of computer-trade reports),
   not at Computerworld. Minor; the post does mention it was a "1976
   *Computerworld* article" earlier on line 80. The attribution is
   a little loose but defensible.

7. **"Cray-2 ... shipped about thirty units"** (line 153) -- the
   research files don't specifically confirm this number. Could be
   verified externally before publication. Defer.

8. **"Wiin-Nielsen ... served as ECMWF's first Director from January
   1, 1974, through December 31, 1979."** (line 143) -- exact dates
   match Cray-1.md line 159. **PASS**.

9. **Bengtsson as later director-general 1982-1990** -- post says
   "Bengtsson, who would become Director-General from 1982 to 1990"
   (line 143). Cray-1.md line 161 says "later became Director-General
   (**1982-1990**)". **PASS**.

10. **N48 spectral model for ECMWF first operational forecast**
    (line 145) -- Cray-1.md line 167 says "using the **N48 grid
    model**". The post says "N48 spectral model"; the research file
    says "grid model". This is a meaningful technical distinction.
    Note: ECMWF's first operational model from 1979 was the **N48
    grid-point model**; ECMWF moved to a spectral model only later
    (April 1983, T63 spectral). The post should say "grid model" or
    "N48 grid-point model", not "N48 spectral model".
    **HIGH PRIORITY**: this is a factual error about a model the
    blog audience cares about.

11. **"2024-era HPE Cray EX systems that NCAR runs in Cheyenne
    today"** (line 167) -- NCAR's current system is "Derecho" (HPE
    Cray EX, operational since 2023), succeeding "Cheyenne" (SGI/HPE
    ICE XA, 2017-2023). Calling it "HPE Cray EX" is correct.
    **PASS**.

12. **Cray-1 "5.5-ton C-shaped cylindrical computer"** (line 11) --
    Cray-1.md line 47 confirms 5.5 tons including the Freon system.
    **PASS**.

13. **115 kilowatts of heat / 230 kilowatts total power** (line 16,
    line 78) -- Cray-1.md line 48-49 confirms both figures. **PASS**.

14. **1 662 modules in 113 different varieties** (line 16) --
    Cray-1.md line 36 confirms exact figures. **PASS**.

15. **"30 construction workers, engineers, and helpers"** to move
    the machine (line 18) -- Cray-1.md line 96 says "more than 30".
    Post phrases as "Thirty construction workers, engineers, and
    helpers were needed". Consistent (the Cray-1.md says "more than
    30" which the post simplifies to 30). Acceptable.

**Cross-references:**
- Manabe Nobel post (line 119, line 288): **PASS**.
- The Fireman and the Visionary (line 119, line 289, line 134, line
  170): **PASS**.
- The Man Who Fit the Entire Ocean (line 134, line 290, line 170):
  **PASS**.
- The Language That Refused to Die (line 129, line 291): **PASS**.
- The Swedes Got There First (line 143, line 292): **PASS** (the
  Wiin-Nielsen training under Rossby in Stockholm during the BESK
  era is consistent with the existing Sweden post).

### Language

- Em-dashes / curly quotes / ellipses: **NONE detected**.
- Voice is sustained and appealing; "IBM made boxes. Cray made
  furniture." (line 80) is a memorable line.
- "the people writing the cheques wanted, deeply, to own one"
  (line 173) is well-judged.
- The closing "The mathematics of the atmosphere did not require a
  beautiful computer. The career of the man who designed the computer
  did. Both got what they needed." is an excellent landing.

### Forward-looking

- **No forward-looking promises detected.**

### Character

- Cray as the "Hermit of Chippewa Falls": consistent with the
  Seymour_Cray.md research portrait (silent rooms, #3 Ticonderoga
  pencil, graph paper, no CAD).
- Washington as the boy from Portland whose counsellor told him to
  attend business school: consistent with Warren_Washington.md.
- The "Rollwagenisms" caveat on line 41 properly tags the
  embellishment of the elf/tunnel/sailboat stories. Good faith-honest.

### Verdict

**Publish after the N48 grid-vs-spectral correction**. The post is
otherwise the most polished of the batch and a fine cap to the
sub-series.

---

## CROSS-CUTTING NOTES

### Em-dashes / curly quotes / ellipses
**ALL FOUR POSTS clean of Unicode punctuation.** Verified by grep on
`[–—‘’“”…]` -- zero matches.

### Forward-looking phrases
- Post 22 (Arakawa): one mild forward-looking phrase -- "The first
  two legs we have covered in other posts of this series and **will
  cover again**" (line 200). Recommend trim.
- Posts 23, 24, 25: no forward-looking phrases.

### Self-disavowed framings
- Post 22 ("The Fireman and the Visionary"): the previous title
  "The Fireman and the Brooklyn Romantic" was retitled because Mintz
  was Manhattan-born (the redirect at line 8 preserves the old URL).
  The new title is correct and self-consistent. **NO further action
  needed on this front.**
- Posts 23, 24, 25: no self-disavowed-framing concerns.

### Cross-references between posts (verified)
- Bryan post -> Manabe Nobel: **PASS**
- Cray-1 post -> Mintz/Arakawa: **PASS**
- Cray-1 post -> Bryan: **PASS**
- Cray-1 post -> Manabe: **PASS**
- Bjerknes post -> Mintz/Arakawa: **PASS**
- Bjerknes post -> Bryan: **PASS** (line 192)

### Day-of-week errors
- Post 24 (Bjerknes) line 60: "[on Tuesday]" referring to the
  22 April 2026 Arakawa post. **22 April 2026 was a Wednesday.**

### Page-count nits
- Post 23 (Bryan) line 20: "twenty-nine-page paper" should be
  thirty-page (347-376).
- Post 23 (Bryan) line 34: Stommel 1948 "three pages and one
  equation" -- actual span 202-206 (5 pages).

---

## PRIORITY-RANKED FIX LIST

**HIGH (factual errors that any informed reader would catch):**
1. Post 22, line 48: "Duane Johnson" -> "Donald Johnson" or "D. R.
   Johnson".
2. Post 22, line 194: "Nozaki's singular-value decomposition" --
   replace or delete.
3. Post 23, line 54: "Munk's 1950 theory of the Sverdrup transport"
   -- the Sverdrup transport is Sverdrup 1947.
4. Post 24, line 60: "[on Tuesday]" -> "[on Wednesday]" or remove.
5. Post 25, line 145: "N48 spectral model" -> "N48 grid-point model"
   (ECMWF moved to spectral only in 1983).

**MEDIUM (small inaccuracies that would erode credibility):**
6. Post 22, line 130: UCLA prototype "IBM 709 and then on an IBM
   360" -- the UCLA I succession was 709 -> 7094.
7. Post 23, line 34: Stommel 1948 "three pages" -- actual is 5
   (202-206).
8. Post 23, line 20: "twenty-nine-page paper" -- 347-376 = 30.
9. Post 23, footnote 20: Bryan-Gill 1971 paper title verification
   (heat transport vs Southern Ocean).
10. Post 24, line 22: "first American department of meteorology at a
    civilian university" overstates -- soften to "first West Coast"
    or "one of the first".
11. Post 24, line 58: "Eady-Holmboe analysis" non-standard --
    verify or remove.

**LOW (stylistic adjustments):**
12. Post 22, line 200: drop "and will cover again".
13. Post 23, line 34: Stommel "thirty-one years old" might be 30 in
    early 1951; could be reworded to "in his early thirties".

---

## OVERALL VERDICT

These four posts are the strongest cluster in the series so far. They
are punchy, factually defensible on the high-stakes claims, free of
Unicode-punctuation artefacts, and effective at carrying recurring
characters (Mintz, Bjerknes, Manabe, Stommel) across post boundaries.
After the high-priority fixes above, all four are publishable to the
same standard as posts 19-21.

The strongest of the four is **Post 24 (Bjerknes / "He Made Walker
Right")** -- the family-arc structure, the 1957 three-deaths motif,
and the Walker-vindication-by-Bjerknes payoff are unusually well
braided. The weakest is **Post 23 (Bryan)** purely because of the
Munk/Sverdrup confusion and the Stommel page-count slip; both are
easy fixes.
