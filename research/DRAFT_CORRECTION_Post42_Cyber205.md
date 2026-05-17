# Draft Corrections — Post 42: The First in Bracknell

**Post path:** `_posts/2026-05-15-The-first-in-Bracknell.md`
**Status:** verification complete (2026-05-17)

## Summary

The post is well-researched and largely accurate. Only a handful of small refinements are recommended below. None correct a factual error fatal to the post's narrative; all are precision improvements.

## Recommended edits (in order of priority)

### 1. (Optional, precision) FSU ETA-10 S/N 1 delivery vs installation date

**Location:** Section 6 ("The 1983 spinoff and the 1986 machine"), and footnote `[^eta1ship]`.

**Current text:**
> The first ETA-10E shipped to **Florida State University SCRI** on **5 January 1987** -- serial number 1, formally announced at SCRI in April 1987 as the launch customer.

**Issue:** FSU's RCC history page says "Installation of the first prototype ETA-10 processor began at the FSU Computing Center on January 5, 1987" — this is the installation start, not the truck-delivery date. Rob Peglar's first-hand "ETA Saga" gives the truck delivery as 31 December 1986 ("a large media event when the trucks rolled from ETA to Florida State, containing ETA-10 Model E S/N 1"). Both dates are correct for different events.

**Suggested edit:**
> The first ETA-10E -- serial number 1 -- arrived at **Florida State University SCRI** in a "large media event" of truck deliveries on **31 December 1986**; installation of the prototype processor began at the FSU Computing Center on **5 January 1987**, and the machine was formally announced at SCRI in April 1987 as the launch customer.

Footnote `[^eta1ship]` should be updated to cite both Peglar (delivery) and docs.rcc.fsu.edu (installation start).

### 2. (Optional, sourcing) JVNC ETA-10 destruction claim

**Location:** Section 9 ("The shutdown").

**Current text:**
> the John von Neumann Center at Princeton (which had ordered two systems, both of which were later destroyed to prevent unauthorised access after the JVNC closure)

**Issue:** Rob Peglar's "ETA Saga" — the canonical insider account of ETA Systems — does not mention the JVNC machines being destroyed. Peglar's only JVNC discussion is about EOS multitasking limits. The "destroyed to prevent unauthorised access" detail is not independently verifiable in this verification pass.

**Suggested options:**
- (a) Source the claim explicitly to wherever it came from in a footnote.
- (b) Soften to "later decommissioned" or "later removed from service" if the destruction detail cannot be sourced.
- (c) Drop the parenthetical entirely; the main point (JVNC ordered two ETA-10s) is sufficient.

The post's core argument does not depend on this detail; if it cannot be sourced, removal is the safest option.

### 3. (Optional, precision) Cyber 205 production count

**Location:** Section 4 ("The American customers, 1982-1985") and Section 5.

**Current text (Section 4):**
> Beyond those three the customer base for the 205 across its production life was small -- estimates put total deliveries at approximately 35 machines worldwide

**Current text (Section 5):**
> The total customer base across the production life of the architecture was approximately 35 units.

**Issue:** The internal research files give inconsistent counts (CDC_Cyber_205.md: "~30"; Cyber_205_US_sites.md: "a dozen 205s were built in total before CDC spun off ETA Systems in August 1983"; secondary sources: "approximately 35"). The 35 figure is the most common in secondary literature but is not a firm count.

**Suggested edit:** Keep "approximately 35" but consider adding a footnote noting that the exact production count is not in the public record; secondary-source estimates range from "around 30" to "approximately 35" depending on whether Cyber 203s and unshipped CDC inventory are counted.

### 4. (Optional, hedging) Met Office ETA-10 installation

**Location:** Section 9 ("The shutdown").

**Current text:**
> The customer list at shutdown included Florida State University, [...], the UK Met Office (about which more in a moment), [...]

The post already hedges this carefully in the following paragraph. No change needed here — but the section 9 list might note that the Met Office's listing is contested: Peglar's "ETA Saga" includes UK Met Office as a liquid-cooled customer; the Wikipedia ETA-10 customer list omits it; the Met Office's own chronological list of operational supercomputers does not include an ETA-10.

The post's existing treatment ("ambiguous chapter that the public record cannot quite resolve") is fair. No edit required, but the underlying ambiguity might warrant being acknowledged in the section-9 list line rather than only in the following paragraph.

### 5. (Optional, hedging) "Monday afternoon" detail for 17 April 1989 shutdown

**Location:** Section 1 (introduction paragraph) and Section 9.

**Current text (Section 1):**
> shut down ETA on the afternoon of 17 April 1989

**Current text (Section 9):**
> On **17 April 1989** -- a Monday afternoon in Bloomington, Minnesota -- Control Data Corporation abruptly closed ETA Systems

**Issue:** 17 April 1989 was a Monday (confirmed). Peglar's "ETA Saga" says "all 800 employees were locked out and informed of termination effective June 17th." The "afternoon" detail is plausible but not in Peglar.

**Suggested edit:** Either source the "afternoon" detail or relax to "On 17 April 1989 -- a Monday -- Control Data Corporation abruptly closed ETA Systems." Minor.

### 6. (Optional, precision) Cray X-MP per-CPU peak figure

**Location:** Section 5 ("The Cray competitor in the field").

**Current text:**
> 200 to 235 MFLOPS per CPU peak at 64-bit precision

**Issue:** Wikipedia Cray X-MP article says "Each CPU had a theoretical peak performance of 200 MFLOPS." The 235 figure may apply to the 8.5 ns variants or to specific 1985+ models. The 200 figure is the canonical peak. The range "200 to 235" is defensible across model variants but is unusual.

**Suggested edit:** No change required; the range is accurate across model variants. Could be tightened to "200 MFLOPS per CPU peak (rising to 235 MFLOPS on the faster 1985+ 8.5 ns models)" for precision.

## Non-issues (claims that look unusual but check out)

- **Met Office mesoscale 1985 as world first non-hydrostatic convection-permitting operational model**: confirmed from Met Office NWP history page verbatim.
- **NCEP SSI 25 June 1991**: the post does not actually claim this date but the prompt mentions it as a watch-item. Confirmed in Parrish & Derber 1992 if needed.
- **Sir John Houghton DG 1983-1991**: confirmed verbatim from Wikipedia.
- **Lincoln's Boundary Waters canoe trip**: this is part of the standard CDC retelling and appears in multiple secondary sources; the post correctly hedges with "as the standard CDC retelling has it."
- **The "1300-line Q8 call FFT" at the Met Office**: from R. Bell's CSIROpedia chapter; confirmed.
- **FSU MTBF figures (34.7, 127.2, 25.4, 2064.2 hours)**: all confirmed in internal research files drawn from docs.rcc.fsu.edu and ed-thelen.org.
- **AFGWC = Cray X-MP under AWAPS 1986**: confirmed (DTIC ADA172801).
- **NCAR Cray-1A serial 3 commissioned 11 July 1977**: confirmed (CISL NCAR supercomputing history).
- **ECMWF NEVER operated Cyber 205**: confirmed extensively (Hawkins-Weger 2015).
- **Steve Chen as Cray X-MP principal designer**: confirmed (Wikipedia).
- **Tim Palmer's 1986 ECMWF move**: confirmed verbatim from Wikipedia.
- **McIntyre-Palmer 1983 *Nature* on Rossby wave breaking**: confirmed.

## Assessment

The post is publishable as-is. The recommended edits above are precision refinements rather than factual corrections. The post's overall research depth is high, the negative-result discipline (ECMWF/AFGWC/NCAR did NOT have Cyber 205) is excellent, and the FSU MTBF statistical record is correctly reproduced. The Bracknell narrative is solidly sourced from Bell, Flood, the Met Office NWP history page, and Wikipedia / IT History Society.

The two corrections from the verification prompt that warranted special attention:
- **ECMWF never operated a Cyber 205**: post correctly states this in Section 4 ("There is one important negative item to flag explicitly here, because the prompt that started this series had it the other way round...") and gives a full chronology.
- **AFGWC never operated a Cyber 205 or ETA-10**: post correctly states this in Section 4 and identifies the AFGWC/AFGL confusion as the source of the misattribution.
- **Met Office DG was Houghton 1983-1991, not Mason**: post correctly attributes Mason (1965-1983) to the procurement decision and Houghton (1983-1991) to the operational lifetime, which is exactly right.

The corrections are minor and the post is recommended for publication unchanged or with the optional edits in section 1 (ETA-10 delivery date precision) and section 2 (JVNC destruction sourcing) applied.
