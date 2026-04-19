# Dorothy Vaughan -- Deep Research

Research compiled 2026-04-19 for the Fortran origins blog post. Focus: separating the historical record from the *Hidden Figures* (2016 film/book) dramatization.

---

## 1. Life and Career Facts

### Birth and Early Life

- **Born:** 20 September 1910, Kansas City, Missouri, to Leonard and Annie Johnson.
- **Mother's death:** Annie Johnson died when Dorothy was two. Her father remarried; stepmother Susan worked as a housekeeper, father Leonard as a waiter.
- **Move to West Virginia:** Family relocated to **Morgantown, West Virginia** when Dorothy was about seven (c. 1917).
- **High school:** Entered **Beechurst High School** at age 11 (1921) after finishing eighth grade. Elected class president. Graduated as valedictorian at age 15.

### Education

- **Wilberforce University** (Wilberforce, Ohio). Full-tuition scholarship from the **West Virginia Conference of the A.M.E. Sunday School Convention**.
- **B.A. in mathematics, 1929** (age 19). Graduated cum laude. Professors encouraged graduate study at Howard University.
- Declined graduate school to help support her family during the Great Depression.

### Teaching Career (1929-1943)

- Taught mathematics at **Robert Russa Moton High School** in Farmville, Virginia (the same school that, two decades later, became famous for the 1951 student strike that fed into *Brown v. Board of Education*).
- Also taught briefly in Tamms, Illinois, and at a school in West Virginia before Moton.

### Marriage and Family

- **Married Howard S. Vaughan in 1932.** Moved to Newport News, Virginia. Lived with Howard's parents on South Main Street.
- **Six children:** Ann, Maida, Leonard, Kenneth, Michael, and Donald.
- Howard Vaughan died in **1955**, while Dorothy was still at NACA.
- One son also later worked at NASA-Langley.

### NACA / NASA Career

- **Hired at NACA Langley Memorial Aeronautical Laboratory: December 1943** (Mathematician, Grade P-1). [Note: user's brief said "June 1943"; all NASA sources say December 1943. The job was initially listed as temporary for the duration of the war.]
- Worked in the segregated **West Area Computing** unit established after Executive Order 8802 (1941) opened defense-industry jobs to Black workers.
- **1949: Became acting head of West Area Computing** after the previous (white) supervisor died. It took **two years** to receive the permanent title -- she was the **first Black supervisor at NACA**, and one of very few female supervisors of any race at the laboratory.
- Led West Area Computing from **1949 to 1958**.
- **1958: NACA became NASA** (1 October 1958). Segregated facilities including West Area Computing were abolished. Vaughan lost her supervisor title when the unit dissolved.
- Joined the new **Analysis and Computation Division (ACD)**, a racially and gender-integrated electronic-computing group. She sought, but **never received, another management title** at Langley.
- Became an expert Fortran programmer within ACD's Numerical Techniques Branch. Contributed to the **Scout Launch Vehicle Program** (a four-stage solid-fuel rocket for launching small satellites).
- **Retired from NASA in 1971** after a 28-year career.

### Retirement and Death

- Retired to Hampton, Virginia. Deeply involved in **St. Paul AME Church in Newport News**, where she was a member for over 50 years, active in the music ministry and missionary work.
- **Died: 10 November 2008, age 98.** Buried at Hampton Memorial Gardens.

---

## 2. The Fortran Story -- Historical Record

### Timeline of Computing at Langley

- **Mid-1950s:** NACA Langley installs an **IBM 650** (drum-memory vacuum-tube machine).
- **March 1957 (verified):** NASA employees are photographed operating an **IBM 704** at Langley Research Center (photo dated 21 March 1957). The 704 was the first mass-produced machine with hardware floating-point arithmetic; Fortran was developed by John Backus's IBM team specifically for the 704 and released in 1957.
- **1958:** NACA becomes NASA. West Area Computing unit dissolved.
- **Early 1960s:** IBM 7090 (transistorized successor to the 704) arrives at Langley. This is the machine depicted in the *Hidden Figures* film delivery scene.
- **1962:** Katherine Johnson famously verifies the IBM 7090's trajectory calculations for John Glenn's Mercury-Atlas 6 flight ("get the girl to check the numbers").

### When Did Vaughan Actually Learn Fortran?

Per Shetterly and NASA's biography, Vaughan **"prepared for the introduction of computers in the early 1960s by teaching herself and her staff the Fortran programming language."** The learning appears to have begun in the late 1950s -- she saw that electronic computers would eventually replace human computers and deliberately retrained to stay relevant.

By the time NASA's larger machines (IBM 7090, 7094) were in full production work, Vaughan was already an experienced Fortran programmer. She programmed for the **IBM 704** and later **IBM 7090**, translating engineers' equations into Fortran and preparing punch cards.

### Her Teaching Role

Vaughan taught Fortran to her staff in the West Area Computing unit **before the unit was dissolved in 1958**, anticipating the transition. This was a deliberate strategy to protect her women's jobs: if they could code the new machines, they would not be replaced by them.

Shetterly frames this as Vaughan making herself and her women **"indispensable"** by mastering the new language. Specific numbers are hard to pin down; one secondary source claims "thirty of her human computers" became the programming team for the IBM mainframe, but this figure is not traceable to a primary source and should be treated with caution.

Known names who learned Fortran through or alongside Vaughan include members of the West Area group who later moved into ACD as programmers. Katherine Johnson later credited Vaughan's group with teaching her Fortran during the Apollo transition.

### After 1958: What She Actually Did

Within ACD's Numerical Techniques Branch:
- Expert Fortran programmer.
- Worked on **Scout Launch Vehicle** orbital mechanics code.
- Headed the programming section of ACD (unofficial technical lead, but never formally re-promoted to a supervisor title equivalent to what she had held in West Area).
- No evidence she taught COBOL or ALGOL -- her later career stayed focused on Fortran on IBM hardware.

---

## 3. What *Hidden Figures* (Film, 2016) Dramatizes or Changes

### The Library Scene

**In the film:** Dorothy Vaughan visits a segregated public library, is ejected from the "whites only" section by a policeman while her two sons watch, and on the bus home reveals she has **stolen** a book -- shown as *Understanding Fortran*.

**Historical issues:**
- The prop book *Understanding Fortran* by Mary McCammon was first published in **1968**, years after Vaughan was already programming in Fortran. The book cannot have been the source.
- Shetterly's book does **not** document Vaughan stealing a Fortran book from a segregated library. The book discusses her learning Fortran but not through a library theft scene.
- The library ejection motif in the film is partly drawn from historical Jim-Crow-era practices and partly compressed from the broader experience of all three women -- particularly **Mary Jackson**, whose career had her fighting for access to segregated educational facilities (she petitioned the city of Hampton to attend night classes at all-white Hampton High School to qualify as an engineer).
- **Verdict: the scene is essentially invented for dramatic compression.** The core fact -- Vaughan taught herself Fortran under segregation -- is true. The specific scene is not.

### The IBM Delivery Scene

**In the film:** An IBM (7090-class) machine is delivered in ~1961. The components won't fit through the doorway. Vaughan races in to save the day.

**Historical issues:**
- Langley had an **IBM 704 running since at least March 1957** -- four years before the film's depicted delivery. The dramatic "first IBM arrives" framing collapses years of gradual computing-center buildout into one scene.
- Vaughan had already been programming IBM machines for years by the time the 7090 arrived.

### Character Amalgamation

The film's "Dorothy Vaughan" is a compression of her real biography plus some narrative beats borrowed from other West Area women. The depicted timeline (everything happens around 1961-1962) flattens a career that actually spanned 1943-1971.

### Supervisor Status

**In the film:** Vaughan is finally promoted to supervisor at the climax, after Mr. Mitchell (the fictional white supervisor) relents.

**Reality:** Vaughan had already been supervisor of West Area Computing since **1949** -- twelve years before the film's action. She **lost** that title in 1958 when the unit was dissolved and **never regained formal supervisory rank**, despite seeking it. The film reverses the direction of her actual career arc on this point.

### The "Colored Ladies Room" Sign Destruction

This scene (Kevin Costner's character smashing a segregated-bathroom sign with a crowbar) is invented. Historians have criticized it as a "white savior" trope. Katherine Johnson herself said she generally used the integrated bathrooms near her desk.

---

## 4. What to Quote in a Blog Post

### On teaching herself Fortran (paraphrase of Shetterly's framing, widely reproduced):

> Vaughan prepared for the introduction of computers in the early 1960s by teaching herself and her staff the Fortran programming language.
> -- NASA biography of Dorothy Vaughan

### On making herself indispensable (Shetterly, *Hidden Figures*, Ch. 20 "Degrees of Freedom"):

The chapter frames Vaughan learning Fortran as a deliberate act of career preservation -- she saw the electronic computers coming for human-computer jobs and chose to **"help control her own fate by learning how to code and therefore making herself indispensable."**

### On loss of supervisor status (Shetterly, paraphrased in multiple secondary sources):

Vaughan **"sought, but never received, another management position at Langley"** after the 1958 integration.

### Usable factual openers for a blog post:

- "In 1949, Dorothy Vaughan became the first Black supervisor at NACA's Langley laboratory, running the segregated West Area Computing unit until it was dissolved in 1958."
- "Fortran was released in 1957. By the early 1960s, Dorothy Vaughan had taught herself the language and was teaching it to her staff -- preparing them for the IBM 704 and 7090 machines that would eventually eliminate their jobs as human computers."
- "The *Hidden Figures* film shows Vaughan stealing a Fortran book from a segregated library. Shetterly's book doesn't document the theft, and the prop book shown (*Understanding Fortran* by Mary McCammon) wasn't published until 1968 -- years after Vaughan was already programming."

---

## 5. Recognition and Honors

- **2019: Congressional Gold Medal** (posthumous), authorized by the *Hidden Figures Congressional Gold Medal Act*. Accepted by family at a September **2024** ceremony alongside medals for Katherine Johnson, Mary Jackson, and Christine Darden (plus one for all women who contributed to NASA during the space race).
- **2019: Lunar crater "Vaughan"** named on the far side of the Moon. Submitted by planetary scientist Ryan N. Watkins on what would have been Dorothy Vaughan's 109th birthday.
- **2017: Dorothy J. Vaughan Academy of Technology** opened in Charlotte, North Carolina.
- **2019: Hidden Figures Way** in Washington, D.C. -- the stretch of E Street SW in front of NASA Headquarters renamed to honor Vaughan, Johnson, Jackson, and the West Area women collectively.
- **July 2024: NASA Johnson Space Center Building 12** (central data office) renamed the **"Dorothy Vaughan Center in Honor of the Women of Apollo."**
- **2005: Music scholarship fund** in her name at the Salem Community Foundation (for music training, reflecting her lifelong church music ministry).

### In Popular Culture

- Margot Lee Shetterly, *Hidden Figures* (2016) -- Vaughan is one of three women foregrounded (with Katherine Johnson and Mary Jackson).
- *Hidden Figures* film (2016) -- portrayed by Octavia Spencer, who received an Academy Award nomination for Best Supporting Actress.

---

## 6. Where Sources Conflict

| Fact | Version A | Version B | Likely correct |
|------|-----------|-----------|----------------|
| NACA hire month | June 1943 (user brief) | December 1943 (NASA bio, Wikipedia, Biography.com) | **December 1943** |
| Number of women Vaughan taught Fortran | "30" (Metaltoad blog) | Unspecified (Shetterly, NASA) | Unknown; "30" is not traceable to a primary source |
| Age at Beechurst High School graduation | 15 | Unclear in some sources | 15 (consistent across most sources) |
| When Vaughan lost supervisor status | 1958 when West Area dissolved | Implied ongoing in some summaries | 1958 (NASA biography is clear) |
| Whether library scene is historical | Film depicts it as fact | Shetterly's book does not document it | Dramatized for the film |

---

## 7. Sources (all accessed 2026-04-19)

### Primary / Authoritative

- [Dorothy J. Vaughan -- NASA Langley biography](https://www.nasa.gov/centers-and-facilities/langley/dorothy-j-vaughan/)
- [Dorothy Vaughan -- NASA People](https://www.nasa.gov/people/dorothy-vaughan/)
- [From Computers to Leaders: Women at NASA Langley -- NASA](https://www.nasa.gov/general/from-computers-to-leaders-women-at-nasa-langley/)
- [Dorothy Vaughan's Retirement Party, 1971 -- NASA image](https://www.nasa.gov/image-article/dorothy-vaughans-retirement-party-1971/)
- Shetterly, Margot Lee. *Hidden Figures: The American Dream and the Untold Story of the Black Women Mathematicians Who Helped Win the Space Race* (William Morrow/HarperCollins, 2016). Especially **Chapter 20, "Degrees of Freedom."**

### Biographical

- [Dorothy Vaughan -- Wikipedia](https://en.wikipedia.org/wiki/Dorothy_Vaughan)
- [Dorothy Johnson Vaughan -- Biography.com](https://www.biography.com/scientists/dorothy-johnson-vaughan)
- [Dorothy Johnson Vaughan (1910-2008) -- BlackPast.org](https://blackpast.org/african-american-history/vaughan-dorothy-johnson-1910-2008/)
- [Dorothy Vaughan -- e-WV (West Virginia Encyclopedia)](https://www.wvencyclopedia.org/entries/2429)
- [Dorothy Vaughan -- Britannica](https://www.britannica.com/biography/Dorothy-Vaughan)
- [Dorothy Vaughan -- Biographies of Women Mathematicians, Agnes Scott College](https://mathwomen.agnesscott.org/women/vaughan.htm)
- [Dorothy Vaughan -- AWIS](https://awis.org/historical-women/dorothy-vaughan/)

### Hidden Figures Context and Film Accuracy

- [Hidden Figures (book) -- Wikipedia](https://en.wikipedia.org/wiki/Hidden_Figures_(book))
- [Hidden Figures -- Wikipedia (film)](https://en.wikipedia.org/wiki/Hidden_Figures)
- [Hidden Figures Chapter 20: Degrees of Freedom -- LitCharts](https://www.litcharts.com/lit/hidden-figures/chapter-20-degrees-of-freedom)
- [A closer look at the library scene in 'Hidden Figures' (2016) -- Reel Librarians](https://reel-librarians.com/2021/03/10/a-closer-look-at-the-library-scene-in-hidden-figures-2017/)
- [Hidden Figures: Laudable Liberties -- An Historian Goes to the Movies](https://aelarsen.wordpress.com/2017/02/12/hidden-figures-laudable-lies/)
- [Hidden Figures Movie vs the True Story -- History vs. Hollywood](https://www.historyvshollywood.com/reelfaces/hidden-figures/)
- [Charles Petzold: Reading Margot Lee Shetterly's "Hidden Figures"](http://www.charlespetzold.com/blog/2016/09/Reading-Margot-Lee-Shetterly-Hidden-Figures.html)

### Recognition

- [SWE Honors Hidden Figures Congressional Gold Medal Awardees](https://alltogether.swe.org/2019/12/swe-honors-hidden-figures-congressional-gold-medal-awardees/)
- [Dorothy J. Vaughan Academy of Technology -- Charlotte-Mecklenburg Schools](https://www.cmsk12.org/post-details/~board/academic-excellence/post/dorothy-j-vaughan-academy-of-technology-52955-20504)
- [NASA marks moon landing anniversary by dedicating building to 'women of Apollo' -- collectSPACE](https://www.collectspace.com/news/news-071924a-johnson-space-center-dorothy_vaughan_women_apollo.html)
- [The Dorothy Vaughan Center in Honor of the Women of Apollo -- NASA JSC Roundup](https://roundupreads.jsc.nasa.gov/roundup/2404)

### Computing Context

- [IBM 704 -- Wikipedia](https://en.wikipedia.org/wiki/IBM_704)
- [IBM 7090 -- Wikipedia](https://en.wikipedia.org/wiki/IBM_7090)
- [NASA employees with IBM 704, Langley, 21 March 1957 -- Alamy / NASA photo](https://www.alamy.com/nasa-employees-working-with-ibm-type-704-electronic-data-processing-machine-used-for-making-computations-for-aeronautical-research-at-langley-research-center-in-hampton-virginia-march-21-1957-image-courtesy-national-aeronautics-and-space-administration-nasa-image245270588.html)
- [Hidden Figures No Longer -- Computer History Museum](https://computerhistory.org/blog/hidden-figures-no-longer/)

---

## 8. Key Takeaways for the Fortran Blog Post

1. **Vaughan really did teach herself Fortran**, likely starting in the late 1950s, and did teach it to her staff -- this is the core true fact the film is built around.
2. **The library theft scene is invented.** Don't repeat it as fact. Instead, emphasize that she taught herself under segregation-era constraints on library access, professional development, and bathroom facilities.
3. **The IBM 704 was at Langley from 1957**, not 1961. Vaughan was already programming it well before the film's dramatic "new IBM arrives" scene.
4. **She lost her supervisor rank in 1958.** The film inverts this: it shows her finally winning a promotion, when in reality she was fighting to recover status she had already held for nearly a decade.
5. **She was 48 when she learned Fortran** -- a midcareer retraining story, not a youthful ambition story. This is a particularly strong narrative angle for a weekend-read blog.
6. **Fortran (released 1957) was the first high-level language that engineers would actually use.** Vaughan's West Area women learning it was a piece of the broader shift from human computers to computer programmers that Fortran enabled.
