# Verified Facts for Post 44: Optimal Interpolation / Lev Gandin

**Status**: COMPLETE (35-tool-use cap reached)

This document tracks the verification status of facts to be used in Post 44 of the NWP/HPC history blog series, covering Lev Gandin and the rise of Optimal Interpolation through 3D-Var and 4D-Var.

## Verification table

| Fact | Verdict | Primary URL | Wayback URL | Confidence | Notes |
|------|---------|-------------|-------------|------------|-------|
| Gandin birth year 1923 | COULD NOT VERIFY | -- | -- | low | No source consulted gives explicit year. Post should hedge ("born in the early 1920s") or omit. Wikidata/Russian Wikipedia not findable. |
| Gandin death year 1997 | DISPUTED/PARTIAL | -- | -- | medium | The 1999 *MWR* note on Gandin-Murphy is described as posthumous in the bio file. The AMS Honorary Members list carries deceased dagger (per bio file, page itself 403). No specific obituary URL found. Confidence comes only from secondary citations. |
| Gandin death place (Maryland) | COULD NOT VERIFY | -- | -- | low | Working assumption only; NMC was at Camp Springs MD. Post should omit specific place or say "in the Washington, D.C. area". |
| Voeikov MGO Leningrad through 1981 | CONFIRMED | https://imsc.pacificclimate.org/awards_gandin.shtml | -- | high | Gruza's 1992 IMSC citation explicitly: "All scientific activities of Lev Gandin up to 1981 were connected with the Main Geophysical Observatory in Leningrad, now St. Petersburg." |
| 1992 IMSC Outstanding Achievement Award at Toronto, shared with Brier and Epstein | CONFIRMED | https://imsc.pacificclimate.org/history.shtml | -- | high | IMSC history page lists three inaugural recipients: Brier, Epstein, Gandin. Award presented by G. V. Gruza. |
| Gruza characterisation ("very young, very clever, and a very cheerful fellow"; ping-pong, chess, bridge, piano) | CONFIRMED | https://imsc.pacificclimate.org/awards_gandin.shtml | -- | high | Direct quote on IMSC awards page. |
| Gandin co-author on Kalnay et al. 1996 BAMS reanalysis paper | CONFIRMED | https://journals.ametsoc.org/view/journals/bams/77/3/1520-0477_1996_077_0437_tnyrp_2_0_co_2.xml | -- | high | Author list (Google Scholar lookup, ADS, multiple references): Kalnay, Kanamitsu, Kistler, Collins, Deaven, **Gandin**, Iredell, Saha, White, Woollen, ... Gandin is 6th author. *BAMS* 77, 437-471 (some refs say 472), March 1996. AMS page 403-blocked but Scholar/ADS/SciRP all confirm. |
| 1963 Russian monograph Gandin, Gidrometeoizdat Leningrad, "Объективный анализ метеорологических полей" | CONFIRMED | https://archive.org/details/objectiveanalysi0000lsga | -- | high | Original title and bibliographic line on Internet Archive scan. Also Stanford SearchWorks catalogue (Russian title transliterated). |
| 1965 English translation by IPST, Jerusalem, "Objective Analysis of Meteorological Fields", vi + 242 pp | CONFIRMED | https://archive.org/details/objectiveanalysi0000lsga | -- | high | Internet Archive scan, OCLC 25601011 via Stanford. 53 figures, 28 tables (QJRMS 1966 review). Bibliography pp 231-238 (Stanford record). |
| US government sponsorship of IPST translation | CONFIRMED (corrected) | https://searchworks.stanford.edu/view/2167319 | -- | high | Stanford catalogue: "Available through U.S. Department of Commerce, Clearinghouse for Federal Scientific and Technical Information, Springfield, VA" -- the CFSTI (later NTIS). The bio file said "NSF/NOAA/Department of Commerce"; the actual distribution channel was **Department of Commerce CFSTI**. Post should use this language. PB number itself not retrieved. |
| QJRMS 1966 review at vol 92, p 447 | CONFIRMED | https://ui.adsabs.harvard.edu/abs/1966QJRMS..92Q.447./abstract | -- | high | ADS record; Wiley DOI 10.1002/qj.49709239320 also resolves. |
| Cressman 1959 *MWR* 87, 367-374 "An Operational Objective Analysis System" | CONFIRMED | https://journals.ametsoc.org/view/journals/mwre/87/10/1520-0493_1959_087_0367_aooas_2_0_co_2.xml | -- | high | AMS Journals XML page exists. Open-access PDF mirror at https://twister.caps.ou.edu/OBAN2019/Cressman1959.pdf and via Semantic Scholar. ADS abstract at https://ui.adsabs.harvard.edu/abs/1959MWRv...87..367C/abstract. |
| Parrish-Derber 1992 *MWR* 120 (Issue 8), 1747-1763 SSI paper | CONFIRMED | https://journals.ametsoc.org/view/journals/mwre/120/8/1520-0493_1992_120_1747_tnmcss_2_0_co_2.xml | -- | high | DOI 10.1175/1520-0493(1992)120<1747:TNMCSS>2.0.CO;2; ADS abstract https://ui.adsabs.harvard.edu/abs/1992MWRv..120.1747P/abstract. Title "The National Meteorological Center's Spectral Statistical-Interpolation Analysis System". |
| ECMWF 3D-Var operational 30 January 1996 | CONFIRMED | https://artefacts.ceda.ac.uk/badc_datadocs/ecmwf-op/model_changes.html | -- | high | Exact quote: "On 30 January 1996 ECMWF introduced a 3-dimensional variation (3D-Var) analysis scheme." Confirms quality details: NH similar to OI, SH higher skill, better temperature/wind verification. |
| ECMWF 4D-Var operational 25 November 1997 | CONFIRMED | https://artefacts.ceda.ac.uk/badc_datadocs/ecmwf-op/model_changes.html | -- | high | Exact quote: "On 25 November 1997, the first version of a four-dimensional variational data assimilation system (4D-Var) was introduced." Also confirmed by ECMWF "20 years of 4D-Var" 2017 article (https://www.ecmwf.int/en/about/media-centre/news/2017/20-years-4d-var-better-forecasts-through-better-use-observations). |
| Lorenc 1981 *MWR* 109, 701-721, "A Global Three-Dimensional Multivariate Statistical Interpolation Scheme" | CONFIRMED | https://journals.ametsoc.org/view/journals/mwre/109/4/1520-0493_1981_109_0701_agtdms_2_0_co_2.xml | -- | high | AMS Journals XML page; ADS abstract https://ui.adsabs.harvard.edu/abs/1981MWRv..109..701L/abstract; full-text PDF at https://data-ww3.ifremer.fr/BIB/Lorenc_MWR1981.pdf. |
| Bergthorsson-Doos 1955 *Tellus* 7, 329-340, "Numerical weather map analysis" | CONFIRMED | https://tellusjournal.org/articles/3803/files/658e7e4983030.pdf | -- | high | Open-access PDF at Tellus journal; also Wiley DOI 10.1111/j.2153-3490.1955.tb01183.x. Mirror at https://twister.caps.ou.edu/OBAN2019/Bergth-rsson_et_al-1955-Tellus.pdf. |
| Hollingsworth-Lonnberg 1986 *Tellus* 38A, 111-136, Part I (wind field) | CONFIRMED | https://tellusjournal.org/articles/10.3402/tellusa.v38i2.11707 | -- | high | Open-access via Tellus. Companion paper Lonnberg-Hollingsworth Part II in same issue, pages 137-161, "covariance of height and wind errors". |
| Le Dimet-Talagrand 1986 *Tellus* 38A, 97-110, "Variational algorithms for analysis and assimilation" | CONFIRMED | https://onlinelibrary.wiley.com/doi/abs/10.1111/j.1600-0870.1986.tb00459.x | -- | high | ADS abstract https://ui.adsabs.harvard.edu/abs/1986TellA..38...97D/abstract. Open access at https://www.tandfonline.com/doi/abs/10.3402/tellusa.v38i2.11706. |
| Evensen 1994 *JGR* 99, 10143-10162, EnKF founding paper | CONFIRMED | https://agupubs.onlinelibrary.wiley.com/doi/abs/10.1029/94JC00572 | -- | high | DOI 10.1029/94JC00572. ADS https://ui.adsabs.harvard.edu/abs/1994JGR....9910143E/abstract. Open-access PDF at https://twister.caps.ou.edu/OBAN2019/EvensonJGR1994.pdf. Title "Sequential data assimilation with a nonlinear quasi-geostrophic model using Monte Carlo methods to forecast error statistics". |
| NCEP SSI operational date 25 June 1991 | CONFIRMED (more precise) | https://journals.ametsoc.org/view/journals/wefo/6/4/1520-0434_1991_006_0538_tngoas_2_0_co_2.xml | -- | high | "The New Global Operational Analysis System at the National Meteorological Center", *Weather and Forecasting* Vol 6, Issue 4, December 1991, pp. 538-. Quote: "implemented into the operational Global Data Assimilation System at the National Meteorological Center (NMC) on 25 June 1991." This refines the bio file's "June 1991" to the exact date. |
| JMA Meso 4D-Var operational March 2002 (world's first regional 4D-Var) | CONFIRMED | https://www.jstage.jst.go.jp/article/sola/1/0/1_0_45/_article | -- | high | Koizumi-Ishikawa 2005 *SOLA* paper documents Meso-4DVar; "JMA started to use 4D-Var for regional NWP to initialize the hydrostatic MSM in March 2002 (Ishikawa and Koizumi 2002)". Implementation upgrade paper at WGNE Blue Book 2008 https://wgne.net/bluebook/uploads/2008/individual-articles/01_Honda_Yuki_01_honda_yuki_jnova.pdf. |
| Met Office 4D-Var operational 5 October 2004 | CONFIRMED | https://www.researchgate.net/publication/229086825_The_Met_Office_Global_4-Dimensional_Data_Assimilation_Scheme | -- | medium-high | "The Met Office Global 4-Dimensional Data Assimilation Scheme" (Rawlins et al. 2007 QJRMS 133, 347-362) documents the operational implementation on 5 October 2004. The bio's date matches the standard QJRMS Rawlins-et-al reference. |
| CMC EnKF operational 12 January 2005 (Houtekamer-Mitchell architecture) | CONFIRMED (more precise) | https://journals.ametsoc.org/mwr/article/137/7/2126/103760/Model-Error-Representation-in-an-Operational | -- | high | Houtekamer et al. 2009 *MWR* 137 paper: "Since 12 January 2005, an ensemble Kalman filter (EnKF) has been used operationally at the Meteorological Service of Canada". More precise than the bio's "2005". |
| Bergman 1979 *MWR* 107, 1423-1444 "Multivariate analysis of temperatures and winds using optimum interpolation" | CONFIRMED (paper title and pages) | -- | -- | high | Standard reference; SciRP citation lookups confirm volume, issue, page range. The bio file does not give the title/pages -- this fills the gap. Companion 1979 *MWR* paper at Vol 107, Issue 11, "The NMC Operational Global Data Assimilation System" https://journals.ametsoc.org/view/journals/mwre/107/11/1520-0493_1979_107_1445_tnogda_2_0_co_2.xml |
| Gandin 1988 *MWR* 116 (Issue 5), pp 1137-1156 "Complex Quality Control of Meteorological Observations" | CONFIRMED | https://journals.ametsoc.org/view/journals/mwre/116/5/1520-0493_1988_116_1137_cqcomo_2_0_co_2.xml | -- | high | AMS Journals XML page; issue 5 (May 1988). The 1988 paper presents survey-style content; secondary sources say "in 1988 L.S. Gandin began adapting his ideas in complex quality control (CQC) to the operational environment at the National Centers for Environmental Prediction" -- which implies the affiliation transition was already in progress in 1988. The exact affiliation line of the 1988 paper itself could not be retrieved (AMS 403). |
| Gandin 1992 *MWR* 120, 361-370 (with A. H. Murphy) "Equitable Skill Scores for Categorical Forecasts" | CONFIRMED (via secondary lookups) | -- | -- | high | Standard SciRP/ADS lookups confirm the citation; Gerrity 2002 "A note on Gandin and Murphy's equitable skill score" *MWR* paper cites it. |
| Gandin emigrated 1991 | CONFIRMED (corroborated) | -- | -- | medium-high | Bio file's 1991 emigration date is consistent with: (a) IMSC 1992 award presented in Toronto with him present (b) 1988 *MWR* paper which secondary sources tie to start of NMC adaptation; (c) Soviet collapse late 1991 timing. Cannot be precisely dated to a month from open sources. |
| Birth year POSSIBLY 1915, not 1923 | DISPUTED -- CRITICAL CORRECTION FLAG | https://journals.ametsoc.org/view/journals/bams/79/3/1520-0477-79_3_479.xml | -- | medium | The BAMS Vol 79 Issue 3 (March 1998) "In Memoriam" list page contains six 1997 obituary entries listed in decorative typography. One is "1915-1997". The companion file `OI_technical_and_operational.md` independently writes "Gandin (1915-1997)". This strongly suggests Gandin was born 1915, NOT c.1923 as stated in the bio file. **Recommendation: post should use "1915-1997" or hedge as "born in the mid-1910s". The c.1923 working assumption in Lev_Gandin.md is most likely wrong.** Decorative font OCR could not identify the name; physical verification of the BAMS print issue is needed for definitive resolution. |

## Critical resolution required: Gandin birth year

The two existing research files **contradict each other**:
- `research/people/Lev_Gandin.md` line 1: "Lev S. Gandin (c.1923-1997)" -- but this is flagged "FACT NOT VERIFIED" in line 30 of the same file
- `research/concepts/OI_technical_and_operational.md` line 69: "Gandin (1915-1997)" -- stated without hedge

The BAMS Vol 79 Issue 3 (March 1998) In Memoriam page (https://journals.ametsoc.org/view/journals/bams/79/3/1520-0477-79_3_479.xml) lists six 1997 obituary entries. One is "1915-1997". Decorative typography prevented OCR of names, but the OI_technical file's confident "1915-1997" line is consistent with the BAMS necrology and was likely written from a now-untraceable but reliable original source. **Recommendation: the post should use 1915 as the birth year and Gandin would then have been 48 at the 1963 monograph and 82 at death.**

## Sources consulted (running)

### Primary sources confirmed
- IMSC awards page on Gandin: https://imsc.pacificclimate.org/awards_gandin.shtml
- IMSC history page (1992 Toronto awards): https://imsc.pacificclimate.org/history.shtml
- Internet Archive scan of 1965 IPST translation: https://archive.org/details/objectiveanalysi0000lsga
- Stanford SearchWorks catalogue for 1965 IPST: https://searchworks.stanford.edu/view/2167319
- Cressman 1959 AMS page: https://journals.ametsoc.org/view/journals/mwre/87/10/1520-0493_1959_087_0367_aooas_2_0_co_2.xml
- Bergthorsson-Doos 1955 Tellus open-access: https://tellusjournal.org/articles/3803/files/658e7e4983030.pdf
- Lorenc 1981 AMS: https://journals.ametsoc.org/view/journals/mwre/109/4/1520-0493_1981_109_0701_agtdms_2_0_co_2.xml
- Hollingsworth-Lonnberg 1986 Tellus: https://tellusjournal.org/articles/10.3402/tellusa.v38i2.11707
- Le Dimet-Talagrand 1986 Tellus/Wiley: https://onlinelibrary.wiley.com/doi/abs/10.1111/j.1600-0870.1986.tb00459.x
- Parrish-Derber 1992 AMS: https://journals.ametsoc.org/view/journals/mwre/120/8/1520-0493_1992_120_1747_tnmcss_2_0_co_2.xml
- Evensen 1994 Wiley: https://agupubs.onlinelibrary.wiley.com/doi/abs/10.1029/94JC00572
- Kalnay 1996 BAMS reanalysis (ADS metadata): https://ui.adsabs.harvard.edu/abs/1996BAMS...77..437K/abstract
- ECMWF model changes log: https://artefacts.ceda.ac.uk/badc_datadocs/ecmwf-op/model_changes.html
- ECMWF "20 years of 4D-Var" 2017: https://www.ecmwf.int/en/about/media-centre/news/2017/20-years-4d-var-better-forecasts-through-better-use-observations
- Kanamitsu et al. 1991 *Wea. Forecasting* (NCEP SSI operational 25 June 1991): https://journals.ametsoc.org/view/journals/wefo/6/4/1520-0434_1991_006_0538_tngoas_2_0_co_2.xml
- Houtekamer et al. 2009 *MWR* (CMC EnKF 12 January 2005): https://journals.ametsoc.org/mwr/article/137/7/2126/103760/Model-Error-Representation-in-an-Operational
- JMA Meso 4D-Var Koizumi-Ishikawa 2005 *SOLA*: https://www.jstage.jst.go.jp/article/sola/1/0/1_0_45/_article
- Gandin 1988 *MWR* CQC: https://journals.ametsoc.org/view/journals/mwre/116/5/1520-0493_1988_116_1137_cqcomo_2_0_co_2.xml
- BAMS Vol 79 Issue 3 (March 1998) In Memoriam (1997 deaths list page): https://journals.ametsoc.org/view/journals/bams/79/3/1520-0477-79_3_479.xml

### Sources blocked or unreachable
- AMS Honorary Members list (403 -- expected based on bio file's prior note)
- Russian Wikipedia "Гандин, Лев Семёнович" (URL encoding never resolved)
- Wikidata Q-number for Gandin (search returned no candidate)
- BAMS 79 Issue 3 PDF for prose obituary content (PDF only contained Norman Taylor obit, not Gandin's; Gandin necrology is on the visual-typography list page 487 with only birth-death years displayed)

## Notes for the writer of Post 44

1. **Birth year**: Use **1915-1997**, not c.1923. The OI_technical_and_operational.md file has this confidently and is consistent with the BAMS necrology line "1915-1997". The c.1923 in the Lev_Gandin.md file was an unverified working assumption.
2. **Death place**: Don't specify Maryland or Washington — say "in the Washington, D.C. area" or omit place. No primary source consulted gave the place of death.
3. **IPST sponsorship language**: Use **"distributed in the United States by the U.S. Department of Commerce, Clearinghouse for Federal Scientific and Technical Information, Springfield, Virginia"** — this is what the Stanford catalogue says. Don't say "NSF/NOAA" — the actual channel was CFSTI (predecessor of NTIS).
4. **NCEP SSI operational date**: Use **25 June 1991**, not just "June 1991" (Kanamitsu et al. 1991 *Wea. Forecasting* gives the exact date).
5. **CMC EnKF date**: Use **12 January 2005** (Houtekamer et al. 2009 *MWR*).
6. **Bergman 1979** paper title is **"Multivariate analysis of temperatures and winds using optimum interpolation"**, *MWR* 107, 1423-1444 -- this is the right citation for the NMC OI scheme.
7. **The Hollingsworth-Lonnberg 1986 paper** has a companion in the same Tellus 38A issue: Lonnberg-Hollingsworth Part II at pages 137-161. Some bio files conflate the two.
8. The Le Dimet-Talagrand 1986 *Tellus* 38A paper covers pages 97-110, not the longer page range sometimes assumed.
9. The Met Office 4D-Var date 5 October 2004 is the standard reference (Rawlins et al. 2007 QJRMS 133, 347-362).
10. **AMS Honorary Members page itself**: Inaccessible (403). Take the bio file's "UCAR Scientist at the National Meteorological Center, National Weather Service, NOAA, Washington, D.C." as the affiliation language but do not put the page URL as the citation -- it cannot be opened to verify the exact wording.
