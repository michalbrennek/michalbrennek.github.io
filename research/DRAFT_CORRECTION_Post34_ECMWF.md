# DRAFT CORRECTIONS - Post 34: First Cray in Europe (ECMWF)

Compiled 2026-05-17 from research/VERIFIED_FACTS_Post34_ECMWF.md.

Priority: HIGH for ERRORS 1-5, MEDIUM for 6-10.

---

## ERROR 1 (HIGH): "Heinrich Süssenberger" → "Erich Süßenberger"

**Current text (paragraph 4, line 37):**
> "In **November 1967** the European Economic Community established an **Expert Group on Meteorology**, chaired by **Heinrich Süssenberger**, then director of the German national weather service Deutscher Wetterdienst."

**Correction:** The chairman of the EEC Expert Group on Meteorology and DWD president (1966-1977) was Dr **Erich Süßenberger**, not Heinrich. He died 5 December 2007.

**Source:** Deutscher Wetterdienst press release 5 December 2007; DLR scientific reports; DWD English-language history pages. The Wetterzentrale article confirms: "Erich Süßenberger, als Präsident des DWD, [...] gehörte mit Ernst Lingelbach [...] zum Sachverständigenausschuss für Meteorologie."

**Suggested replacement:**
> "In **November 1967** the European Economic Community established an **Expert Group on Meteorology**, chaired by **Erich Süßenberger**, then president of the German national weather service Deutscher Wetterdienst, with Ernst Lingelbach of the German Ministry of Transport as the other principal German member."

---

## ERROR 2 (HIGH): Founding states count — 16 vs 18; Norway and Luxembourg

**Current text (paragraphs 11-12, lines 43-45):**
> "diplomatic representatives of **fifteen European states** met in Brussels and signed the **Convention** [...] The fifteen signatories at Brussels on 11 October 1973 were: **Belgium, Denmark, Federal Republic of Germany, Spain, Finland, France, Greece, Ireland, Italy, Netherlands, Portugal, Switzerland, Sweden, Turkey, and the United Kingdom**. **Austria** acceded on **22 January 1974**, bringing the total to **sixteen** founding member states. **Norway** did not sign and would not accede for another sixteen years. **Iceland** never acceded."

**Correction:** ECMWF and Wikipedia both list **18 founding states of 1975**:
Austria, Belgium, Denmark, Finland, France, Germany, Greece, Ireland, Italy, **Luxembourg**, Netherlands, **Norway**, Portugal, Spain, Sweden, Switzerland, Turkey, United Kingdom.

The post excludes **Luxembourg** (a clear oversight — Luxembourg is in every list) and **Norway** (claim that Norway acceded only sixteen years later is contradicted by ECMWF). Iceland acceded in 2009 (post correctly notes it was a later addition).

**Note on the discrepancy:** The post's claim of 15 signatories at Brussels may reflect a chronologically earlier subset before Austria joined formally on 22 January 1974. The Luxembourg and Norway memberships are confirmed in the 1975 founding list. The post likely conflates the "Brussels signatories" with the "1975 ratified parties". Either way the count of 16 is wrong; ECMWF says 18.

**Suggested replacement:**
> "The Convention establishing the European Centre for Medium-Range Weather Forecasts was signed at Brussels on 11 October 1973. The eighteen founding states whose names appear on the Convention as ratified in 1975 are: Austria, Belgium, Denmark, Finland, France, the Federal Republic of Germany, Greece, Ireland, Italy, Luxembourg, the Netherlands, Norway, Portugal, Spain, Sweden, Switzerland, Turkey, and the United Kingdom. Iceland, which observed the negotiation process, did not accede until 2009; the original eighteen-state membership has expanded over the subsequent decades to twenty-three Member States and additional Cooperating States in 2026."

(Note: the "Yugoslavia observed but did not sign" claim should be removed unless verifiable — ECMWF official sources do not name Yugoslavia as an observer.)

---

## ERROR 3 (HIGH): Number of ratifications for entry into force — 12 vs 13

**Current text (line 55):**
> "The Convention was deposited at the United Kingdom Foreign and Commonwealth Office and required ratification by **twelve** member states before it could enter into force. The twelfth ratification arrived in mid-1975. The Convention entered into force on 1 November 1975, two years and three weeks after signing in Brussels. The thirteenth ratification arrived a few weeks later."

**Correction:** ECMWF's official 2015 "40 years ago" anniversary article states:
> "The Convention establishing ECMWF came into force on 1 November 1975, having been ratified by **13** countries."

The Convention's Article 18 (entry into force) requires acceptance by ratification of a specified number of states, after which the Convention enters force. The number 13 is what ECMWF documents — not 12.

**Suggested replacement:**
> "The Convention was deposited at the United Kingdom Foreign and Commonwealth Office and required ratification by a quorum of member states before it could enter into force. The Convention entered into force on **1 November 1975**, by which date **thirteen of the eighteen signatories had ratified**, two years and three weeks after the Brussels signing. The remaining ratifications followed over the next four years; Spain's was the last, in 1979, delayed by post-Franco constitutional reorganisation."

---

## ERROR 4 (HIGH): EPS resolution T21L19 → T63L19

**Current text (line 115):**
> "The **Ensemble Prediction System (EPS)** went operational at ECMWF on **24 November 1992**, at T21 spectral resolution with nineteen vertical levels (T21L19), and with **thirty-three ensemble members per forecast cycle** -- one control plus sixteen perturbed pairs."

**Correction:** The forecast integration ran at **T63L19**. The T21L19 truncation was used only for computing the singular vectors (perturbation generation). The 33-member ensemble was 1 control plus 32 perturbations (which can be described as 16 perturbed pairs since perturbations were applied as symmetric ± pairs).

**Source:** ECMWF "20 years of ensemble prediction" newsletter article: "the singular vectors used to generate the perturbed initial conditions were computed globally at T21L19 resolution, and the ensemble size was set to 32 perturbed and 1 unperturbed 10-day **T63L19** nonlinear integrations."

**Suggested replacement:**
> "The **Ensemble Prediction System (EPS)** went operational at ECMWF on **24 November 1992**, with the forecast model running at **T63 spectral resolution and nineteen vertical levels (T63L19)** and with **thirty-three ensemble members per forecast cycle** -- one unperturbed control integration plus thirty-two perturbed integrations (sixteen positive-negative pairs of singular-vector perturbations applied to the initial state). The singular vectors used to compute the perturbations were calculated at the lower T21L19 truncation. The system initially ran three times a week (Friday, Saturday, Sunday)."

---

## ERROR 5 (HIGH): Aksel Wiin-Nielsen's middle name

**Current text (line 61):**
> "**Aksel Christen Wiin-Nielsen** had been born in Frederiksberg, Denmark, on **17 December 1924**."

**Correction:** Wikipedia and biographical sources consistently use either "Aksel C. Wiin-Nielsen" (initialism) or "Aksel **Christopher** Wiin-Nielsen". The post's "Christen" is incorrect.

**Suggested replacement:**
> "**Aksel Christopher Wiin-Nielsen** -- usually known as Aksel C. Wiin-Nielsen -- had been born in Frederiksberg, Denmark, on **17 December 1924**."

---

## ERROR 6 (MEDIUM): Wiin-Nielsen Copenhagen 1948 vs 1952 with Fjørtoft

**Current text (line 61):**
> "He took his master of science degree at the University of Copenhagen in 1948 under **Ragnar Fjørtoft** [...]"

**Verified sources:** Wiin-Nielsen's documented association with Fjørtoft was as **scientific assistant** in 1952, not as 1948 master's student. Fjørtoft was at the Norwegian Meteorological Institute in 1948 and joined the Joint Numerical Weather Prediction Project (Maryland) in 1953. The 1948 master's degree could have been awarded under a different supervisor (likely Pedersen or another Copenhagen meteorologist), with the Fjørtoft connection beginning in 1952.

**Suggested replacement:**
> "He took his master of science degree at the University of Copenhagen in 1948 and joined the Copenhagen meteorology department as scientific assistant to **Ragnar Fjørtoft** in 1952 -- the Norwegian meteorologist who had been one of the principal architects of the [first numerical weather forecasts on ENIAC](/weather/hpc/history/2026/04/02/From-cables-to-chaos.html) in 1950 alongside Charney and von Neumann."

---

## ERROR 7 (MEDIUM): WMO Secretary-General term ended 31 December 1983, not 1983

**Current text (line 96):**
> "He left Reading and returned to Geneva, where he became **Secretary-General of the World Meteorological Organization** -- a position he held from 1980 to 1983."

**Correction:** Wikipedia states he served "from 1 January 1980 to 31 December 1983" — a four-year term, not three. The post implies a 1980-1983 range (which is three years inclusive).

**Suggested replacement:**
> "He left Reading and returned to Geneva, where he became **Secretary-General of the World Meteorological Organization** -- a position he held from 1 January 1980 to 31 December 1983, a single four-year term."

---

## ERROR 8 (MEDIUM): Tim Palmer Oxford chair date 2011 → 2010

**Current text (line 122):**
> "Tim Palmer would lead the Centre's ensemble research until 2010, when he moved to a chair at the University of Oxford."

**Current text (figure caption line 119):**
> "joined ECMWF in 1986, led the development of the Ensemble Prediction System operationalised on 24 November 1992, **moved to a chair at the University of Oxford in 2011**."

**Correction:** Per Wikipedia, Palmer became Professor of Climate Physics at Oxford in **2010** as a Royal Society Research Professor. The 2011 date in the figure caption should be 2010. The narrative date "until 2010" is correct.

**Suggested replacement (figure caption):**
> "[...] moved to a Royal Society Research Professorship and chair of climate physics at the University of Oxford in 2010."

---

## ERROR 9 (LOW): William Bourke's institution name

**Current text (line 102):**
> "**William Bourke**, at the **Australian Bureau of Meteorology Research Centre** in Melbourne, had operationalised the world's first global spectral numerical weather prediction model in **1976-1977**"

**Correction:** Per the *Monthly Weather Review* journal records, Bourke was at the **Australian Numerical Meteorology Research Centre (ANMRC)** in 1972-1974 — the predecessor institution of what became the Bureau of Meteorology Research Centre (BMRC) in 1985. The post uses an anachronistic name. The institutional ancestry is correct; the name should be ANMRC for the 1970s period.

**Suggested replacement:**
> "**William Bourke**, at the **Australian Numerical Meteorology Research Centre (ANMRC)** in Melbourne -- the institutional ancestor of today's Bureau of Meteorology Research Centre -- had operationalised the world's first global spectral numerical weather prediction model in **1976-1977** [...]"

---

## ERROR 10 (LOW): "Yugoslavia observed but did not sign"

**Current text (line 45):**
> "**Yugoslavia** had observed but did not sign."

**Correction:** This claim could not be verified from any ECMWF official source. Recommended: remove unless a citation can be supplied.

---

## ERROR 11 (LOW / DATE): SN1 at Rutherford from October 1977 vs November 1977

**Current text (line 75):**
> "Beginning **October 1977** the Centre arranged with the **Rutherford Appleton Laboratory** at Chilton, Oxfordshire, to use **Cray-1 serial number one**"

**Correction:** Cray-history.net (citing Charlie Clark 1989) states SN1 moved to ECMWF (housed at Rutherford) in **November 1977**, not October. The difference is minor but should be checked against the ECMWF Newsletter 143 (Spring 2015) Hawkins-and-Weger article that the post cites as footnote 1.

**Suggested replacement:**
> "Beginning **November 1977** [...]"

---

## ERROR 12 (LOW): Casson Conder building "three-storey concrete-and-glass"

**Current text (line 79):**
> "the executed building was a three-storey concrete-and-glass structure designed by the British architectural firm Casson Conder and Partners"

**Status:** Architectural details unverified. The Casson Conder Partnership's involvement is plausible (firm founded 1956 by Sir Hugh Casson and Neville Conder) but their authorship of the specific Shinfield Park building has not been independently confirmed via accessible sources. The RIBA Pix collection mentions "European Centre for Medium-Range Weather Forecasting, Shinfield Park, Reading" but the page returned HTTP 403 on direct fetch. Confidence: MEDIUM that Casson Conder were architects; LOW on the "three-storey concrete-and-glass" descriptor.

**Recommendation:** Soften the phrasing pending confirmation.

---

## SUMMARY OF CORRECTIONS NEEDED

High priority (factual errors):
1. Erich (not Heinrich) Süßenberger
2. 18 founding states (not 16), including Luxembourg and Norway
3. 13 ratifications for entry into force (not 12)
4. EPS forecast model T63L19 (not T21L19)
5. Aksel Christopher Wiin-Nielsen (not Christen)

Medium priority:
6. Wiin-Nielsen 1948 master's vs 1952 Fjørtoft scientific assistant
7. WMO Secretary-General dates 1 Jan 1980 to 31 Dec 1983 (four years)
8. Tim Palmer Oxford chair from 2010 (not 2011)
9. ANMRC (not Australian Bureau of Meteorology Research Centre) for Bourke

Low priority (verify or soften):
10. Remove "Yugoslavia observed" claim
11. SN1 to Rutherford October vs November 1977
12. Casson Conder Shinfield Park architectural details
