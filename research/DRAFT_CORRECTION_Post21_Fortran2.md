# DRAFT CORRECTIONS — Post 21: The Empire That Its Creator Repudiated (Fortran Part 2)

Post path: `/home/michal/repos/michalbrennek.github.io/_posts/2026-04-20-The-empire-that-its-creator-repudiated.md`

The post is largely sound. The Dijkstra quotes from EWD 340 (Humble Programmer) and EWD 692 (review of Backus) all verify verbatim against the UT Austin archive. The Backus Turing Lecture quotes match the 1978 CACM PDF. The Cray-1, FORTRAN 77, ALGOL 60, Pascal, and Frances Allen biographical details verify against Wikipedia. The dates of October 17, 1977 Monday, the FORTRAN II 1958 release, FORTRAN IV 1962, ANSI X3.9-1966 March 1966, and ANSI X3.9-1978 April 1978 all check.

Three issues to consider for the next revision.

---

## Issue 1 — Backus's age when named IBM Fellow (1963)

**Where in the post:** end of the "FORTRAN IV" section.

**Current text:**
> "Backus himself had been named an **IBM Fellow** in 1963, at the age of thirty-nine."

**Problem:** Backus was born December 3, 1924. He was 38 for almost all of 1963, turning 39 only on December 3 of that year. IBM Fellow appointments are normally announced earlier in the year, and Wikipedia's John Backus article puts his age at 38 when named.

**Suggested fix:** Change "at the age of thirty-nine" to "at the age of thirty-eight." If the precise month of the appointment cannot be pinned down, alternative phrasing: "named an **IBM Fellow** in 1963, in his late thirties."

---

## Issue 2 — Peter Naur as "Danish mathematician"

**Where in the post:** "The Ambivalent Father" section.

**Current text:**
> "a thirty-one-year-old Danish mathematician named Peter Naur as editor of the final report."

**Problem:** Peter Naur was an astronomer in 1960, not a mathematician. He received his PhD in 1957 from the University of Copenhagen for work on "Minor planet 51 Nemausa and the fundamental system of declinations." He moved into computer science from astronomy. (Born October 25, 1928, so 31 at the January 1960 meeting — that part is fine.)

**Suggested fix:** Change "Danish mathematician" to "Danish astronomer-turned-computer-scientist" or simply "Danish computer scientist." A factual but informative rewrite:
> "a thirty-one-year-old Danish astronomer named Peter Naur — by 1960 already moving into the new field of computer science — as editor of the final report."

---

## Issue 3 — Two quotes attributed to EWD 498 that are not in EWD 498

**Where in the post:** "Dijkstra Reads Backus" section.

**Current text:**
> "In the essay I quoted earlier, EWD 498, he wrote that 'teaching COBOL should be considered a criminal offence,' that 'it is practically impossible to teach good programming to students that have had a prior exposure to BASIC,' that the 'first APL enthusiasts I have known were, without exception, remarkably unscientific,' and that 'Programming in PL/1 is like drowning in a sea of sirup.'"

**Problem:** Only two of these four quotes are actually in EWD 498:
- ✓ "teaching COBOL should be considered a criminal offence" — close paraphrase. EWD 498 actually says "The use of COBOL cripples the mind; its teaching should, therefore, be regarded as a criminal offence."
- ✓ "it is practically impossible to teach good programming to students that have had a prior exposure to BASIC" — exact.
- ✗ "first APL enthusiasts I have known were, without exception, remarkably unscientific" — NOT in EWD 498. EWD 498's APL passage says: "APL is a mistake, carried through to perfection. It is the language of the future for the programming techniques of the past: it creates a new generation of coding bums."
- ✗ "Programming in PL/1 is like drowning in a sea of sirup" — NOT in EWD 498. EWD 498's PL/I passage says: "PL/I — 'the fatal disease' — belongs more to the problem set than to the solution set."

The "sea of sirup" and "remarkably unscientific" lines may come from other Dijkstra essays. The first one ("sirup") is a popular paraphrase that I could not source to a specific EWD via web search.

**Suggested fix:** Replace the inaccurate quotes with the actual EWD 498 versions. Suggested rewrite:

> "In the essay I quoted earlier, EWD 498, he wrote that 'The use of COBOL cripples the mind; its teaching should, therefore, be regarded as a criminal offence,' that 'it is practically impossible to teach good programming to students that have had a prior exposure to BASIC: as potential programmers they are mentally mutilated beyond hope of regeneration,' that 'APL is a mistake, carried through to perfection ... it creates a new generation of coding bums,' and that PL/I was 'the fatal disease.'"

---

## Minor: ALGOL 58 expansion of "IAL"

**Where in the post:** "The Ambivalent Father" section.

**Current text:**
> "The Zürich meeting produced a specification for what was initially called the International Algorithmic Language (IAL) and was quickly renamed ALGOL 58."

**Note (no fix necessarily required):** The current Wikipedia article on ALGOL 58 calls IAL "International Algebraic Language." Both expansions appear in the historical literature — the 1958 preliminary report used "Algebraic"; the renaming to "ALGOL" (= ALGOrithmic Language) brought "Algorithmic" into common use. The two terms are often used interchangeably by later historians. This is a minor point of inconsistency in the source literature itself, not a clear error.

If the author wants strict accuracy with the 1958 source: change "Algorithmic" to "Algebraic." Otherwise this can be left alone.

---

## Things that look fine but are worth listing because they could easily be wrong

- "On Monday, October 17, 1977" — confirmed via `cal 10 1977`: October 17 fell on Monday.
- Backus age 52 at Turing Lecture — confirmed (born Dec 3, 1924).
- Backus's 28-page Turing Lecture / Dijkstra's "about a quarter" / "seven pages" estimate — confirmed in EWD 692.
- "von Neumann bottleneck" / "assignment statement is the von Neumann bottleneck" — confirmed verbatim in Backus 1978 PDF.
- "Conventional programming languages are growing ever more enormous, but not stronger" opening — confirmed verbatim.
- All EWD 340 (Humble Programmer) quotes — confirmed verbatim.
- All other EWD 692 (Dijkstra reads Backus) quotes — confirmed verbatim, including "obesity" and "I have learned to mistrust since World War II."
- Cray-1 weight 5.5 tons, 80 MHz, 160 MFLOPS, 8x64-element vector registers, S/N 001 to Los Alamos 1976, CFT 1978 — all confirmed.
- Frances Allen July 15, 1957 IBM Research entry date — confirmed by her own Turing biographical interview (Wikipedia gives year only; the post's "July 15" is her own self-stated date).
- All FORTRAN 77 features and the "~24 features removed" count — confirmed.
- ANSI committee renames (X3.4.3 → X3J3) — left unverified by this pass; standard committee history.
- Frank Engel of Westinghouse as X3J3 chair from September 1970 through FORTRAN 77 — not directly verifiable from Wikipedia alone; the J3 Fortran committee site would be the place. Left as accepted.
- Jeanne Clare Adams of NCAR as later X3J3 chair — confirmed.
