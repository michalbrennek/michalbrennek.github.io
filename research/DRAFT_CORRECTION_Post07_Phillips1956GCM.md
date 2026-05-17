# Draft Corrections for Post 7 (Phillips 1956 GCM)

Status: FINAL. Compiled 2026-05-17.

Post 7 file: `_posts/2026-03-30-The-first-climate-model-had-5KB-of-RAM.md`

Companion fact-verification document: `research/VERIFIED_FACTS_Post07_Phillips1956GCM.md`

---

## EXECUTIVE SUMMARY

**Post 7 does NOT carry any of the Phillips biographical errors flagged in the Post 43 briefing.** The post already says (correctly):
- Born "July 9, 1923, in Chicago" -- not March
- Deployed to "the Azores" -- not India/China
- PhD "under George Platzman" -- correct
- Does not mention wife, death location, or Rossby Medal year -- so cannot misstate them

**The biographical errors flagged in the briefing apply to OLDER notes that informed Post 43, not to Post 7 itself.** Post 7 is biographically clean.

**The corrections that ARE needed in Post 7 are minor IAS computer specification adjustments.** Two numerical errors (vacuum tube count and multiply time) and one unverifiable claim (power consumption) should be tightened. These are correctness-tightening edits, not factual retraction.

---

## REQUIRED CORRECTIONS

### Correction 1 (MINOR but specific): IAS multiply time

**Current text** (line 47):
```
- **Multiply time**: 700 microseconds
```

**Corrected text:**
```
- **Multiply time**: 713 microseconds
```

**Reason:** Both Wikipedia and the project's own IAS_machine.md research file give the IAS multiply time as exactly 713 microseconds (citing primary engineering reports). The 700 figure is a rounded approximation; 713 is the precise value. Trivial fix.

---

### Correction 2 (MINOR but specific): IAS vacuum tube count

**Current text** (line 49):
```
- **Construction**: about 2,300 vacuum tubes (logic plus memory drivers) and several thousand diodes; 40 Williams cathode-ray tubes for memory
```

**Corrected text:**
```
- **Construction**: about 1,700 vacuum tubes (logic plus memory drivers); 40 Williams cathode-ray tubes for memory (each storing a 32 x 32 bit array of 1,024 bits, plus 1 monitoring CRT for 41 CRTs total)
```

**Reason:** Wikipedia gives 1,700 total. The project's IAS_machine.md research file says "~1700 logic tubes (triodes: 6J6, 5670, 5687; diodes: 6AL5) + ~150 pentodes driving the memory CRTs; total ~3000 including all subsystems." The 2,300 figure may originate from the original 1946 design specification (which planned for ~2,300 RCA Selectron memory tubes that were never built; the switch to Williams tubes reduced the count substantially). Recommend the Wikipedia figure of 1,700 for cleanest provenance.

**Alternative (lighter) wording if the writer prefers to avoid being precise:**
```
- **Construction**: about 1,700 vacuum tubes; 40 Williams cathode-ray tubes for memory
```

---

### Correction 3 (RECOMMENDED): Power consumption claim

**Current text** (line 50):
```
- **Power consumption**: 61 kilowatts
```

**Issue:** The 61 kW figure cannot be verified against Wikipedia, IAS.edu, Computer History Museum, or any other accessible primary or secondary source. The Smithsonian page (which might have it) returned HTTP 403. The IAS_machine.md project research file does not give a power figure.

**Options:**

(a) **Trace the original source** for 61 kW and add a footnote citing it.
(b) **Soften the phrasing** to "tens of kilowatts."
(c) **Remove the line** entirely (the IAS_machine.md research file omits power consumption).

**Recommended action:** Option (a) -- trace the source. If the writer cannot find a primary citation, fall back to option (b) and soften to "tens of kilowatts" rather than the specific 61 kW number.

---

## OPTIONAL TIGHTENING (NOT ERRORS - just precision)

### Optional 1: IAS-machine date framing

**Current text** (line 40):
```
The computer at the IAS was built under the direction of John von Neumann between 1946 and 1951.
```

**Optionally tightened to:**
```
The computer at the IAS was built under the direction of John von Neumann between 1946 and 1952, with limited operation beginning in 1951.
```

**Reason:** The machine was formally dedicated on 10 June 1952. Limited operation began in summer 1951. The original phrasing is defensible but slightly understates the construction timeline; 1946-1952 is more accurate.

---

### Optional 2: Footnote attribution for the programming-language quote

**Current text** (footnote [^1], line 214):
```
[^1]: Phillips, N. A. (1990). Dispersion Processes in Large-Scale Weather Prediction. Sixth IMO Lecture, WMO No. 700, World Meteorological Organization, Geneva. Phillips' retrospective on IAS-machine-era programming.
```

**Optionally clarified:**

The verbatim quote about "code was written in what would now be called 'machine language' except that it was one step lower" is reproduced in Lewis 1998 BAMS retrospective (p. 47) where Lewis cites it to Phillips's 1989 NCAR oral history transcript. The Phillips 1990 IMO Lecture covers similar material but the exact phrasing may differ. The writer should verify which Phillips publication has the exact quote and adjust the citation accordingly. (Both citations are defensible if the same words appear in both publications.)

**No edit strictly required** -- the existing attribution is plausible. This is purely a precision note.

---

### Optional 3: "Approximately 10 kilobytes" gloss on drum memory

**Current text** (line 45):
```
- **Drum memory**: 2,048 words - approximately **10 kilobytes** (later upgraded to 12,288 words)
```

**Issue:** 2048 words x 40 bits = 81,920 bits = ~10 KB. Correct. But the "approximately 10 kilobytes" phrasing for the original 2K drum could be slightly tighter: 10,240 bytes = 10 KB exactly. The "approximately" is unnecessary. This is style, not factual error. **No edit needed.**

---

### Optional 4: Smagorinsky "reported for duty"

**Current text** (line 191):
```
Smagorinsky was asked to lead the new **General Circulation Research Section**, and reported for duty on October 23, 1955.
```

**Note:** 23 October 1955 is the OFFICIAL FOUNDING DATE of the General Circulation Research Section (per POST16_REVIEW.md citing primary sources). Whether Smagorinsky physically "reported for duty" on that exact date or was the founding director from that date is a fine distinction. **The date is correct.** The phrasing "reported for duty" is a stylistic choice consistent with the source narrative.

**No edit needed** unless the writer wants to be very precise, in which case:
```
The new General Circulation Research Section was established on October 23, 1955, with Smagorinsky as its founding director.
```

---

## ITEMS THAT DO NOT REQUIRE CORRECTION (briefing flagged, but Post 7 is already correct)

For the record, the following Post 43 briefing concerns DO NOT apply to Post 7 because Post 7 already has the correct values:

1. **Birth month:** Post 7 says "July 9, 1923" -- correct (not March).
2. **WWII deployment:** Post 7 says "the Azores" -- correct (not India/China).
3. **PhD advisor:** Post 7 says "George Platzman, a mathematical meteorologist who later wrote the definitive history of the ENIAC forecasts" -- correct.
4. **Wife and family:** Post 7 does not mention Phillips's wife or family -- cannot misstate.
5. **Death location:** Post 7 does not mention Phillips's death -- cannot misstate.
6. **Rossby Medal year:** Post 7 does not mention the Rossby Medal -- cannot misstate.
7. **AMS Norman Phillips Award:** Post 7 does not mention an AMS Norman Phillips Award -- cannot misstate.

**Post 7's biographical narrative is correct as written.** The post predates the Post 43 detailed biographical research but used reliable sources for its biographical claims.

---

## OVERALL RECOMMENDATION

**Post 7 does not require URGENT correction.** It does not carry any of the biographical errors flagged in the Post 43 briefing.

If the writer wants to tighten the post to the highest verifiable standard, three small edits to the IAS computer specifications would help:
1. Change multiply time from 700 to 713 microseconds.
2. Change vacuum tube count from "about 2,300 vacuum tubes (logic plus memory drivers) and several thousand diodes" to "about 1,700 vacuum tubes."
3. Either source or soften the "61 kilowatts" power-consumption claim.

These edits are correctness improvements, not error corrections. The post can stand as-published without them; with them, the post becomes more rigorously sourceable.

The biographical and scientific narrative of Post 7 is solid and consistent with the now-verified Phillips facts.
