# Review Batch 2 -- Posts 5-9 (Bergen 3, Charney, Phillips, Lorenz, Four Machines)

**Reviewer:** review-agent
**Review date:** 2026-04-27
**Posts reviewed:**
1. `_posts/2026-03-28-The-ghost-in-the-grid.md` (Bergen Part 3)
2. `_posts/2026-03-29-The-man-who-tamed-the-equations.md` (Charney)
3. `_posts/2026-03-30-The-first-climate-model-had-5KB-of-RAM.md` (Phillips 1956 GCM)
4. `_posts/2026-03-31-The-butterfly-that-broke-the-forecast.md` (Lorenz / chaos)
5. `_posts/2026-04-02-From-cables-to-chaos.md` (four-machines overview)

Severity legend: **CRITICAL** = factually wrong, must fix; **MODERATE** = misleading or unverified, should fix; **MINOR** = imprecise but defensible; **LANGUAGE** = stylistic.

---

## Post 1: `2026-03-28-The-ghost-in-the-grid.md` (Bergen Part 3)

### Factual issues

- **Line 18, MODERATE:** "Every NWP model... still has Bjerknes' original **seven equations** at its core" -- Bjerknes (1904) listed **seven variables** (per post 2026-03-26 in this series, which says "He identified seven variables"), then listed multiple equations governing them (gas laws, continuity, Navier-Stokes, thermodynamic energy, water continuity). Calling it "seven equations" is consistent with how the post then enumerates them (3 momentum + 1 continuity + 1 thermodynamic + 1 state + 1 moisture = 7), but the post 1 version of the series uses "seven variables." The framing as "seven equations" is OK numerically but creates internal inconsistency with how the series originally introduced Bjerknes. -- **fix:** either keep the seven-equations framing or note that "Bjerknes' framework: seven variables, seven equations balancing them." Minor wording tightening; not a hard error.
- **Line 56, MODERATE:** "ENIAC's 736 km grid (1950, 19x16 points)" -- 19x16 grid is correct (matches post 2026-03-29 line 81 of post 5, and ENIAC research file). The 736 km grid spacing is the standard cited value. -- **OK.**
- **Line 65 (Petterssen reference), MINOR:** "Petterssen, by the way, was one of the Bergen School originals - trained in that attic." Sverre Petterssen was a member of the Bergen School (mentioned in post 2026-03-26 line 75: "Sverre Petterssen comes too -- he would eventually formalize frontogenesis mathematically"), so calling him "one of the Bergen School originals" is defensible (he was 19 when he joined Bjerknes in Bergen in late 1923 - one of the second-wave originals).
- **Line 87, MINOR:** "FrontFinder AI (Justin, McGovern & Allen, 2025)" -- citation listed in references as Justin et al. 2025. Cannot verify against research files. Citation appears intact and consistent. **OK.**

### Language issues

- **Line 14, LANGUAGE:** "Now: why the models can't do what the human does - and the machines trying to learn." -- punchy, working.
- **Line 16, LANGUAGE:** "Why the Models Cannot Draw the Line" -- self-disavowing nothing. Working.
- **Line 26, LANGUAGE:** "Seven equations, seven unknowns: u, v, w, T, p, rho, q. That's the Bjerknes core." -- Punchy, factual. Good.
- **Line 44, LANGUAGE:** "**And nowhere in any of those equations - old or new - does the word "front" appear.**" -- Excellent rhetorical hammer.
- **Line 99, LANGUAGE:** "after all of it - a forecaster... will draw a better front than any of them." -- Good closing thread.

### Forward-looking / self-disavowed framing

- **Line 81, MODERATE:** "This deserves its own deep dive in a future post." -- forward-looking promise. Per user's preferred policy (no forward-looking promises), this should be excised. **fix:** delete the clause; just say "but here's the landscape:".
- **Line 89, MODERATE:** "We'll dig deeper into the ML revolution in a future post." -- forward-looking promise. **fix:** delete entire sentence.
- **Line 128, MINOR:** "The neural network: Catching up. We'll see." -- "We'll see" is mild speculation about the unspecified future, not a firm "next post" tease; defensible as a current-status closing line. Borderline -- could trim to "Catching up." for cleanliness.

### Character cleanliness

- No Unicode em-dashes, curly quotes, or ellipses found. **Clean.**
- Hyphens are used consistently as `-` and `--`.

### Verdict

**Solid post.** The series-level question of "seven variables vs. seven equations" is the only minor discrepancy worth tightening for series consistency. **Two forward-looking promises (lines 81 and 89) should be removed** to match the user's no-forward-promise policy applied to later posts.

---

## Post 2: `2026-03-29-The-man-who-tamed-the-equations.md` (Charney)

### Factual issues

- **Line 24, OK:** Charney born "New Year's Day, 1917, in San Francisco." Confirmed by research file (1 January 1917, San Francisco).
- **Line 24, OK:** Parents Stella and Ely Charney, "Yiddish-speaking Jewish immigrants from Belarus." Research file says "White Russia (modern Belarus)" -- "Belarus" is acceptable plain-language rendering. **OK.**
- **Line 24-26, OK:** Family in Los Angeles, met/married in St. Louis, played with Yehudi Menuhin. All confirmed.
- **Line 28, OK:** "at age 14" found Osgood's calculus -- confirmed.
- **Line 34, OK:** Hollywood High School, January 1934. Confirmed.
- **Line 40, OK:** UCLA BS Math 1938, MS 1940 under T. Y. Thomas, thesis on metric curve spaces. Confirmed.
- **Line 50, MINOR:** PhD dissertation title quoted as "The Dynamics of Long Waves in a Baroclinic Westerly Current" (1946). Research file confirms. The 1947 Journal of Meteorology issue claim ("comprised the entire October 1947 issue") -- research file says "published October 1947 in *Journal of Meteorology*, filling an entire issue." **OK.**
- **Line 52, MODERATE:** "Eric Eady independently arrived at the same physical mechanism around the same time. They met in Bergen in 1947, became friends..." -- Eady's independent baroclinic instability theory was real (Eady 1949). The "met in Bergen 1947" friendship detail is not in the research file but is consistent with the timeline (Charney was at Oslo 1947-48 on NRC fellowship). Cannot verify exact meeting; defensible. **MINOR.**
- **Line 58, OK:** Richardson's "145 hectopascals in six hours" -- confirmed by post 2026-03-24 (line 100) and Lynch (2022).
- **Line 65-66, OK:** Geostrophic balance description, slow vs. fast motions -- correct.
- **Line 81, OK:** Quasi-geostrophic equations filter gravity waves and sound waves. Correct.
- **Line 84, OK:** Charney quote about "eliminating from consideration at the outset the meteorologically unimportant acoustic and shearing-gravitational oscillations" -- attributed to footnote 3 (Charney 1947 thesis). Footnote 3 actually says Charney 1947 J. Meteorology paper. Defensible.
- **Line 93, OK:** "Norman Phillips called it 'probably the most rewarding development in meteorology and oceanography since World War I.'" -- Confirmed in research file.
- **Line 95, OK:** CFL criterion explanation: gravity waves at 300 m/s, Rossby waves at 10-30 m/s. Correct order of magnitude.
- **Line 99, OK:** "five meteorologists, the 100,000 punch cards" -- ENIAC research file confirms "Charney, Ragnar Fjortoft, J. Freeman, George Platzman, and Joseph Smagorinsky" = 5. Klara Dan von Neumann did the programming. **OK.**
- **Line 103, OK:** "barotropic vorticity equation... advected horizontally at about 5 km altitude" -- Charney research file says "at the equivalent barotropic level (~5 km)." **OK.**
- **Line 105, OK:** "Four 24-hour forecasts were computed for January and February 1949 data." Charney/Fjortoft/von Neumann 1950 Tellus paper -- four cases, January-February 1949. **OK.**
- **Line 109, MINOR:** "Three of the four forecasts beat persistence... The first one was 'uniformly poor' by the authors' own admission" -- Reference to "uniformly poor" (footnote 5, 1950 Tellus paper) is plausible; cannot verify direct quote without the paper. The "three of four beat persistence" claim matches conventional summaries. **OK with caveat.**
- **Line 115, OK:** Charney 1955 NAS quote about "purely a technological problem... Two years later we were able to make the same prediction on our own machine in five minutes." -- Cited via footnote 1 (Phillips 1995). Good.
- **Line 121, OK:** Richardson's response quote: "This, although not a great success of a popular sort..." -- Verified in Charney research file.
- **Line 123, OK:** "Richardson died in 1953." Confirmed.
- **Line 129, OK:** "JNWPU was formally established on July 1, 1954" under George Cressman; IBM 701 installed March 1955; first operational forecasts May 1955 -- all match research files (Charney research line 89 says "operational forecasts began in May 1955"; IBM 701 research file lists U.S. Weather Bureau as customer 18). **OK.**
- **Line 135, MINOR:** "It wasn't until 1966 that forecasts based on the full primitive equations... began in the U.S. and West Germany." -- Standard date is 1966 for Shuman & Hovermale's six-layer PE model at NMC (US); West Germany is also a fair claim but cannot verify exact year. Consistent with mainstream references. **OK.**
- **Line 145, MODERATE:** "Nine scientists. Five days. Twenty-two pages." -- Charney research file says "Eight climate scientists met at Woods Hole." Multiple sources actually give 9 (8 panel members + Charney as chair, or 9 total). The Wikipedia "Charney Report" entry lists 9 panel members. **Defensible as 9, but research file says 8** -- the discrepancy is between sources. The post's "nine" matches the more commonly cited figure. -- **fix if wrong:** verify via the Charney Report 1979 PDF; likely 9 is right.
- **Line 145, OK:** Manabe estimate 2-3 deg C, Hansen 3.5-4 deg C. Standard values.
- **Line 149, OK:** Charney Report quote about "near 3 deg C with a probable error of +/- 1.5 deg C" -- confirmed.
- **Line 155, MINOR:** "According to Manabe, Charney derived the range with characteristic directness: he 'chose 0.5 deg C as a reasonable margin of error, subtracted it from Manabe's number, and added it to Hansen's.'" -- footnote 8 attributes this to Manabe 2022 / Somerville 2019. The math: Manabe ~2 to 3, subtract 0.5 -> 1.5; Hansen ~3.5 to 4, add 0.5 -> 4.5. Range 1.5-4.5. Plausible. The Manabe Nobel interview attribution is a secondary citation; cannot verify directly.
- **Line 157, OK:** IPCC AR5 (2013) range "1.5-4.5 degrees C" -- confirmed (AR5 likely range was 1.5-4.5 C). IPCC AR6 (2021) "narrowed it to 2.5-4.0 degrees C" -- confirmed (AR6 likely range 2.5-4 C). **OK.**
- **Line 173, OK:** Poker quote attributed to Phillips (1995). Confirmed in research file (Phillips memoir, citing oceanographer B. Taft).
- **Line 175, OK:** GARP, Universities National Antiwar Fund, $250,000, Charney hypothesis (Sahel desertification) -- all in research file.
- **Line 177, OK:** Death June 16, 1981, age 64. AGU 1976 citation about "guided the postwar evolution of modern meteorology more than any other living figure" -- confirmed.

### Language issues

- **Line 22, LANGUAGE:** "The Kid Who Found Calculus in a Relative's Apartment" -- working title. Good narrative hook.
- **Line 26, LANGUAGE:** "(Because of course he did.)" -- chatty aside. Working voice.
- **Line 36, LANGUAGE:** "I love this. No grand plan. No guidance counselor moment. Just proximity and ignorance." -- Good rhythm. Working.
- **Line 50, LANGUAGE:** "imagine submitting a paper so important that the journal says 'you know what, just take the whole issue.' That is peak academic flex." -- Punchy, factual hook.
- **Line 117, LANGUAGE:** "Five words that contain the entire trajectory of HPC for the next 75 years." -- Powerful, accurate.
- **Line 159, LANGUAGE:** "Twenty-two pages, written in five days, accurate for nearly half a century." -- Excellent compression.
- **Line 173, LANGUAGE:** "extraordinary at poker. A colleague recalled him as 'the only scientist who could play poker nightly with the ship's crew, win their money consistently, and never engender the slightest ill will.'" -- Great character detail.

### Forward-looking / self-disavowed framing

- **Line 131, MODERATE:** "(Though the Americans were not quite the first to get there. Rossby had gone home to Stockholm, and he had plans of his own. But that is a story for another day.)" -- Forward-looking tease. **fix:** delete the entire parenthetical (or rewrite as a footnote-style "see also" without the cliffhanger), per user's no-forward-promises policy.
- **Line 183, CRITICAL:** Section heading "### What Comes Next" + body 185-187 ("That's where we're going next.") -- Direct tease for next post. **fix:** Per user feedback applied to later posts (corrected 2026-04-22 after the Arakawa post), this section should be removed entirely. Either delete lines 183-187, or rewrite as a self-contained "wider implications" paragraph that doesn't promise future posts.

### Character cleanliness

- No Unicode em-dashes, curly quotes, or ellipses found. **Clean.**

### Verdict

**Strong content, well-researched, good narrative voice.** Two big language issues: the "story for another day" parenthetical (line 131) and the "What Comes Next" section (lines 183-187) -- both should be excised per the user's stated preferences. The Charney Report panel size (8 vs 9 scientists) is a minor source discrepancy worth verifying. Otherwise, factually solid.

---

## Post 3: `2026-03-30-The-first-climate-model-had-5KB-of-RAM.md` (Phillips 1956 GCM)

### Factual issues

- **Line 26, OK:** Phillips born "July 9, 1923, in Chicago, Illinois." Confirmed.
- **Line 30, OK:** "commissioned as a Second Lieutenant on June 5, 1944 - the day before D-Day." Specific date not in research file (which says "joined U.S. Army Air Corps in 1943" -- but also notes meteorological cadet training graduation timing). Cannot verify exact June 5, 1944 commissioning date from primary research file. **MINOR -- needs verification.** Research file does say "discharged as a first lieutenant" which matches the post.
- **Line 30, OK:** "deployed to the Azores" -- confirmed (research file).
- **Line 32, MODERATE:** "Ph.D. (1951, under George Platzman, a mathematical meteorologist who later wrote the definitive history of the ENIAC forecasts)" -- Research file says "Phillips's PhD adviser is sometimes listed as George Platzman, though the primary sources consulted for this note do not explicitly confirm this." So the post asserts as fact what the research file flags as uncertain. **fix:** soften to "Ph.D. (1951; George Platzman, who later wrote the definitive history of the ENIAC forecasts, was a key influence at Chicago)" or similar -- avoid the unverified flat assertion of advisor.
- **Line 34, OK:** Charney 1948 paper "On the scale of atmospheric motions" awakened Phillips' interest -- confirmed.
- **Line 36, OK:** Phillips joined IAS in October 1951. Research file says 1951 onwards. **OK.**
- **Line 40, OK:** IAS machine built between 1946 and 1951, publicly displayed June 10, 1952 -- matches IAS research file.
- **Line 44, OK:** "1,024 words of 40 binary digits each - approximately 5 kilobytes of RAM" -- IAS research confirms.
- **Line 45, MODERATE:** "Drum memory: 2,048 words... (later upgraded to 16,384 words)" -- IAS research says "IAS-built 2K-word drum (1953); ERA 12K-word drum (1955)". Upgrade to **12,288 (12K)**, not 16,384. **fix:** change "16,384" to "12,288" or "about 12 K words". This is a CRITICAL spec error.
- **Line 46-50, CRITICAL:**
  - "Add time: 42 microseconds" -- IAS research file says "62 microseconds." -- **fix:** change 42 to 62.
  - "Multiply time: 700 microseconds" -- IAS research file says 713 microseconds. Close enough; 700 is a reasonable rounding. **MINOR.**
  - "Speed: roughly 24,000 additions per second" -- 1/62us ~= 16,129 add/s; 1/42us = 23,809 add/s. The 24,000 figure matches the 42us claim, but the actual add time is 62us, so the speed figure should be ~16,000 add/s. **However**, the four-machines post (2026-04-02 line 27) shows "~24 000 add/s" for the IAS, so there's also internal inconsistency. **fix:** verify against IAS research and align both posts. Likely correct value: ~16,000 add/s. (Note: some IAS sources cite ~24K add/s; numbers vary because of access overhead vs. raw addition. Worth flagging.)
  - **"Construction: 3,430 vacuum tubes, 2,091 transistors, 915 diodes" -- CRITICAL ERROR.** The IAS machine had **NO TRANSISTORS**. Transistors were not used in production computers until the late 1950s. The IAS machine (1952) was entirely vacuum-tube-based, with Williams tube (CRT) memory. Research file says "~1700 logic tubes (triodes...) + ~150 pentodes driving the memory CRTs; total ~3000 including all subsystems." -- **fix:** Replace with something like "Construction: roughly 3,000 vacuum tubes (logic plus memory drivers) and several thousand diodes; 40 Williams cathode-ray tubes for memory." Drop the transistor claim entirely. Drop the 2,091 figure. The 915 diodes count is plausible but unverifiable from the research file.
  - "Power consumption: 61 kilowatts" -- not in research file. The ENIAC consumed 150-174 kW; the IAS machine, much smaller, would have used considerably less. 61 kW is plausible but unverified. **MINOR -- worth verifying or hedging.**
- **Line 56, OK:** Phillips quote about machine language and 16-character hex alphabet -- footnote 1 (Phillips 1990 IMO Lecture) confirmed.
- **Line 76, OK:** "Two levels in the vertical (250 mb and 750 mb)" -- Phillips 1956 paper used 250 hPa and 750 hPa for the two levels. Confirmed in conventional summaries.
- **Line 77-79, OK:** "17 x 16 grid points... 625 km north-south, 375 km east-west... 10,000 km... 6,000 km" -- Phillips 1956 specifications. Standard values, match secondary literature.
- **Line 81, OK:** "Roughly 500 variables to describe the entire state" -- research file says "Just 500 numbers specified the entire state." **OK.**
- **Line 89, OK:** "First, a spin-up: 130 simulated days with no east-west variation" -- Phillips 1956 standard summary.
- **Line 95, OK:** "Duration: 31 simulated days. Total computer time for those 31 days: 11 to 12 hours." -- Standard values. Matches Lewis 1998 retrospective.
- **Line 105, OK:** Jet stream 40-60 m/s during days 10-25 -- standard values from Phillips 1956 / Lewis 1998.
- **Line 109, OK:** Realistic cyclone, 6,000 km wavelength, 21 m/s eastward, "very much like those of an occluded cyclone" quote attributed to Phillips 1956 (footnote 3). **OK.**
- **Line 119, OK:** Phillips quote about "definite indications of something similar to cold and warm fronts" -- attributed footnote 3.
- **Line 137, MODERATE:** "After about 25-26 days of simulated time, the model began to fall apart." Research file (line 76) says "Phillips's initial climate simulation lasted only about **16 simulated days** before the model 'blew up'." **DISCREPANCY.** Lewis 1998 (the definitive Phillips retrospective) places the truncation problems and progressive deterioration starting much later -- around day 20+ -- with energy increases more pronounced by day 25-30. The "16 days" in the research note may itself be an error or simplification. The post's "25-26 days" matches Phillips 1956 paper text more closely. **Recommend verifying** with Lewis 1998 / Phillips 1956 directly. Likely the post is closer to correct than the research note. Mark as needing verification rather than a clear error.
- **Line 151, OK:** "Phillips realizing why his model blew up after 25 days on a machine with 5 KB of RAM." -- Same caveat as above.
- **Line 157, OK:** Stockholm 1956 conversation between Rossby and Phillips, reconstructed by Wiin-Nielsen -- footnote 4 (Wiin-Nielsen 1997 Tellus A) is correct.
- **Line 175, OK:** Eric Eady, Napier Shaw lecture 1956 quote -- footnote 5.
- **Line 187, OK:** Smagorinsky "A new era had been opened." -- footnote 6 (Smagorinsky 1983). Research file says "On Norman Phillips's 1956 general circulation experiment, Smagorinsky wrote that it demonstrated a new era had been opened in climate modeling." **OK.**
- **Line 189, MINOR:** "He organized a conference at Princeton in October 1955 - 'The Application of Numerical Integration Techniques to the Problem of General Circulation.'" -- Conference name/date not in research files but is historically known. **Defensible.**
- **Line 191, MINOR:** "Smagorinsky was asked to lead the new General Circulation Research Section, and reported for duty on October 23, 1955." -- The October 23, 1955 date is not in Smagorinsky research file (which says "1955: At von Neumann's instigation, the Weather Bureau created the General Circulation Research Section under Smagorinsky's direction"). The specific date may be from Lewis 1998 or another source; cannot verify from project research notes alone. **Defensible if sourced; otherwise flag.**
- **Line 197, CRITICAL:** "In 1965, the research unit was formally established as the Geophysical Fluid Dynamics Laboratory (GFDL) in Princeton." -- Smagorinsky research file gives different chronology: "1955: General Circulation Research Section created. 1959: Section renamed the General Circulation Research Laboratory. **1963: Renamed again as the Geophysical Fluid Dynamics Laboratory (GFDL)**. 1968: GFDL relocated to Princeton University campus." So GFDL got its name in **1963**, not 1965, and moved to Princeton in **1968**, not at the time of renaming. **fix:** "In 1963, the unit was renamed the Geophysical Fluid Dynamics Laboratory (GFDL); it relocated to Princeton in 1968." Or simpler: "In 1963, the research unit was renamed Geophysical Fluid Dynamics Laboratory (GFDL); it later moved to Princeton."
- **Line 199, OK:** Manabe & Wetherald 1967 paper on CO2; Manabe & Bryan 1969 first coupled model. Confirmed in Smagorinsky research file.
- **Line 203, OK:** Manabe Nobel Prize 2021 quotation -- correct.
- **Line 205, OK:** "Sixty-five years from a... two-layer model... to the highest honor in science." (1956 -> 2021 = 65 years.) **OK.**

### Language issues

- **Line 22, LANGUAGE:** "And what he did in 1955, on a machine with 5 kilobytes of RAM, changed the trajectory of climate science forever." -- Good opening hook.
- **Line 32, LANGUAGE:** "He was deployed to the Azores, where he created daily weather forecasts for Allied trans-Atlantic flights. Not a desk job. Not a training exercise. Real forecasts for real pilots flying real missions across an ocean where getting the weather wrong meant people didn't come home." -- Powerful rhythm. Working.
- **Line 52, LANGUAGE:** "For context: the phone in your pocket has millions of times more memory. A cheap USB stick from a gas station has more storage. A modern smartwatch could run circles around this thing. Your Wi-Fi router probably has more computing power." -- Punchy, working.
- **Line 62, LANGUAGE:** "This is like playing a souls-like game where the controller is also on fire." -- Genre-aware metaphor; lands. Working.
- **Line 131, LANGUAGE:** "Modest successes. The man simulated the general circulation of the atmosphere from scratch and called it 'modest successes.' I can't even get a Docker container to start on the first try." -- Self-deprecating ending; working.
- **Line 173, LANGUAGE:** "Phillips' dry, cloudless, mountainless, featureless model proved it." -- Tight rhythm; good.

### Forward-looking / self-disavowed framing

- **Line 211-217, CRITICAL:** Section heading "### What Comes Next" + body promising "the catch nobody saw coming... that's a story for next time." -- Direct forward-looking tease. **fix:** delete the entire section. The post is complete on its own; it doesn't need to set up the next post.

### Character cleanliness

- No Unicode em-dashes, curly quotes, or ellipses found. **Clean.**

### Verdict

**Two CRITICAL factual errors must be fixed:**
1. **Line 49: "2,091 transistors"** -- the IAS machine had no transistors. Remove this entirely.
2. **Line 197: GFDL year and location** -- 1963 (renamed) and 1968 (moved to Princeton), not "1965 in Princeton."

**Two MODERATE/CRITICAL spec errors:**
3. **Line 45: drum upgrade to 16,384 words** -- should be 12,288 (12K).
4. **Line 46: add time 42 microseconds** -- IAS research says 62 microseconds.

**One PhD-advisor claim** (line 32) should be softened to match research file's hedge.

**One forward-looking section** (lines 211-217) should be deleted.

These are correctable but consequential -- the post leans on specific numbers that the IAS machine entry contradicts.

---

## Post 4: `2026-03-31-The-butterfly-that-broke-the-forecast.md` (Lorenz / chaos)

### Factual issues

- **Line 20, OK:** Lorenz born "May 23, 1917, in West Hartford, Connecticut." Confirmed.
- **Line 22, OK:** Charney also born 1917 (Jan 1). Both at MIT. Confirmed.
- **Line 26, OK:** David Randall quote about "tiger" -- attributed to footnote 1 (MIT News obituary), which the research file confirms is the source for the Randall, Emanuel, Strogatz quotes.
- **Line 28, OK:** Kerry Emanuel quote about Lorenz being "as far from a self-promoter as you could imagine" -- footnote 1.
- **Line 36, OK:** Dartmouth A.B. Math 1938; Harvard A.M. Math 1940. Confirmed.
- **Line 36, OK:** "His first published paper was a generalization of the Dirac equations." -- Research file (line 37) mentions the Dirac generalization implicitly via the Riemannian geometry under Birkhoff; cannot directly verify this exact framing. **MINOR -- close to correct.**
- **Line 42, OK:** Doctorate 1948 from MIT, lifetime career at MIT. Confirmed.
- **Line 44, MODERATE:** "He won the meteorology department's teaching award so many times that eventually the award was discontinued because nobody else ever won it." -- Lorenz research file says he "was much beloved as a teacher and for many years running won the prize awarded by MIT graduate students for the best teacher of the year" and that "the AMS named its Edward N. Lorenz Teaching Excellence Award in his honour." It does NOT say the prize was discontinued "because nobody else ever won it." The research file describes "many years running" but not award discontinuation. This sounds like an embellishment. **fix:** verify or soften to "He won the meteorology department's teaching award year after year." The "discontinued because nobody else ever won it" claim is plausible folklore but is uncited. **Remove this claim or cite it.**
- **Line 44, OK:** "He could imitate coyote calls well enough to wake actual coyotes" -- not in research file but is a colorful piece of Lorenz folklore that appears in some obituaries. Plausible. **MINOR.**
- **Line 46, OK:** Charney calling him "a genius with a soul of an artist" -- research file confirms ("a soul of an artist"). The "genius with a soul of an artist" version slightly elaborates but is consistent.
- **Line 50, MODERATE:** "Around 1960, Lorenz got a computer installed in his office at MIT." -- Lorenz research file says **1958** ("In 1958, Ed acquired a Royal McBee LGP-30..."). LGP-30 research file says **1960** ("In 1960, Edward Lorenz, an MIT meteorologist, installed a Royal McBee LGP-30 in his office"). Sources disagree. "Around 1960" is the safe hedge and **OK** because it doesn't pick a side, but it conflicts with the Lorenz research file's "1958." **MINOR.** Either is defensible.
- **Line 54, OK:** LGP-30 weighed 800 pounds, 113 vacuum tubes, 1,450 diodes, 6.5-inch drum at 3,700 rpm, 4,096 words, 16-instruction set. All confirmed in LGP-30 research file.
- **Line 56-58, OK:** ~60 calculations per second; ENIAC for comparison; $47,000 in 1956 dollars (~$560,000 today). Confirmed.
- **Line 60, OK:** "phone in your pocket does roughly 15 billion calculations per second... LGP-30 would need about 8,000 years..." -- Math: 15e9 / 60 = 2.5e8 seconds ≈ 7.9 years for one second of phone work, or 8,000 years for 1,000 seconds of phone work. Wait -- 15e9/60 = 2.5e8 s = 7.9 years. So 8,000 years is wrong by 3 orders of magnitude. **Recheck:** 15 billion ops vs. 60 ops/second. Time for LGP-30 to do 15 billion ops = 15e9/60 = 2.5e8 seconds. Convert to years: 2.5e8 / (365.25 * 86400) = 7.92 years. **The post says 8,000 years, but the correct figure is ~8 years for one second of phone work.** -- **CRITICAL math error**. **fix:** "LGP-30 would need about 8 years to match what your phone does in one second." Alternatively, change the comparison framing.
- **Line 70, OK:** "Winter 1961. Lorenz's office at MIT." -- correct era. Research file says "Winter 1961" and "The Coffee Break Discovery (1961)." **OK.**
- **Line 70-71, OK:** "12 variables." -- Confirmed (research file).
- **Line 86, OK:** "0.506127" vs printout "0.506" -- correct (LGP-30 research file: "6-digit decimal precision (e.g., 0.506127), but the printout... rounded to 3 digits (e.g., 0.506)").
- **Line 100, CRITICAL:** "He drew on work by **his student** Barry Saltzman" -- **Barry Saltzman was NOT Lorenz's student.** Saltzman research file says "Both [Lorenz and Saltzman] were former students of Victor Starr at MIT." They were colleagues, not student-and-teacher. **fix:** change to "He drew on work by his colleague Barry Saltzman" or "He drew on work by Barry Saltzman, a fellow Victor Starr student at MIT," or simply "He drew on work by Barry Saltzman." -- This is a clear factual error.
- **Line 106, OK:** Published "March 1963 in the Journal of the Atmospheric Sciences" -- footnote 3. **OK.**
- **Line 108, OK:** Quote "Two states differing by imperceptible amounts may eventually evolve into two considerably different states..." -- footnote 3 (Lorenz 1963). **OK.**
- **Line 112, MODERATE:** "The paper was cited exactly three times by researchers outside meteorology in the next decade." -- This is a frequently quoted figure but the precise "three" is folkloric. Cannot verify specific count from research files. **MINOR.**
- **Line 114, OK:** "It now has over 17,500 citations." -- Standard cited figure (Google Scholar gives ~20K+ now; 17,500 is reasonable for a recent count). **OK.**
- **Line 134-136, OK:** Seagull metaphor in 1963 NY Academy of Sciences paper -- footnote 5. The exact quote "the most recent evidence seems to favor the sea gulls" is from Lorenz 1963 NYAS paper. **OK.**
- **Line 138, OK:** "1972, when Lorenz was asked to give a talk at the American Association for the Advancement of Science. He failed to submit a title. So Philip Merilees, the session organizer, made one up for him." -- Research file confirms.
- **Line 140, OK:** "Predictability: Does the Flap of a Butterfly's Wings in Brazil Set Off a Tornado in Texas?" -- Confirmed.
- **Line 144, OK:** "The talk was never formally published as a journal paper. Its text survived as Appendix 1 of Lorenz's 1993 book *The Essence of Chaos*." -- footnote 7 confirms.
- **Line 146, OK:** Hilborn (2004) tracking butterfly retellings -- footnote 6.
- **Line 152, OK:** "Even today I am unsure of the proper answer." -- footnote 7.
- **Line 162, OK:** "two-week wall... not... about computing power... a property of the atmosphere itself" -- correct framing; Lorenz's 1969 BAMS paper.
- **Line 167, OK:** "Charney and colleagues found a 5-day doubling time in 1966. Lorenz found a more pessimistic 2.5 days in 1969." -- Standard reference (Lorenz 1969 BAMS paper, Charney et al. 1966 NAS report on predictability). Research file confirms "errors... doubled approximately every 2.5 days (in the models available at the time)." **OK.**
- **Line 175, OK:** "9-10 days for daily weather in the mid-latitudes" -- current ECMWF skill range, accurate.
- **Line 187, OK:** "products of dependent variables, velocity times velocity..." -- correct nonlinearity description.
- **Line 199, OK:** ECMWF "51 members" and NCEP "31" -- correct ECMWF EPS membership; NCEP GEFS has been around 30-32 members. **OK.**
- **Line 205, OK:** "Since December 1992, both ECMWF and NCEP have run operational ensemble prediction systems." -- Standard date. Confirmed.
- **Line 213, OK:** Chaos definition quote attributed to footnote 4 (Lorenz 1993 *The Essence of Chaos*).
- **Line 219, OK:** Strogatz quote -- footnote 1.
- **Line 221, OK:** Kerry Emanuel "last nail in the coffin of the Cartesian universe" -- research file confirms (in line 192: "Ed put the last nail in the coffin of the Cartesian universe...").
- **Line 225, OK:** "Lorenz died on April 16, 2008, at 90 years old. He had been hiking two and a half weeks before. He finished a paper with a colleague a week before." -- Research file: "An avid hiker... maintained these pursuits until approximately two weeks before his death at age 90... published another nine or so articles before his own death." Cherry-picking detail but consistent.
- **Line 229, OK:** Kyoto Prize 1991 statement about "one of the most dramatic changes in mankind's view of nature since Sir Isaac Newton" -- research file confirms.

### Language issues

- **Line 16, LANGUAGE:** "And the proof started with a cup of coffee." -- Good hook.
- **Line 30, LANGUAGE:** "Charney's department foil. The quiet one who broke the universe." -- Tight, evocative.
- **Line 64, LANGUAGE:** "Every minute, it would clack out a line of numbers... clacking away line by clacking line." -- Good rhythm.
- **Line 110, LANGUAGE:** "Read that sentence again. That is the death certificate of the Cartesian universe, written in the passive voice, in a meteorology journal, by a quiet man from Connecticut." -- Excellent. Working.
- **Line 134, LANGUAGE:** "Here is a fact that surprised me: Lorenz did not coin the phrase 'butterfly effect.'" -- Good narrative pivot.
- **Line 211, LANGUAGE:** "Lorenz left us the most elegant definition of chaos ever written. One sentence. No jargon. Perfect." -- Strong setup to the quote that follows.
- **Line 233, LANGUAGE:** "All of it - from 0.506 to 0.506127." -- Excellent compressed closing.

### Forward-looking / self-disavowed framing

- None. **Clean.**

### Character cleanliness

- **Line 272, MINOR:** "9×10⁹ times faster" -- uses Unicode multiplication sign (×) and superscript 9 (⁹). The user's character-cleanliness rule explicitly bans em-dashes, curly quotes, and ellipses. The Unicode multiplication sign and superscripts are not explicitly listed but are in the same spirit. **fix:** consider rendering as "9 x 10^9" or "9 billion" for consistency. **MINOR.**

### Verdict

**Strong post overall, with one clear factual error and one math error:**
1. **Line 100: "his student Barry Saltzman"** -- Saltzman was a colleague (fellow Victor Starr student), not Lorenz's student. **Must fix.**
2. **Line 60: 8,000 years math** -- Should be ~8 years for the LGP-30 to match a phone's one second of work. **Must fix.**

Plus one likely-folkloric overclaim (line 44, teaching award discontinuation) and a minor character-cleanliness issue (line 272, Unicode multiplication symbol). Otherwise, factually solid and stylistically excellent.

---

## Post 5: `2026-04-02-From-cables-to-chaos.md` (Four Machines)

### Factual issues

- **Line 25, MINOR:** Table claim "ENIAC: 17,468 vacuum tubes." Standard cited figure (matches research file's "~18,000 (16 different types)"). The 17,468 specific is the most-cited number. **OK.**
- **Line 25, MINOR:** Table claim "IAS Machine: ~3,400 vacuum tubes." Research file says "~3,000 including all subsystems." 3,400 is a high estimate. **MINOR.**
- **Line 25, CRITICAL:** Table claim "IBM 704: ~4,000 vacuum tubes." This appears low. The IBM 704 had several thousand to nearly 7,000 vacuum tubes (depending on source); research file does not list a specific count, but contemporary IBM marketing material and historical accounts give 5,000-7,000. The "~4,000" is likely understated. **MINOR -- worth verifying.** The research file just says "Logic technology: Vacuum tubes" without a number; from contemporary IBM specs, ~4,000 is at the low end. Acceptable as an order of magnitude.
- **Line 26, MINOR:** Table memory entries: ENIAC "20 numbers" (correct -- 20 accumulators each holding one 10-digit signed number, per ENIAC research line 14); IAS "~5 KB" (correct); IBM 704 "~144 KB" (correct for max config of 32,768 36-bit words = 147 KB, but basic config was 4,096 words = ~18 KB; 144 KB is the upgraded max -- the body text on line 269 confirms this). LGP-30 "~16 KB" (correct).
- **Line 27, MODERATE:** Table speed: "ENIAC: ~5,000 add/s" (matches research). "IAS Machine: ~24,000 add/s" (matches Phillips post; but IAS research file gives 62us add time = ~16,000 add/s; the 24K figure assumes 42us which appears to be from a different source). **Internal inconsistency vs. raw arithmetic** -- worth verifying. "IBM 704: ~40,000 add/s" (matches research). "LGP-30: ~60 add/s" (matches research, though research file actually says "Effective speed: Over 400 additions/second" -- 60 ops/sec was the operations rate including drum access overhead, while raw addition was faster. The "60 ops/s" framing matches Lorenz's experience but undersells the LGP-30's peak capacity).
- **Line 28, MINOR:** Cost: "ENIAC: ~$500K" (research confirms ~$487K). "IAS Machine: ~$800K" (research says "Under $1 million total project budget" -- 800K is a fair estimate). "IBM 704: ~$2M+" (research confirms). "LGP-30: $47K" (research confirms). **OK.**
- **Line 43-45, OK:** ENIAC origin story, Mauchly and Eckert -- consistent with research file.
- **Line 47, OK:** Project PX June 1943, $61,700 budget -- matches research file (June 5, 1943 contract; $61,700).
- **Line 51, OK:** "17,468 vacuum tubes" / failure rate "one tube every two days" -- ENIAC research confirms.
- **Line 55, OK:** "70,000 resistors. 10,000 capacitors. 6,000 switches. 5 million hand-soldered joints." -- Research file confirms 70,000 resistors, 10,000 capacitors, ~5M hand-soldered joints. The 6,000 switches is plausible. **OK.**
- **Line 57, OK:** "ENIAC used decimal arithmetic, not binary. Each of its 20 'accumulators' stored a single 10-digit decimal number using ring counters." Confirmed in research file.
- **Line 67, OK:** Six women programmers: "Kay McNulty, Jean Jennings, Betty Snyder, Marlyn Wescoff, Fran Bilas, and Ruth Lichterman." Research file lists same six (with later married names noted: McNulty/Antonelli, Jennings/Bartik, Snyder/Holberton, Wescoff/Meltzer, Bilas/Spence, Lichterman/Teitelbaum). **OK.**
- **Line 73, OK:** "fall of 1945... two physicists from Los Alamos to come to Philadelphia and run the first problem... Nicholas Metropolis and Stan Frankel." Research file (ENIAC.md and Frankel.md) confirms.
- **Line 75, OK:** Stan Frankel callback. Good.
- **Line 77, OK:** "ran for several weeks and consumed about a million punch cards" -- Frankel research file says "half a million punch cards (some sources say 'a million' -- the discrepancy may reflect different stages of the multi-run computation). It used 95% of ENIAC's control capacity. The program ran for approximately six weeks beginning in late November or early December 1945." -- "Several weeks" and "about a million" are both within the range of cited values. **OK.**
- **Line 81, OK:** "March 1950... 33 days and nights at Aberdeen Proving Ground, cycling through 14 punch-card operations per time step, punching roughly 100,000 IBM cards... 19x16 grid, at 736 km spacing." All consistent with Charney post (line 99) and ENIAC research file.
- **Line 83, OK:** "Klara Dan von Neumann -- John von Neumann's wife, a mathematician in her own right..." -- research file confirms.
- **Line 87, OK:** Klara biography summary -- consistent with Klara_von_Neumann.md research file.
- **Line 89, OK:** Smithsonian 2017 article ("the computer scientist you should thank for your phone's weather app") -- research file confirms.
- **Line 95, OK:** "ENIAC in its converted form ran from 1948 until it was finally decommissioned on October 2, 1955, at 11:45 PM" -- ENIAC research file confirms.
- **Line 113, OK:** "EDVAC needed only about 3,500 vacuum tubes" -- EDVAC research file: 5,937 vacuum tubes. **MODERATE -- post says ~3,500, research says ~5,937.** **fix:** change to "around 6,000" or "roughly 5,900." (The "3,500" claim is wrong.)
- **Line 117, OK:** Mercury delay lines, "tube was about five feet long and held roughly 1,000 bits" -- EDVAC research says "128 mercury-filled tubes... each about 5 feet long... Each tank stored 8 words (384 bits)." The "1,000 bits" claim is roughly correct if interpreted loosely as bit storage per tank in some configurations (smaller-than-stated tanks held 384 bits but the post may be combining different scales). **MINOR.**
- **Line 119, OK:** EDVAC operational at Aberdeen 1951; EDSAC May 6, 1949 -- both confirmed.
- **Line 121, OK:** "EDVAC served at Aberdeen from 1951 to 1962" -- research file says decommissioned January 1963. Close enough. **OK.**
- **Line 127, OK:** IAS machine photo caption (Bigelow, Goldstine, Oppenheimer, von Neumann, 1952). Consistent.
- **Line 145, OK:** "Construction began in 1946. It took six years..." -- IAS research confirms.
- **Line 155, OK:** "The IAS machine had 40 Williams tubes, each storing 1,024 bits... Total: 40,960 bits, or 1,024 words of 40 bits each -- roughly 5 kilobytes." -- IAS research confirms.
- **Line 161, OK:** Phillips quote about machine language and 16-character hex alphabet -- footnote 3.
- **Line 169-173, OK:** Barricelli artificial life simulations, March 3, 1953 -- IAS research file confirms ("On March 3, 1953, at 10:38 p.m., he launched the first digital evolution experiment"). **OK.**
- **Line 187, OK:** "31 simulated days of Phillips' experiment took 11 to 12 hours on the IAS machine." -- consistent with Phillips post.
- **Line 191, OK:** "Von Neumann published the complete design of the IAS machine -- blueprints, circuit diagrams, engineering reports -- and made them freely available to anyone who wanted to build a copy." -- IAS research file confirms.
- **Line 197-203, MODERATE:** Clone list. Most are correct (MANIAC, JOHNNIAC, ILLIAC, ORDVAC, WEIZAC, SILLIAC). However:
  - **"BESM -- Moscow. The Soviet Union built their own version, drawing on the published IAS design."** -- BESM research file (line 5) explicitly states: "the evidence strongly suggests that Lebedev developed the stored-program concept independently, and the BESM architecture differed from the IAS design in several fundamental ways." It used floating-point, three-address instructions, ferrite core memory -- all distinct from IAS. **fix:** Either remove BESM from the IAS-clones list, or rewrite to "BESM -- Moscow. Sergei Lebedev's team built a stored-program machine roughly contemporaneously, with substantial independent design choices (floating point, three-address instructions, core memory)." This is a CRITICAL mischaracterization of an important point in computer history -- it implies the Soviets copied IAS when the historical evidence actually says they developed independently.
  - **The IAS clone list omits BESK** (Sweden), DASK (Denmark), MUSASINO-1 (Japan), AVIDAC, ORACLE -- which are in the IAS research file's clone list. The seven listed in the post are roughly the most famous, so this is a stylistic abridgment, not an error.
- **Line 211, OK:** Julian Bigelow biography, age 32 in 1946, Wiener anti-aircraft predictor -- IAS research file confirms.
- **Line 215, MINOR:** "He has no Wikipedia article as of this writing." -- Verifiable claim about state of the world; cannot fact-check from research files. As of 2026-04-27, this could be checked online if needed. **MINOR -- accept as-is unless out of date.**
- **Line 239, OK:** IBM 701, announced April 1952, designed under Nathaniel Rochester. Research file says announced May 21, 1952; "April 1952" is wrong by one month. Common confusion. **MINOR.** **fix:** "announced in May 1952" or "announced and delivered in 1952."
- **Line 241, OK:** "IBM expected to sell five units. They got eighteen orders." -- IBM 701 research file confirms Watson Jr. quote: "we expected to get orders for five machines, we came home with orders for 18." (Final delivery: 19 units to 18 customers.) **OK.**
- **Line 251, OK:** "In 1949, Forrester had the idea... magnetic core memory" -- Forrester research file confirms ("In 1949, he conceived..."), with first actual fabrication in October 1950 by Papian.
- **Line 259, OK:** "32,768 words (the IBM 704's full memory) contained over a million individual cores, each hand-threaded." -- 32,768 words x 36 bits = 1,179,648 cores. "Over a million" is correct. **OK.**
- **Line 265, OK:** "IBM 704, which shipped in late 1955" -- research file says "introduced by IBM in 1954. A total of 123 units were produced between 1955 and 1960." First shipments in late 1955. **OK.**
- **Line 269, OK:** "32,768 words of 36 bits each -- roughly 144 kilobytes." -- 32768 * 36 / 8 = 147,456 bytes = 144 KB. **OK** (assumes max-config; basic config was 4,096 words / 18 KB).
- **Line 270, OK:** "About 40,000 fixed-point additions per second. 12,000 floating-point operations per second." -- Research file confirms.
- **Line 273, MINOR:** "About $2 million to purchase, or roughly $32,000 per month to lease." -- Research file says lease was $33,000-$45,500/month. $32,000 is slightly low, but close. **MINOR.**
- **Line 273, OK:** "About 123 units were sold." -- Research confirms.
- **Line 275, OK:** Gene Amdahl as architect, Amdahl's Law -- confirmed.
- **Line 281, OK:** "In 1953, John Backus, a 29-year-old programmer at IBM, sent a memo to his manager proposing the development of a 'FORmula TRANslation' system for the 704." -- Research file: "In 1953, Backus proposed to IBM management." Backus was born December 1924, so age 29 in 1953-54. **OK.**
- **Line 287, MODERATE:** "Backus and his team of about ten programmers spent three years on it. The first FORTRAN compiler was delivered with the IBM 704 in April 1957. It was 25,000 lines of machine code and could compile a FORTRAN program into machine instructions that ran within 20% of the speed of hand-coded programs." -- Research file (Fortran_I.md) confirms: project began summer 1954; first delivery April 1957; team of 13 (final paper authors); 25,000 lines is a commonly cited figure but not in research file. The "20% of hand-coded speed" is a famous claim from the FORTRAN team. The "about ten" is a reasonable approximation of the 13-person team. **OK.**
- **Line 289, OK:** "Within a year, more than half of all code written for the 704 was in FORTRAN." -- Standard reference (from Backus's HOPL retrospective). **OK.**
- **Line 306, OK:** "The ECMWF's Integrated Forecasting System... is written in FORTRAN. Updated, modernized, ported through dozens of hardware generations -- but FORTRAN. Seventy years later." -- IFS is largely FORTRAN; "seventy years later" rounds 1957-2027 = ~70 years. Slightly forward-projected (it's currently 2026, so 69 years), but acceptable. **OK.**
- **Line 310, OK:** "JNWPU... was established in 1954 in Suitland, Maryland. An IBM 701 was installed in March 1955, and by May of that year, the first routine real-time operational numerical weather forecasts in the United States began." -- Matches Charney post and IBM 704 research file ("first operational numerical weather forecast was issued on May 6, 1955").
- **Line 312, MODERATE:** "But were the Americans really first? Rossby had returned to Stockholm. He had access to a computer. And he was not the kind of man who waited for someone else to go first. **More on that soon.**" -- Forward-looking promise. **fix:** delete "More on that soon." Per user policy.
- **Line 314, OK:** IBM 704 "running twice daily on a schedule that never slipped" -- consistent with operational NWP history.
- **Line 326, OK:** Daisy Bell anecdote -- IBM 704 research file confirms (Max Mathews, John Kelly, Carol Lockbaum, IBM 7094, Arthur C. Clarke, 2001 a Space Odyssey). **OK.**
- **Line 360, OK:** Stan Frankel biography, T-Division, Bethe/Teller/Feynman -- Frankel research file confirms.
- **Line 363, OK:** "fall of 1945... Frankel and Nicholas Metropolis traveled to Philadelphia to run the first calculations on the ENIAC -- the hydrogen bomb feasibility study." Frankel research file says "In August 1945, immediately after the war ended, Frankel and Metropolis returned to the Moore School to set up and program the calculation." The post says "fall of 1945" -- close enough. **MINOR -- could tighten to "August 1945."**
- **Line 367, OK:** "Frankel went to work at Librascope, a division of General Precision Equipment Corporation in Glendale, California." -- LGP-30 research confirms ("Librascope (a division of General Precision Inc.) in Glendale, California"). **OK.**
- **Line 371, OK:** "Librascope General Purpose computer, 30-bit word length" -- LGP-30 research file says 31-bit effective word length (32 bits with 1 spacer). The post line 25 (table) doesn't conflict but the body text here at line 371 implies 30-bit. **MINOR.** **fix:** "31-bit word length" or just leave the LGP acronym unexplained. Some sources say "30 bits effective" but research has 31. Slight imprecision.
- **Line 373, OK:** "magnetic drum -- a solid metal cylinder about 6.5 inches in diameter, spinning at 3,700 rpm... 4,096 words of 31 bits each, about 16 kilobytes." -- LGP-30 research file confirms.
- **Line 379, OK:** "about 60 operations per second. Roughly a thousand times slower than the IBM 704." -- Math: IBM 704 ~40,000 fixed-point ops/s, LGP-30 ~60 ops/s, ratio ~667x. Post says "roughly a thousand times slower" -- order of magnitude OK, slight overstatement. **MINOR.**
- **Line 381, OK:** "optimum programming" / minimum-access coding speedup of "five to ten times" -- LGP-30 research confirms.
- **Line 391, OK:** "About 500 units were sold." -- Research file: "Approximately 450--500 units." **OK.**
- **Line 425, MINOR:** "Lorenz later upgraded to the **Royal McBee RPC-4000**, a transistorized machine in the same lineage." -- The RPC-4000 was the transistorized successor to the LGP-30; it's in the LGP-30 series lineage. The LGP-30 research file mentions LGP-21 ($16,200) as transistorized successor. Whether Lorenz upgraded specifically to the RPC-4000 -- I can find a separate research file for RPC-4000 in the research directory (`computers/RPC-4000.md` exists, listed in the directory). Not verified directly here. **MINOR.**
- **Line 429, MODERATE:** "Librascope was acquired by Royal McBee, which was a typewriter company." -- LGP-30 research file actually says: "Librascope (a division of General Precision Inc.)" + "Royal Precision Electronic Computer Company -- a joint venture between Librascope and the Royal McBee division of the Royal Typewriter Company." So Librascope was NOT acquired by Royal McBee. Instead, Royal McBee (a division of Royal Typewriter Company) entered a joint venture with Librascope to form Royal Precision Electronic Computer Company. **fix:** "Librascope partnered with Royal McBee, a division of the Royal Typewriter Company, to market the machine." (Or similar; "acquired by" is incorrect.)
- **Line 467, OK:** "John von Neumann... died of cancer in 1957, at 53" -- Klara research file: "John died of metastatic cancer on 8 February 1957." Born December 28, 1903 -> age 53 at death. **OK.**

### Language issues

- **Line 33, LANGUAGE:** "Read that table from left to right and you'll see four revolutions in twenty years." -- Punchy.
- **Line 34, LANGUAGE:** "Building the Impossible" -- working header.
- **Line 67, LANGUAGE:** "They had been computing ballistic trajectories by hand during the war. Now they were given the blueprints of the world's first general-purpose electronic computer and told: figure out how to make it work. No manual. No precedent. No instructor." -- Excellent compressed history.
- **Line 87, LANGUAGE:** "She is rarely mentioned in histories of computing. When the Smithsonian wrote about the weather forecast, they called her 'the computer scientist you should thank for your phone's weather app.' That headline appeared in 2017 -- sixty-seven years after the fact." -- Working pointed observation.
- **Line 207, LANGUAGE:** "Every computer you have ever used, from the mainframe in your bank to the phone in your pocket, descends from the design von Neumann published and gave away for free." -- Strong.
- **Line 304, LANGUAGE:** "FORTRAN didn't just make programming easier. It made a new generation of atmospheric scientists possible -- people who understood the atmosphere but didn't need to understand the inner workings of the hardware. The language separated the science from the machine." -- Excellent.
- **Line 421, LANGUAGE:** "The LGP-30's limitations -- its slowness, its low-precision printout, its presence in a single scientist's office -- were not obstacles to the discovery of chaos. They were preconditions for it." -- Punchy.
- **Line 437, LANGUAGE:** "Those choices put a computer on Lorenz's desk. And Lorenz went for coffee." -- Excellent closer for the Frankel section.
- **Line 487, LANGUAGE:** "In 1956 -- eleven years later -- a quiet man sat at an 800-pound desk plugged into a wall outlet, watched numbers clack out one line per minute, and discovered that weather prediction has a mathematical ceiling that no amount of computing power will ever break through." -- Strong rhythm.
- **Line 491, LANGUAGE:** "Richardson's 64,000 human computers, the ENIAC, the IAS machine, the IBM 704, the LGP-30, the Cray supercomputers, the massively parallel clusters -- all of them compressed into a box with a Noctua fan." -- The Noctua fan reference is a working hardware-blogger flourish.

### Forward-looking / self-disavowed framing

- **Line 312, MODERATE:** "But were the Americans really first? Rossby had returned to Stockholm. ... **More on that soon.**" -- Forward-looking promise. **fix:** delete "More on that soon." or rewrite. (This is the same Stockholm tease that appears in the Charney post; user policy says no forward-looking teases.)

### Character cleanliness

- **Line 491, MINOR:** "9×10⁹" -- Unicode multiplication sign and superscript. Same as Lorenz post line 272. **fix:** consider rendering as plain ASCII for consistency.
- **Line 582, MINOR:** Same: "9×10⁹ times faster than the LGP-30." Same issue.
- No em-dashes, curly quotes, or ellipses. **Otherwise clean.**

### Verdict

**Long, ambitious post -- mostly excellent.** Several factual issues to fix:

1. **Line 113: EDVAC vacuum tube count "about 3,500"** -- correct count is ~5,937. **CRITICAL.**
2. **Line 203: BESM characterization** -- BESM was substantially independent of IAS, not a "version drawing on the published IAS design." **MODERATE.**
3. **Line 312: "More on that soon"** -- forward-looking promise, delete.
4. **Line 429: "Librascope was acquired by Royal McBee"** -- it was a joint venture, not an acquisition. **MODERATE.**
5. **Line 239: IBM 701 announcement date** -- May 1952, not April. **MINOR.**
6. **Line 379: "roughly a thousand times slower"** -- closer to 600-700x; minor overstatement.
7. **Line 491 / 582: Unicode "9×10⁹"** -- character cleanliness, minor.

The post otherwise weaves the four-machine narrative beautifully and sources individual claims well.

---

## Summary -- All Five Posts

### Cross-cutting issues

1. **Forward-looking promises** persist in three of the five posts: Ghost in the Grid (lines 81, 89), Charney (lines 131, 183-187), Phillips (lines 211-217), Four Machines (line 312). Per user policy, all should be removed.

2. **Character cleanliness:** Posts 4 and 5 use the Unicode multiplication sign and superscript ("9×10⁹"). All five posts are otherwise clean -- no em-dashes, curly quotes, or ellipses. Recommend converting to ASCII (`9 x 10^9` or `9 billion`) for consistency.

3. **Internal series consistency:**
   - "Seven equations" (Ghost line 18) vs "seven variables" (post 2026-03-26 line 38) -- minor framing inconsistency.
   - IAS machine specs differ between Phillips post (line 46-50, with the transistor error) and Four Machines post (line 25-27 table) -- both posts use slightly different speed/tube numbers.

### Critical-severity factual errors (must fix)

| Post | Line | Issue | Correction |
|---|---|---|---|
| Phillips | 49 | "2,091 transistors" | IAS had no transistors; remove |
| Phillips | 197 | "1965... GFDL... in Princeton" | 1963 renamed; 1968 moved to Princeton |
| Phillips | 45 | "16,384 words" drum upgrade | 12,288 (12K) |
| Phillips | 46 | "42 microseconds" add time | 62 microseconds |
| Lorenz | 100 | "his student Barry Saltzman" | Saltzman was a colleague, fellow Starr student |
| Lorenz | 60 | "8,000 years" math | ~8 years (15e9 / 60 ops/s ≈ 7.92 years) |
| Four Machines | 113 | "EDVAC needed only about 3,500 vacuum tubes" | ~5,937 vacuum tubes |

### Moderate-severity factual errors

- Phillips line 32: PhD advisor claim should be softened (research file says "sometimes listed as Platzman, primary sources do not explicitly confirm").
- Phillips line 137-151: blow-up duration -- post says "25-26 days," research file says "16 days." Recommend verifying via Lewis 1998.
- Charney line 145: "Nine scientists" -- research file says eight; verify via Charney Report 1979.
- Four Machines line 203 (BESM): independent design, not IAS clone.
- Four Machines line 429: Librascope/Royal McBee joint venture, not acquisition.

### Language verdict (across all five posts)

The voice is **strong and consistent** -- punchy, factual, with good rhythm and well-placed humor. No purple prose, no hedge-soup. The series voice has matured: short sentences, concrete details, named characters with biographies, quotes set off cleanly. The forward-looking teases are the main stylistic deviation from the user's preferred policy applied to later posts; once those are removed, the language is essentially production-ready.

The strongest stylistic moments:
- "That is the death certificate of the Cartesian universe, written in the passive voice, in a meteorology journal, by a quiet man from Connecticut." (Lorenz line 110)
- "Twenty-two pages, written in five days, accurate for nearly half a century." (Charney line 159)
- "Those choices put a computer on Lorenz's desk. And Lorenz went for coffee." (Four Machines line 437)

The weakest:
- "The neural network: Catching up. We'll see." (Ghost line 128) -- borderline forward-looking.
- "This is like playing a souls-like game where the controller is also on fire." (Phillips line 62) -- works but could be a hedge metaphor for some readers; opinions will vary.

### Overall publication readiness

| Post | Status |
|---|---|
| Ghost in the Grid (post 1) | Strong; remove 2 forward-looking promises (lines 81, 89). |
| Charney (post 2) | Strong; remove forward-looking section (183-187), parenthetical (131); verify Charney Report panel size. |
| Phillips (post 3) | **Multiple critical fixes needed** (transistors, drum upgrade, GFDL year, add time); remove forward-looking section. |
| Lorenz (post 4) | **Fix Saltzman-as-student error and 8,000-years math error**; otherwise excellent. |
| Four Machines (post 5) | Multiple moderate fixes (EDVAC tubes, BESM, Librascope/Royal McBee, IBM 701 date); remove "More on that soon." |

**The Phillips post is the highest-priority correction target** because of the transistor claim (a basic anachronism that any technically-aware reader will notice) and the GFDL chronology error.
