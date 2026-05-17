# Draft Corrections: Post 8 "The Butterfly That Broke the Forecast"

Targeted corrections for Post 8 (`_posts/2026-03-31-The-butterfly-that-broke-the-forecast.md`) based on the fact-check pass against the deeper-research files compiled for Post 41 (shipped 2026-05-15). Cross-reference: `VERIFIED_FACTS_Post08_Butterfly.md`.

The brief flagged six potential corrections; after fact-checking, **five of the six do not apply** to Post 8 as written -- the post simply does not make those claims. The two real corrections are: (1) a wrong journal citation in footnote [^5], and (2) the absence of Margaret Hamilton and Ellen Fetter from the LGP-30 discovery story.

---

## Correction 1: Footnote [^5] cites the wrong 1963 Lorenz paper

### Current text (line 242, footnote section)

```
[^5]: Lorenz, E. N. (1963). The predictability of hydrodynamic flow. *Transactions of the New York Academy of Sciences*, Series II, 25(4), 409-432.
```

### Problem

The seagull quotation in the body ("One meteorologist remarked that if the theory were correct, one flap of a sea gull's wings would be enough to alter the course of the weather forever...") does NOT come from the NYAS *Transactions* paper. It comes from Lorenz's other 1963 paper, "The mechanics of vacillation" (*J. Atmos. Sci.* 20(4), 448-464), where the seagull line appears on p. 461. This is confirmed in Kerry Emanuel's NAS Biographical Memoir of Lorenz, footnote 6.

The two 1963 Lorenz papers are routinely conflated in the popular literature -- they share an author, a year, and the early-chaos subject matter -- but the seagull metaphor belongs to the JAS paper.

### Corrected text

```
[^5]: Lorenz, E. N. (1963). The mechanics of vacillation. *Journal of the Atmospheric Sciences*, 20(4), 448-464. The seagull line is on p. 461. [AMS](https://journals.ametsoc.org/view/journals/atsc/20/5/1520-0469_1963_020_0448_tmov_2_0_co_2.xml)
```

(URL to be verified against current AMS journal redirects before publishing.)

### Context in body

The reference appears in the body around line 134-136:

> His original metaphor was a **seagull**. In a 1963 paper for the New York Academy of Sciences, he wrote:
>
> > "One meteorologist remarked that if the theory were correct, one flap of a sea gull's wings would be enough to alter the course of the weather forever. The controversy has not yet been settled, but the most recent evidence seems to favor the sea gulls."[^5]

This body text also identifies the venue wrongly. The body claim "In a 1963 paper for the New York Academy of Sciences" should be changed.

### Corrected body text

> His original metaphor was a **seagull**. In his 1963 paper "The mechanics of vacillation" in the *Journal of the Atmospheric Sciences*, he wrote:
>
> > "One meteorologist remarked that if the theory were correct, one flap of a sea gull's wings would be enough to alter the course of the weather forever. The controversy has not yet been settled, but the most recent evidence seems to favor the sea gulls."[^5]

This is a minimal-edit correction: just swap "1963 paper for the New York Academy of Sciences" for "1963 paper 'The mechanics of vacillation' in the *Journal of the Atmospheric Sciences*" and fix the footnote target.

---

## Correction 2: Hamilton and Fetter are absent from the discovery story

### Problem

Post 8 narrates the truncated-printout incident as a one-person event: "Lorenz looked at the printout. Found the line he wanted. Typed the numbers back in. Then he went down the hall for a cup of coffee."

The deeper research (Quanta Magazine 2019, "The hidden heroines of chaos"; cross-referenced in `Lorenz_chaos_and_predictability.md` section 2) establishes that two women were the programmers of the LGP-30 during the critical period:

- **Margaret Hamilton** (later famous for leading the Apollo flight-software effort at MIT Draper Lab) arrived at MIT in summer 1959 fresh out of Earlham with a math degree and no programming experience. She wrote and debugged the LGP-30 code, editing binary instructions on paper tape with a pencil. She trained her replacement in summer 1961.
- **Ellen Fetter** (Mount Holyoke math, 1961) took over from Hamilton in summer 1961. Fetter is the programmer who was likely at the keyboard during the truncated-printout incident in winter 1961, and she produced the hand-plotted strange-attractor trajectories that became the canonical chaos figures.

Lorenz himself, asked about their contribution late in life: "Every one of them would say that if this were going on today... they'd be a co-author!" (Sokoler/Yoder/Gabai, Quanta 2019.)

This omission matters because the central narrative of Post 8 -- the human moment of discovery -- needs the humans in it. There is also a contemporary discoverability concern: Hamilton and Fetter were uncredited for decades; their absence from Post 8 perpetuates that uncreditedness.

### Proposed insertion

Add a short paragraph just before "The Cup of Coffee" section (between line 65 "But that 800-pound desk changed science forever." and line 66 "### The Cup of Coffee"), or alternatively early within "The Cup of Coffee" section. Draft language (about 100 words, matching the post's voice):

```
### The People at the Keyboard

Lorenz did not run the LGP-30 alone. Two women programmed the machine for him -- and for decades they were uncredited.

**Margaret Hamilton** arrived at MIT in summer 1959 with a fresh math degree from Earlham and zero programming experience. She wrote and debugged Lorenz's code, sometimes editing binary instructions on paper tape with a pencil. (She would later lead the flight software for Apollo at MIT Draper Lab. Yes, that Margaret Hamilton.) In summer 1961 she trained her replacement, **Ellen Fetter** of Mount Holyoke. It was Fetter, almost certainly, who typed in the truncated numbers on the day Lorenz discovered chaos. She also produced the first hand-plotted figures of the strange attractor.

Asked late in life what their role would be called today, Lorenz answered without hesitation: "Every one of them would say that if this were going on today... they'd be a co-author!"
```

### Then revise "The Cup of Coffee" opening

The current text says "He looked at the printout. Found the line he wanted. Typed the numbers back in." This can stay (Lorenz himself may well have done this particular re-entry), but a hedge can be added at the right narrative beat. Alternative if a more accurate framing is preferred:

> Someone -- probably Fetter, though Lorenz himself sometimes ran the machine -- looked at the printout, found the line he wanted, and typed the numbers back in.

The "almost certainly Fetter" framing is what the Quanta piece supports; treat as a soft attribution since the primary source is Lorenz's own decades-later interviews. Either framing (preserved as Lorenz, or amended to credit Fetter) is defensible.

---

## Brief-flagged corrections that do NOT apply

The fact-verification brief listed six corrections to apply if found in Post 8. Five of those do not apply, because Post 8 does not make the corresponding claims:

1. **"LGP-30 specs: 60 multiplications/second, 31-bit words"** -- Post 8 correctly states "roughly 60 calculations per second" (line 56 and footer line 272). Post 8 does not mention word size at all. No correction needed.

2. **"'Butterfly' title was Philip Merilees's, NOT Lorenz's"** -- Post 8 already explains this correctly (lines 132-144). The post devotes an entire section ("The Butterfly That Wasn't His") to this very point. No correction needed.

3. **"Lorenz's 1963 metaphor was a SEAGULL"** -- Post 8 already says this correctly (line 134: "His original metaphor was a **seagull**"). No correction needed.

4. **"The 1972 AAAS talk WAS delivered (not abstract-only)"** -- Post 8 represents the talk as delivered (lines 138-144 describe Lorenz being "asked to give a talk... made one up for him... The talk was never formally published as a journal paper. Its text survived as Appendix 1..."). No correction needed.

5. **"Lorenz's PhD advisor was James Murdoch Austin (NOT Victor Starr)"** -- Post 8 does not name a PhD advisor at all. No correction needed.

6. **"Father was MIT mechanical engineer (NOT dentist)"** -- Post 8 does not mention the father's profession at all. No correction needed.

---

## Optional refinements (not strictly required)

These are not corrections of errors but possible enrichments aligned with the deeper-research narrative:

- **Statistical Forecasting Project context.** Mention that Lorenz built the 12-variable model as a strawman to disprove statistical (linear-regression) forecasting -- and instead discovered chaos. This is the irony at the heart of his career. It would fit in "The Cup of Coffee" section before introducing the 12-variable model.

- **Smagorinsky's 1969 butterfly.** Joseph Smagorinsky used the butterfly metaphor in print in 1969, three years before Merilees coined the talk title. Worth a footnote alongside the Merilees story.

- **Original paper title "Deterministic Turbulence."** The JAS editor made Lorenz change it. A nice one-line trivium.

- **Cross-link forward to Post 41.** Now that Post 41 "Two Decimal Places at MIT" exists (shipped 2026-05-15), a backward cross-link from Post 8 to Post 41 -- something like "the deeper biography is in [Two Decimal Places at MIT](...)" -- would help readers find the expanded treatment. (This is the kind of cross-link that the no-forward-promises rule explicitly permits, because the target is already live.)

None of these are required to ship a correction; flagged for the next revision pass.

---

## Patch summary (minimal-edit version)

If only the two errors are fixed, the actual diff to Post 8 is small:

1. **Line 134** body text: change "In a 1963 paper for the New York Academy of Sciences, he wrote:" to "In his 1963 paper 'The mechanics of vacillation' in the *Journal of the Atmospheric Sciences*, he wrote:"

2. **Line 242** footnote [^5]: change the reference from the NYAS *Transactions* paper to the JAS "The mechanics of vacillation" paper.

3. **Insert a "The People at the Keyboard" mini-section** between lines 65 and 66 (just before "### The Cup of Coffee") crediting Margaret Hamilton and Ellen Fetter.

The patch is mechanically small but historically significant -- particularly the Hamilton/Fetter insertion, which gives credit to two women who were uncredited for decades on the work that produced one of the iconic discoveries in 20th-century science.
