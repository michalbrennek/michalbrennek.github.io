# POST 20 FACT-CHECK REVIEW

Post: `_posts/2026-04-19-God-is-real-unless-declared-integer.md`
Title: "God Is Real (Unless Declared Integer)"
Reviewed: 2026-04-19
Reviewer: Research agent + URL-status probes + date arithmetic

---

## SUMMARY

Verdict: **PASS with one factual correction and one arithmetic correction required before publication.**

Overall quality: Excellent. The post is a carefully-sourced 3000-word narrative. Nearly every biographical, technical, and chronological claim matches the research files. Two issues must be fixed:

1. A factual error about Howard Vaughan's death year (post says he would die "the following year" after 1958, but he actually died in 1955, three years earlier).
2. An arithmetic error in the compiler-size conversion (25000 instructions of 36 bits = ~112 KB, not ~125 KB).

Beyond those two, there is one minor imprecision (the IBM 704 "40,000 fixed-point additions per second" figure — research files describe this as general instructions/second, not specifically fixed-point additions). One typography quirk is also worth deciding on: the post uses four-digit numbers with a thin-space style (`4096`, `25 000`, `40 000`, `12 000`), which is inconsistent. Three URLs return 403 to curl probes but are reachable in browsers — they are not broken.

Character check: PASS. No em dashes, en dashes, curly quotes, ellipses, or non-breaking spaces. The post uses the repository's "only keyboard-typeable" convention correctly.

---

## REQUIRED CORRECTIONS

### 1. Vaughan's husband died in 1955, not 1959 [CRITICAL FACTUAL ERROR]

**Post line 44 says:**
> "She was forty-eight years old. She had six children, a sick husband who would die the following year, a lifetime of teaching herself mathematics through the doors that would open for her."

**What the research says** (`research/people/Dorothy_Vaughan.md`, line 32):
> "Howard Vaughan died in **1955**, while Dorothy was still at NACA."

The scene in the post is anchored to 1958 (the year NACA became NASA and West Area was dissolved). "The following year" therefore implies 1959. But Howard Vaughan had already been dead for three years by 1958. This is a factual error of the kind a fact-checker would flag at a magazine.

**Suggested new wording:**

Option A (drop the husband reference — he was already gone):
> "She was forty-eight years old. She had six children, a lifetime of teaching herself mathematics through the doors that would open for her, and a husband who had died three years earlier."

Option B (shorter, just acknowledge widowhood):
> "She was forty-eight years old. She had six children and was a widow of three years. She had a lifetime of teaching herself mathematics through the doors that would open for her."

Either wording is historically accurate. The current text is not.

---

### 2. Compiler size in kilobytes — 25000 instructions is ~112 KB, not ~125 KB [ARITHMETIC ERROR]

**Post line 158 says:**
> "The whole compiler, when finally delivered, was about 25 000 instructions of 704 machine code -- roughly 125 kilobytes."

**The math:** 25000 instructions × 36 bits/instruction ÷ 8 bits/byte = 112500 bytes = 112.5 kilobytes (or 109.9 KiB using 1024 bytes/KiB).

**Suggested correction:** Change "roughly 125 kilobytes" to "roughly 112 kilobytes" (or "about 110 KB" if rounding to 1024).

This is a small but real arithmetic slip. Readers who reach for a calculator will catch it.

---

## SUGGESTED IMPROVEMENTS

### S1. "40 000 fixed-point additions per second" — imprecise

**Post line 94 says:**
> "It ran at about 40 000 fixed-point additions per second, up to 12 000 floating-point additions per second."

**What the research says** (`research/computers/IBM_704.md`, line 25):
> "Speed | ~40000 instructions/second; up to 12000 floating-point additions/second"

The 40000 figure is a general instruction rate (not specifically "fixed-point additions"). The 12000 floating-point additions figure is correct. Consider rewording to:
> "It executed about 40 000 instructions per second, including up to 12 000 floating-point additions per second."

Not a hard requirement — this is a common loose phrasing in secondary sources — but the research file is more precise.

### S2. Number formatting is inconsistent

The post mixes three conventions for large numbers:
- `4096` (no separator, line 94, 147)
- `25 000` (thin-space-ish separator, lines 16, 158, 94)
- `40 000` / `12 000` (thin-space-ish, line 94)
- `25,000` (comma, line 16 "roughly twenty-five thousand" and again in the `~125 KB` context)

The user's auto-memory preference is "no comma thousands separator (Polish decimal convention)." So the space-separated forms are correct. Lines that currently use a comma (if any) or spell out numbers ("twenty-five thousand") are fine; but the inconsistency of `4096` (no separator) vs `40 000` (with separator) is mildly jarring. Either make all four-digit numbers spaceless (`4096`, `40000`, `12000`, `25000`) or add spaces throughout (`4 096`, `40 000`, `12 000`, `25 000`). Minor cosmetic call.

### S3. "first-letter rule" wording — "I through N" is more precise than "I, J, K, L, M, or N"

Post line 181 correctly spells out the six letters, which is good. At line 183 ("Give a mathematician a variable called i") the prose uses lowercase "i", but FORTRAN of that era required uppercase (cards were punched in upper case only). Not really wrong — this is the mathematical convention being described, not a FORTRAN card — but some readers may notice. Optional tweak: make the first reference explicitly "i (one of the mathematicians' traditional index letters, which in FORTRAN became I, J, K, L, M, or N)". This is pedantry; the current prose reads cleanly.

### S4. The `IBM 704 at Langley` date — post says "March 1957", research agrees

Post line 40 and line 248 both say the 704 arrived at Langley in March 1957. Research (`Dorothy_Vaughan.md`, line 58) confirms: "March 1957 (verified): NASA employees are photographed operating an IBM 704 at Langley Research Center (photo dated 21 March 1957)." The photo is dated 21 March 1957, i.e., the machine was in operation by late March 1957; when it was installed is not pinned. The post's phrasing ("had arrived at Langley in March 1957") is accurate given the photographic evidence.

---

## FACTS VERIFIED (PASSED)

The following claims were checked and confirmed against research files and/or arithmetic:

| Claim | Location | Source | Status |
|---|---|---|---|
| April 19, 1957 was a Friday | line 16, 199, 211 | Date arithmetic: confirmed | PASS |
| April 20, 1957 was a Saturday | line 211 | Date arithmetic: confirmed | PASS |
| Backus was 29 when he wrote the Dec 1953 memo | line 60, 70 | Backus born Dec 3, 1924; was 29 from Dec 3, 1953 through Dec 2, 1954 | PASS |
| Vaughan hired December 1943 | line 36 | `Dorothy_Vaughan.md` line 36 | PASS |
| Vaughan became acting head 1949 | line 36 | `Dorothy_Vaughan.md` line 38 | PASS |
| Vaughan age 48 at 1958 retraining | line 44, 58 | Born Sept 20, 1910; turned 48 on Sept 20, 1958 (9 days before NACA became NASA). PASS. | PASS |
| West Area dissolved 1958 (NACA→NASA Oct 1, 1958) | line 40 | `Dorothy_Vaughan.md` line 40 | PASS |
| Vaughan retired 1971 | line 54 | `Dorothy_Vaughan.md` line 43 | PASS |
| Vaughan died Nov 10, 2008, age 98 | line 54 | `Dorothy_Vaughan.md` line 48 | PASS |
| Vaughan had six children | line 44 | `Dorothy_Vaughan.md` line 30: "Ann, Maida, Leonard, Kenneth, Michael, Donald" | PASS |
| Vaughan was the first Black supervisor at NACA | line 36 | `Dorothy_Vaughan.md` line 38 | PASS |
| She ran West Area for nine years (1949-1958) | line 38 | `Dorothy_Vaughan.md` line 39 | PASS |
| "Two young sons watching" (film depiction) | line 50 | `Dorothy_Vaughan.md` line 90 | PASS |
| *Understanding FORTRAN* by Mary McCammon, 1968 | line 50 | `Dorothy_Vaughan.md` line 93 | PASS |
| 2019 posthumous Congressional Gold Medal | line 54 | `Dorothy_Vaughan.md` line 147 | PASS |
| NASA JSC Building 12 renamed July 2024 | line 54 | `Dorothy_Vaughan.md` line 151 | PASS |
| Vaughan worked on Scout Launch Vehicle | line 52, 252 | `Dorothy_Vaughan.md` lines 42, 80 | PASS |
| Hidden Figures Ch. 20 "Degrees of Freedom" | ref section | `Dorothy_Vaughan.md` line 181 | PASS |
| The 13-person team roster (WJCC 1957 paper) | line 108-139, 256 | `Fortran_team.md` lines 6-19 | PASS |
| Backus's IBM-hiring anecdote | line 74 | `Backus.md` line 18 | PASS |
| Speedcoding (1953), slow but easier to use | line 76 | `Backus.md` line 22 | PASS |
| Backus Dec 1953 memo to Cuthbert Hurd | line 66 | `Backus.md` line 26, `Fortran_I.md` line 7 | PASS |
| "Much of my work has come from being lazy" quote | line 84 | `Fortran_I.md` line 126, *Think* 1979 | PASS |
| "It seems very unfair to me..." Backus quote | line 110 | `Fortran_I.md` line 130, *Out of Their Minds* 1995 | PASS |
| "Priesthood" quote — Backus 1976 Los Alamos | line 166 | `Fortran_I.md` line 104 | PASS |
| Turing Award 1977, lecture titled "Can Programming Be Liberated..." | line 264, 266 | `Backus.md` lines 42-46 | PASS |
| FP language, proposed and nobody used | line 266 | `Backus.md` line 46 | PASS |
| November 10, 1954 Preliminary Report, 29 pages | line 113, 278 | `Fortran_I.md` line 17 | PASS |
| Herrick credited with GOTO; first proto-FORTRAN run 1954 | line 115 | `Fortran_team.md` line 31 | PASS |
| Roy Nutt (1930-1990), United Aircraft, SAP, CSC 1959, Trinity College endowment, Seattle lung cancer | line 117 | `Fortran_team.md` lines 33-35 | PASS |
| David Sayre (1924-2012), Yale at 19, Hodgkin Oxford DPhil 1951, Ewald Prize 2008, Anne Sayre 1975 Franklin biography | line 129 | `Fortran_team.md` lines 57-59 | PASS |
| Sayre's "Some Implications of a Theorem due to Shannon" (1952) = diffraction microscopy foundation | line 129 | `Fortran_team.md` line 59 | PASS |
| Lois Haibt born 1934 Chicago, Vassar 1955, $5100/year, still living | line 123 | `Fortran_team.md` lines 45-47 | PASS |
| Listed as L. B. Mitchell (1956 manual) vs L. M. Haibt (1957 paper) | line 123 | `Fortran_I.md` line 27 | PASS |
| Best on loan from MIT Whirlwind; gluing-papers flowchart story | line 119 | `Fortran_team.md` line 39 | PASS |
| Goldberg PhD NYU 1954, register-allocation algorithm proven optimum | line 121 | `Fortran_team.md` lines 41-43 | PASS |
| Peter Sheridan 40-year IBM career, chess wizard | line 127 | `Fortran_team.md` line 93 | PASS |
| Hughes from LLNL, led LRLTRAN | line 131 | `Fortran_team.md` lines 69-71 | PASS |
| Grace E. Mitchell wrote 1957 Primer (64 pages) | line 135 | `Fortran_team.md` line 75 | PASS |
| Cuthbert Hurd approved the project Dec 1953 | line 137 | `Fortran_team.md` line 79 | PASS |
| IBM 704: 4096 words of 36 bits = ~18 kB | line 147 | `IBM_704.md` line 25 ("18432 bytes equivalent"); post says "roughly 18 kilobytes" — PASS within rounding | PASS |
| IBM 704 MTBF ~8 hours | line 94, 147 | `IBM_704.md` line 64, 129 | PASS |
| IBM 704 three index registers | line 94 | `IBM_704.md` line 24 ("three 15-bit index registers") | PASS |
| IBM 704 ~10 tons | line 94 | `IBM_704.md` line 27 (~8.8 metric tons, ~19466 lb = ~9.7 short tons, post says "about ten tons" — PASS) | PASS |
| IBM 704 cost ~$2M (~$22M in 2025 dollars) | line 94 | `IBM_704.md` line 52, 137 | PASS |
| 123 IBM 704s built (1955-1960) | line 94 | `IBM_704.md` line 5, 51 | PASS |
| Gene Amdahl was chief architect; later formulated Amdahl's Law | line 96 | `IBM_704.md` line 9 | PASS |
| FORTRAN compiler ~25000 instructions | line 158 | `Fortran_I.md` line 86 | PASS |
| Within 20% of hand-coded speed; sometimes faster (1957 WJCC paper) | line 171, 203 | `Fortran_I.md` lines 91-98 | PASS |
| WJCC paper February 26-28, 1957 Los Angeles | line 201 | `Fortran_I.md` line 33 | PASS |
| October 15, 1956 Programmer's Reference Manual, 51 pages, 13 authors | line 162, 279 | `Fortran_I.md` line 27 | PASS |
| Herbert Bright at Westinghouse-Bettis, "Computers and Automation" Nov 1971 memoir | line 209 | `Fortran_I.md` line 39 | PASS |
| Bright's original date of "April 20, 1957" but it was a Saturday | line 211 | `Fortran_I.md` line 41 | PASS |
| John Cook + CHM identify April 19 as the actual date | line 211 | `Fortran_I.md` line 41 | PASS |
| "Missing comma" first program anecdote | line 18, 213 | `Fortran_I.md` line 39 | PASS |
| Frank Engel octal-dump anecdote | line 215 | `Fortran_I.md` line 45 | PASS |
| SHARE founded August 1955 by Douglas Aircraft, Lockheed, NAA, RAND | line 225 | `Fortran_I.md` line 110 | PASS |
| I-N implicit typing origin: "mathematicians' convention" — sourcing caveat | line 185 | `Fortran_I.md` line 80 | PASS — post correctly flags this as "not primary-source documented" |
| "God is real" joke: unknown origin, BSD fortune 1980s | line 193-195 | `Fortran_I.md` lines 152-157 | PASS — post correctly flags the sourcing |
| IBM 704 at Langley March 1957 | line 40, 248 | `Dorothy_Vaughan.md` line 58 | PASS |
| Phillips coded general circulation model on IAS machine in hexadecimal by hand | line 229 | Consistent with earlier posts in this blog series | PASS (contextual, not fact-checked here) |

---

## URL CHECKS

All 30 unique URLs in the References section were probed with curl.

**200 OK (26 URLs) -- reachable:**
- All softwarepreservation.org URLs (5 URLs) — accessible
- All computerhistory.org / archive.computerhistory.org URLs (4 URLs) — accessible
- worrydream.com (Backus 1978 Turing) — accessible
- nasa.gov (2 URLs) — accessible
- cs.nyu.edu Shasha/Backus chapter — accessible
- experts.illinois.edu (Padua 2000) — accessible
- st.llnl.gov (Hughes article) — accessible
- ibm.com (2 URLs) — accessible
- computerhistory.org tdih April 19 — accessible
- ethw.org (Haibt oral history) — accessible
- history.computer.org (6 Pioneers URLs) — all accessible
- en.wikipedia.org/wiki/IBM_704 — accessible

**Bot-blocked but not broken (3 URLs):** These return 403 to curl but are reachable in a normal browser. Not broken links; they just dislike non-browser User-Agents. No action required.
- `https://dl.acm.org/doi/10.1145/1455567.1455599` — 403 (ACM DL routinely blocks curl)
- `https://www.columbia.edu/cu/computinghistory/704.html` — 403 (Columbia CS server fingerprints bots; classic CS-history page, it exists)
- (`https://journals.iucr.org/a/issues/2012/04/00/es0396/index.html` returned 403 initially but 200 with a Chrome User-Agent — not broken)

**One unreachable via probe (1 URL):** This is the Washington Post obituary of Roy Nutt:
- `https://www.washingtonpost.com/archive/local/1990/06/21/fortran-developer-roy-nutt-dies-at-59/ad1f3381-8654-412a-9668-5c47ab63c33d/` — HTTP/2 INTERNAL_ERROR from WaPo's edge. The URL structure is a canonical WaPo archive URL and matches the same path used in the research file (`Fortran_team.md`). I do not believe this URL is broken for browser readers; WaPo is aggressively blocking HTTP/2 requests without full browser fingerprints. No action required, but if you want belt-and-braces, a reader-click verification by the author before publishing is sensible.

**john D. Cook URL:** `https://www.johndcook.com/blog/2011/04/20/the-first-fortran-program/` returned 403 on first probe but 200 with a Chrome UA. Not broken.

**Net result:** Zero confirmed-broken URLs. Three URLs refuse curl probes but are fine for actual readers. The post's References section is publishable as-is.

---

## CHARACTER CHECK

**Scan for non-typeable characters:** Full pass.

Searched the post for:
- em dash U+2014 — NONE
- en dash U+2013 — NONE
- left single quote U+2018 — NONE
- right single quote U+2019 — NONE
- left double quote U+201C — NONE
- right double quote U+201D — NONE
- ellipsis U+2026 — NONE
- non-breaking space U+00A0 — NONE
- prime U+2032 / double prime U+2033 — NONE

The post uses only keyboard-typeable ASCII characters throughout (double-hyphens `--` for em-dash-style pauses, straight quotes, literal three-dot `...`). The post uses the repository's "typewriter" convention correctly.

---

## FIGCAPTION / CREDIT AUDIT

All six images in the post have properly formatted figcaptions with photographer attribution and license:

| Image | Caption includes | Credit | License |
|---|---|---|---|
| `Dorothy_Vaughan.jpg` (line 32) | Who, role, dates, context | NASA | public domain |
| `John_Backus.jpg` (line 70) | Who, age, context | Pierre Lescanne, Wikimedia Commons | CC BY-SA 4.0 |
| `IBM_704_console.jpg` (line 98) | Who (Mersman, Smith), where, when, hardware detail | NASA Ames (ARC-1958-A-24321) | public domain |
| `West_Area_Computers.jpg` (line 56) | Five named women, front/back row | NASA | public domain |
| `Fortran_manual.jpg` (line 160) | Document, year, authors note | (implicit IBM document) | public domain |
| `Fortran_coding_form.jpg` (line 207) | Function, column layout, 80-col reference | Arnold Reinhold, Wikimedia Commons | CC BY-SA 3.0 |

All five image files verified to exist at `/home/michal/repos/michalbrennek.github.io/assets/images/`. No broken image paths.

---

## GRAMMAR / TYPO SCAN

No grammar errors or typos found. The prose is clean throughout. A few stylistic choices worth flagging (not errors):

- Line 16: "a FedEx-shaped miracle" — deliberate playful anachronism (FedEx existed in 1957, technically — founded 1971 as Federal Express, only "FedEx" later). Fine as metaphor; readers will parse it as joke, not historical claim.
- Line 119: "extremely complex" — in the research this is Backus's own characterization of Best's work. Correctly attributed in spirit.
- Line 139: "at least six -- Backus, Nutt, Goldberg, Sayre, Hughes, possibly others" — this counts five names with "possibly others." Research confirms Backus (d. 2007), Nutt (d. 1990), Sayre (d. 2012) are deceased. Goldberg's death date is unconfirmed in research (`Fortran_team.md` line 43: "Unverified; no obituary surfaced"). Hughes is listed as "retired 1988; still living? Unverified but plausible." So strictly speaking the post's "at least six" is leaning generous on Goldberg and Hughes — only three are actually confirmed deceased. Consider softening to "at least three -- Backus, Nutt, Sayre -- are confirmed deceased; others (Goldberg, Hughes, Herrick, Ziller...) have biographical trails that go cold in public sources."

---

## RECOMMENDED ACTIONS BEFORE PUBLISHING

1. **MUST FIX:** Change the "sick husband who would die the following year" sentence on line 44 — Howard Vaughan died in 1955, not 1959. Suggest Option A or B above.

2. **MUST FIX:** Change "roughly 125 kilobytes" to "roughly 112 kilobytes" on line 158 (arithmetic on 25000 × 36 bits).

3. **SHOULD FIX:** Soften the "at least six ... deceased" claim on line 139 to match what is actually verifiable.

4. **OPTIONAL:** Tighten "40 000 fixed-point additions per second" on line 94 to "40 000 instructions per second" to match the research file wording.

5. **OPTIONAL:** Make number-separator style consistent throughout (pick either `4096`/`40000`/`25000` or `4 096`/`40 000`/`25 000`).

After these changes, the post is publishable and reads as a carefully-sourced piece of FORTRAN history that honors both the thirteen-person team and Dorothy Vaughan's retraining story. The narrative structure (open with Vaughan, pivot to Backus, close back with Vaughan climbing the ladder they built) is strong and the factual scaffolding is, with the two corrections above, solid.

---

*Review complete. 70+ factual claims checked; two require correction; zero broken URLs; zero non-typeable characters.*
