# DRAFT CORRECTION — Post 33: "It Didn't Make Weather" (ILLIAC IV)

Post path: `_posts/2026-05-08-It-didnt-make-weather.md`

Five concrete factual errors plus one significant omission. None of them affect the post's core thesis (SIMD too early, GPU vindication, GISS GCM failed), but all should be fixed before the post stays archived.

---

## CORRECTION 1 — Slotnick's Westinghouse city: Baltimore, not Pittsburgh

**Current text (paragraph in "Daniel Slotnick" section):**
> Three years later, in 1960, he moved to **Westinghouse Electric Corporation** in Pittsburgh, where between 1960 and 1965 he led the design of two prototype parallel computers: SOLOMON I (built 1962) and SOLOMON II (built 1963).

**Suggested correction:**
> Three years later, in 1960, he moved to **Westinghouse Electric Corporation** in Baltimore, Maryland, where between 1960 and 1965 he led the design of two prototype parallel computers: SOLOMON I (built 1962) and SOLOMON II (built 1963).

**Sources:**
- Wikipedia "ILLIAC IV" (cites IEEE Computer Society profile) explicitly says: "In 1960, Slotnick was employed by Westinghouse Electric Corporation in Baltimore, Maryland."
- IEEE Computer Society Slotnick profile (history.computer.org/pioneers/slotnick.html) confirms Baltimore.

**Note:** The Baltimore connection is also relevant later — Slotnick died in Baltimore in 1985. The geographic continuity is striking.

---

## CORRECTION 2 — Slotnick's age at death: 53, not 54

**Current text (last paragraph of "Decommissioning, and Slotnick"):**
> On **25 October 1985**, while jogging in **Baltimore Maryland** during a visit, he suffered an apparent heart attack and died at age fifty-four.

**Current footnote 27:**
> Daniel L. Slotnick biographical: died 25 October 1985 in Baltimore Maryland of an apparent heart attack while jogging, age 54.

**Suggested correction:** Replace "fifty-four" with "fifty-three" in both main text and footnote.

**Source:** Wikipedia (Daniel Slotnick): "died in Baltimore, Maryland, on October 25, 1985, age 53". Born 12 November 1931; he died 18 days short of his 54th birthday.

---

## CORRECTION 3 — Slotnick's master's was Columbia (1952), not NYU

**Current text:**
> He took his Bachelor of Arts at Columbia in 1951, his Master of Arts and Doctor of Philosophy in mathematics at New York University, and joined IBM at Poughkeepsie in 1957.

**Suggested correction (also addresses the omitted IAS Electronic Computer Project — see CORRECTION 4):**
> He took his Bachelor of Arts at Columbia in 1951 and his Master of Science there in 1952, after which he joined the staff of the Electronic Computer Project at the Institute for Advanced Study in Princeton under John von Neumann. He returned to graduate study and took his Doctor of Philosophy in applied mathematics at the New York University Courant Institute in 1956 (or 1957, sources differ), then joined IBM's Development Laboratory at Poughkeepsie.

**Sources:**
- Multiple biographies: Columbia BA 1951, Columbia MS 1952, IAS Electronic Computer Project from June 1952, NYU Courant PhD applied math 1956 (or 1957 per Math Genealogy Project), IBM Poughkeepsie thereafter.

---

## CORRECTION 4 — Add the IAS / von Neumann episode (significant omission)

The post mentions Slotnick "joined IBM at Poughkeepsie in 1957" but omits that between 1952 and 1956 he worked on **the Electronic Computer Project at the Institute for Advanced Study under John von Neumann**, where he raised the idea of parallel computing and von Neumann dismissed it as requiring "too many tubes." This is a load-bearing origin story for the entire post's thesis — the very dismissal that "took fifty years for the silicon to catch up" came from von Neumann to Slotnick at IAS in 1952-1954. The post repeatedly invokes IAS for other characters in the NWP series; omitting it for Slotnick is a glaring gap.

**Suggestion:** Incorporate into CORRECTION 3 above (covered).

---

## CORRECTION 5 — Yale Mintz did not move to GISS

**Current text (third paragraph of opening section):**
> The Goddard model was, in its previous existence, a derivative of the UCLA general circulation model that **Yale Mintz** and Akio Arakawa had built at the University of California in the early 1960s. Mintz had carried the model east to NASA's Manhattan campus when he moved to GISS in the late 1960s; James Hansen would later inherit it.

**Current text (paragraph in "What ran for the climate"):**
> Yale Mintz had moved East from UCLA to GISS in the late 1960s; he had taken the model with him; the resulting GISS GCM was a nine-level primitive-equation model that ran in 1973-1975 on NASA Goddard's IBM 360/95.

**Suggested correction (both instances):**
> Mintz remained at UCLA throughout his career; the second-generation Mintz-Arakawa UCLA model was adopted at the Goddard Institute for Space Studies in 1972, where James Hansen would inherit and extend it. The resulting GISS GCM was a nine-level primitive-equation model that ran in 1973-1975 on NASA Goddard's IBM 360/95.

**Source:** Paul Edwards, *A Vast Machine*, online companion: "In 1972, [UCLA II] was adopted by the Goddard Institute for Space Studies in New York (GISS), whose current model is a direct descendant." Mintz remained at UCLA. (pne.people.si.umich.edu/vastmachine/i.UCLA.html)

---

## CORRECTION 6 — Robert Fassnacht was a postdoc, not a thesis student

**Current text (Vietnam at Urbana section):**
> The bombing killed **Robert Fassnacht**, a thirty-three-year-old physicist working overnight on a thesis-related experiment, and injured three others.

**Suggested correction:**
> The bombing killed **Robert Fassnacht**, a thirty-three-year-old postdoctoral physicist who had stayed late cooling a dewar of liquid nitrogen for a superconductivity experiment before leaving for a family vacation, and injured three others.

**Source:** Wikipedia "Sterling Hall bombing" and "Robert Fassnacht": Fassnacht (PhD already complete) was a postdoctoral physics researcher in superconductivity at UW-Madison. He was "in the process of cooling down his dewar with liquid nitrogen" when the bomb detonated at 3:42 AM. He had stayed late because his family was scheduled to leave for vacation in San Diego.

---

## MINOR — Hans Mark emigration framing

**Current text (Hans Mark and Edward Teller section):**
> Hans Michael Mark, born 17 June 1929 in Mannheim Germany, son of an Austrian chemistry professor, emigrated to the United States in 1940, took his doctorate in physics at the Massachusetts Institute of Technology in 1954, ...

**Note:** Mark left Germany in late 1939, went first to Canada, then to the US "approximately one year later" (settling in Brooklyn). "Emigrated to the United States in 1940" is acceptable shorthand but loses the Canada stopover. Optional refinement: "fled Germany in late 1939 and reached the United States by 1940". Not strictly an error — flag as optional polish only.

---

## ARCHITECTURAL DETAIL — Clock speed

**Current text (Sixty-four processors in lockstep section):**
> running on a sixteen-megahertz clock

**Note:** Wikipedia ILLIAC IV indicates the original design clock was 25 MHz, was redesigned to 16 MHz after IC issues, and **operated in practice at 13 MHz**. The post's "16 MHz" is the designed-after-revision rate, consistent with Hord 1982. Defensible. Optional footnote could note the 13 MHz operational reality.

---

## VERIFICATION SUMMARY

| Claim | Status |
|-------|--------|
| ILLIAC IV delivered April 1972, operational Nov 1975, decommissioned 7 Sept 1981 | ✓ |
| 64 PEs built of 256 planned | ✓ |
| Budget $8M → $31M | ✓ |
| Burroughs / Paoli (Great Valley) | ✓ |
| Bouknight et al. 1972 Proc IEEE 60(4):369-388 | ✓ |
| Rogallo NASA TM-81315 Sept 1981 | ✓ |
| Sterling Hall 24 Aug 1970, Fassnacht killed | ✓ (but post miscalled him a thesis student) |
| NORSAR 1968 Norwegian-American ARPA collaboration | ✓ |
| Slotnick IEEE McDowell Award 1983 | ✓ |
| Slotnick born 1931 NYC, died 25 Oct 1985 Baltimore | ✓ (but age was 53, not 54) |
| Slotnick at Westinghouse 1960-1965 | ✓ year, but **Baltimore not Pittsburgh** |
| Slotnick joined IBM in 1957 | partially ✓ (omits 1952-1956 IAS / von Neumann episode) |
| Hans Mark born 17 June 1929 Mannheim, MIT PhD 1954, NASA Ames Dir 1969-1977, died 18 Dec 2021 | ✓ |
| Mintz moved to GISS late 1960s | ✗ — Mintz stayed at UCLA; **model** was adopted by GISS in 1972 |
| Connection Machine CM-1 (1985) | ✓ defensible (dissertation 1985; product timeline 1986; either workable) |
| TMC founded 1983, bankrupt 1994 | ✓ |
| ILLIAC IV "first network-accessible supercomputer" 1975 | ✓ |

---

## Risk-rated summary for the user

- **High** (corrects clear factual error): #1 (Pittsburgh→Baltimore), #2 (age 54→53), #5 (Mintz moved→model moved), #6 (Fassnacht thesis-student→postdoc).
- **Medium** (corrects compressed/misleading framing): #3 (NYU MA→Columbia MS) and #4 (add IAS Electronic Computer Project).
- **Low / optional**: Hans Mark Canada stopover; ILLIAC IV operational clock 13 MHz footnote; CM-1 1985/1986 ambiguity.
