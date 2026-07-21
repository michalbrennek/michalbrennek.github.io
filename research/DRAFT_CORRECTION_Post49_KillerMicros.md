# Draft Corrections — Post 49: The Attack of the Killer Micros

**Post path:** `_posts/2026-07-20-The-attack-of-the-killer-micros.md`
**Status:** verification complete (2026-07-20); all corrections below APPLIED to the post prior to publication.
**Companion:** `VERIFIED_FACTS_Post49_KillerMicros.md` (canonical fact table).

## Method

Independent citation-and-quote verification pass following the series protocol
(`VERIFICATION_SUMMARY_2026-05-17.md`, `feedback_independent_verification`), on top of the
in-workflow verify/review/patch stages:

1. **Citation resolution.** All 57 unique primary (non-archive) URLs in the footnotes were
   fetched (HTTP, follow-redirects, browser UA). 53 returned HTTP 200. The exceptions:
   - `computerhistory.org/events/bio/Tony,Hey` -> **404 dead link** (corrected below).
   - `washingtonpost.com/archive/...` x3 -> HTTP 000 (WaPo blocks automated clients but serves
     browsers); each is a *secondary* citation in a footnote that leads with a working primary
     (Wikipedia / hpcwire) AND carries a resolving Wayback archive. Acceptable.
   - `mcs.anl.gov/~lusk/` -> 500; `anl.gov/article/...` and two `sciencedirect.com` DOIs -> 403
     (bot-block / publisher). Each is a secondary URL with a working co-primary (newswise, dblp)
     and, for `~lusk/`, a resolving Wayback snapshot. Acceptable per protocol.
   - The archive fixes made by the patcher were confirmed: all 39 Wayback lines now carry real
     14-digit timestamps (up from the timestampless generic form).
2. **Quotes.** The post contains **no verbatim block quotes** to source-check. The "attack of
   the killer micros" catchphrase is deliberately handled as folklore, not presented as a direct
   Brooks quotation (per the VERIFIED_FACTS caution); the footnote flags that "Eugene D. Brooks
   III" is unverified and asserts only "Eugene Brooks". Verified the one specific title claim --
   Hoffmann's edited volume *The Dawn of Massively Parallel Processing in Meteorology* -- resolves
   as a real Springer book (link.springer.com/book/10.1007/978-3-642-84020-3, HTTP 200).
3. **Facts / read-through.** Full read for accuracy and for the NWP-thread balance. Load-bearing
   facts (Brooks/SC1990; Seymour Cray accident 23 Sep / death 5 Oct 1996 age 71; Cray Computer
   Corp Chapter 11 24 Mar 1995; TMC Aug 1994; SGI Feb 1996 $740M; TOP500 first list Jun 1993,
   CM-5/1024 at Los Alamos 59.70 GFLOP/s; MPI-1 1994 / MPI-2 1997; Gustafson CACM May 1988,
   1021/1020/1016 speed-ups on a 1024-node nCUBE; ECMWF C90 -> VPP700 Sep 1996 (46 PEs / 39
   compute) -> VPP5000 -> IBM POWER4 cluster 2002-04; IFS transposition strategy) all match the
   VERIFIED_FACTS table.

## Corrections applied

### 1. (Citation -- dead link) Tony Hey Computer History Museum URL returned 404

**Location:** Footnote `[^hey]`.

**Issue:** the secondary primary `https://computerhistory.org/events/bio/Tony,Hey` returns
HTTP 404 (malformed/removed). The footnote already leads with a working primary
(`en.wikipedia.org/wiki/Tony_Hey`, 200) plus a resolving Wayback line.

**Fix applied:** removed the dead CHM URL and its clause; footnote now cites the Wikipedia
primary + Wayback archive only.

### 2. (Accuracy -- photo/caption mismatch) CM-5 figure

**Location:** Section 3, the CM-5 figure caption (`Post49_CM5_Frostburg.jpg`).

**Issue:** the caption read "A ... CM-5, the machine that topped the first TOP500 list ... at
Los Alamos", implying the *pictured* machine was the Los Alamos TOP500 topper. The photograph
(brewbooks, CC BY-SA 2.0) is of a different CM-5 (the NSA's FROSTBURG, per the image filename),
which did not top TOP500.

**Fix applied:** reworded to decouple the photograph from the claim -- "A ... CM-5. In a
1024-processor configuration at the Los Alamos National Laboratory, a CM-5 topped the very
first TOP500 list in June 1993." -- keeping the (correct) fact without asserting the pictured
machine is that one.

## Not changed (verified acceptable)

- The three WaPo `000` URLs and the `~lusk/` 500 / anl.gov + sciencedirect 403s: all secondary,
  each with a working lead primary and (where blocked) a resolving Wayback archive.
- The inline SVG halo-exchange diagram carries an explicit white background rect, so it renders on
  both the light and dark site skins.

## Verdict

No Tier-1 factual errors. Two corrections (one dead link, one photo/caption accuracy), both
applied. Post is citation-clean and quote-safe (no verbatim block quotes) for publication.
