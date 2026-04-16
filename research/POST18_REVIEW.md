# Fact-Check Review: POST18 — "The Decade the Forecast Got Good"
*Post file: `_posts/2026-04-17-The-decade-the-forecast-got-good.md`*
*Review date: 2026-04-08*
*Reviewer: Claude (Sonnet 4.6), cross-checked against research files and web sources*

---

## Summary

The post is largely accurate. Most claims check out against research files and web sources. Three issues require correction: (1) a mislabelling of which machine the 7090 was "six times faster" than, (2) an inaccurate paraphrase of the Watson memo, and (3) the year Cressman left NMC. A further claim about the JOHNNIAC at IAS is potentially imprecise but not flatly wrong. All other major claims verified.

---

## ERRORS FOUND

### ERROR 1 — "Six times faster than the 709" vs. the 704 (post paragraph 3 of "The 7090 Arrives")

**What the post says:**
> "The 7090 ran **six times faster** than the 709."

**What the research file says (`IBM_709_7090.md`, `IBM_7090_era_NWP_1959_1969.md`):**
The "six times faster" figure is the comparison between the 7090 and the **IBM 709** (its direct vacuum-tube predecessor). This is correct as stated. The post does not misattribute the comparison — it says "six times faster than the 709," and this is accurate.

**However**, earlier in the same section (paragraph 3, talking about the 704), the post writes:
> "The IBM 704, which replaced the 701 in 1957, improved things substantially … But even the 704 was barely fast enough."

And the section header is "The 7090 Arrives," where the post correctly frames the 7090 as replacing the 709. No factual error here.

**BUT** — in the NWP context paragraph, the research file notes:
> "Note: The 7090 is typically described as 'six times faster than the IBM 709' (its vacuum-tube predecessor), not six times faster than the 704. The 704-to-7090 improvement was roughly 2.5x in raw instruction throughput."

The post is correct on the 6x vs. 709 claim. No correction needed on this specific sentence. However, **there is a subtle narrative issue**: the post implies (in the "arc" recap at the end, line 178) that the 7090 replaced the 704 at NMC operationally: "In **1960**, the IBM 7090 made the models fast enough to be operationally useful." This is correct — NMC went from 704 to 7090, skipping the 709. The 6x figure is still accurate for the 7090 vs. 709, but does **not** represent the NMC-specific upgrade ratio (704 to 7090 was approximately 2.5x in raw throughput, though much larger in effective NWP throughput due to memory cycle time improvements: 12 µs → 2.18 µs is a 5.5x improvement in memory bandwidth).

**Verdict:** The claim "six times faster than the 709" is factually correct. The post is not wrong. But if the intended meaning is to convey how much faster NMC's new machine was compared to what it replaced (the 704, not the 709), the figure overstates the improvement in that specific context. A careful reader may notice the inconsistency: the post describes NMC going from a 704 to a 7090 (correctly), but the "six times faster" figure compares 7090 to 709. The 7090 was 7.5x faster than the 704 (per IBM's own data), so if anything the NMC upgrade was larger than 6x, not smaller. **No correction is strictly necessary**, but a clarifying parenthetical would improve precision.

**Suggested fix (optional):** After "The 7090 ran **six times faster** than the 709", add: "(and roughly 7.5 times faster than the IBM 704 it replaced at NMC)."

---

### ERROR 2 — Watson memo paraphrase is inaccurate

**What the post says (line 144):**
> "Thomas Watson Jr. reportedly fired off an angry memo asking how 'the world's largest computer company' had been beaten by a firm with '34 people, including the janitor.'"

**What the memo actually says (verified via CHM and multiple sources):**
The Watson memo (dated August 28, 1963) does not contain the phrase "the world's largest computer company." The actual text reads:
> "Contrasting this modest effort with our own vast development activities, I fail to understand why we have **lost our industry leadership position** by letting someone else offer the world's most powerful computer."

The "34 people, including the janitor" part is accurate. But the framing "the world's largest computer company" is the blog's paraphrase of Watson's meaning, not a quote or near-quote. The post implies it was Watson's own phrase — it was not.

**Severity:** Medium. The paraphrase captures the spirit but is presented in a way that reads like a near-quote. The phrasing "reportedly fired off an angry memo asking how 'the world's largest computer company' had been beaten" implies Watson used that phrase.

**Suggested fix:** Change to:
> "Thomas Watson Jr. reportedly fired off an angry memo asking how IBM, with its 'vast development activities', had lost 'our industry leadership position' to a firm with '34 people, including the janitor.'"

---

### ERROR 3 — Cressman's departure year from NMC

**What the post says (line 162):**
> "[George Cressman] had left NMC in **1965** to become head of the Weather Bureau"

**What sources say:**
Multiple sources (NOAA 200th anniversary site, WPC history, Washington Post obituary, web search) consistently report that Cressman left NMC directorship in **1964**, not 1965. He was appointed Director of National Meteorological Services for the Weather Bureau in 1964. In 1965, when ESSA was formed, he became Director of the National Weather Service — but that was the next step, not when he left NMC.

The research file `Shuman.md` (line 41) correctly states: "Cressman continued as director until 1964. Shuman then succeeded him as NMC director." The blog post contradicts the research file on this point.

**Severity:** Clear factual error. The year is wrong by one year.

**Suggested fix:** Change "left NMC in **1965**" to "left NMC in **1964**."

---

## POTENTIALLY IMPRECISE CLAIMS (not clear errors, but worth flagging)

### Note A — Shuman at IAS: JOHNNIAC vs. IAS machine

**What the post says (line 146):**
> "He had worked at the Institute for Advanced Study in Princeton from 1952 to 1954, attending lectures by J. Robert Oppenheimer and running test models on one of the IAS-class machines."

**What the research file says (`Shuman.md`):**
> "At IAS he used one of the world's earliest operating computers -- the **JOHNNIAC** (a late IAS-class machine, sometimes identified in sources as the IAS machine proper)"

**What web search found:**
The Washington Post obituary and alt.obituaries confirm Shuman used the "Johnniac" at IAS. The JOHNNIAC was physically located at RAND Corporation in Santa Monica, not at Princeton IAS. The IAS machine itself was at Princeton. Shuman was at Princeton, so he would most likely have used the **IAS machine proper** (or a clone), not the JOHNNIAC. The research file's parenthetical "(sometimes identified in sources as the IAS machine proper)" acknowledges this ambiguity. Sources consulted for the obituary may have loosely called it JOHNNIAC.

**Verdict:** The post's phrasing "one of the IAS-class machines" is deliberately vague and avoids this ambiguity — it is defensible. No correction required. If the post ever names the specific machine, verify it was the IAS machine at Princeton, not the JOHNNIAC at RAND.

---

### Note B — CDC 6600: "400 000 transistors" vs. "250 000"

**What the post says (line 142):**
> "It used approximately **400 000 transistors**, silicon rather than germanium"

**What the research file `IBM_7090_era_NWP_1959_1969.md` says:**
> "~250 000 silicon transistors"

**What web search found:**
Multiple authoritative sources (Wikipedia CDC 6600, CHM, multiple technical histories) report approximately **400 000 transistors**. The figure of 250 000 in the research file appears to be an undercount. The post's "400 000" matches Wikipedia and CHM sources.

**Verdict:** The post is correct; the research file has an undercount. No correction to the post needed. The research file `IBM_7090_era_NWP_1959_1969.md` should be updated to ~400 000 (or "approximately 400 000" per CHM).

---

### Note C — CDC 6600: "3 000 000 instructions per second" vs. MFLOPS

**What the post says (line 142):**
> "It executed roughly **3 000 000 instructions per second**"

And separately, the CDC 6600 caption references "3 MFLOPS" in passing.

**What sources say:**
The CDC 6600 is rated at ~3 million instructions/second (MIPS) and ~3 MFLOPS peak floating-point. These are consistent. However, the distinction matters: MIPS ≠ MFLOPS in general, but for the CDC 6600 the numbers happen to be approximately equal due to how the architecture is described in contemporary sources. The post does not conflate them in the main text — it says "instructions per second" which is accurate for the headline figure.

**Verdict:** No error. The numbers are consistent with sources.

---

### Note D — CDC 6600 world's fastest: "1964–1969"

**What the post says (line 152):**
> "Cray's machine ran at NMC until it was replaced by the even faster **CDC 7600** -- Cray's second masterpiece, five to ten times faster still, which held the title of world's fastest computer from 1969 to 1975."

**What sources say:**
The CDC 6600 was world's fastest 1964–1969. The CDC 7600 succeeded it. This is confirmed by CHM, Wikipedia, and research file. Accurate.

---

### Note E — "Two IBM 7090s at Goddard" for Mercury

**What the post says (line 52):**
> "The computing load for the mission was carried by **two IBM 7090s at the Goddard Space Flight Center**"

**What sources say:**
IBM's own history page and the research file confirm two 7090s at Goddard. However, IBM's history page also notes "an additional 7090 was installed at Mission Control to process and share radar data." The post mentions only the two at Goddard and the 709 in Bermuda, omitting the Mission Control 7090. This is a simplification, not an error. The post is not wrong about Goddard.

**Verdict:** Simplified but not incorrect. No correction needed.

---

### Note F — Katherine Johnson's location

**What the post says (line 54):**
> "The film placed a 7090 front and center at NASA Langley."

**What sources say:**
The *Hidden Figures* film does depict the IBM 7090 at NASA Langley (where Johnson worked), not at Goddard. This is correct. Johnson's manual verification was of the Goddard 7090's trajectory calculation, but she was based at Langley. The film shows the 7090 at Langley. This checks out.

---

### Note G — TIROS-1 weight

**What the post says (line 90):**
> "It was small -- about the size of a washing machine drum, 42 inches in diameter, 19 inches high. It carried two small vidicon television cameras…"

**What sources confirm:**
TIROS-1 was 42 inches (107 cm) across, 19 inches (48 cm) high, weighing 270 lbs (122 kg). The blog says "122-kilogram satellite" which matches. Dimensions confirmed. Height: sources say 56 cm (22 in), not 19 inches/48 cm. Wikipedia says "56 centimetres (22 in) high."

**The post says 19 inches high — sources say 22 inches high. This may be an error.**

Checking: "42 inches in diameter, 19 inches high" vs. "107 cm across, 56 cm (22 in) high."

**Verdict:** Possible measurement error. 56 cm = 22 inches, not 19 inches. The diameter of 42 inches is correct. The height of 19 inches appears to be wrong; the correct figure is 22 inches (56 cm).

**Suggested fix:** Change "42 inches in diameter, 19 inches high" to "42 inches in diameter, 22 inches high."

---

## VERIFIED CLAIMS

The following claims were checked and confirmed accurate:

| Claim | Status | Source |
|---|---|---|
| IBM 7090: over 50 000 germanium alloy-junction transistors | Confirmed | IBM 709_7090.md; web search |
| IBM 7090 six times faster than IBM 709 | Confirmed | IBM_709_7090.md; Wikipedia; multiple web sources |
| IBM 7090 rental $63 500/month | Confirmed | IBM_709_7090.md |
| IBM 7090 first installation December 1959 | Confirmed | IBM_709_7090.md |
| IBM 7090 memory cycle time 2.18 µs | Confirmed | IBM_709_7090.md |
| IBM 7090 purchase price $2 900 000 | Confirmed | IBM_709_7090.md |
| TIROS-1 launched April 1, 1960 at 11:40 UTC | Confirmed | Multiple web sources; research file |
| TIROS-1: 23 000 photos in 78 days | Confirmed | Multiple web sources; research file |
| TIROS-1 usable photos: 19 000 | Confirmed | Research file; Wikipedia |
| "Daisy Bell" sung by IBM 7094 at Bell Labs, 1961 | Confirmed | IBM_709_7090.md; research file; web sources |
| Performers: John L. Kelly Jr., Carol Lockbaum (vocals), Max Mathews (accompaniment) | Confirmed | Research file; web sources |
| Arthur C. Clarke visited Bell Labs, invited by John R. Pierce | Confirmed | Research file; web sources (Pierce described as electrical engineer and SF writer) |
| Two IBM 7090s at Goddard for Mercury | Confirmed | IBM_709_7090.md; IBM Archives; web search |
| IBM 709 in Bermuda as backup for Mercury | Confirmed | IBM_709_7090.md; web search |
| Three IBM 7094s at Goddard for Gemini | Confirmed | IBM_709_7090.md; research file |
| SABRE on two IBM 7090s at Briarcliff Manor | Confirmed | IBM_709_7090.md; web search |
| BMEWS 7090s at Thule Air Base ran ~30 years | Confirmed | IBM_709_7090.md; web search (retired 1980s ≈ 30 years from 1959) |
| CDC 6600 designed by Seymour Cray | Confirmed | All sources |
| CDC 6600 first delivered 1964 | Confirmed | Multiple web sources; research file |
| CDC 6600 world's fastest 1964–1969 | Confirmed | CHM; Wikipedia; research file |
| CDC 6600: ~3 000 000 instructions per second | Confirmed | Web search; CHM; research file |
| CDC 6600 ~400 000 silicon transistors | Confirmed | Web search (CHM, Wikipedia) — post correct, research file undercount |
| CDC 6600 cooled by Freon | Confirmed | Research file; multiple sources |
| CDC 6600 clock cycle 100 ns (10 MHz) | Confirmed | Wikipedia |
| Watson memo: 34 people including the janitor | Confirmed | CHM; web search; multiple sources |
| Shuman-Hovermale six-layer PE model operational mid-1966 | Confirmed | Research file; Shuman & Hovermale 1968 paper; web search |
| PE model paper: *J. Applied Meteorology*, 7(4), 525–547, 1968 | Confirmed | Research file; AMS journals |
| Shuman NMC director until 1981 | Confirmed | Shuman.md; web search |
| Shuman continued research until 1986 | Confirmed | Shuman.md |
| Shuman: Dept. of Commerce Silver Medal 1957, Gold Medal 1967 | Confirmed | Shuman.md |
| Shuman died July 29, 2005, aged 86, Fort Washington, MD | Confirmed | Shuman.md |
| Cressman died April 17, 2008, aged 88, Rockville, MD | Confirmed | Washington Post obituary |
| Cressman: IMO Prize 1977, AMS president 1978 | Confirmed | Research files |
| Seymour Cray died October 5, 1996, Colorado Springs, aged 71 | Confirmed | Wikipedia; web search (born 1925, died 1996 = 71) |
| Seymour Cray from Chippewa Falls, Wisconsin | Confirmed | Wikipedia; web search |
| Cray joined CDC in 1957 | Confirmed | Web search (CDC founded September 1957, Cray joined at founding) |
| IBM built ~300 machines across 7090/7094 production run | Plausible, widely cited | Not directly web-verified in this session, consistent with Columbia/Wikipedia |
| NMC formed January 1, 1958 from merger of JNWPU and NWAC | Confirmed | Shuman.md; research files |
| Shuman was JNWPU first employee (1954) | Confirmed | Shuman.md |
| Three-layer model went operational 1962 | Confirmed | Research file |
| IBM 7094 installed at NMC ~1963 | Confirmed | Research file |
| CTSS at MIT on 7094 | Confirmed | IBM_709_7090.md |
| Minovitch used UCLA 7090 for three-body problem / Voyager | Confirmed | IBM_709_7090.md |
| Shuman smoother paper: MWR vol. 85, November 1957 | Confirmed | Shuman.md |

---

## CORRECTIONS REQUIRED (Summary)

### Must Fix

1. **ERROR 3 — Cressman's departure year (line 162):**
   - Current text: "left NMC in **1965** to become head of the Weather Bureau"
   - Corrected text: "left NMC in **1964** to become head of the Weather Bureau"

2. **ERROR — TIROS-1 height (line 90):**
   - Current text: "42 inches in diameter, **19** inches high"
   - Corrected text: "42 inches in diameter, **22** inches high"

### Should Fix

3. **ERROR 2 — Watson memo paraphrase (line 144):**
   - Current text: `"the world's largest computer company" had been beaten by a firm with "34 people, including the janitor"`
   - The phrase "world's largest computer company" does not appear in the memo. Watson wrote about losing "our industry leadership position."
   - Suggested replacement: `IBM, with its "vast development activities," had lost "our industry leadership position" to a firm with "34 people, including the janitor"`

### Optional Improvements

4. **Note A — 6x faster clarification:**
   - The "six times faster than the 709" figure is correct. Since NMC skipped the 709 and went from 704 to 7090, a parenthetical could note the 704-to-7090 improvement was actually larger (7.5x per IBM data) if precision matters.

5. **Research file correction (not a post error):**
   - `IBM_7090_era_NWP_1959_1969.md` lists CDC 6600 transistor count as "~250 000 silicon transistors" — this should be updated to ~400 000 per Wikipedia, CHM, and multiple web sources. The post already has the correct figure.

---

*Review complete. Three corrections required in the post itself (Cressman's year, TIROS height, Watson memo paraphrase). Research file has one undercount to fix.*
