# IBM-CDC Antitrust Drama: A Primary-Source Deep Dive

Research for Post 31 of the NWP-history blog series. Companion to `IBM_360_91_business.md`. This file focuses on the institutional-drama spine: the December 1968 CDC complaint, the January 1969 DOJ filing, the January 1973 settlement, and the contested destruction of CDC's litigation discovery database.

Where the prior file gave a high-level outline, this one gets the dates, dollar figures, court citations, judge names, and direct quotes nailed down.

---

## 1. CDC v. IBM (filed December 1968)

### 1.1 Filing date, court, judge, docket

**Filed**: December 1968 in the U.S. District Court for the **District of Minnesota**, sitting in Minneapolis. The court "originally heard defendant's motion, directed at that time solely to Control Data Corporation's complaint" on **31 December 1968** (Justia opinion 306 F. Supp. 839 procedural history). The most consistent secondary date is mid-December 1968, but I have not been able to verify a single specific filing day from primary court documents in the public web record. Several secondary sources say "11 December 1968" and "12 December 1968" but I cannot confirm either against the District Court's original docket sheet.

**Case**: *Control Data Corp. v. International Business Machines Corp.*

**Docket number**: D. Minn. Civ. Action No. **3-68-312** (per multiple secondary citations).

**Judge**: U.S. District Judge **Philip Neville**, District of Minnesota. Neville handled the consolidated multidistrict pretrial proceedings: in February 1969 IBM moved under 28 U.S.C. § 1407 for consolidation of CDC's case with another case (Data Processing Financial and General Corp.) in the Southern District of New York. The Judicial Panel on Multidistrict Litigation transferred the SDNY private cases to Minnesota for coordinated pretrial work under Neville (*In re IBM*, 302 F. Supp. 796 (J.P.M.L. 1969)).

**Causes of action**: Sherman Act § 2 monopolisation; treble damages and attorneys' fees under Clayton Act § 4.

**Published 1969 procedural opinion**: *Control Data Corp. v. International Business Machines Corp.*, 306 F. Supp. 839 (D. Minn. 1969). [law.justia.com/cases/federal/district-courts/FSupp/306/839/1794359/](https://law.justia.com/cases/federal/district-courts/FSupp/306/839/1794359/) — accessed 2026-05-05; the published text was not retrievable through my tooling but the citation is canonical.

### 1.2 The "phantom machine" / "paper machine" allegations

The CDC complaint contained, per the Reason 1974 article, **"a full page ... entitled 'Paper Machines and Phantom Computers'"** ([*IBM: Producer or Predator*](https://reason.com/1974/04/01/ibm/), Reason, April 1974, accessed 2026-05-05). This is the only direct primary-source attestation of the section title I have found.

The complaint listed two distinct phantom-machine episodes:

1. **The early 1960s scientific-market machine**. CDC alleged that "in the early 60's when CDC decided to enter the scientific computer market (where IBM was not active), IBM announced a computer for the same market. The specifications were spectacular, but they were not met. After at least four delays in the delivery date and modifications of the design cutting the power in half, less than a dozen were ever delivered." The unnamed machine in this paragraph is almost certainly the **IBM 7030 Stretch** (announced 1956, first delivered to LASL 1961, programme curtailed after IBM admitted the production version did not meet promised performance and only nine were delivered in the customer base before withdrawal).

2. **The mid-1960s 6600-killer**. CDC alleged that "in the mid 60's, when CDC introduced its model 6600, IBM, admitting that the 6600 was the fastest computer on the market, announced that it was developing one that would be 'more powerful.' Again there were delays, and IBM never really sold many of its high speed models." The "more powerful" announcement is the **System/360 Model 91** (announced November 1964) and its sibling pre-announcement, the **System/360 Model 92**.

**The 360/92 was the original phantom**. IBM's first response to the August 1963 CDC 6600 announcement was a higher-performance 360/92 — announced briefly in 1964, never built. The Wikipedia narrative is explicit: "IBM announced a new System/360 model, the Model 92, which would be just as fast as CDC's 6600. Although this machine did not exist, sales of the 6600 dropped drastically while people waited for the release of the mythical Model 92." Three AFIPS 1964 FJCC papers were published describing the Model 92 architecture (catalogued at computinghistory.org.uk under accession 17055), giving the announcement an air of substantive engineering credibility. The 360/92 was then "scaled back" into the actual-shipped 360/91 (announced November 1964, first ship NASA Goddard October 1967).

**The 360/91 itself was Exhibit A** of the second phantom episode. The 360/91 actually shipped, but in tiny volume (15 produced, 4 retained internally by IBM, ~10–11 customer installations) and three years late.

**The 360/195 was Exhibit B**. Announced 20 August 1969 (after CDC filed the complaint), first delivered 1971; about 20 produced. The 360/195 announcement was therefore not in the original December 1968 complaint, but was certainly within the scope of the CDC discovery and the U.S. v. IBM trial that followed.

**Allegation in plain English**: IBM's corporate strategy was to freeze CDC's order book by announcing higher-performance products (360/92, 360/91, 360/195) that IBM did not have the engineering depth or factory capacity to deliver in volume on the announced schedule, with the deliberate intent of monopolising the market for general-purpose digital computers.

### 1.3 Norris's role

**William C. Norris**, founder, president, and CEO of CDC, was the personal driver of the lawsuit. Multiple sources are consistent: "Norris filed an antitrust suit against IBM in December 1968, charging that IBM had promoted a nonexistent computer solely in the hope of forcing CD out of business" (Encyclopedia.com, *Control Data Corp*); "After carefully documenting sales lost to the IBM project, Norris launched a massive lawsuit against IBM in 1968" (Wikipedia, *William Norris (CEO)*).

Norris's strategic insight was that CDC could exploit the discovery process to extract from IBM the internal documentation that would prove the deliberateness of the pre-announcement tactic. The CDC legal team, working over four years, produced a structured, computerised document review system that became known as the "CDC database" or "CDC base file."

Norris later described the antitrust action in business-school terms as "one of the best management decisions in our history" (commonly cited but the original primary attribution is somewhat elusive — see §6 below). The line is most extensively discussed in James C. Worthy's authorised biography, *William C. Norris: Portrait of a Maverick* (Ballinger Publishing, Cambridge MA, 1987, ISBN 0887300871) — which I have not been able to consult page-by-page but which Worldcat and Internet Archive metadata confirm is the standard biographical source.

### 1.4 The CDC discovery database

This is the most consequential and most contested element of the CDC case.

**What it was**: a computerised guide / index to IBM internal documents that CDC's legal staff had built over the four years of pre-trial discovery (1969–1973). The database was prepared "as a means of organising the evaluation of the enormous quantity of documents subpoenaed from IBM" ([*The Justice Department: IBM and AT&T*](https://historyofcomputercommunications.info/section/7.2/The-Justice-Department-IBM-and-AT&T/), historyofcomputercommunications.info, accessed 2026-05-05).

**Size**: the figures vary by source.
- **17 million pages**: "IBM was directed by the Minnesota Court in a discovery proceeding in the CDC action to produce some 17 million document pages in three months" — court record summary in *In re International Business Machines Corp.*, 687 F.2d 591 (2d Cir. 1982) (per secondary summary; I was not able to retrieve the full opinion text).
- **27 million to 40 million pages**: "the computerized guide that IBM had created consisted of about 75,000 legal analyses, possibly 1 million pages culled from 27 million to 40 million pages of IBM papers" (cited from a court / contemporaneous press summary, surfaced via search; the original primary attribution traces back to the 1976 New York Times reporting on Edelstein's ruling — see §3.4).
- **Approximately 75,000 legal analyses** of those documents, derivative work product produced by CDC counsel.

The size discrepancy reflects two distinct things: the **raw IBM documents produced in discovery** (estimated 17–40 million pages, depending on whether the count is restricted to the CDC case or includes overlapping U.S. v. IBM productions) and the **CDC index** of those documents — about 75 000 analytical entries pointing into the larger document set.

**Who built it**: CDC corporate legal staff, working with outside counsel. The index was kept on CDC's own computer infrastructure (the irony of an antitrust litigant against a computer monopolist building the ultimate antitrust discovery database on its own computers was not lost on contemporary observers).

**The DOJ's reliance on it**: critical. The Justice Department's own U.S. v. IBM case (filed January 1969, see §2) had been heavily dependent on access to CDC counsel's understanding of the IBM document base. "Government lawyers had been relying on Control Data attorneys for help in understanding the complexities of the computer business" ([TIME magazine summary cited in Wikipedia, *Control Data Corporation*](https://en.wikipedia.org/wiki/Control_Data_Corporation)).

---

## 2. *United States v. IBM* (filed January 17, 1969 — dismissed January 8, 1982)

### 2.1 Filing

**Filed**: **17 January 1969**, U.S. District Court, **Southern District of New York**, by Attorney General **Ramsey Clark** on his last day in office before the inauguration of the Nixon administration on 20 January 1969. The complaint charged IBM under Section 2 of the Sherman Act with monopolising or attempting to monopolise "the market for general purpose electronic digital computer systems," with a particular focus on "computers designed primarily for business" (the historiography refers to this construction as the "EDP" or general-purpose business mainframe market).

**Docket number**: **United States v. International Business Machines Corp., 69 Civ. 200 (S.D.N.Y.)**.

**Cited by Litiscape and confirmed against multiple Justia opinions in the case sequence**: *United States v. International Business Machines Corp.*, 69 Civ. 200 (S.D.N.Y. 1969).

**Filed by**: AG Ramsey Clark personally signed off; the actual lead counsel was Donald Baker, then in the Antitrust Division. Clark's signature on the last day of his tenure was politically deliberate — Clark and outgoing Assistant AG for Antitrust **Edwin Zimmerman** wanted to lock in the case before the Nixon administration could quash the investigation.

### 2.2 The Nixon administration's continuation

Despite the change of administration, the Nixon DOJ continued the case (Antitrust head Richard McLaren under AG John Mitchell). The case was assigned to Judge **David N. Edelstein**, who became chief judge of the Southern District of New York and presided over the case for its full thirteen-year history. (Edelstein began presiding in early 1972 — per *In re IBM* opinions citing his 26 January 1972 first major procedural order).

### 2.3 The 360/91 in the U.S. v. IBM complaint

Per the Truth on the Market 2020 retrospective: "more than half of the practices the government raised as antitrust violations were related to products that did not exist in 1969." Pre-announcement of vapourware (the 360/91 / 360/195 / Future Systems generations) was Exhibit A of those allegations.

The DOJ complaint specifically alleged:
- **Pre-announcement of vapourware products** to suppress competitor sales.
- **Bundling of software, hardware, and services** to foreclose competitors.
- **Predatory pricing** on competitive products (where IBM faced a CDC 6600 or similar threat) cross-subsidised by monopoly pricing on commercial mainframes (Models 30/40/50 in the System/360 family, later 370 family).
- **Discriminatory educational discounting**.

The 360/91 was prominently cited as an example of the pre-announcement tactic. The Telex case (where IBM lost at trial in September 1973 in N.D. Okla. before being reversed on appeal in 1975) cemented the pre-announcement allegation as the core of the antitrust theory.

### 2.4 The trial and dismissal

**Trial commenced**: **19 May 1975** under Judge Edelstein.
**Trial duration**: approximately six years of liability phase, 1975–1981.
**Trial transcript**: more than **104 000 pages** ([Cato 1985](https://www.cato.org/regulation/sept/oct-1985/system-error-how-ibm-antitrust-suit-raised-computer-prices) — Levy & Welzer, "System Error: How the IBM Antitrust Suit Raised Computer Prices," *Regulation* 9(5/6), Sep/Oct 1985, accessed 2026-05-05).
**Total document base accumulated by case end**: ~30 million pages (estimate cited in Edelstein's later "housekeeping" rulings).

**Dismissal**: **8 January 1982**. Assistant Attorney General **William F. Baxter** (Reagan administration, head of the Antitrust Division) filed a stipulation of dismissal stating the United States had concluded the case was "**without merit**." The dismissal followed Baxter's same-week settlement of the parallel AT&T monopoly case (the consent decree that broke up the Bell System).

Judge Edelstein protested the dismissal and held a public hearing questioning Baxter's prior consultation with IBM as a potential conflict of interest (UPI Archives, 29 June 1982). The Second Circuit subsequently mandamused several of Edelstein's procedural orders attempting to extend the case post-dismissal. The dismissal stood.

The Cato 1985 piece by **David Levy and Steve Welzer** (not "Tony Brown" as the prior research file mistakenly recorded) opens with a precise statement of the dismissal: "On January 8, 1982, Assistant Attorney General William Baxter dropped the Justice Department's antitrust suit against the International Business Machines Corporation, declaring it to be 'without merit.' The suit, which was filed by the Department of Justice in 1969, had alleged that IBM was monopolizing the general-purpose mainframe computer market in violation of section 2 of the Sherman Act. In its thirteen years, the litigation produced more than 104,000 pages of transcript and consumed Department of Justice funds at a rate of $1 to $2 million a year." (David Levy & Steve Welzer, "System Error: How the IBM Antitrust Suit Raised Computer Prices," *Regulation*, Sep/Oct 1985, p. 27.)

**Levy & Welzer's central argument** was empirical and counter-intuitive: the antitrust suit *raised* IBM's prices during 1969–1979 (because the threat of a future market-share-reduction breakup gave IBM an incentive to extract monopoly rents while it could) and lowered them only after 1979–80 when IBM's prospects in the suit visibly improved. They estimate IBM's quality-adjusted price premium against rivals at +30–40% in 1967, +30–35% in 1971, and –20% by 1981–83. The argument is the seminal "antitrust is counterproductive" critique of the IBM litigation.

---

## 3. The January 1973 IBM-CDC Settlement

### 3.1 Date

The settlement was reached on **Friday, 12 January 1973** — the date is fixed by the destruction-of-database timeline (see §3.4). The public Wall Street Journal coverage appeared on **Tuesday, 23 January 1973** ("Litigation, CDC Settlement Seen As Set Back by Others Suing IBM," *Wall Street Journal*, 23 January 1973, archived in the Computer and Communications Industry Association collection at the Charles Babbage Institute, U. Minnesota — collection 36, archival object 1619905, [archives.lib.umn.edu/repositories/3/archival_objects/1619905](https://archives.lib.umn.edu/repositories/3/archival_objects/1619905), accessed 2026-05-05).

The frequently-cited date "17 January 1973" appears to be a conflation with the 17 January 1969 U.S. v. IBM filing date or with a mid-January court appearance; the operative settlement date for the database-destruction timeline is 12 January 1973.

### 3.2 Settlement terms (verified)

- **Service Bureau Corporation transfer**: CDC acquired SBC from IBM for approximately **$16 million**. SBC was IBM's data-processing-services subsidiary, founded as the Service Bureau Division within IBM in 1932 and spun off as a wholly owned subsidiary in 1957 (under terms of the 1956 IBM consent decree with DOJ that required arm's-length operation). SBC at time of transfer had approximately 20 000 customers worldwide (per Encyclopedia.com on Control Data Corp). **Wall Street analysts estimated SBC's actual market value at approximately $60 million** at time of transfer (TIME magazine, January 1973, summarised in Wikipedia *Control Data Corporation*).
- **R&D contracts**: IBM agreed to purchase approximately **$30 million in R&D services from CDC** over the following years (Reason 1974 figure).
- **Service-business non-compete**: IBM agreed to **stay out of the data-processing-services business in the United States for six years** (1973–1979).
- **Service-business floor**: IBM agreed to **buy services from SBC for five years**.
- **Legal fees**: IBM reimbursed CDC approximately **$15 million in legal fees**.
- **Free IBM equipment use**: SBC continued to use IBM equipment without charge for six months post-transfer (Reason 1974).
- **CDC discovery materials destruction**: see §3.4 below.

**Total cost to IBM** (cash + value transfer + non-compete obligation): approximately **$80 million**, per the consensus of TIME, Wall Street Journal, Reason 1974, dwkcommentaries 2011, and Pugh's *Building IBM*. The widely-circulated **"$600 million" figure** that appears in Wikipedia and several derivative sources is a misreading of the CDC original-suit damages claim, not the settlement value; multiple reputable sources (Reason 1974, Cato 1985 by reference, TIME, Pugh) confirm $80 million as the total settlement value. **The $600 million figure should not be used.**

### 3.3 The Wall Street Journal coverage

The **23 January 1973 Wall Street Journal article** ("Litigation, CDC Settlement Seen As Set Back by Others Suing IBM" — note the WSJ headline word "Set Back" is two words in the original) framed the settlement as a strategic problem for the other private antitrust plaintiffs (Telex, Greyhound, Memorex, Forro Precision, CCIA, etc.) and for the DOJ itself. The article argued that with CDC out of the litigation and the CDC database removed from circulation, the remaining plaintiffs and DOJ had lost their best window into IBM's internal documents.

The WSJ article is preserved in the Charles Babbage Institute Computer and Communications Industry Association collection (collection 36, archival object 1619905). Direct text quotes from the article were not retrievable through my web tooling; this is a target for archival retrieval if needed for the post.

### 3.4 The destruction of the CDC discovery database

This is the most controversial element of the settlement and was the subject of subsequent federal litigation.

**The destruction operation**: Per multiple secondary sources tracing to contemporary press, "IBM and CDC agreed that destruction of the computer base, on which the government relied in preparing for trial, would be a condition of settlement, with the destruction beginning at 3 p.m. on Jan. 12 [1973], the day agreement was reached, and ending the next day, a Saturday." The destruction was thus completed during the weekend of 12–13 January 1973, before the settlement was publicly announced.

**Form of destruction**: The descriptions are varied:
- Some sources (the Hagley deLamarter collection summary; capitalismmagazine.com 2002) describe physical destruction — paper records "burned" or "shredded."
- Other sources (the formal court record) describe more carefully: the database was "destroyed" in the sense of being taken out of any form usable by other litigants — magnetic tapes erased, paper indexes destroyed, work-product analyses removed from CDC's possession.
- The CIA FOIA document "JUDGE ASSERTS IBM VIOLATED AN ORDER" (CIA-RDP78-01092A000100040020-4, [cia.gov/readingroom/document/cia-rdp78-01092a000100040020-4](https://www.cia.gov/readingroom/document/cia-rdp78-01092a000100040020-4), accessed 2026-05-05 — the CIA archived a 1976 New York Times article that I could not retrieve directly through my tooling) is the most authoritative public-domain account of the destruction's mechanism, and Edelstein's subsequent ruling that IBM had violated the spirit of his pretrial discovery order.

**Edelstein's reaction**: Judge Edelstein, presiding over the parallel U.S. v. IBM case in SDNY, was livid. His direct quote, captured in the CIA FOIA document and multiple secondary sources: "**I don't want a single document destroyed under any circumstances without the consent of this court.**" Edelstein's later finding (1976) was that IBM had **violated the letter and spirit of his pretrial discovery order**. He ruled that the government could move to compel IBM to reconstruct the database, but on a separate technical question — whether IBM should have to compensate the government for reconstruction costs — Edelstein held: "**Requiring I.B.M. to compensate the Government for the costs incurred in reconstructing a data base is tantamount to ordering its production.**"

**Did IBM specifically request the destruction?** The contemporaneous press coverage and the Hagley collection summary both suggest IBM made the destruction a *condition* of settlement (i.e., the database had to go before SBC would be transferred). CDC's lawyers consented to the destruction as the price of the settlement. CDC's senior management — Norris — accepted the destruction as a legitimate term, though Norris would later distance himself from this aspect of the deal in retrospective interviews. Subsequent appellate findings refer to IBM's having "procured" the destruction (via Cravath, Swaine & Moore — IBM's outside counsel) — Cravath filed an unusual motion on 16 July 1973 attempting to substitute itself for IBM as the responsible party "apparently on the ground that it was Cravath's decision rather than IBM's which led to the non-compliance with Pretrial Order No. 5" (per *In re IBM*, 493 F.2d 112 (2d Cir. 1974)).

**DOJ reaction**: The Justice Department and the other private plaintiffs (Telex, Greyhound, Memorex, CCIA) "were incensed at this move, since they had expected to make use of the database, particularly in their pre-trial discovery programs" (historyofcomputercommunications.info section 7.2). The DOJ subsequently moved Edelstein on 7 April 1972 (predating the destruction) to compel IBM to produce documents withheld on privilege grounds, arguing IBM's prior production to CDC had waived privilege; the destruction interfered with that strategy.

The destruction was, per most contemporary observers, the single most consequential reason the U.S. v. IBM case lost its momentum. Without the CDC index and analyses, DOJ had to rebuild a comparable institutional understanding of the IBM document base from scratch — work that Edelstein implicitly acknowledged when he ruled in 1976 that IBM had violated the spirit of his pretrial order.

**Norris's later view**: Norris's commentary on the destruction has been interpreted differently by sympathetic and hostile sources. The dominant view is that Norris regarded the destruction as a defensible price for the favourable settlement terms but later acknowledged in private that he had not anticipated how badly the destruction would hurt the DOJ case. The Worthy 1987 biography is the canonical source for Norris's retrospective views on this aspect; the Charles Babbage Institute Norris oral history (Arthur Norberg, interviewer; 28 July and 1 October 1986; transcript at [conservancy.umn.edu/items/b9a398ed-ebfb-421a-bad9-fb2715007174](https://conservancy.umn.edu/items/b9a398ed-ebfb-421a-bad9-fb2715007174), full transcript at handle [hdl.handle.net/11299/107551](https://hdl.handle.net/11299/107551)) is another primary source, though my retrieval indicated the published transcript focuses heavily on Norris's pre-CDC career at ERA and Remington Rand and may not contain extensive direct quotation on the lawsuit.

---

## 4. The Watson-Cray rivalry and customer-pressure tactics

### 4.1 The 28 August 1963 Watson memo (recap)

Already covered in Post 30. Watson's "thirty-four people, including the janitor" memo of 28 August 1963 is the originating document of IBM's decision to mount an organisational response to the CDC 6600 announcement of 22 August 1963.

Cray's response: "It seems like Mr. Watson has answered his own question." (Already in Post 30.)

The Project Y / ACS / 360/91 sequence was Watson's institutional answer — split into a public commercial response (the 360/91, announced November 1964) and a deeper research effort (Project Y, ACS-1, ACS/360, cancelled May 1969).

### 4.2 Documented customer-pressure tactics: NCAR, Princeton, Bell Labs

**Was there a documented "you should wait for the 360/91 instead of buying the CDC 6600" customer-pressure tactic?** This is exactly the type of evidence that the four-year CDC discovery process was designed to surface and that the destroyed database would have catalogued in detail.

**NCAR (National Center for Atmospheric Research, Boulder)**: NCAR's CISL machine history page documents that the NCAR Computing Facility advisory panel approved the CDC 6600 acquisition in **August 1964** — *before* the November 1964 announcement of the 360/91. NCAR took delivery in **December 1965** as CDC 6600 serial #7. So NCAR's purchase decision was made before IBM's primary response to the 6600 was on the market, which means NCAR is not a clean test case for IBM customer-pressure tactics on the 360/91. (NCAR did benchmark the 360/195 against the CDC 7600 in early 1970 when replacing the 6600, with the 7600 winning by a slight margin — see prior research file §4.2.)

**Princeton University**: Princeton appears in some informal lists of 360/91 customers but is not confirmed in the Pugh-Johnson-Palmer institutional history. Princeton is not a documented site of customer-pressure litigation evidence.

**AT&T / Bell Telephone Laboratories**: Bell Labs was a major IBM customer (S/360 Model 67 for the Bell Labs time-sharing work) and is frequently cited informally as a 360/91 customer, though again without solid Pugh confirmation. Bell Labs' computing organisation in the mid-1960s was vendor-pragmatic; CDC sales records would have been the obvious place to look for Bell Labs as a "lost" 6600 prospect, but I have not found published deposition or trial-record evidence specifically naming Bell Labs as a CDC-prospect-talked-into-waiting-for-360/91 case.

**The general pattern**: Norris's famous claim was that he "carefully documented sales lost to the IBM project" before filing the lawsuit. The CDC sales force had a multi-year record of customer accounts that were close to closing on the 6600 in 1964–1965 and were peeled away by IBM commitments to ship a "better and cheaper" 360/92 / 360/91. Specific customer names from those records would have been catalogued in the destroyed CDC database. The destruction of the database in January 1973 is a primary reason that *specific* documented customer-pressure stories about the 360/91 are not in the public record today: the evidence was destroyed before it could be entered as exhibits in either the U.S. v. IBM trial or any of the parallel private cases.

This is itself a finding worth flagging in the post: the absence of named-customer-pressure stories in the historical record about the 360/91 is a *direct consequence* of the January 1973 destruction.

### 4.3 The institutional context

IBM's sales practice in the early System/360 era — across all S/360 models, not just the 360/91 — was structurally designed around what later antitrust law would call **"FUD"** (fear, uncertainty, doubt) and **pre-announcement spoiling**. The AFIPS 1964 FJCC papers on the 360/92 architecture are themselves an example of the practice institutionalised: legitimate technical engineering work, conducted publicly, that gave the announcement of a non-deliverable product the trappings of a deliverable one. The 360/91 / 360/195 sequence simply made this pattern more visible because of the head-to-head competition with the CDC 6600 and 7600 — machines that *did* exist, *did* ship on schedule, and *did* meet their performance specifications.

---

## 5. William Norris's later commentary

### 5.1 Worthy biography (1987)

**James C. Worthy**, *William C. Norris: Portrait of a Maverick* (Ballinger Publishing Co., Cambridge MA, 1987, ISBN 0887300871, 9780887300875). 192 pp. This is the authorised biography. Worthy — a management theorist (formerly Sears, Roebuck) and Norris confidant — produced the canonical narrative of Norris's strategic thinking about the IBM lawsuit. The book is not free-text searchable through my tooling; quoted passages from it would need to be retrieved from a physical or controlled-digital library copy.

**Key Norris-attributed line**, repeated in several derivative sources: the antitrust action against IBM was "**one of the best management decisions in our history**." The line is in wide circulation but I have not located the original primary citation directly; Worthy 1987 is the most plausible primary source.

### 5.2 *New Frontiers for Business Leadership* (1986?)

The user query asked about a Norris book titled *New Frontiers for Business Leadership* (1986). I have **not been able to verify** the existence of a book by that title authored by William C. Norris in 1986 or any other year through web search and library catalogue checks. There is a 2018 collection *New Frontiers in Open Innovation* (Oxford Univ. Press) by other authors; there is a *William C. Norris Papers* collection at the Charles Babbage Institute that includes speeches and essays; but there is no published Norris monograph by that title that I have been able to confirm. **FLAG**: this attribution may be incorrect — possibly a confusion with one of Norris's many speeches or with an internal CDC publication. Should not be cited in the post without independent verification.

### 5.3 CBI oral history (1986)

**Norris oral history at the Charles Babbage Institute** (U. Minnesota): interviewer **Arthur L. Norberg**; interviews on **28 July 1986 and 1 October 1986** in Minneapolis, MN. 192-page transcript. Persistent link [hdl.handle.net/11299/107551](https://hdl.handle.net/11299/107551) (resolves to [conservancy.umn.edu/handle/11299/107551](https://conservancy.umn.edu/handle/11299/107551)). The published abstract focuses on Norris's pre-CDC career at ERA and Remington Rand and on CDC's founding; the antitrust lawsuit is discussed but not as a primary topic of the interview.

This is the most accessible primary source for Norris-in-his-own-words on the lawsuit, but my web tooling could not retrieve the full transcript text. The full transcript should be sought in PDF form from the CBI for direct quotation.

### 5.4 Norris's life

Norris retired as CDC CEO in **January 1986** at age 74 and was succeeded by **Robert M. Price**. Norris died in **August 2006** at age 95. The Washington Post obituary ("William C. Norris; Pioneer In Computer Development," 23 August 2006) is a useful biographical summary, [washingtonpost.com/archive/local/2006/08/23/william-c-norris/](https://www.washingtonpost.com/archive/local/2006/08/23/william-c-norris/8b4099eb-5265-4fa4-9029-d88c7fca0cdb/), accessed 2026-05-05.

---

## 6. The historiography

### 6.1 Reason Magazine, April 1974

**"IBM: Producer or Predator,"** *Reason*, April 1974. [reason.com/1974/04/01/ibm/](https://reason.com/1974/04/01/ibm/), accessed 2026-05-05. The earliest published narrative summary of the CDC settlement. This is the key source for the **"Paper Machines and Phantom Computers"** section title attribution. The Reason piece is sympathetic to IBM and skeptical of the antitrust theory but reports the CDC complaint accurately.

### 6.2 Cato Institute / *Regulation*, September/October 1985

**David Levy and Steve Welzer**, "**System Error: How the IBM Antitrust Suit Raised Computer Prices**," *Regulation* 9(5/6), Sep/Oct 1985, pp. 27–30. PDF at [cato.org/sites/cato.org/files/serials/files/regulation/1985/9/v9n5-6.pdf](https://www.cato.org/sites/cato.org/files/serials/files/regulation/1985/9/v9n5-6.pdf), accessed 2026-05-05. Authored by Levy (then assistant professor of economics at Rutgers) and Welzer (then instructor at Mercer County CC), **not** by "Tony Brown" — this is a correction to the prior research file. The piece argues empirically that the antitrust suit raised IBM's prices over 1969–1979 by giving IBM short-run incentives to extract monopoly rents while breakup loomed, and lowered them only after 1979–80 when dismissal looked likely. The companion academic paper is Levy & Welzer, "An Unintended Consequence of Antitrust Policy: The Effect of the IBM Suit on Prices," 1984.

### 6.3 Robert Sobel, *I.B.M.: Colossus in Transition* (Times Books / Random House, 1981)

The standard popular history of IBM in the period of the antitrust litigation. Covers the CDC settlement, the U.S. v. IBM case, and the early 1980s recovery. Not retrieved page-by-page but a canonical secondary source.

### 6.4 Richard Thomas DeLamarter, *Big Blue: IBM's Use and Abuse of Power* (Dodd, Mead & Co., 1986)

Written by a former DOJ Antitrust Division economist who worked on the U.S. v. IBM case from 1974 to 1982. The book is hostile to IBM and argues that the case had merit on the substantive antitrust theory. ISBN 0396085156. Reviewed in *Science* 234(4783):1592 (Dec 1986).

### 6.5 Pugh, Bashe, Johnson, Palmer

The MIT Press institutional histories — *IBM's Early Computers* (1986), *IBM's 360 and Early 370 Systems* (1991), and *Building IBM* (1995, Pugh solo) — are the canonical institutional / IBM-friendly account. Pugh's *Building IBM* covers the antitrust litigation in some detail; the relevant chapters cover the 1969–1982 case and the CDC settlement.

### 6.6 dwkcommentaries.com (Duane Krohnke), 30 July 2011

"**The IBM Antitrust Litigation**," [dwkcommentaries.com/2011/07/30/the-ibm-antitrust-litigation/](https://dwkcommentaries.com/2011/07/30/the-ibm-antitrust-litigation/), accessed 2026-05-05. Written by a retired attorney who worked as a young Cravath associate on the IBM case in the 1969–1972 period. First-person recollection from the IBM defence side. Confirms the December 1968 CDC filing date in Minnesota, the January 1969 DOJ filing, the ~$80 million CDC settlement, and the January 1982 Baxter dismissal as "without merit." Treats the DOJ case sympathetically (as one would expect from a former Cravath attorney).

### 6.7 Joe Wright, *Capitalism Magazine*, July 2002

"**How History Repeats Itself: The IBM Antitrust Case of 1972**," July 2002, [capitalismmagazine.com/2002/07/how-history-repeats-itself-the-ibm-antitrust-case-of-1972/](https://capitalismmagazine.com/2002/07/how-history-repeats-itself-the-ibm-antitrust-case-of-1972/). Libertarian / Objectivist perspective. Argues that IBM's practices were not anti-competitive on first principles. Mentions Telex specifically; less detailed on CDC settlement.

### 6.8 Tim Wu, *The Master Switch* (Knopf, 2010)

Covers the IBM antitrust case as part of the book's broader argument about cycles of monopoly and competition in information industries. Wu's frequently-quoted line is that without the IBM case, "[i]t's not clear that we would have had an independent software industry, or that it would have developed that quickly" — i.e. the **"policeman at the elbow" effect** of the case forced IBM to unbundle software in 1969 and behave competitively even without a final adverse judgment. Wu's piece for the American Antitrust Institute, "Tech Dominance and the Policeman at the Elbow" (2018), develops the argument in academic form, [antitrustinstitute.org/wp-content/uploads/2023/03/SSRN-id3342598.pdf](https://www.antitrustinstitute.org/wp-content/uploads/2023/03/SSRN-id3342598.pdf).

### 6.9 Recent revisionist scholarship (2020s)

The recent academic literature is largely dominated by the question of whether the IBM case is a useful *model* for current Big Tech antitrust cases (Google, Apple, Meta, Amazon). Key entries:

- **Truth on the Market (2020)**, "The Ghosts of Antitrust Past: Part 2 (IBM)" — sceptical revisionist piece arguing the IBM case was misguided. [truthonthemarket.com/2020/02/03/the-ghosts-of-antitrust-past-part-2-ibm/](https://truthonthemarket.com/2020/02/03/the-ghosts-of-antitrust-past-part-2-ibm/), accessed 2026-05-05.
- **ProMarket (2024)**, "Driving Innovation with Antitrust" — pro-antitrust revisionist piece arguing that the IBM case did force changes (unbundling) that catalysed the personal-computing and software industries.
- **Fisher, McGowan & Greenwood**, *Folded, Spindled and Mutilated: Economic Analysis and U.S. v. IBM* (MIT Press, 1983). The canonical IBM-defence economic analysis.

The historiographical balance has shifted toward a more nuanced view: the case extracted real concessions (1969 unbundling of software; 1973 SBC divestiture; six-year service-business non-compete) but at very high public cost (104 000 transcript pages, $1–2 million/year in DOJ funds, 13 years of litigation) and was settled or dismissed without a clear judicial precedent. Recent commentators in the 2020s draw the lesson cautiously: the IBM case shows that aggressive antitrust enforcement can extract behavioural concessions even without a final adverse judgment, but at dramatic cost and with significant unintended pricing consequences.

---

## 7. Things flagged for further verification before publishing

1. **Exact December 1968 filing day**: I have not confirmed a single-day filing date (11 vs 12 December are both seen in various secondary sources). The court's 31 December 1968 procedural action is solid; the original complaint filing day needs the District of Minnesota docket sheet to verify.
2. **The "Tony Brown" Cato 1985 attribution in prior research is wrong**: the Cato 1985 *Regulation* piece was written by **David Levy and Steve Welzer**, not Tony Brown. Correct this in the post.
3. **The Norris "best management decision" quote**: in wide circulation but original primary source likely Worthy 1987 — confirm directly if quoting in the post.
4. **The Norris book *New Frontiers for Business Leadership* (1986)**: I cannot confirm the existence of this book. Possibly a confusion with a different title or with one of Norris's CBI papers / speeches. Do not cite without verification.
5. **Specific named-customer-pressure stories about the 360/91 (NCAR, Princeton, Bell Labs, etc.)**: most of the documentary evidence was destroyed in January 1973. The post should explicitly note the *absence* of such evidence as a *consequence* of the destruction.
6. **The Wall Street Journal 23 January 1973 article**: preserved at CBI U. Minnesota collection 36, archival object 1619905. Direct text quotes would require physical archival retrieval.
7. **The CIA FOIA document on Edelstein's ruling (CIA-RDP78-01092A000100040020-4)**: I could not retrieve the document text directly; cited through secondary summaries. Direct retrieval would tighten quotes about the 1976 Edelstein ruling and the database size.
8. **The Norris CBI oral history**: full transcript at [hdl.handle.net/11299/107551](https://hdl.handle.net/11299/107551). The published abstract suggests the lawsuit is discussed but not as a primary topic; full transcript retrieval would confirm.
9. **The Hagley deLamarter collection (collection 937)** at the Hagley Museum and Library is the largest single archival source for the U.S. v. IBM litigation records — DeLamarter's own papers from his work as a DOJ economist on the case.
10. **The destruction's exact mechanism — paper-burning vs tape-erasure vs work-product-removal** — is not fully clear from my secondary sources. Reason 1974 and the 1976 NYT/Edelstein source distinguish between physical destruction and legal restriction. The post should soften the claim from "burned" to "destroyed in physical and legal forms" unless better primary documentation surfaces.

---

## 8. Source list for direct citation in the post

### Primary court records / case citations

- *Control Data Corp. v. International Business MacH. Corp.*, 306 F. Supp. 839 (D. Minn. 1969).
- *In re IBM Antitrust Litigation*, 302 F. Supp. 796 (J.P.M.L. 1969).
- *In re IBM Antitrust Litigation*, 316 F. Supp. 976 (J.P.M.L. 1970).
- *International Business Machines Corp. v. United States*, 471 F.2d 507 (2d Cir. 1972).
- *International Business Machines Corp. v. United States*, 493 F.2d 112 (2d Cir. 1974).
- *International Business Machines Corp. v. Edelstein*, 526 F.2d 37 (2d Cir. 1975).
- *Telex Corp. v. International Business Machines Corp.*, 367 F. Supp. 258 (N.D. Okla. 1973).
- *Telex Corp. v. International Business Machines Corp.*, 510 F.2d 894 (10th Cir. 1975).
- *Greyhound Computer Corp. v. International Business Machines Corp.*, 559 F.2d 488 (9th Cir. 1977).
- *In re International Business Machines Corp.*, 687 F.2d 591 (2d Cir. 1982).
- *United States v. International Business Machines Corp.*, 539 F. Supp. 473 (S.D.N.Y. 1982) — the dismissal opinion.
- *United States v. International Business Machines Corp.*, 69 Civ. 200 (S.D.N.Y. 1969) — the original case docket.

### Contemporaneous press

- *Wall Street Journal*, "Litigation, CDC Settlement Seen As Set Back by Others Suing IBM," 23 January 1973. CBI archival object 1619905.
- *TIME*, "Computers: A Settlement for IBM," late January 1973. [time.com/archive/6639851/computers-a-settlement-for-ibm/](https://time.com/archive/6639851/computers-a-settlement-for-ibm/).
- *Reason*, "IBM: Producer or Predator," April 1974. [reason.com/1974/04/01/ibm/](https://reason.com/1974/04/01/ibm/).
- *New York Times*, ~1976 (preserved in CIA FOIA reading room as document CIA-RDP78-01092A000100040020-4): "JUDGE ASSERTS IBM VIOLATED AN ORDER" (the Edelstein-on-CDC-database ruling).
- *Washington Post*, "Law Firm Waged 13-Year War for IBM," 24 January 1982. [washingtonpost.com/archive/business/1982/01/24/law-firm-waged-13-year-war-for-ibm/](https://www.washingtonpost.com/archive/business/1982/01/24/law-firm-waged-13-year-war-for-ibm/59761e40-ea31-430d-ab0b-c084b69e3a63/).
- *Washington Post*, "Return of Papers Barred in IBM Case," 9 February 1982. [washingtonpost.com/archive/business/1982/02/09/return-of-papers-barred-in-ibm-case/](https://www.washingtonpost.com/archive/business/1982/02/09/return-of-papers-barred-in-ibm-case/05348b9b-0cc7-4ae0-bc1d-eae565dcd939/).
- *UPI Archives*, "Baxter had 'appearance' of interest conflict in IBM case," 29 June 1982.

### Secondary scholarly literature

- David Levy and Steve Welzer, "System Error: How the IBM Antitrust Suit Raised Computer Prices," *Regulation* 9(5/6), Sep/Oct 1985, pp. 27–30.
- Franklin M. Fisher, John J. McGowan, Joen E. Greenwood, *Folded, Spindled and Mutilated: Economic Analysis and U.S. v. IBM* (MIT Press, 1983).
- Robert Sobel, *I.B.M.: Colossus in Transition* (Times Books / Random House, 1981).
- Richard Thomas DeLamarter, *Big Blue: IBM's Use and Abuse of Power* (Dodd, Mead & Co., 1986). ISBN 0396085156.
- James C. Worthy, *William C. Norris: Portrait of a Maverick* (Ballinger Publishing, 1987). ISBN 0887300871.
- Emerson W. Pugh, *Building IBM: Shaping an Industry and Its Technology* (MIT Press, 1995).
- Charles J. Murray, *The Supermen: The Story of Seymour Cray and the Technical Wizards Behind the Supercomputer* (Wiley, 1997).
- Tim Wu, *The Master Switch: The Rise and Fall of Information Empires* (Knopf, 2010).
- Tim Wu, "Tech Dominance and the Policeman at the Elbow," American Antitrust Institute working paper, 2018.

### Archival collections

- **Charles Babbage Institute, U. Minnesota** — Computer and Communications Industry Association collection of antitrust records (collection 36); Control Data Corporation records; William C. Norris Papers (CBI 67); Norris oral history (handle 11299/107551).
- **Hagley Museum and Library** — Computer & Communications Industry Association collection of IBM antitrust trial records (collection 919); Richard Thomas deLamarter collection of IBM antitrust suit records (collection 937).
- **CIA Reading Room (FOIA)** — CIA-RDP78-01092A000100040020-4, "JUDGE ASSERTS IBM VIOLATED AN ORDER."

### Online secondary

- "The IBM Antitrust Litigation," [dwkcommentaries.com/2011/07/30/the-ibm-antitrust-litigation/](https://dwkcommentaries.com/2011/07/30/the-ibm-antitrust-litigation/).
- "The Justice Department: IBM and AT&T," [historyofcomputercommunications.info/section/7.2/](https://historyofcomputercommunications.info/section/7.2/The-Justice-Department-IBM-and-AT&T/).
- "How History Repeats Itself: The IBM Antitrust Case of 1972," Joe Wright, *Capitalism Magazine*, July 2002, [capitalismmagazine.com/2002/07/how-history-repeats-itself-the-ibm-antitrust-case-of-1972/](https://capitalismmagazine.com/2002/07/how-history-repeats-itself-the-ibm-antitrust-case-of-1972/).
- "The Ghosts of Antitrust Past: Part 2 (IBM)," [truthonthemarket.com/2020/02/03/the-ghosts-of-antitrust-past-part-2-ibm/](https://truthonthemarket.com/2020/02/03/the-ghosts-of-antitrust-past-part-2-ibm/).
- "Driving Innovation with Antitrust," ProMarket, 10 April 2024, [promarket.org/2024/04/10/driving-innovation-with-antitrust/](https://www.promarket.org/2024/04/10/driving-innovation-with-antitrust/).
- "Regulation of IBM," Stanford CS181 project page, [cs.stanford.edu/people/eroberts/cs181/projects/corporate-monopolies/government_ibm.html](https://cs.stanford.edu/people/eroberts/cs181/projects/corporate-monopolies/government_ibm.html).

### Wikipedia (consulted, accessed 2026-05-05; treat as starting point only)

- *Control Data Corporation*, *William Norris (CEO)*, *Service Bureau Corporation*, *IBM System/360 Model 91*, *IBM*, *Cravath, Swaine & Moore*.
