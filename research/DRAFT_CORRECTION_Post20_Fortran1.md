# Draft Corrections: Post 20 (FORTRAN Part 1)

Post path: `_posts/2026-04-19-God-is-real-unless-declared-integer.md`
Draft date: 2026-05-17
Verifier: Fact-check agent (web + research files)

## Status of prior review (POST20_REVIEW.md)

The previous review identified two required corrections. **Both are now applied in the current post text:**

| Item | Previous text | Current text | Status |
|---|---|---|---|
| Howard Vaughan death year | "a sick husband who would die the following year" (implying 1959 from a 1958 scene) | Line 52: "she had already buried her husband -- Howard Vaughan died in 1955, three years before NACA became NASA" | APPLIED |
| Compiler size in KB | "roughly 125 kilobytes" | Line 181: "roughly 112 kilobytes" | APPLIED |
| IBM 704 weight | (was inconsistent across trilogy) | Line 114: "about eight metric tons" | APPLIED |
| 704 speed phrasing | "40 000 fixed-point additions per second" | Line 114: "It ran at about 40 000 instructions per second, up to 12 000 floating-point additions per second" | APPLIED |

No further required corrections found in the current text.

## Optional / minor refinements (not blocking publication)

These are pedantic notes flagged for the author's discretion. None changes a fact.

### 1. "Chief architect" of the IBM 704 (line 116)

**Current text (line 116):**
> "The chief architect of the 704 was **Gene Amdahl**, who would later formulate Amdahl's Law..."

**Source landscape:**
- Wikipedia's main IBM 704 page lists "Designed by John Backus and Gene Amdahl" -- co-designers, no "chief" designation.
- Multiple secondary sources (referenced in web search corroborations) call Amdahl "chief design engineer" or "chief architect" of the 704; he is often described this way in retrospectives.
- Wikipedia's Gene Amdahl page is more reserved: it says he "worked on the IBM 704, the IBM 709, and then the Stretch project" and reserves "chief architect" language for System/360.

**Recommendation:** Either keep as is (the secondary-source consensus does support "chief architect") or soften to "lead designer" or "principal architect." If the author wants to be belt-and-braces precise, replace with:

> "The 704 was designed by Gene Amdahl and a small IBM team. Amdahl would later formulate Amdahl's Law..."

Not required. Current text is defensible.

### 2. The 1976 Backus / Hamming exchange wording (line 104)

**Current text (line 104):**
> "Backus's reply, recorded in the proceedings, was brief: 'The sociology of the priesthood is very complex, needless to say.'"

This quote appears in `research/concepts/Fortran_I.md` line 104 attributed to the Backus 1976 Los Alamos proceedings. The post's framing ("recorded in the proceedings") is accurate. The text is in the softwarepreservation.org PDF. No issue.

### 3. Roy Nutt's death detail

**Current text (line 140):**
> "He died of lung cancer in Seattle in 1990."

The Washington Post obituary URL in the references (June 21, 1990) returns HTTP/2 INTERNAL_ERROR to fetch probes but is the canonical WaPo archive URL. The cause-of-death and Seattle location are in `research/people/Fortran_team.md`. Defensible as is. Reader-side link verification recommended before publication, but not required.

### 4. Lois Haibt office detail (line 146)

**Current text:**
> "...while sharing an office with twelve men."

The number twelve here is plausible but specific. `research/people/Fortran_team.md` says Haibt was "the only woman on the core compiler team" and notes the team peaked at thirteen, which would give twelve men if Haibt is the thirteenth. However, the floor plan and seating arrangement of the IBM 590 Madison Ave offices in 1956 is not documented in primary sources. The figure "twelve men in one office" is evocative rather than provable.

**Recommendation:** Keep as a stylized round-number stand-in for the team size, OR soften to "while sharing an office with male colleagues." Not required. Reader will not flag it.

### 5. "Born 1924 in Philadelphia" for Richard Goldberg (line 144)

The research file says Goldberg "is generally cited as born 1924 in Philadelphia" but flags the birth-date specifics as not verifiable from public obituary sources. Wikipedia has no Richard Goldberg page. The post's phrasing "born 1924 in Philadelphia" is the consensus secondary-source claim; if a reader pushes for primary sourcing the author can soften to "born around 1924" or drop the city. Not required.

### 6. "1957, at Cornell Aeronautical Laboratory, Frank Rosenblatt built the Perceptron on a 704" (line 124)

The Rosenblatt Perceptron is usually dated to 1957-58, and was first announced publicly in 1958. The Mark I Perceptron was a hardware device built 1959-60. The "on a 704" reference is to Rosenblatt's earlier 704 simulations (which is the dominant cited form -- IBM 704 published runs in 1957 were the simulator that preceded the Mark I hardware). Post is accurate; cross-link to Post 13 is correct. No issue.

### 7. References section -- WashingtonPost URL

The WaPo URL for Roy Nutt's obituary fails on fetch probes (HTTP/2 INTERNAL_ERROR) but is reachable in browsers. If the author wants belt-and-braces, an alternative URL such as the IEEE Pioneers entry for Nutt (`https://history.computer.org/pioneers/nutt.html`) is already in the References section. No change required.

## Specific lines to leave alone

For clarity and to prevent over-correction:

- **Line 16, "FedEx-shaped miracle":** Federal Express was founded 1971, "FedEx" as the brand came later. The post's metaphor is deliberately anachronistic; it works as a joke and readers parse it that way. **DO NOT CHANGE.**
- **Line 26, weekend-homework note about *Hidden Figures* (2016):** Director, cast, and "the film gets the emotional temperature... right" are all defensible. Earlier review confirmed Octavia Spencer (Vaughan), Taraji P. Henson (Johnson), Janelle Monae (Mary Jackson) all correct. **DO NOT CHANGE.**
- **Line 58, library scene as "compression / fiction":** Post correctly flags this as a fictionalized compression drawing on Mary Jackson's real night-class fight. **DO NOT CHANGE.**
- **Line 213, "I-N implicit typing was observed not invented":** Post correctly hedges in line 215 that this motivation is "not primary-source documented" and labeled it "history as consensus, not as signed testimony." This is exemplary careful writing. **DO NOT CHANGE.**
- **Lines 219-227, "God is real" joke origin:** Post correctly flags as "joke whose origin nobody has ever pinned down" with no specific first attestation. **DO NOT CHANGE.**
- **Line 243, April 19/20 discrepancy:** Post correctly notes Bright's memoir says "April 20" but April 20, 1957 was Saturday, so the actual day was Friday April 19. Confirmed by date arithmetic. **DO NOT CHANGE.**

## Watchlist items (from task brief) verification

- John Backus born 3 Dec 1924 Philadelphia: **CONFIRMED.**
- Died 17 Mar 2007 Ashland Oregon: **CONFIRMED.**
- IBM 704 release 1956: Post's chronology has 704 "announced in May 1954 and first shipped in late 1954 to early 1955" (line 112) and "first FORTRAN compiler delivered April 1957" (line 16, line 199). Watchlist date "1956" is for first IBM 704 customer shipments, which began 1955. The post's dates match Wikipedia and CHM. **CONFIRMED in post.**
- FORTRAN I shipped April 1957: **CONFIRMED.** April 19 1957 first customer delivery (Westinghouse-Bettis).
- Speedcoding 1953 paper (consistent with Post 14): **CONFIRMED.** Post 20 line 92 says "In 1953, working on the IBM 701, he built a program called Speedcoding." Consistent.
- Backus team: Harlan Herrick, Lois Haibt, Sheldon Best, Robert Nelson, Roy Nutt, Sue Knapp, Irving Ziller: Post lists 13 authors per the 1957 WJCC paper. **Sue Knapp is NOT in the post.** She appears in `research/concepts/Fortran_I.md` line 26 as an early hire but not on the canonical 1957 paper byline (which has Backus, Beeber, Best, Goldberg, Haibt, Herrick, Nelson, Sayre, Sheridan, Stern, Ziller, Hughes, Nutt). The post's choice to follow the WJCC byline is correct; Knapp's inclusion in the early team predates the 1956-57 byline scoping. **POST IS CORRECT TO OMIT.**
- 1962 Turing Award: **WATCHLIST IS WRONG -- this is a typo in the task brief.** Backus's Turing Award was **1977**, not 1962. Post correctly says "1977" (line 305). Post is correct; task brief watchlist had a typo.
- 1977 ACM lecture "Can Programming Be Liberated from the von Neumann Style?": **CONFIRMED.** Delivered October 17, 1977, at ACM Annual Conference in Seattle. Post correctly says "October 1977" and "in Seattle" (line 305).

## Final recommendation

**Post 20 is publish-ready.** Prior required corrections are applied, all watchlist items are correctly handled (with task brief's "1962 Turing Award" being a typo for 1977 -- the post is correct), and no new factual errors were found in this round of verification.

The optional refinements above are author-discretion only. None of them block publication.
