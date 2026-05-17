# DRAFT CORRECTIONS — Post 36: From Tubes to GPUs

Post path: `_posts/2026-05-11-From-tubes-to-GPUs.md`
Date: 2026-05-17
See `research/VERIFIED_FACTS_Post36_ArchSurvey.md` for the full verification log.

This is a SYNTHESIS post. Most factual claims are either VERIFIED against prior verified posts in the series or VERIFIED against external sources. The corrections below are the genuine errors and the priority precision improvements.

---

## PRIORITY 1 — Clear factual errors to fix

### 1. NMC IBM 7090 installation date (1962 → 1960)

**Post 36, Era 2 second paragraph (line 37):**

> "The 1962 **IBM 7090** ([Post 14](...)) at the National Meteorological Center at Suitland was a contemporary -- a transistorised re-implementation of the IBM 709 vacuum-tube architecture..."

Per Post 18 verified and Wikipedia "IBM 7090" (first 7090 installation December 1959; NMC installed its 7090 in 1960):

**Change to:** "The 1960 **IBM 7090** ([Post 14](...)) at the National Meteorological Center at Suitland was a contemporary..."

---

### 2. NMC IBM 7094 date and JNWPU/NMC naming (1964 → 1963; JNWPU → NMC)

**Post 36, Era 2 second paragraph (line 37):**

> "The Joint Numerical Weather Prediction Unit at Suitland ran the 7090 alongside a 7094 from 1964 onwards."

Two issues:
1. By 1964, the unit was no longer called "JNWPU" — it was renamed **NMC** on 1 January 1958 (Post 14 verified).
2. Per Post 18, the 7094 was installed at NMC by 1963, not 1964. Wikipedia: first 7094 installation September 1962.

**Change to:** "The National Meteorological Center at Suitland (the post-1958 successor to the JNWPU) ran the 7090 alongside a 7094 from 1963 onwards."

---

### 3. Phillips 1956 GCM wall-clock time (33 days → 12 hours)

**Post 36, Era 1 last paragraph (line 31):**

> "...used five kilobytes of total memory and ran on the Princeton IAS machine for thirty-three days of wall clock time."

This is wrong. The Phillips 1956 experiment took **about 12 hours** of IAS computer time for 31 simulated days (Post 7 verified file; Phillips 1956 paper itself). The "33 days" appears to confuse Phillips's GCM run with the 33 days at Aberdeen of the 1950 ENIAC forecast team (Post 9).

**Change to:** "...used five kilobytes of total memory and ran on the Princeton IAS machine for approximately twelve hours of wall clock time per simulated month."

---

### 4. Cane-Zebiak "first successful operational forecast" → "first successful experimental forecast"

**Post 36, Era 5 second paragraph (line 79):**

> "The Cane-Zebiak model produced the **first successful operational forecast of an El Niño event** in late 1986..."

Per Post 27 verified, the 1986 Cane-Zebiak forecast was experimental, not operational. Routine operational ENSO forecasting at NCEP began only in 1995.

**Change to:** "The Cane-Zebiak model produced the **first successful experimental forecast of an El Niño event** in late 1986..."

(or: **first successful research forecast of an El Niño event**)

---

### 5. 1992 ECMWF EPS truncation (T21 → T63)

**Post 36, Era 6 third paragraph (line 91):**

> "The 1992 ECMWF EPS (Post 34) on a Cray Y-MP could afford 33 ensemble members at T21 resolution; by 2010 cluster-based EPS systems were affording 51 members at T799 resolution -- an improvement of approximately two thousand times in compute per ensemble member."

The initial 1992 ECMWF EPS used **T63** spectral truncation (~210 km equivalent resolution at the equator), not T21. T21 is the very early 1980s research-experiment truncation; the 1992 operational EPS was T63.

**Change to:** "The 1992 ECMWF EPS (Post 34) on a Cray Y-MP could afford 33 ensemble members at T63 resolution; by 2010 cluster-based EPS systems were affording 51 members at T799 resolution..."

(The "approximately two thousand times" estimate stands: T63 → T799 is roughly a 144× grid-point increase per layer; the additional time-step shortening for the higher resolution adds another order of magnitude.)

---

### 6. CMIP and IPCC AR2 → AR3

**Post 36, Era 6 third paragraph (line 91):**

> "The **Coupled Model Intercomparison Project** (CMIP), launched 1995 and providing the principal computational input to every Intergovernmental Panel on Climate Change Assessment Report from AR2 (1995) to AR6 (2021)..."

CMIP1 launched in 1995 was too new to supply AR2 (also 1995). AR2 relied on individual-institution model runs. CMIP began feeding the IPCC from the AR3 (2001) onward.

**Change to:** "The **Coupled Model Intercomparison Project** (CMIP), launched 1995 and providing the principal computational input to every Intergovernmental Panel on Climate Change Assessment Report from AR3 (2001) to AR6 (2021)..."

---

### 7. GFDL Manabe-Wetherald 1975 ran on TI-ASC, not Cray-1

**Post 36, Era 4 third paragraph (line 71):**

> "**Operational medium-range weather forecasting at the European Centre for Medium-Range Weather Forecasts**... **doubling-of-CO2 climate sensitivity** simulation at GFDL Princeton (Manabe-Wetherald 1975, [Post 16])..."

Per `research/computers/GFDL_machine_timeline.md`, the 1975 Manabe-Wetherald paper ran at GFDL on the **TI 4-pipe ASC** (which arrived 1974), NOT on a Cray-1. The TI-ASC and Cray-1 share architectural genes (both vector processors) but are commercially distinct.

**Two possible fixes:**

**Option A** (preferred; reframe to acknowledge the TI-ASC):
> "...and the **doubling-of-CO2 climate sensitivity** simulation at GFDL Princeton (Manabe-Wetherald 1975, [Post 16]), the latter running on GFDL's contemporary TI 4-pipe Advanced Scientific Computer rather than on a Cray-1 but in the same architectural family of pipelined vector processors..."

**Option B** (rename the era heading):
> Change "Era 4: LSI, ECL, and the Cray-1 (1975-1985)" → "Era 4: LSI, ECL, and the vector supercomputer (1975-1985)"

Option A is more faithful to the post's narrative arc. Option B is less surgical.

---

### 8. ENIAC grid dimensions (Post 9 needs amendment, NOT Post 36)

This is an inconsistency between Post 36 and Post 9, but **Post 36 is correct** (15×18 = 270 grid points, matching the standard secondary literature reference of "270 grid points about 700 km apart"). **Post 9** says "19 x 16 grid at 736 km spacing" which is wrong. This is a Post 9 correction, not a Post 36 correction. No change to Post 36.

---

## PRIORITY 2 — Minor precision improvements

### 9. ECMWF 1979 forecast cadence (twice daily → once daily / daily)

**Post 36, Era 4 third paragraph (line 71):**

> "**operational medium-range weather forecasting at the European Centre for Medium-Range Weather Forecasts** (1 August 1979, ten-day global forecasts twice daily on a 1.875-degree grid-point primitive-equation model)..."

Per Post 26 verified, ECMWF began on 1 August 1979 with **once-daily** forecasts five days a week. The twice-daily (00 UTC and 12 UTC) operational schedule emerged later. Initially: 5 days/week; on 1 August 1980 moved to 7 days/week; twice-daily came later still.

**Change to:** "**operational medium-range weather forecasting at the European Centre for Medium-Range Weather Forecasts** (1 August 1979, ten-day global forecasts once daily on a 1.875-degree grid-point primitive-equation model)..."

---

### 10. Cane-Zebiak hardware: "MicroVAX" → softer

**Post 36, Era 5 second paragraph (line 79):**

> "**Mark Cane** and **Stephen Zebiak**'s 1985 coupled atmosphere-ocean model of El Niño-Southern Oscillation, designed at the Lamont-Doherty Earth Observatory and small enough to run on a single MicroVAX in approximately four hours per ENSO cycle."

Post 27 verified flags this exact hardware claim as **unverified** in primary sources. Post 27 says VAX 11/780; Post 36 says MicroVAX. Underlying research notes (`research/people/Mark_Cane.md`) flag both as unverified.

**Change to:** "...small enough to run on a single DEC VAX-class minicomputer in approximately four hours per ENSO cycle."

(Internal consistency: Post 27 should also be softened along the same lines.)

---

### 11. Beowulf 1995 paper author order

**Post 36 footnote [^8]:**

> "Beowulf cluster: Sterling, T., Savarese, D., Becker, D. J., Dorband, J. E., Ranawake, U. A., and Packer, C. V. 'Beowulf: A Parallel Workstation for Scientific Computation,' *Proceedings of the 24th International Conference on Parallel Processing (ICPP)*, 1995."

Per Wikipedia "Beowulf cluster" and the original 1995 ICPP proceedings, the author order on the published paper is **Becker, D. J., Sterling, T., Savarese, D., Dorband, J. E., Ranawake, U. A., and Packer, C. V.** — Becker first, not Sterling.

**Change footnote [^8] (and the corresponding body reference at line 87) to:** "Becker, D. J., Sterling, T., Savarese, D., Dorband, J. E., Ranawake, U. A., and Packer, C. V."

---

### 12. NCAR cluster generations — Bluefire vs Yellowstone-Cheyenne-Derecho

**Post 36, Era 6 second paragraph (line 89):**

> "**NCAR**'s Cray architectures gave way through the early 2000s to **IBM Power-based clusters** (Bluefire, Yellowstone, Cheyenne, Derecho)..."

Only Bluefire was IBM Power-based. Yellowstone was an IBM iDataPlex (x86); Cheyenne and Derecho are SGI/HPE x86-based.

**Change to:** "**NCAR**'s Cray architectures gave way through the early 2000s to commodity-CPU clusters (IBM Power on Bluefire, then x86 on Yellowstone, Cheyenne, and Derecho)..."

---

### 13. NVIDIA GPU generations — restore omitted Maxwell, Turing, Ada Lovelace (optional)

**Post 36, Era 7 first paragraph (line 97):**

> "...the **Tesla** generation (2008-2010), the **Fermi** generation (2010-2012), the **Kepler** generation (2012-2014), and onwards through the **Pascal**, **Volta**, **Ampere**, **Hopper**, and **Blackwell** generations of 2016-2026."

Omitted intermediates: Maxwell (2014-2016), Turing (2018-2020), Ada Lovelace (2022-2024). The omission is defensible at a survey level but worth either acknowledging in a footnote or restoring.

**Recommendation:** add a footnote acknowledging the omitted intermediate generations, or change to:
> "...the **Tesla** generation (2008-2010), the **Fermi** generation (2010-2012), the **Kepler** generation (2012-2014), the **Maxwell** generation (2014-2016), and onwards through the **Pascal**, **Volta**, **Turing**, **Ampere**, **Ada Lovelace**, **Hopper**, and **Blackwell** generations of 2016-2026."

---

## PRIORITY 3 — Unverified-but-plausible (flag, do not change)

### 14. "First operational five-day forecast at NMC began regular production in 1962 on the IBM 7090"

Could not verify in this session. Defensible but needs Shuman 1989 or NCEP primary source. **No change recommended; flag for future verification.**

### 15. COLA cluster scale "500 cores by 2000, 2000 cores by 2005"

Not in any prior verified file. Plausible from IGES institutional history. **No change recommended; flag for future verification.**

### 16. "2024 ECMWF Annual Seminar identified ML-based forecasting as the principal disruptive technology of operational meteorology since the 1979 commissioning of ECMWF itself"

Defensible as the author's characterisation of the seminar's emphasis. **No change recommended.**

### 17. Cray X-MP + Y-MP "over 200 units combined"

Plausible. Wikipedia does not give sales figures. **No change recommended; flag for future verification.**

---

## SUMMARY

**Total proposed edits to Post 36: 12** (8 priority-1 factual corrections + 4 priority-2 precision improvements).

**Most consequential changes:** the NMC 7090/7094 dates (Edits 1-2), the Phillips wall-clock time (Edit 3), the Cane-Zebiak "operational" framing (Edit 4), the ECMWF EPS T21→T63 (Edit 5), the CMIP AR2→AR3 (Edit 6), the GFDL TI-ASC framing (Edit 7), and the Beowulf author order (Edit 11).

**Most surgical changes (one-word fixes):**
- "1962 IBM 7090" → "1960 IBM 7090"
- "from 1964 onwards" → "from 1963 onwards"
- "Joint Numerical Weather Prediction Unit" → "National Meteorological Center (the post-1958 successor to the JNWPU)"
- "thirty-three days of wall clock time" → "approximately twelve hours of wall clock time"
- "first successful operational forecast" → "first successful experimental forecast"
- "T21 resolution" → "T63 resolution"
- "from AR2 (1995)" → "from AR3 (2001)"

**Intra-series consistency issues flagged for separate posts (NOT this post):**
- Post 9 has 19×16 grid (wrong); Post 36 has 15×18 (correct).
- Post 27 has "DEC VAX 11/780"; Post 36 has "MicroVAX". Both unverified; harmonise to "DEC VAX-class minicomputer".
- Post 26 has 18 ECMWF founding states; Post 34 has 16. Post 36 implies 16 ("sixteen national budgets").

The post is otherwise factually strong, well-cross-referenced to the series, and well-sourced where it adds new material (Beowulf, ML models). The corrections above are precision tightening rather than structural rework.
