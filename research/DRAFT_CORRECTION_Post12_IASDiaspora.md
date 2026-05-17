# Draft Correction - Post 12: The Blueprint Von Neumann Gave Away

Status: COMPLETE
Source post: `/home/michal/repos/michalbrennek.github.io/_posts/2026-04-08-The-blueprint-von-Neumann-gave-away.md`

## Summary

Post 12 is generally well-researched and most major facts check out. Found 4 definite errors needing correction, 4 ambiguities that could be tightened, and several minor cosmetic issues. The narrative arc, the architectural claims, and the BESM "parallel invention" framing all hold up well.

---

## Errors that need correction

### 1. JOHNNIAC date in family table (line 32)

POST currently:
```
| | MANIAC (1952) | JOHNNIAC (1954) | ILLIAC I (1952) | ORDVAC (1952) | WEIZAC (1955) | SILLIAC (1956) |
```

JOHNNIAC was operational in **1953**, not 1954. Wikipedia: "The JOHNNIAC is an early computer built in 1953 by the RAND Corporation". Search confirms: "JOHNNIAC was taken offline on 11 February 1966, and officially retired on 18 February" after "operating almost continuously from 1953 for over 13 years."

**SUGGESTED EDIT:** Change "JOHNNIAC (1954)" to "JOHNNIAC (1953)".

The section heading on line 71 also says "JOHNNIAC -- The Machine That Invented AI (RAND Corporation, 1954)". The post body line 75 also says "operational in 1954". Both should be changed to 1953.

NOTE: Some sources do cite 1954 as the year JOHNNIAC ran its first useful program; 1953 is the year it was "built" or "first operational." Either date is defensible if specifying which event; but Wikipedia and CHM both lean to 1953.

### 2. ORDVAC tube count (line 36, table)

POST currently: ORDVAC | ~2200

Wikipedia ORDVAC article and the actual ORDVAC 1952 manual say **2718 vacuum tubes** total (40 CRTs in memory + 800 + 1100 arithmetic + 500 control = 2440 + 278; Wikipedia text says 2178 in one paragraph and 2718 manual count -- numbers vary by source). Some 1955 BRL survey reports cite 2178. None say 2200.

**SUGGESTED EDIT:** Change "~2200" to "2718" (or "~2700") for ORDVAC.

### 3. Klara von Neumann -- ENIAC and IAS or MANIAC? (line 55)

POST currently:
> "**Klara von Neumann** -- John's wife, and one of the first programmers to write code for both the ENIAC and the IAS machine -- wrote MANIAC's first programs."

Documented record: Wikipedia article on Klara Dán von Neumann lists her contributions as "the Monte Carlo method, ENIAC, and MANIAC I." She is not specifically documented as having programmed the IAS machine itself; her code work was for ENIAC (the meteorology forecast project) and MANIAC I at Los Alamos.

**SUGGESTED EDIT:** Replace "ENIAC and the IAS machine" with "ENIAC and the MANIAC". The sentence currently has internal redundancy too -- ENIAC and IAS machine, then "wrote MANIAC's first programs". Better:

> "**Klara von Neumann** -- John's wife, and one of the first programmers in history -- wrote MANIAC's first programs. (She had previously written code for the ENIAC meteorology forecast at Aberdeen.)"

### 4. WEIZAC: Estrins arrived 1953, not 1954 (line 149)

POST currently:
> "He arrived in Israel in 1954 with his wife **Thelma Estrin**, also an electrical engineer."

IEEE ETHW primary source: "In October 1953 the Estrins set out for Israel, with numerous stops along the way. **They arrived in Haifa on 26 December 1953**." The Wikipedia article on WEIZAC says "In 1952, Gerald Estrin... was chosen to lead the project." The post is off by ~6 months on the arrival.

**SUGGESTED EDIT:** Change "He arrived in Israel in 1954" to "He arrived in Israel in late 1953" or "The Estrins arrived in Haifa on 26 December 1953."

### 5. BESM-6 clock speed (line 236)

POST currently:
> "It used 60 000 transistors, ran at 9 MHz, and achieved 1 million instructions per second."

Wikipedia article body: "48-bit processor ran at **10 MHz** clock speed". Wikipedia infobox says 9 MHz. The body, with multiple secondary citations, is more authoritative. The Russian Virtual Computer Museum confirms 10 MHz in the design specification.

**SUGGESTED EDIT:** Change "9 MHz" to "10 MHz". (Or accept the 9-10 MHz range as commonly reported and write "ran at around 10 MHz".)

---

## Ambiguities worth tightening

### 6. SILLIAC currency formatting (lines 181)

POST currently:
> "Jeweler and horse-racing enthusiast **Adolph Basser** donated AU 50 000. Media mogul Sir Frank Packer funded the associated Nuclear Research Foundation. Estimated cost: AU 35 200 (about ten times the price of a Sydney suburban house). Final cost: AU 75 000."

Australia used the pound (£) until February 1966 (decimalization to Australian dollar). All these figures should be **AU£** (Australian pound), not "AU" alone. Wikipedia consistently formats as "AU£50,000."

**SUGGESTED EDIT:** Change "AU 50 000" → "AU£50,000"; "AU 35 200" → "AU£35,200"; "AU 75 000" → "AU£75,000". (Or with non-breaking spaces per blog convention: "AU£50 000" etc.)

### 7. Pekeris -- mathematician or meteorologist? (line 143)

POST currently:
> "**Chaim Leib Pekeris** was a mathematician at the Weizmann Institute of Science in Rehovot, Israel."

IEEE ETHW source describes him as "educated as a meteorologist" who later led the Department of Applied Mathematics. By the time WEIZAC was built he was indeed running an applied mathematics department, so "mathematician" is defensible but obscures his background -- he was an applied mathematician trained as a meteorologist/geophysicist, with major contributions in seismology, oceanography, and atmospheric science.

**SUGGESTED EDIT:** Soften to "applied mathematician" or add depth:
> "**Chaim Leib Pekeris** was an applied mathematician at the Weizmann Institute of Science in Rehovot, Israel, with a background in meteorology and geophysics."

### 8. Illiac Suite dating (line 123-125)

POST currently:
> "In 1955, composer **Lejaren Hiller** and mathematician **Leonard Isaacson** began feeding the machine rules of musical counterpoint...In August 1956, a student quartet at the University of Illinois performed the first three movements. The completed work, the **Illiac Suite** (later retitled String Quartet No. 4), was the first substantial musical composition created by a computer."

This is fine -- the composition began 1955, partial performance 1956, completed 1957. Wikipedia categorizes the work as "a 1957 composition" because that's when all four movements were finished. The post timing is correct; the only thing worth noting is that the "completed work" was finished in 1957, not 1956.

**SUGGESTED EDIT:** No change strictly required. Optionally clarify: "The completed four-movement work, finished in 1957..."

---

## Cosmetic / minor

### 9. Adolph Basser's profession

POST line 181 says Basser was a "Jeweler and horse-racing enthusiast." Wikipedia article on SILLIAC simply calls him a benefactor; the jeweler/horse-racing detail comes from Australian sources and biographies. Not incorrect, just unsourced in the post.

No correction needed.

### 10. "First computer in the Middle East" vs "First computer in Israel"

POST line 155: "It was the **first computer in the Middle East**."

IEEE ETHW source: "the first digital electronic computer constructed in the Middle East." Wikipedia: "the first computer in Israel, and one of the first large-scale, stored-program, electronic computers in the world." Both formulations exist in the primary literature.

No correction needed - "first computer in the Middle East" is supported by IEEE ETHW.

### 11. Bob May's first calculation

POST line 191: "The very first scientific calculation on SILLIAC was run by a PhD student named **Bob May**."

Wikipedia SILLIAC: "SILLIAC's first scientific computation was carried out by PhD student Bob May (later Robert May, Baron May of Oxford) in June 1956." Confirmed.

No correction needed.

---

## Verification limits

- Wayback Machine save attempts returned 429 (rate-limited) but the IEEE ETHW WEIZAC page is already archived at https://web.archive.org/web/20260227072110/https://ethw.org/Milestones:WEIZAC_Computer,_1955
- RAND.org URLs (footnote 1 source for JOHNNIAC history) returned HTTP 403 to WebFetch -- the public-facing PDF may still work in a browser
- 51,349-hour figure for JOHNNIAC lifetime and the "10 hours of continuous error-free operation" Selectron record both appear in the RAND History of the JOHNNIAC (Gruenberger 1968) -- not directly verified here but consistent with secondary sources reporting "over 50,000 hours"

## Recommendation

The post is in good shape. Apply edits 1-5 (the four definite errors) and edit 6 (currency formatting). Consider 7 (Pekeris) for accuracy depth. Skip 8-11 (already accurate or stylistic only).
