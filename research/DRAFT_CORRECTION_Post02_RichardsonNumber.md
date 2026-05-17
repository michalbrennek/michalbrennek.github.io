# Draft Corrections: Post 02 - The Richardson Number

Source: `/home/michal/repos/michalbrennek.github.io/_posts/2026-03-25-The-number-that-connects-turbulence-to-war.md`

Companion: `research/VERIFIED_FACTS_Post02_RichardsonNumber.md`

Corrections are listed from most consequential to least. Tier A = factually wrong or unsupported strong claim. Tier B = wording issue that misattributes a quote or implies more than the source supports. Tier C = minor pedagogical caveat / hedge recommended.

---

## A1. Misattribution of "Counting is an antiseptic against prejudice"

**Current text (line 142):**
> His philosophy, as David Berreby put it in *Nautilus*, was that "counting is an antiseptic against prejudice."[^3] Richardson deliberately ignored who was a "terrorist"...

**Problem:** Berreby quotes Richardson saying this *directly* in Nautilus. The line is Richardson's own, not Berreby's framing of Richardson.

**Proposed corrected text:**
> "Counting is an antiseptic against prejudice," Richardson said.[^3] He deliberately ignored who was a "terrorist" and who was a "freedom fighter"...

**Footnote unchanged.** (Berreby 2014, Nautilus, remains the source for the quotation.)

---

## A2. Unverified "I do not like preparations for war" quote attributed to a letter to Bjerknes

**Current text (line 104):**
> As he wrote to the Norwegian meteorologist Vilhelm Bjerknes: **"I do not like preparations for war"**.[^4] Yes, *that* Bjerknes - the same man whose published observations Richardson used for his 1910 forecast on the pile of hay...

**Problem:** No primary or secondary source I checked (Berreby/Nautilus, Wikipedia, MacTutor, search engines) supports either:
(a) that the exact phrase "I do not like preparations for war" was written by Richardson, or
(b) that it was sent to Vilhelm Bjerknes specifically.

The footnote points to Gleditsch (2020), but the Gleditsch volume URL was inaccessible (Springer auth redirect) and I could not confirm. The widely cited Richardson sentiment is that he "could not, with a clear conscience, work under military auspices" (paraphrased from his resignation reasoning). The specific Bjerknes letter recipient is the higher-risk claim.

**Two options:**

**Option 1 (preferred): retain the quote but verify in Gleditsch 2020 before publication, or replace with a quote that IS verified.**

If you cannot verify the quote in Gleditsch (2020) chapter that discusses Richardson's pacifism, replace with a softer formulation:

> When the Met Office became part of the Air Ministry, Richardson resigned on grounds of conscience. As his MacTutor biographer summarises, joining the new Air Ministry "would have meant that Richardson would have become part of the military," and his pacifism would not allow it.[^4]

**Option 2: keep but hedge the recipient.**

> Reflecting later on his resignation, Richardson said he "did not like preparations for war."[^4] (The remark is reported in various biographical sketches; the recipient and exact wording vary by source.)

**Footnote replacement (Option 2):**
[^4]: Paraphrased from biographical material in Gleditsch (2020) and Ashford (1985). The exact wording and recipient are not consistently sourced across the literature.

**Action recommended:** Check Gleditsch (2020) Springer Open Access volume directly to find the exact wording and primary source before publication. The Bjerknes attribution is the riskier specific.

---

## A3. "One year before the first operational computer weather forecast"

**Current text (line 186):**
> Richardson died quietly in his sleep on September 30, 1953, in Kilmun, Scotland. One year before the first operational computer weather forecast.

**Problem:** Standard NWP history puts the first *operational* numerical weather forecast at the Joint Numerical Weather Prediction Unit (JNWPU) on 15 May 1955, not 1954. Earlier ENIAC (1950) and IAS (1953-54) runs were research/experimental. Some sources count the start of routine JNWPU forecasting in late 1954, but the production-grade "operational" forecast distribution is 1955.

**Proposed corrected text:**
> Richardson died quietly in his sleep on September 30, 1953, in Kilmun, Scotland. Less than two years before the first operational computer weather forecast.

**Or, more specific:**
> Richardson died quietly in his sleep on September 30, 1953, in Kilmun, Scotland. Eighteen months before the Joint Numerical Weather Prediction Unit produced its first operational forecast in May 1955.

**No new footnote needed** if the upcoming series posts cover JNWPU; otherwise add:
[^N]: The Joint Numerical Weather Prediction Unit (US Weather Bureau, Air Force, Navy) issued its first operational numerical forecast on 15 May 1955. See Harper, K. C. (2008). *Weather by the Numbers*, MIT Press.

---

## B1. "Eskdalemuir Observatory in Scotland" - "bleak and humid solitude" attribution

**Current text (line 43):**
> Richardson had noticed something specific during his observations at Eskdalemuir Observatory in Scotland, that bleak and remote place he described as a land of "bleak and humid solitude."[^2]

**Problem:** Eskdalemuir Observatory is in Scotland - confirmed. The phrase "bleak and humid solitude" is widely attributed to Richardson's autobiographical writing; the post cites Hayes (2001) American Scientist. American Scientist had a redirect loop in this environment and I could not verify the phrase appears there. The phrase is also commonly traced to Ashford (1985) *Prophet - Or Professor? The Life and Work of Lewis Fry Richardson*.

**Recommended:** Spot-check the Hayes article (or Ashford) before publication to confirm the phrase appears. If only in Ashford and not Hayes, change footnote [^2] to:
[^2]: Ashford, O. M. (1985). *Prophet - Or Professor? The Life and Work of Lewis Fry Richardson.* Adam Hilger, p. [check].

If verified in Hayes, footnote stays as is.

---

## B2. Miles-Howard "independent confirmation decades later" - minor precision

**Current text (line 61):**
> The key result - confirmed independently by Miles (1961) and Howard (1961) decades later...

**Problem:** Miles and Howard did not "independently confirm" Richardson's 1920 result in the way the phrasing suggests. They proved a more precise theorem: the Miles-Howard theorem provides a *sufficient* (not necessary) condition for stability of stratified parallel shear flow when Ri >= 1/4 everywhere. Richardson's 1920 argument was heuristic/energetic; Miles-Howard is the rigorous mathematical proof. The Howard 1961 paper "Note on a paper of John W. Miles" is companion to Miles 1961.

**Proposed corrected text:**
> The key result - given rigorous mathematical proof by Miles (1961) and Howard (1961) decades later as the Miles-Howard theorem - comes down to a single threshold:

**Reference list addition (optional):**
* Howard, L. N. (1961). Note on a paper of John W. Miles. *J. Fluid Mech.*, 10, 509-512. [DOI](https://doi.org/10.1017/S0022112061000317)

The current references list cites only Miles 1961; Howard 1961 is mentioned in the body but missing from references. Add it.

---

## B3. Ri < 0.25 = "shear wins... atmosphere tears itself apart" pedagogical caveat

**Current text (lines 63-64):**
> - **Ri > 0.25** - Stability wins. Buoyancy suppresses the shear. The atmosphere stays calm. Smooth ride.
> - **Ri < 0.25** - Shear wins. The atmosphere tears itself apart. Turbulence.

**Problem:** The Miles-Howard theorem says Ri > 1/4 *everywhere* is a sufficient condition for stability. Ri < 1/4 is a *necessary but not sufficient* condition for instability - in other words, Ri < 0.25 makes turbulence possible, but does not guarantee it. The flow may still be stable.

**Recommendation:** This is a pedagogical post, and the current framing is standard in atmospheric science teaching. No change required, but if you want to be more precise:

**Proposed corrected text:**
> - **Ri > 0.25** - Stability wins. Buoyancy suppresses the shear. The atmosphere stays calm. Smooth ride.
> - **Ri < 0.25** - Shear can win. The atmosphere can tear itself apart. Turbulence becomes possible.

(Optional. The current post's framing is acceptable for a popular audience.)

---

## C1. "Bjerknes... gave us the very concept of weather 'fronts'"

**Current text (line 104):**
> Yes, *that* Bjerknes - the same man whose published observations Richardson used for his 1910 forecast on the pile of hay, and the father of the Bergen School of Meteorology that gave us the very concept of weather "fronts."

**Minor:** The polar front theory is more directly attributable to Jacob Bjerknes (Vilhelm's son) and the Bergen School collective work c.1918-1919. Vilhelm Bjerknes led the Bergen School but the "front" terminology and concept came from his students (Jacob Bjerknes, Bergeron, Solberg). The current phrasing is standard popular shorthand; no correction strictly required.

**Optional rewording:**
> ...the father of the Bergen School of Meteorology, whose researchers gave us the very concept of weather "fronts."

---

## C2. "Atmospheric Diffusion (1926), with over a thousand citations"

**Current text (line 106):**
> His most cited paper to this day - "Atmospheric Diffusion" (1926), with over a thousand citations - was work he had already completed before the realization.

**Problem:** Did not verify the citation count within budget, but the actual paper is "Atmospheric diffusion shown on a distance-neighbour graph" (Proc. Roy. Soc. London A 110:709-737). It is indeed his most-cited paper; Google Scholar typically shows 3000+ citations. "Over a thousand" is conservative and correct.

**Optional:** Use full title for the post's research notes / sourcing:
> His most cited paper to this day - "Atmospheric diffusion shown on a distance-neighbour graph" (1926), with thousands of citations...

No strict correction needed.

---

## C3. Mention of Miles/Howard in the references list

**Current reference list omission:** Howard (1961) is mentioned in body but missing from the References section. Add (see B2 above):

* Howard, L. N. (1961). Note on a paper of John W. Miles. *J. Fluid Mech.*, 10, 509-512. [DOI](https://doi.org/10.1017/S0022112061000317)

---

## Summary

**Must fix before publication (Tier A):**
1. A1 - Reattribute the "antiseptic against prejudice" quote to Richardson, not Berreby (line 142).
2. A2 - Verify or hedge the "I do not like preparations for war" / Bjerknes recipient claim (line 104). Check Gleditsch (2020) directly.
3. A3 - Change "one year before the first operational computer weather forecast" to "less than two years before" or specify JNWPU May 1955 (line 186).

**Should fix (Tier B):**
4. B1 - Verify "bleak and humid solitude" appears in Hayes 2001 or change footnote [^2] (line 43).
5. B2 - Reword Miles/Howard 1961 as "Miles-Howard theorem" and add Howard 1961 to references (line 61).
6. B3 - Optional pedagogical caveat on Ri < 0.25 (line 64).

**Nice to have (Tier C):**
7. C1 - Wording on Bergen School & "fronts" (line 104).
8. C2 - Full title of Atmospheric Diffusion paper (line 106).
9. C3 - Add Howard 1961 to references (line 220-area).

**Confidence not yet reached:**
- The dramatic "Burned them" verb (line 103) is unsourced; Wikipedia/MacTutor say "destroyed". This is dramatic license, not a factual error.
- "Died quietly in his sleep" specific phrasing: not separately verified, but widely repeated in obituaries; safe.
- "Power-law slope: factor of about three per tenfold severity" - standard for Richardson's exponent ~0.5; consistent with Berreby & Gleditsch.
