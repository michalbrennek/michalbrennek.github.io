# Draft Corrections — Post 48: The Hemisphere That Caught Up

**Post path:** `_posts/2026-07-20-The-hemisphere-that-caught-up.md`
**Status:** verification complete (2026-07-20); both corrections below APPLIED to the post prior to publication.
**Companion:** `VERIFIED_FACTS_Post48_SatelliteRadiance.md` (canonical fact table).

## Method

Independent citation-and-quote verification pass following the series protocol
(`VERIFICATION_SUMMARY_2026-05-17.md`):

1. **Citation resolution.** All 46 unique primary (non-archive) URLs in the post's footnotes
   were fetched (HTTP, follow-redirects, browser UA). Result: 44 returned HTTP 200; one
   returned a genuine 404 (dead link, corrected below); one returned a Wiley 403 that was
   confirmed valid via the `doi.org` resolver (bot-blocking, not a dead link). The generic
   `web.archive.org/web/<url>` archive form was spot-checked and resolves (HTTP 200).
2. **Quote fidelity.** Every verbatim block/inline quote in the post was checked against the
   source PDF (downloaded + `pdftotext` + whitespace-flattened grep):
   - Simmons & Hollingsworth 2002 abstract ("about a one-day gain… last three years in the
     southern hemisphere") — **verbatim match** (ECMWF TM342).
   - Simmons & Hollingsworth 2002 payoff line ("reduced so much in the southern hemisphere…
     almost as skilful as those for the northern hemisphere") — **verbatim match** (TM342).
   - Eyre 2007 ("sounding quality in cloudy areas that had only been available hitherto in
     cloud-free areas"; "crucial to the performance of NWP systems") — **verbatim match**.
   - ECMWF "Fifty years of data assimilation" ("the transition to variational assimilation and
     direct radiance assimilation resulted in the largest changes to operational forecast
     scores at the end of the 1990s") — **verbatim match**.
   - TM711 ("catastrophic degradation in the southern hemisphere, and very significant
     degradation in the northern hemisphere") — **verbatim match**.
   - Cardinali 2013 FSOI ranking — **one discrepancy found and corrected** (see Tier 2 below).
3. **Facts.** Load-bearing dates, channel counts, launch dates, and attributions were confirmed
   in the workflow verifier pass and recorded in the VERIFIED_FACTS table; no Tier-1 factual
   error was found in this pass.

## Corrections applied

### 1. (Tier 2 — quote fidelity) Cardinali 2013 FSOI ranking quote

**Location:** Section 10 ("The proof: which eye matters most"), block quote; footnote `[^cardinali2013]`.

**Issue:** The post rendered the block quote as "…IASI, AIRS, AIREP **(aircraft)** and GPS-RO
observations account for 10%…". The source (Cardinali 2013 ECMWF lecture notes,
`16937-observation-impact-short-range-forecast.pdf`, p. lines 397–399) actually reads
"…IASI, AIRS, AIREP **(aircraft data** and GPS-RO observations account for 10%…" — i.e. the
source contains the word **"data"** and an **unclosed parenthesis** (a typo in the original).
The post had dropped "data" and re-scoped the parenthesis, so the passage was not verbatim as
presented. The workflow verifier had propagated the same altered wording into VERIFIED_FACTS
while labelling it "read verbatim"; this independent pass against the PDF surfaced it.

**Fix applied:** changed "AIREP (aircraft)" → "AIREP **(aircraft data)**" in both the post and
the VERIFIED_FACTS table, restoring the source's word "data" and closing the parenthesis
editorially (the source's open paren is an obvious typo). Tilde/percent spacing ("(~25%)" for
the source's "(∼ 25 %)") is left as an accepted ASCII normalisation consistent with house style.

### 2. (Citation — dead link) AIRS JPL mission URL returned 404

**Location:** Footnote `[^airs]`.

**Issue:** the secondary primary URL `https://airs.jpl.nasa.gov/mission/overview/` returns
HTTP 404 (the JPL AIRS site was restructured). The footnote's other primary
(Wikipedia AIRS) resolves 200.

**Fix applied:** replaced the dead URL with the current JPL AIRS mission page
`https://www.jpl.nasa.gov/missions/atmospheric-infrared-sounder-airs/` (HTTP 200).

## Not changed (verified acceptable)

- `[^andersson1994]` primary `…/qj.49712051707` returns 403 on direct fetch (Wiley
  bot-blocking); the DOI resolves 200 via `doi.org` and is confirmed correct. Left as-is with
  its Wayback fallback.
- Wayback archive links use the generic `web.archive.org/web/<url>` form (no timestamp); this
  resolves (HTTP 200) and is the series' accepted "permanence layer, not a gate" convention.
  Per `VERIFICATION_SUMMARY_2026-05-17.md`, harness-level Wayback save POSTs are intermittently
  blocked; timestamped snapshots may be added later via the web form if desired.
- All COULD-NOT-VERIFY rows in the VERIFIED_FACTS table were correctly OMITTED by the writer
  (no McMillin birth/death year; split-window hedged to "mid-1970s"; no unverified
  SH-without-satellites web figure; no specific present-day day-N convergence value).

## Verdict

No Tier-1 factual errors. Two corrections (one quote-fidelity, one dead link), both applied.
Post is citation-clean and quote-faithful for publication.
