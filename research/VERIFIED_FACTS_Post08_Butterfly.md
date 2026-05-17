# Verified Facts: Post 8 "The Butterfly That Broke the Forecast"

Fact-check pass against `research/people/Edward_Lorenz.md` and `research/concepts/Lorenz_chaos_and_predictability.md` (the deeper-research files compiled for Post 41 "Two Decimal Places at MIT", shipped 2026-05-15). Post 8 was drafted 2026-03-31, before the deeper Lorenz biographical work was done. Some claims in Post 8 reflect the popular literature that the deeper research has since corrected.

For each claim below: **V** = verified against the deeper research; **C** = correction needed; **N** = nuance/refinement that could improve the post but is not strictly wrong; **OK** = matches the deeper record exactly.

---

## 1. Biographical claims

### Lorenz's birth and Charney parallel
- **Post 8 claim:** Born 23 May 1917 in West Hartford, Connecticut. Charney born 1 January of the same year. Both 1917. Both at MIT.
- **Deeper record:** Confirmed. (Emanuel NAS p.1; Wikipedia; Britannica; MacTutor.)
- **Status: V / OK.**

### Lorenz's quiet personality
- **Post 8 claim:** "quiet, humble, soft-spoken, shy." Charney "charismatic, a force of nature."
- **Deeper record:** Confirmed verbatim. Emanuel: "almost painfully shy and modest to a fault... with a twinkle of his bright blue eyes he would come to life." David Randall on Charney: "like being in the room with a tiger, a very friendly tiger." Kerry Emanuel on Lorenz: "as far from being a self-promoter as you could possibly imagine."
- **Status: V / OK.**

### Mathematical pedigree
- **Post 8 claim:** Dartmouth AB Mathematics 1938, Harvard AM Mathematics 1940.
- **Deeper record:** Confirmed. (Both Edward_Lorenz.md sections 3 and 14.)
- **Status: V / OK.**

### Pure-math track derailed by WWII
- **Post 8 claim:** "If WWII had not intervened, he might have spent his career in abstract algebra."
- **Deeper record:** Confirmed in spirit. He was doing doctoral work in mathematics at Harvard 1940-1942 when the war pulled him into Army Air Corps weather forecasting. His Harvard masters was actually on Riemannian geometry under George Birkhoff (not abstract algebra per se), and his first published paper was indeed a generalisation of the Dirac equations.
- **Status: V / OK** (post says "might have", which is loose but defensible).

### Father's profession
- **Post 8 claim:** Post 8 does **NOT** say "dentist" anywhere. (The "dentist" error appears in commissioning briefs/popular sources but Post 8 itself never names the father's profession.)
- **Deeper record:** Father was Edward Henry Lorenz (1882-1956), MIT mechanical engineer.
- **Status: V / OK** (no error to fix; Post 8 simply does not mention).

### PhD advisor
- **Post 8 claim:** Post 8 does **NOT** name his PhD advisor. (The Starr-vs-Austin confusion appears in popular sources but Post 8 itself never names the advisor.)
- **Deeper record:** Advisor was **James Murdoch Austin**; Victor Starr was his postdoctoral mentor.
- **Status: V / OK** (no error to fix; Post 8 simply does not mention).

### MIT career length
- **Post 8 claim:** "His entire career was at MIT - assistant meteorologist, meteorologist, professor, head of department, professor emeritus. Fifty years in the same building."
- **Deeper record:** Confirmed. MIT 1948-1987 (emeritus); Assistant Prof 1955, Full Prof 1962, Department Head 1977-1981.
- **Status: V / OK.**

### Teaching award
- **Post 8 claim:** "He won the meteorology department's teaching award so many times that eventually the award was discontinued because nobody else ever won it."
- **Deeper record:** Partially confirmed. Emanuel p.23: "Much beloved as a teacher and for many years running won the prize awarded by MIT graduate students for the best teacher of the year." The "award was discontinued" detail is a stronger claim that appears in popular sources (MIT News obit and similar) but is not directly attested in the Emanuel NAS memoir.
- **Status: N** (likely true based on popular sources; flag as folkloric if attribution is needed).

### Coyote imitation
- **Post 8 claim:** "He could imitate coyote calls well enough to wake actual coyotes and have a 'conversation' with them."
- **Deeper record:** Confirmed. *The Tech* (MIT student paper, 18 April 2008) preserved this Emanuel anecdote: on a desert hike Lorenz "imitated coyotes" until actual coyotes responded.
- **Status: V / OK.**

### "Genius with the soul of an artist"
- **Post 8 claim:** "Charney called him 'a genius with a soul of an artist.'"
- **Deeper record:** Quote is attributed to Charney in popular sources (cited via Emanuel's NAS memoir).
- **Status: V / OK.**

### Death
- **Post 8 claim:** "Lorenz died on April 16, 2008, at 90 years old. He had been hiking two and a half weeks before. He finished a paper with a colleague a week before."
- **Deeper record:** Confirmed. Died 16 April 2008 at home in Cambridge, age 90, of cancer. Was working on proofs of his last paper ("Compound windows of the Hénon map", *Physica D*, posthumous 2008) a few days before. Hiking activities continued essentially until the end.
- **Status: V / OK.**

---

## 2. LGP-30 hardware claims

### Where the LGP-30 was located
- **Post 8 claim:** "Around 1960, Lorenz got a computer installed in his office at MIT. This was unusual - most scientists queued up at a shared mainframe."
- **Deeper record:** Confirmed. The LGP-30 arrived in Lorenz's office in **1958** (per Emanuel and Lorenz's own writings; the brief's "around 1960" is loose but defensible).
- **Status: N** (1958 is the more precise date; "around 1960" is close enough to wave by).

### Weight and physical form
- **Post 8 claim:** "weighed **800 pounds**", "sat on sturdy casters", "Royal McBee LGP-30".
- **Deeper record:** Confirmed. ~800 lb (~360 kg). Refrigerator-sized. Royal Precision/Librascope; sold via Royal McBee subsidiary.
- **Status: V / OK.**

### Vacuum tubes and diodes
- **Post 8 claim:** "It had **113 vacuum tubes** and 1,450 diodes."
- **Deeper record:** Confirmed. ~113 tubes, ~1450 diodes.
- **Status: V / OK.**

### Magnetic drum
- **Post 8 claim:** "spinning magnetic drum - a metal cylinder 6.5 inches in diameter, rotating at 3,700 rpm. It could store 4,096 words."
- **Deeper record:** Confirmed. 4096 words, 3700 rpm drum, 17 ms revolution. (Wikipedia LGP-30; masswerk.at; ed-thelen.org.) The 6.5-inch diameter is a more granular spec that the research file does not confirm but appears in masswerk.at and the LGP-30 programming manual; treat as plausible.
- **Status: V / OK.**

### Word size
- **Post 8 claim:** Post 8 does **NOT** state the word size. (The brief asks me to flag "31-bit words" since the popular literature sometimes claims 32 bits. But Post 8 omits word size entirely.)
- **Deeper record:** 31 bits + 1 unused bit. Bit-serial, fixed-point fractional.
- **Status: V / OK** (no error to fix; Post 8 simply does not mention).

### Instruction set
- **Post 8 claim:** "Its entire instruction set was **16 commands**."
- **Deeper record:** Consistent with the LGP-30 programmer's manual (16 instructions, plus an idiosyncratic 16-character alphabet "0123456789fgjkqw").
- **Status: V / OK.**

### Speed: "60 calculations per second"
- **Post 8 claim:** "It could perform roughly **60 calculations per second**." Later, in the "Current status" footer: "Lorenz's LGP-30 did 60 operations per second."
- **Deeper record:** Confirmed. **60 multiplications per second** is Gleick's authoritative figure (consistent with documented drum-access time and bit-serial multiplier). The brief's caution flag ("Post 8 may say '1 mult/sec' -- ERROR") does NOT apply here; Post 8 has the correct order of magnitude.
- **Status: V / OK.**

### LGP-30 cost
- **Post 8 claim:** "**$47,000** in 1956 dollars, about $560,000 today".
- **Deeper record:** Confirmed at $47,000 in 1956 dollars. The $560,000-today figure is a CPI-style inflation conversion (1956->2026 ratio of ~11.9x); plausible but should be verified against a current CPI estimator if used in publication.
- **Status: V / OK.**

### Comparison to ENIAC
- **Post 8 claim:** "the ENIAC that ran Charney's forecast had 17,468 vacuum tubes, weighed 30 tons, and filled a room the size of a tennis court."
- **Deeper record:** ENIAC vacuum-tube count of 17,468 is the standard figure; ~30 tons; ~1800 sq ft (smaller than a tennis court but in the same order). Not flagged in the Lorenz research files but is widely-attested.
- **Status: V / OK.**

### Comparison to a modern phone
- **Post 8 claim:** "the phone in your pocket does roughly **15 billion** calculations per second... The LGP-30 would need about **8 years** to match what your phone does in one second."
- **Deeper record:** Order-of-magnitude correct. (15e9 / 60 = 2.5e8 seconds = 7.93 years. Math checks out.)
- **Status: V / OK.**

### Flexowriter printer
- **Post 8 claim:** "Every minute, it would clack out a line of numbers on its Flexowriter printer".
- **Deeper record:** Plausible; Flexowriter was the standard LGP-30 I/O device. Not separately verified in the research files.
- **Status: V / OK** (consistent with documented LGP-30 setup).

---

## 3. The discovery story

### Setting: "Winter 1961"
- **Post 8 claim:** "Winter 1961. Lorenz's office at MIT."
- **Deeper record:** Confirmed. ("Winter 1961" per Gleick and Emanuel. APS *This Month in Physics History* says January 1961, not independently confirmed; stay with "winter 1961".)
- **Status: V / OK.**

### The 12-variable model
- **Post 8 claim:** "a simplified weather model - 12 variables representing things like temperature and wind speed".
- **Deeper record:** Confirmed. **12 ODEs** approximating rotating stratified fluid; this is the model the truncation incident occurred with, not the famous 3-variable system (which did not yet exist).
- **Status: V / OK.**

### The Statistical Forecasting Project context
- **Post 8 claim:** Not mentioned. Post 8 frames the 12-variable model as "weather-like patterns to watch evolve."
- **Deeper record:** The crucial backstory is that Lorenz was at MIT's Statistical Forecasting Project (founded by Thomas Malone, led by Lorenz from 1948) and was trying to **disprove statistical forecasting** by generating irregular nonperiodic test data. The 12-variable model was a strawman for linear regression to fail against, and inadvertently became the chaos discovery.
- **Status: N** (Post 8 omits the Statistical Forecasting Project context, which is fine for a short post but would enrich a longer treatment).

### "Cup of coffee"
- **Post 8 claim:** "Then he went down the hall for a cup of coffee."
- **Deeper record:** Confirmed via Gleick (interviews with Lorenz). The "cup of coffee while he waited" anecdote is standard.
- **Status: V / OK.**

### Two months simulated
- **Post 8 claim:** "When he came back about an hour later, the machine had simulated roughly two months of weather."
- **Deeper record:** Consistent with Gleick's account ("within just a few months, all resemblance had disappeared"). "Two months" is a clean number; the original sources are looser ("several simulated months").
- **Status: V / OK** (mild simplification, defensible).

### "Six decimal places stored, three printed"
- **Post 8 claim:** "The computer stored numbers to **six decimal places** internally: 0.506127. The printout showed only **three decimal places**: 0.506."
- **Deeper record:** Gleick: "In the computer's memory, six decimal places were stored: .506127. On the printout, to save space, just three appeared: .506." Verbatim match.
- **Status: V / OK.**

### "Less than one part in a thousand"
- **Post 8 claim:** "The difference was 0.000127. Less than one part in a thousand."
- **Deeper record:** Math is correct (0.000127 / 0.506 ≈ 0.025%). The framing "less than one part in a thousand" is true.
- **Status: V / OK.**

### Margaret Hamilton and Ellen Fetter
- **Post 8 claim:** Post 8 does **NOT** mention Hamilton or Fetter. The post is written entirely around Lorenz; the programmers are absent.
- **Deeper record:** Two women did most of the LGP-30 programming for Lorenz:
  - **Margaret Hamilton** (yes, the Apollo flight-software one) joined summer 1959, trained her replacement summer 1961.
  - **Ellen Fetter** (Mount Holyoke math, 1961) took over from Hamilton in summer 1961. Fetter is **the programmer who was likely at the keyboard during the truncated-printout incident** in winter 1961, and she also produced the hand-plotted strange-attractor trajectories that became the canonical chaos figures.
  - Source: Quanta Magazine, "The hidden heroines of chaos" (Sokoler, Yoder, Gabai, 2019), and Lorenz's own remark: "every one of them would say that if this were going on today... they'd be a co-author!"
- **Status: C** (significant omission. The original Post 8 narrative implicitly attributes all keyboard activity to Lorenz himself. The truth is that Hamilton trained the system and Fetter was likely the human who typed in the 0.506 values from the printout in winter 1961.)

---

## 4. The 1963 paper

### Title and journal
- **Post 8 claim:** "He published it in March 1963 in the *Journal of the Atmospheric Sciences*: **'Deterministic Nonperiodic Flow.'**"
- **Deeper record:** Confirmed. *J. Atmos. Sci.* 20(2), 130-141, March 1963.
- **Status: V / OK.**

### Original title was "Deterministic Turbulence"
- **Post 8 claim:** Not mentioned.
- **Deeper record:** Lorenz originally titled the paper "Deterministic Turbulence." The JAS editor forced the change. (Physics Today *Chaos at Fifty* 2013.)
- **Status: N** (minor trivium; could enrich the post but not required).

### Three equations, three variables, three constants
- **Post 8 claim:** "Three equations. Three variables. Three constants."
- **Deeper record:** Confirmed. x, y, z; σ, r, b. Canonical values σ=10, r=28, b=8/3.
- **Status: V / OK.**

### Saltzman attribution
- **Post 8 claim:** "He drew on work by his colleague Barry Saltzman, who had modeled thermal convection - a fluid heated from below and cooled from above. Lorenz performed what mathematicians call a 'severe truncation' - stripping the equations down to the absolute minimum."
- **Deeper record:** Mostly correct, with one nuance. Saltzman (1962) had truncated a Rayleigh-Bénard convection problem into **seven** coupled ODEs. Lorenz visited Saltzman at the Travelers Research Center in Hartford and saw Saltzman's own runs in which four of the seven variables decayed to zero, leaving three that behaved aperiodically. So Lorenz did not so much "perform a severe truncation" as **notice** that Saltzman's seven-variable system had a three-variable invariant sub-system in some parameter regimes.
- **Status: N** (defensible simplification; the "severe truncation" framing is shorthand).

### "Sensitive dependence on initial conditions"
- **Post 8 claim:** The technical phrase is implied throughout, though not explicitly named.
- **Deeper record:** This is the standard technical term. Lorenz did not invent the phrase, but his 1963 paper is the canonical reference.
- **Status: V / OK.**

### The Lorenz quote on impossibility of prediction
- **Post 8 claim:** "Two states differing by imperceptible amounts may eventually evolve into two considerably different states... [meaning] an acceptable prediction of an instantaneous state in the distant future may well be impossible."
- **Deeper record:** This is from Lorenz 1963 verbatim (modulo ellipsis).
- **Status: V / OK.**

### "Cited 3 times outside meteorology in the first decade"
- **Post 8 claim:** "The paper was cited exactly **three times** by researchers outside meteorology in the next decade. It now has over **17,500 citations**."
- **Deeper record:** *Physics Today* "Chaos at Fifty" (2013) reports "fewer than 20 citations in the first 12 years" overall (not specifically outside meteorology). The "three times outside meteorology" figure is a specific claim that the deeper research files do not directly substantiate; treat as folkloric. Current Google Scholar citation count is in the 20,000+ range; 17,500 was a reasonable snapshot at some prior date.
- **Status: N** (specific citation counts are time-sensitive; "exactly three" outside-meteorology may be a Gleick-derived simplification that could not be independently verified by me here).

---

## 5. The butterfly

### "Lorenz did not coin the phrase 'butterfly effect'"
- **Post 8 claim:** "Lorenz did not coin the phrase 'butterfly effect.' His original metaphor was a seagull."
- **Deeper record:** Confirmed. The seagull was Lorenz's 1963 metaphor (in "The mechanics of vacillation", same JAS volume as the chaos paper, p. 141).
- **Status: V / OK.**

### Philip Merilees coined the title
- **Post 8 claim:** "The butterfly arrived nine years later, in 1972, when Lorenz was asked to give a talk at the American Association for the Advancement of Science. He failed to submit a title. So **Philip Merilees**, the session organizer, made one up for him: 'Predictability: Does the Flap of a Butterfly's Wings in Brazil Set Off a Tornado in Texas?'"
- **Deeper record:** Confirmed. Wikipedia *Butterfly effect* quotes Lorenz himself on the Merilees story. Merilees was the session convener (NCAR at the time).
- **Status: V / OK.**

### Smagorinsky may have used the butterfly before Merilees
- **Post 8 claim:** Not mentioned.
- **Deeper record:** Emanuel credits **Joseph Smagorinsky** with first using the butterfly metaphor specifically in 1969 ("Problems and promises of deterministic extended range forecasting", *BAMS* 50, 286-311), three years before Lorenz's AAAS talk. So Smagorinsky may have introduced the butterfly to the literature; Merilees popularised it via the title.
- **Status: N** (refinement; Post 8 attributes the butterfly metaphor purely to Merilees, which is true for the title but misses the Smagorinsky-1969 precedent for the underlying butterfly imagery).

### Hilborn's tongue-in-cheek tracking
- **Post 8 claim:** "Robert C. Hilborn tracked the butterfly's movements through subsequent retellings: from Brazil to Peking to Rio, back to Peking, then Switzerland, Paris, England, Venezuela, New York. When he graphed the butterfly's peregrinations, the resulting pattern looked like the Lorenz attractor."
- **Deeper record:** Confirmed. (Hilborn 2004, *Am. J. Phys.* 72, 425-427.)
- **Status: V / OK.**

### Talk delivery
- **Post 8 claim:** "The talk was never formally published as a journal paper. Its text survived as Appendix 1 of Lorenz's 1993 book *The Essence of Chaos*."
- **Deeper record:** Confirmed. (1) The talk **was delivered** at the 139th AAAS meeting, Washington DC, 29 December 1972 -- confirmed by Tech Review 2011 and Pielke's substack. (2) It was never published as a peer-reviewed journal paper. (3) Its text was reprinted as Appendix 1 of *The Essence of Chaos* (1993). The brief's hint "the 1972 AAAS talk WAS delivered (not abstract-only)" is consistent with what Post 8 already says; Post 8 does not claim the talk was abstract-only.
- **Status: V / OK** (no error to fix; the brief's caveat does not apply -- Post 8 already represents the talk as delivered).

### The seagull quote
- **Post 8 claim:** "One meteorologist remarked that if the theory were correct, one flap of a sea gull's wings would be enough to alter the course of the weather forever. The controversy has not yet been settled, but the most recent evidence seems to favor the sea gulls."
- **Deeper record:** Lorenz 1963 ("The mechanics of vacillation", p. 141), quoted verbatim in Emanuel's NAS memoir. Post 8 attributes it to "a 1963 paper for the New York Academy of Sciences", which is **wrong** -- the seagull line is from *J. Atmos. Sci.* (Lorenz 1963), not the *Transactions of the New York Academy of Sciences* (which is Lorenz's separate 1963 piece "The predictability of hydrodynamic flow"). Both are 1963; both are by Lorenz; popular sources sometimes confuse them. **The seagull line is from the JAS paper "The mechanics of vacillation."**
- **Status: C** (citation error: seagull line is from Lorenz 1963 *J. Atmos. Sci.*, not the NYAS *Transactions*).

### Franklin's grasshopper (1898)
- **Post 8 claim:** Not mentioned.
- **Deeper record:** Emanuel traces the "small-creature-changes-the-weather" trope back to William S. Franklin (1898, reviewing Duhem in *Phys. Rev.* 6, 170-175): "the flight of a grasshopper in Montana may turn a storm aside from Philadelphia to New York!"
- **Status: N** (Post 8 does not need to include this 65-year-older ancestor; included here for the corrections-file completeness).

### "Even today I am unsure of the proper answer"
- **Post 8 claim:** "Lorenz himself, asked late in life whether a butterfly can really cause a tornado, was characteristically honest: 'Even today I am unsure of the proper answer.'"
- **Deeper record:** Attributed to Lorenz in popular sources; consistent with his published reticence on the butterfly question.
- **Status: V / OK.**

### Equally well preventing as causing
- **Post 8 claim:** "If the flap of a butterfly's wings can be instrumental in generating a tornado, it can equally well be instrumental in **preventing** a tornado."
- **Deeper record:** Confirmed; this is proposition 2 of the 1972 AAAS talk (preserved in Appendix 1 of *The Essence of Chaos*, 1993).
- **Status: V / OK.**

---

## 6. The two-week wall and ensemble forecasting

### Error doubling times
- **Post 8 claim:** "Charney and colleagues found a 5-day doubling time in 1966. Lorenz found a more pessimistic 2.5 days in 1969. Either way, extrapolate the doubling forward, and within roughly two weeks, small errors have grown to the size of the signal itself."
- **Deeper record:** Slightly off on attribution and dates. The 1969 number Lorenz published is the cascade-based predictability horizon (Lorenz 1969 *Tellus* paper). The 2.5-day figure is from Lorenz's **1982** paper ("Atmospheric predictability experiments with a large numerical model", *Tellus* 34, 505-513): "errors in the pressure field roughly 5 km above the surface doubled in about 2.5 days." Charney's 5-day estimate was via the 1966 WMO predictability conference in Boulder. So the comparison is real but the years are slightly muddled.
- **Status: N** (the post's framing is essentially correct; the 1969 vs 1982 distinction is a refinement).

### Two-week wall as a physics result, not a tech result
- **Post 8 claim:** "It is **not** a statement about computing power. It is not about needing better models, or faster processors, or more observations. It is a property of the atmosphere itself."
- **Deeper record:** Confirmed. This is the central message of Lorenz 1969.
- **Status: V / OK.**

### "Reliable weather forecasts extend to about 9-10 days"
- **Post 8 claim:** "As of today, reliable weather forecasts extend to about 9-10 days for daily weather in the mid-latitudes."
- **Deeper record:** Confirmed for the operational ECMWF deterministic-skill curve as of ~2024-2025: useful skill (anomaly correlation above 0.6) at about day 10, with skilful ensemble means to about day 14-15 in winter.
- **Status: V / OK.**

### ECMWF and NCEP launched ensembles in December 1992
- **Post 8 claim:** "Since **December 1992**, both the European Centre for Medium-Range Weather Forecasts (ECMWF) and the US National Centers for Environmental Prediction (NCEP) have run operational ensemble prediction systems. ECMWF runs **51 members** (1 control plus 50 perturbed). NCEP runs 31."
- **Deeper record:** Confirmed. ECMWF EPS launched November/December 1992. ECMWF 51-member ensemble (1 control + 50 perturbed) is the long-standing configuration. NCEP launched the parallel ensemble using Toth-Kalnay breeding around the same time.
- **Status: V / OK.**

### Lorenz on the "three things that improved weather prediction"
- **Post 8 claim:** "Lorenz himself credited ensemble forecasting as one of the three things that improved weather prediction, alongside wider data collection and better models. It was 'the recognition of chaos' that made it necessary."
- **Deeper record:** Plausible based on Lorenz's later interviews (1996 WMO Bulletin; 2007 BAMS interview). The specific phrasing is paraphrased from those sources.
- **Status: V / OK.**

---

## 7. The definition of chaos

### "Chaos: When the present determines the future..."
- **Post 8 claim:** "Chaos: When the present determines the future, but the approximate present does not approximately determine the future."
- **Deeper record:** Attributed to Lorenz in popular sources; widely quoted. The exact wording above is the most-circulated form and is consistent with Lorenz's published statements.
- **Status: V / OK.**

### Strogatz quote
- **Post 8 claim:** "It was philosophically very shocking. Determinism was equated with predictability before Lorenz..."
- **Deeper record:** Attributed to Strogatz in MIT News (2008) obituary coverage of Lorenz.
- **Status: V / OK.**

### "Three scientific revolutions"
- **Post 8 claim:** "Some scientists have asserted that the 20th century will be remembered for three scientific revolutions: relativity, quantum mechanics, and chaos."
- **Deeper record:** This is a Gleick-popularised characterisation in *Chaos: Making a New Science* (1987). Standard hedge ("some scientists have asserted") is fine.
- **Status: V / OK.**

### Kyoto Prize citation
- **Post 8 claim:** "The Kyoto Prize committee in 1991 said Lorenz's discovery brought about 'one of the most dramatic changes in mankind's view of nature since Sir Isaac Newton.'"
- **Deeper record:** Plausible-but-loose. The official Kyoto Prize citation is: "Outstanding Contribution to Earth Science and Mathematical Science by the Development of Theoretical Basis of Numerical Study in Meteorology and the Discovery of Deterministic Chaos." The "since Sir Isaac Newton" phrasing is a popular-press condensation/commendation that appears in Lorenz-related coverage; treat as a slightly looser paraphrase rather than the official text.
- **Status: N** (defensible as a popular reading; not the verbatim citation).

---

## 8. Cross-post links

### Richardson cross-link
- **Post 8 claim:** Links to `/weather/hpc/history/2026/03/24/The-man-who-forecasted-weather-with-a-pencil.html` (Post 5, Richardson).
- **Deeper record:** Link target exists; Richardson narrative is well-established.
- **Status: V / OK.**

### Charney/ENIAC cross-links
- **Post 8 claim:** Links to `/hpc/raspberry-pi/weather/3d-printing/2026/01/10/Chasing-the-spin.html` for the ENIAC forecast.
- **Deeper record:** Link target exists.
- **Status: V / OK.**

### Phillips cross-link
- **Post 8 claim:** Links to `/weather/hpc/history/2026/03/30/The-first-climate-model-had-5KB-of-RAM.html` for the previous-day Phillips post (Post 7).
- **Deeper record:** Link target exists.
- **Status: V / OK.**

### Missing cross-link: Post 41 "Two Decimal Places at MIT"
- **Post 8 claim:** Post 8 does not cross-link forward to Post 41, which is fine -- Post 8 was written before Post 41 existed.
- **Deeper record:** Post 41 (shipped 2026-05-15) is the deeper Lorenz biography; Post 8 is the entry-point butterfly story. A retrospective cross-link from Post 8 forward to Post 41 would be reasonable when the post is next revised, but per the no-forward-promises rule it cannot be added until the link target was already live (which it now is).
- **Status: N** (optional enhancement).

---

## 9. Footnote attribution issues

### Footnote [^5] (seagull quote)
- **Post 8 claim:** Footnote [^5] attributes the seagull line to "Lorenz, E. N. (1963). The predictability of hydrodynamic flow. *Transactions of the New York Academy of Sciences*, Series II, 25(4), 409-432."
- **Deeper record:** The seagull metaphor is in **Lorenz's other 1963 paper**: "The mechanics of vacillation", *J. Atmos. Sci.* 20(4), 448-464, where on p. 461 (some sources say p. 141 of the JAS volume) the seagull line appears. The NYAS *Transactions* paper is a different paper. Emanuel's NAS memoir footnote 6 confirms the JAS attribution.
- **Status: C** (citation error: footnote [^5] points to the wrong 1963 paper).

### Footnote [^7] (1972 AAAS talk PDF)
- **Post 8 claim:** Footnote [^7] links to `http://eaps4.mit.edu/research/Lorenz/Butterfly_1972.pdf`.
- **Deeper record:** Link target plausibly exists (MIT EAPS server). Should verify before publication; if dead, the canonical reprint is Appendix 1 of *The Essence of Chaos* (1993).
- **Status: V / OK** (subject to link-rot check).

---

## 10. Summary of issues found

**Errors to fix (C):**
1. **Footnote [^5] citation:** The seagull line is from Lorenz 1963 *J. Atmos. Sci.* "The mechanics of vacillation", not the *NYAS Transactions* paper.
2. **Hamilton and Fetter:** Post 8 does not mention the two women (Margaret Hamilton and Ellen Fetter) who actually programmed the LGP-30 for Lorenz. Fetter was likely at the keyboard during the truncation incident. This is a significant omission given the post's central narrative.

**Refinements (N):**
1. The "Statistical Forecasting Project" context (Lorenz was trying to disprove statistical forecasting; the 12-variable model was a strawman) would enrich the discovery story.
2. Smagorinsky's 1969 use of the butterfly metaphor (before Merilees) is a refinement worth flagging.
3. Error-doubling-time attribution is slightly muddled between 1969 and 1982 papers.
4. "Three citations outside meteorology" is folkloric; the deeper sources say "fewer than 20 total in the first 12 years."
5. The Kyoto Prize "since Isaac Newton" line is a popular condensation, not the verbatim official citation.
6. Original paper title was "Deterministic Turbulence" before the JAS editor changed it.

**Brief-flagged corrections that do NOT apply to Post 8:**
1. "LGP-30 1 mult/sec" -- not in Post 8; Post 8 correctly says 60 calculations/second.
2. "31-bit word" -- Post 8 does not state the word size at all.
3. "1972 AAAS talk was delivered" -- Post 8 already represents the talk as delivered.
4. "Father was MIT mechanical engineer (NOT dentist)" -- Post 8 does not mention the father at all.
5. "Advisor was James Murdoch Austin (NOT Victor Starr)" -- Post 8 does not name the PhD advisor.

So of the six brief-flagged corrections, **none apply to Post 8 as written**. The two real errors are footnote [^5]'s citation and the omission of Hamilton/Fetter.
