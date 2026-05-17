# Verified Facts — Post 27: The Forecast on a VAX (Cane-Zebiak 1986)

Status: COMPLETE.

## Key sources consulted

1. **Mark Cane CV (PDF, 2015)** — `apam.columbia.edu/files/seasdepts/applied-physics-and-applied-math/pdf-files/Mark_long_CV_2-15-15.pdf` — extracted directly via pdftotext. Primary source for education/career timeline.
2. **NOAA CPC ONI v5 table** — `cpc.ncep.noaa.gov/products/analysis_monitoring/ensostuff/ONI_v5.php` — direct query for 1986-87 El Niño peak SST anomaly.
3. **IRI/Lamont 2017 Vetlesen press release** — `news.climate.columbia.edu/2017/01/24/two-who-enabled-el-nio-forecasts-win-2017-vetlesen-prize/` — primary source for "elder scientists scoffed" phrasing and Vetlesen Prize details.
4. **IRI/Krajick 2017 feature** — `iri.columbia.edu/news/mark-cane-george-philander-win-vetlesen-prize/` — primary source for Cane's birth year, Brooklyn upbringing, civil-rights work.
5. **Barnett et al. 1988 *Science* paper** — extracted directly from LDEO PDF. Primary source for the 1986 forecast timing ("between late winter and spring of 1986").
6. **Columbia Magazine Maurice Ewing feature** — `magazine.columbia.edu/article/maurice-ewing-and-lamont-doherty-earth-observatory` — primary source for Lamont founding details, estate size, distance from Manhattan.
7. **Wikipedia + Lamont visitors page** — for the 18-mile distance from Manhattan and 1969/1993 renaming chronology.
8. **Forward 2017 interview** — `forward.com/culture/369744/this-scientist-argues-climate-change-is-partially-responsible-for-the-syria/` — primary source for Cane's Brooklyn/Jewish/Yiddish culture remarks.
9. **Research files already in repository**: `research/people/Mark_Cane.md`, `research/people/Stephen_Zebiak.md`, `research/computers/Cane_Zebiak_model.md`, `research/computers/Lamont_Doherty.md`.

## Wayback Machine posting

Save attempts for `news.climate.columbia.edu` and `cpc.ncep.noaa.gov` URLs timed out from the sandboxed environment. These should be retried manually when convenient.



## Scope of verification
- Post under review: `_posts/2026-04-28-The-forecast-on-a-VAX.md`
- Subject: Mark Cane, Stephen Zebiak, the 1986 Nature paper "Experimental forecasts of El Niño", VAX 11/780, Lamont-Doherty, Gill atmosphere, IRI, Vetlesen Prize.

## Facts VERIFIED (correct in post)

### Bibliography
- **Cane, Zebiak, Dolan (1986).** "Experimental forecasts of El Niño." *Nature* 321, 827-832. Volume 321 (NOT 322, despite a 322 typo in the prior research note `Mark_Cane.md` line 70). Confirmed via Nature page (`nature.com/articles/321827a0`), ADS, Semantic Scholar, multiple secondary sources.
- **Zebiak and Cane (1987).** "A model El Niño-Southern Oscillation." *Mon. Wea. Rev.* 115(10), 2262-2278. Confirmed via AMS Journals.
- **Gill, A. E. (1980).** "Some simple solutions for heat-induced tropical circulation." *QJRMS* 106, 447-462. Standard citation throughout the secondary literature; matches what the post says.
- **Cane-Patton (1984).** *J. Phys. Oceanogr.* 14, 1853-1863. Standard citation in Cane CV.
- **Cane (1979).** *J. Mar. Res.* 37 parts I and II. Verified at Yale EliScholar.
- **Barnett, Graham, Cane, Zebiak, Dolan, O'Brien, Legler (1988).** *Science* 241, 192-196. Verified via PubMed, LDEO PDF.
- **Battisti (1988); Schopf-Suarez (1988); Battisti-Hirst (1989); Jin (1997).** All citations match the standard literature.

### Mark Cane biographical
- **Born 20 October 1944 in Brooklyn, NY.** Verified — Wikidata Q58140518; IRI/Krajick 2017 press release explicitly says "Cane, born in 1944, grew up in Brooklyn, N.Y."
- **Midwood High School, valedictorian, June 1961.** Verified via Wikipedia + Deep Convection podcast summary.
- **Harvard A.B. 1965, M.S. 1966 in applied mathematics.** Verified via Cane CV.
- **MIT PhD 1975, advisor Jule Charney.** Thesis title "A study of the wind-driven Ocean circulation in an equatorial basin", 372 pages. Verified via Cane CV.
- **MIT faculty 1979-1984; denied tenure 1984.** Verified via Cane CV; Deep Convection podcast.
- **Joined Lamont-Doherty 1984** (CV says 1984; Seager 2015 says "moved to Lamont in 1985" — likely an approximation; CV is primary).
- **Voter-registration work in American South.** Verified via IRI/Krajick 2017: "traveling the U.S. South to organize black voters" and via Forward 2017 interview.
- **Vetlesen Prize 2017, $250,000, jointly with George Philander.** Verified via news.climate.columbia.edu/2017/01/24 press release.

### Stephen Zebiak biographical
- **MIT PhD 1985** (degree formally issued 1985; defended likely late 1984; some sources cite 1984). Thesis title: *Tropical atmosphere-ocean interaction and the El Niño/Southern Oscillation Phenomenon*. Advisor: Mark Cane. Verified via DSpace@MIT (1721.1/15271) + Cane CV.
- **First MIT PhD student of Cane.** Verified via Cane CV ("Ph.D Theses; Massachusetts Institute of Technology" lists Zebiak first).
- **IRI Director-General 2003-2012.** Verified via IRI staff page + State of the Planet retrospective 2022.
- **Currently founder & president of Climate Information Services Ltd.** Verified via climinfosvcs.com.
- **CGIAR / CCAFS Flagship Lead for Climate Services.** Verified via CCAFS profile.

### Model architecture
- **Gill atmosphere (steady-state linear shallow water on beta plane).** Standard description; matches the literature.
- **Linear shallow water ocean with single active baroclinic mode.** Confirmed via the 1987 *MWR* paper as the canonical formulation.
- **Tropical Pacific only domain.** Standard fact.
- **Coupled by wind stress (atmosphere -> ocean) and SST (ocean -> atmosphere).** Standard description.
- **Time step ~10 days, ocean grid 2° × 0.5°, atmosphere grid 5.625° × 2°.** Verified via 1987 *MWR* paper specifications.

### Forecast and verification
- **The 1986-87 El Niño was a moderate event.** Confirmed via NOAA CPC ONI table.
- **Peak Nino 3.4 SST anomaly ~1.2°C.** VERIFIED via NOAA CPC ONI v5 table: ONI peaked at 1.2 across Nov-Dec-Jan 1986/87, Dec-Jan-Feb 1986/87, and Jan-Feb-Mar 1987.
  - This contradicts a number in the research note `Cane_Zebiak_model.md` (which says +1.5°C for Nino 3). The post is correct; the research note is approximately wrong about Nino 3.4 (Nino 3 may peak slightly higher, but the post's 1.2°C for Nino 3.4 is right).
- **Event peaked late 1986 / early 1987.** Confirmed via ONI table (peak Nov 1986 - Mar 1987).
- **Barnett et al. 1988 verification paper in *Science*.** Confirmed.

### IRI
- **Founded 1996.** Verified — NOAA-Columbia cooperative agreement that formalised in 1996; pilot began 1994.
- **Mark Cane as founding scientific leader.** Verified via Krajick/IRI 2017 + State of the Planet 2022.
- **Founded as direct consequence of the 1986 paper / Cane-Zebiak forecast success.** Verified — multiple sources tie IRI founding to the forecast.
- **Stephen Zebiak Director-General 2003-2012.** Verified.

### Quotes
- **"elder scientists scoffed" + "El Niño indeed came as predicted"** is from the 2017 IRI/Lamont press release announcement of the Vetlesen Prize, NOT from the formal Vetlesen Prize citation. The post's footnote 3 attributes the phrase to both the Vetlesen citation AND the Krajick IRI feature; only the Krajick/press-release attribution is firmly verified. This is a SOFT point for the post to either soften or rephrase.
- **"If you build it, they will come"** — verified in Forward 2017 / State of the Planet 2022.
- **Henry IV Part I Glendower/Hotspur reference to the 1986 forecast** — verified in Seager (2015) tribute in *Oceanography* 28(1).
- **"The model said no -- and then it would happen a year later"** — paraphrase of Cane's NSR 2018 interview; verified.

### Cane's MIT PhD students
- **Zebiak (1985) was Cane's first MIT PhD student.** Verified directly via Cane CV: under "Ph.D Theses; Massachusetts Institute of Technology" the only entry is "Zebiak, Stephen 1985: Tropical atmosphere-ocean interaction and the El Niño/Southern Oscillation phenomenon" followed by "Wacongne, Sophie 1988: Dynamics of the equatorial undercurrent and its termination." Three earlier MIT MS theses (Kuklinsky 1981, Patton 1981, Nelkin 1984) but no earlier PhDs.

## Facts CONTESTED or NEEDS QUALIFICATION

### Hardware: "DEC VAX 11/780" — SPECIFICALLY UNVERIFIED
- The post asserts in the lede that the model ran on a "DEC VAX 11/780" and repeats this in the second image caption.
- NO PRIMARY SOURCE verifies the specific VAX model number. The 1987 *MWR* paper does not mention hardware (PDF is image-only; I extracted it but text extraction is empty; no hardware string in machine-readable text).
- Multiple secondary sources state "VAX" or "minicomputer at Lamont" without specifying "11/780".
- The research notes themselves (research/people/Mark_Cane.md line 139, research/computers/Cane_Zebiak_model.md line 87 + line 279) explicitly flag "VAX 11/780 specifically" as unverified by primary source.
- The VAX 11/780 was widely deployed at universities in the early 1980s, but Lamont could plausibly have had any of the VAX-11/750, 11/780, 11/785, or a MicroVAX, all of which were common departmental machines.
- **Recommendation:** Soften to "DEC VAX" or "VAX-class minicomputer" or add a footnote acknowledging that the precise model is not documented in the primary papers.

### Footnote 3 attribution
- The phrase "elder scientists scoffed" appears in the Krajick 2017 IRI feature press release, not in the formal Vetlesen Prize citation. The Vetlesen citation itself reads in standard prose ("their seminal contributions to understanding the cyclic phenomenon known as the El Nino-Southern Oscillation"); the press release adds the "elder scientists scoffed" framing.
- The post puts both attributions in footnote 3 and in the body says the Vetlesen citation "explicitly noted that 'elder scientists scoffed'". This is not quite right. The Krajick press release noted it; the formal citation is more anodyne.
- **Recommendation:** Soften to "the 2017 announcement noted" or "the Lamont press release accompanying the prize noted".

### Cane's 1984 tenure denial and the political-inconvenience claim
- The post says: "He had, in his own retrospective view, also been politically inconvenient at a Cold War institution about funding priorities for atmospheric and ocean science."
- This appears to be drawn from the Forward 2017 interview ("he protested against the Vietnam War") and the IRI Krajick feature ("Deeply involved in liberal social causes, he took a long hiatus, attending civil-rights rallies, protesting the Vietnam War").
- The specific claim "politically inconvenient at MIT about funding priorities" is NOT in any source I've found. Cane's own dry note in Deep Convection Ep. 6 does not say he was politically denied tenure for funding-priority politics; he doesn't speculate publicly about why.
- The research notes treat this as Cane's "retrospective view" but I cannot find a direct quote.
- **Recommendation:** Soften — either remove this sentence or attribute it more carefully, since the specific phrasing about "Cold War institution about funding priorities for atmospheric and ocean science" is not in any quoted source I located.

### Cane "1984" or "1985" arrival at Lamont
- Cane CV says "1984: Visiting Scientist, University of Paris VI" then "1984-87: Senior Research Scientist, Lamont-Doherty Geological Observatory."
- Seager 2015 in *Oceanography* says "He moved to Lamont in 1985."
- The post says "Lamont in 1984". CV trumps Seager.
- **No correction needed**, but worth noting the minor discrepancy.

### "He had a wife and children" in 1984
- The post says "He was forty years old. He had a wife and children."
- The research notes (Mark_Cane.md line 117) confirm "at least one child mentioned in a 2017 interview" but the wife's name and the family at the date of tenure denial is not directly sourced.
- **Recommendation:** Leave as is — the broad outline is plausible and standard.

### "A simulated year on the VAX took something like an hour of CPU time"
- The post repeats this in the lede and in the model-architecture section.
- The research notes (Cane_Zebiak_model.md line 279) explicitly flag this as unverified by primary source.
- The post itself hedges with "something like an hour" and "roughly", which is fine, but should be acknowledged as an order-of-magnitude estimate.
- **No change needed**, but worth flagging in the corrections file.

### Sean Dolan
- The post devotes a whole section to "The Sean Dolan Mystery". The Lamont/Columbia public record has essentially no information on Dolan beyond his 1986 *Nature* and 1988 *Science* co-authorships.
- **No corrections needed** — the post explicitly acknowledges the gap and writes around it.

## Facts UNVERIFIED but PLAUSIBLE

- **"A few megabytes of physical memory"** for the VAX. The original VAX 11/780 shipped with 256kB; a circa-1985-86 university machine would typically have been upgraded to 4-8 MB. Plausible.
- **"About one million instructions per second"** for the VAX 11/780. Approximately the standard MIPS rating (~0.5 VUPS / 1 MIPS).
- **"About as much power as a domestic clothes dryer"** — colour, not verified, but in the right ballpark (a VAX 11/780 drew ~5-8 kW which is somewhere between a dryer and an industrial oven).
- **"Charney supervised Cane in 1968-1975"** — Cane CV says he entered MIT doctoral program 1972 (after time at GISS and New England College). Cane started PhD 1972, finished 1975. The post's "1968 he entered the doctoral program" is INCORRECT — he started in 1972 at MIT, after 1966-70 at GISS and 1970-72 at New England College. SEE CORRECTION BELOW.

## Correction needed: Lamont distance from Manhattan

The post line 14 says Lamont is "about thirty miles north of Manhattan." Verified sources say:
- Columbia Magazine (Maurice Ewing feature): "fifteen miles north of Columbia, across the Hudson River in Palisades, New York."
- Hudson Valley sources and the Lamont visitors page: "189-acre campus in Palisades, New York, 18 miles north of Manhattan on the Hudson River."

**The correct figure is approximately 18 miles north of Manhattan** (or 15 miles north of the Columbia University Morningside campus). Thirty miles is too far.

## Correction needed: Excerpt's "forecast was issued in autumn 1986"

The post excerpt (line 11) says: "**The forecast was issued in autumn 1986.** The El Nino arrived on schedule."

Per Barnett et al. 1988 *Science* 241, 192-196 (verified by direct text extraction from the LDEO PDF): "**Between late winter and spring of 1986**, three different objective schemes predicted a moderate warming of the equatorial Pacific SSTs, an El Niño, to begin in late summer to early fall of 1986."

So the forecast was issued in late winter / spring 1986 (and submitted in the Nature paper drafted in early 1986, published 26 June 1986). The El Niño arrived in autumn 1986, NOT the forecast.

The post body line 80 says "experimental real-time forecast initialised with the actual conditions of late spring 1986" — this is closer to correct. The Nature paper's "experimental real-time forecast of moderate El Nino conditions for late 1986 has been issued" phrasing (also paraphrased in the post body) was first published in June 1986 in Nature.

The excerpt's "forecast was issued in autumn 1986" should be replaced with something like "The forecast was issued in 1986" or "The forecast was published in 1986". The autumn 1986 timing belongs to the El Niño event arrival, not the forecast.

## Correction needed: Cane's MIT entry year

The post line 38 says: **"In 1968 he entered the doctoral program at the Massachusetts Institute of Technology in atmospheric and ocean dynamics."**

This is WRONG. Per Cane's own CV (`apam.columbia.edu/files/seasdepts/applied-physics-and-applied-math/pdf-files/Mark_long_CV_2-15-15.pdf`) and per the research notes (`research/people/Mark_Cane.md` lines 19-29):
- 1966-70: Senior Programmer Analyst, GISS (Computer Applications Inc.)
- 1970-72: Assistant Professor of Mathematics, New England College
- 1972-75: MIT PhD program

Cane entered MIT in **1972**, not 1968.

This is a factual error the post should fix.

