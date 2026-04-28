---
layout: single
title: "The Machine That Built IBM"
date: 2026-04-10 08:00:00 +0100
categories: [Weather, HPC, History]
tags: [IBM701, Watson, Rochester, Haddad, Oppenheimer, Cressman, Shuman, Samuel, Dostert, Backus, JNWPU, Computing]
header:
  teaser: /assets/images/header-ibm701.jpg
  overlay_image: /assets/images/header-ibm701.jpg
  overlay_filter: "0.6"
excerpt: "In a Poughkeepsie tie factory with tar dripping from the roof, 150 engineers built the machine that transformed IBM from a punch-card tabulator company into the company that defined computing. It ran the first machine translation, the first machine learning program, and the first operational weather forecast in the United States. Almost everyone has forgotten it."
---

In the summer of 1951, in a former necktie factory on the third floor of a building in Poughkeepsie, New York, about 150 engineers were building the machine that would change IBM forever.

The roof leaked. On hot days, tar dripped down onto their drawings. "We had to scrape it off to keep working," remembered project manager Clarence Frizzell.[^1] Jerrier Haddad, the managing engineer, later joked: "Maybe that's why we did things so fast. We didn't have schedules to slow us down."[^1]

They were building something IBM had never sold before. Not a punch-card tabulator. Not a room-filling accounting machine. A real, stored-program, electronic computer. Inside the company they called it the **Defense Calculator**. To the outside world it would become the **IBM 701**.

Only nineteen of them were ever built. Most have long since been scrapped. A single Williams tube from one of them sits in a display case at the Computer History Museum in Mountain View. There are no complete survivors.

And yet, in the roughly five years it was in active service, the 701 ran the **first machine translation demonstration** in history. It ran the **first machine learning program**. It ran the **first operational numerical weather forecast in the United States**. It turned IBM from a punch-card company worth $200 million a year into the company that dominated global computing for the next 40 years.

This is the story of the machine that built IBM.

---

## Before the 701: IBM's Electronic Problem

To understand the 701, you have to understand what IBM was *before* it.

In 1950, IBM sold punch-card tabulators. Electromechanical machines with clattering metal parts, driven by nine-decade-old technology that dated back to Herman Hollerith's 1890 census machines. They were good machines. They made IBM a lot of money. They were also obsolete.

**Thomas J. Watson Sr.** -- founder, chairman, and god-emperor of IBM -- had been born in 1874, and he had built the company on the gospel of relationship-based tabulator leasing. His sales force was trained to sell service, reliability, and IBM's famous "THINK" culture. They wore dark suits. They did not understand vacuum tubes, and they did not want to.

When the ENIAC was unveiled in 1944, Watson Sr. was furious. He convened his top engineers and demanded that IBM build "a better machine within eight months." The result was the **Selective Sequence Electronic Calculator (SSEC)** of 1948 -- a one-off hybrid of electromechanical and electronic parts, installed behind a big plate-glass window at IBM's headquarters on Madison Avenue, where passers-by could gawk at the flashing lights. It was a publicity stunt, not a product.

A year earlier, in 1947, Watson Sr.'s old rivals **J. Presper Eckert** and **John Mauchly** -- the builders of ENIAC -- had won a contract from Prudential to build them a computer. IBM's internal project to respond died because Watson Sr. refused to approve magnetic-tape storage. His son, **Thomas Watson Jr.**, wrote later in his autobiography *Father, Son & Co.*: "My father initially thought the electronic computer would have no impact on the way IBM did business, because to him punch-card machines and giant computers belonged in totally separate realms."[^2]

But Watson Jr. -- born 1914, MIT-educated, a wartime bomber pilot -- saw what his father could not. He saw that electronic computing was not going to be a sideshow. It was going to be everything. And he was about to get the chance to prove it.

That chance came from Korea.

---

## The Korean War and the Defense Calculator

On June 25, 1950, North Korean forces crossed the 38th parallel, and the Korean War began. Following the IBM tradition of patriotic mobilization established in both world wars, Watson Sr. and Watson Jr. immediately offered the company's facilities to the federal government.

The government's answer was not what the Watsons expected. Washington did not want more punch-card tabulators. **They wanted electronic computers.** Specifically, they wanted machines for "aircraft design, nuclear development and military manufacturing" -- the kind of work that ordinary tabulators could not handle at Cold War speeds.

Watson Jr. dispatched two lieutenants to find out exactly what defense agencies needed. **James Birkenstock**, head of IBM's Future Demands department, and **Cuthbert Hurd**, director of the Applied Science Division (an Oak Ridge mathematician Watson Jr. had hired in 1949), spent the second half of 1950 touring some 22 labs and contractors, from the National Security Agency to Boeing to General Electric. They came back with a bold recommendation: IBM should build a general-purpose scientific computer, fund it internally, and keep the patents.

Birkenstock's pitch, as he later remembered it:

> "It dawned on us that while all of them had different requirements they varied not that much. Probably one scientific computer wouldn't answer one hundred percent of the problems of each agency, but it would solve ninety percent of them. I was particularly anti doing anything that required giving away all our rights and data to the government and not having a solid patent position. I said to Tom, 'Why not build a production lot with IBM's own money?' Tom said it was a big gamble; a three-million-dollar gamble seemed awfully big."[^3]

Three million dollars a year. Ten times the cost of the SSEC. **The most expensive single project in IBM's history.**

Watson Jr. signed off in January 1951. The internal name was carefully chosen: **Defense Calculator**. It was political cover. Wrapping the project in the flag made it harder for the punch-card old guard and the cost-conscious finance people to kill it. IBM's own Product Planning Department fought the decision all through 1950. Hurd later complained: "They told me throughout 1950 that no computer could ever be marketed at a price of more than $1,000 per month."[^3] The Defense Calculator would need to rent for eight or fifteen times that.

Watson Jr. sided with Hurd and Birkenstock against his own planners. His reasoning, which he later quoted to anyone who asked:

> "We thought in those early days that we either had to win this one or fail as a company -- and that's why I think everybody put such effort into it."[^2]

Win or fail. No middle ground.

---

## The Tie Factory

Construction began in February 1951, in IBM's **Poughkeepsie electronics laboratory**, housed in a former Kenyon Neckwear Company factory that IBM had taken over during World War II for munitions work. The third floor was given over to the Defense Calculator team. It started with a handful of engineers. Within a year it had 150.

![The IBM 701 Electronic Data Processing Machine. Roughly 10 tons of vacuum tubes, Williams tubes, and magnetic drums, designed to fit through ordinary doors. Photo: IBM Archives via Wikimedia Commons (CC BY-SA 2.0).](/assets/images/IBM_701_frame.jpg)

The chief architect was **Nathaniel Rochester** (1919-2001), an MIT-trained electrical engineer who had spent World War II at the MIT Rad Lab working on radar. He had joined IBM in 1948 and was, by all accounts, one of the most practical people in the building. Alongside him, **Jerrier Haddad** served as managing engineer, with **Ralph Palmer** overseeing the whole Poughkeepsie electronics operation. Rochester would design the arithmetic unit (for which he later received IBM's Outstanding Invention Award) and write the first symbolic assembler the machine ever had. Haddad kept the schedule, organized the team, and made sure the pieces fit together.

The machine they built was, for its time, enormous. Ten tons. 1071 vacuum tubes. 36-bit words. Two programmer-accessible registers: a 38-bit Accumulator (with two overflow bits) and a 36-bit Multiplier-Quotient. A 33-instruction set with single-address format. No hardware floating point. No index registers. You had to modify your own code on the fly to index arrays -- a practice that would give every early IBM programmer nightmares.

For memory, the team chose **Williams tubes** -- cathode-ray tubes repurposed as electrostatic memory, each tube storing 1024 bits as patterns of charge on its phosphor face. Rochester's deputy Philip Fox had been studying Williams tubes since 1948, so IBM already had the in-house expertise. The final 706 Electrostatic Storage Unit held 72 Williams tubes of 3-inch diameter, giving the machine 2048 words of 36 bits -- about 9 kilobytes in modern terms. Memory cycle time was 12 microseconds. Every add instruction took five cycles, and two of them were pure refresh overhead to keep the Williams tube bits from fading away.

![A Williams tube from an IBM 701. Each 3-inch CRT stored 1024 bits as patterns of charge on its phosphor face. 72 of these tubes together provided the 701's entire main memory: 2048 words, roughly 9 kilobytes. Photo: Computer History Museum via Wikimedia Commons (CC BY-SA 3.0).](/assets/images/Williams_tube.jpg)

**John von Neumann** -- whose Princeton IAS machine was the direct architectural ancestor of the 701 -- weighed in with one crucial piece of advice: add a magnetic drum for secondary storage. He had seen the I/O bottleneck on his own machine, and he knew the 701 would hit the same wall. IBM listened. The result was the **IBM 731 Magnetic Drum Reader/Recorder**, one of the first drum storage units in commercial computing.

Another critical design decision: every component box was sized so that it would **fit through an ordinary door and into a standard elevator**. This sounds trivial. It was not. Early computers were shipped in pieces so large they had to be hoisted through specially cut holes in ceilings, lowered into basements by crane. The IBM 701 could be delivered through the front lobby of any office building in the United States. This made it dramatically easier to sell.

The machine was designed to be manufacturable. Smith Holman, the Poughkeepsie factory general manager, told production manager Richard Halen in 1952: "Layout the department so it looks like a manufacturing set-up. It's the first one in the world... I can't tell you how to do it. But customers will be coming to visit us, so you've got to make it look like we know how to build computers."[^1]

They did. Eventually.

---

## Five Orders, Eighteen Orders

Before IBM committed to production, Watson Jr. did something no one at IBM had ever done before. He took the machine -- which did not yet exist except on paper -- on a sales trip.

In late 1951 and early 1952, Watson Jr., Hurd, and a small team drove and flew around the country visiting prospective customers. They had a "paper plan" of the Defense Calculator and a price list. In March 1951, the engineering team had finalized the detailed design and discovered that the original target rental of $8000 per month was nowhere near production cost. The price had to be raised to **$15,000 per month** -- almost double. Watson Jr. went to re-qualify customers at the new price.

About 20 companies made the itinerary: Los Alamos, Lockheed Glendale, Douglas Santa Monica and El Segundo, Convair Fort Worth, Boeing Seattle, North American Aviation, United Aircraft East Hartford, RAND Corporation, General Electric Lockland, and the Naval Ordnance Test Station at Inyokern. Watson Jr. expected that the price doubling would cost them customers. He hoped for five firm orders.

He got eighteen.

He described the moment a year later, at the IBM annual stockholders' meeting on April 28, 1953:

> "IBM had developed a paper plan for such a machine and took this paper plan across the country to some 20 concerns that we thought could use such a machine. As a result of our trip, on which we expected to get orders for five machines, we came home with orders for 18."[^4]

Watson Jr. later admitted, in *Father, Son & Co.*, that he was in "total amazement." As he put it: **"Customers wanted computers so badly that we could double the price and still not drive people away."**[^2]

The "five, eighteen" line is the real origin of one of computing's most famous misquotations. The apocryphal line "I think there is a world market for maybe five computers," attributed for decades to Thomas Watson Sr., has never been found in any contemporary source. Wikipedia's IBM 701 article makes the correction explicit: the misquote almost certainly stems from **Watson Jr.'s 1953 remark about the sales trip**, garbled and back-projected onto his father. Watson Sr. never predicted anything about the computer market. His son did -- and he got it hilariously wrong in the other direction.

A 19th order was later added from DuPont Central Research in Wilmington. The final customer list was, unsurprisingly for a machine called the Defense Calculator, dominated by defense and aerospace: 19 units, 15 of them at military contractors, weapons labs, or the Department of Defense. Only four commercial customers: GE, GM, DuPont, and IBM itself.

The 701 was going into production.

---

## April 7, 1953: Oppenheimer Blesses the Machine

![Thomas J. Watson Jr., Brown University photo, 1937. He became IBM President in January 1952 and bet the company on the 701. "We thought in those early days that we either had to win this one or fail as a company." Public domain via Wikimedia Commons.](/assets/images/Watson_Jr.jpg)

The first IBM 701 was installed at IBM's own World Headquarters at 590 Madison Avenue in New York in late December 1952, in the ground-floor space previously occupied by the SSEC. The first customer shipment went to **Los Alamos in early April 1953** -- the very lab von Neumann and Metropolis had pioneered computational nuclear physics at.

Four days after the Los Alamos delivery, on **April 7, 1953**, IBM held a dedication luncheon at 590 Madison. Roughly 150 of the top scientists, industrialists, and government officials in America attended.

The principal speaker was **J. Robert Oppenheimer**.

The timing is almost unbearably poignant. In April 1953, Oppenheimer was still Director of the Institute for Advanced Study at Princeton. He was still the "father of the atomic bomb," still the most famous scientist in America, still a trusted advisor to presidents. His security clearance was intact. He was still, in the phrase of his biographers, in establishment grace.

He had exactly eight months left. On **December 21, 1953**, the Atomic Energy Commission would suspend his security clearance. The infamous hearings would begin in April 1954, and on **June 29, 1954** -- 14 months and 22 days after the IBM 701 dedication -- his clearance would be permanently revoked, ending his career as a public servant and leaving him a broken man.

But on April 7, 1953, he stood in the ground floor of IBM World Headquarters, in front of the machine that had been directly inspired by his own Institute's computer in Princeton, and he gave what would be the most famous single sentence ever spoken about the IBM 701.

He called the 701 **"a tribute to the mind's high splendor."**[^5]

Herman Goldstine, who had been a principal architect of the IAS machine and who was in the room, preserved the quote in his 1972 book *The Computer from Pascal to von Neumann*. It is the only statement Oppenheimer ever made about the IBM 701 that has survived. Four days after it was said, on April 11, the first customer 701 was fully operational at Los Alamos. Seven months later, Oppenheimer was on his way out.

The IAS machine had begat the 701. The IAS director had blessed the product. The circle was complete.

---

## Programming the Beast: Backus and Speedcode

There was one problem with the beautiful new machine. It was almost impossible to program.

The 701 had 33 instructions. No floating point. No index registers. If you wanted to index into an array, you had to write self-modifying code -- literally rewrite your own program while it was running, to change the address field of the next instruction. For a scientific computer aimed at physicists, aerodynamicists, and nuclear weapons designers, this was a disaster. These were people who thought in floating-point arithmetic and multidimensional arrays, not in 18-bit machine codes and Williams tube addresses.

**John Backus** -- a 28-year-old IBM programmer who had joined the Scientific Computing Service -- started thinking about the problem in late 1952. In January 1953, just as the first 701s were shipping, he began a project called **Speedcode**. Working with five colleagues -- **Harlan Herrick**, **Donald Quarles Jr.**, **Sherwood Skillman**, **John Pulos**, and **Lucy Siegel** -- he built a software layer that made the 701 *behave* like a three-address floating-point machine with built-in index registers.

Speedcode gave you what the hardware refused to: floating-point add, multiply, and divide. Sine, arc tangent, exponential, logarithm, and square root as pseudo-instructions. Three virtual "B-tube" index registers (RA, RB, RC) that handled address modification automatically. It ran about 10 to 20 times slower than native 701 machine code, but it made programs that would have taken weeks to write possible in days.

Backus presented Speedcode at the ACM meeting in September 1953 and published the paper in the *Journal of the ACM* the next year. His key economic argument -- one of the first defenses of high-level programming languages ever made -- was a single sentence that explains why software ate the world:

> "Programming and testing cost often comprise between 50 and 75% of the total cost of operating a computing installation. Since Speedcoding reduces coding and testing time considerably, and is fairly fast in operation, it will often be the more economical way of solving a problem."[^6]

Backus was just getting started. Three years later, on the 701's successor the **IBM 704** -- which would finally have hardware floating-point and real index registers -- he would lead the team that built **FORTRAN**, the language that made scientific computing possible for the next 70 years.

But the first lesson, the one that made FORTRAN inevitable, was learned on the 701.

---

## The 701 as Showcase: Three Firsts

Because the 701 was expensive, because it was the first serious scientific computer IBM had sold, and because IBM desperately needed the machine to succeed, it became a kind of public demonstration theater. If you wanted to show the world what a computer could do, you showed it on a 701.

Three of these demonstrations went on to define entire fields of computer science. All three, in their first years, were disappointing. All three, in the long run, were world-changing.

---

### First #1: The Machine That Learned (1952-1956)

**Arthur Samuel** was born in Emporia, Kansas, in 1901. By 1950 he had been around: MIT master's degree (1926), Bell Labs (1928-1946), University of Illinois (1946-1949), and finally IBM Poughkeepsie (1949-1966). At Illinois he had briefly been associated with the early **ILLIAC** project. At IBM, he fell in love with the 701.

He had been thinking about computer game-playing since 1948, when he attended a talk by **Claude Shannon** on computer chess and left convinced -- mistakenly -- that Shannon had already built a working chess machine. ILLIAC was not ready in time for him to use it, so he came to IBM.

Samuel wanted to write a chess program. He chose checkers instead. The rules were simpler, the branching factor smaller, the board state fit comfortably in the 701's 2048 words of memory. More importantly, checkers had enough strategic depth to let him focus on what he really wanted to study: **learning**.

He began coding in 1952. The first version was working by 1955. And on the morning of **February 24, 1956**, IBM broadcast a live television demonstration on one of the morning news programs. Samuel was in Poughkeepsie at the 701. The TV host, Will Rogers Jr., was in the studio with a checkers expert who played against the machine for about an hour via remote connection.

Thomas Watson Sr. himself -- in the last months of his life; he would die that June -- had arranged for shareholders to watch the broadcast. He predicted beforehand that the demonstration would push IBM stock up 15 points. **The stock rose 15 points overnight.** This was, arguably, the first public television demonstration of what we now call artificial intelligence.

What did Samuel's program actually do? Two things no computer had ever done before. **Rote learning**: the program memorized every board position it had ever seen together with the minimax value computed from it, so that re-encountered positions came with free "look-ahead" built in. **Generalization learning** (the 1959 breakthrough): the program played against itself -- an "Alpha" side using the current weights, a "Beta" side using fixed reference weights -- and adjusted Alpha's weights based on the difference between its predictions and the values of deeper searches.

Richard Sutton, the modern father of reinforcement learning, would later credit Samuel's 1959 paper as the first implementation of **temporal-difference learning** -- the technique that would, 60 years later, power AlphaGo and AlphaZero. Samuel's 1959 IBM Journal paper, *"Some Studies in Machine Learning Using the Game of Checkers,"* is also the paper where the term **"machine learning"** enters the written record.

The most famous quote attributed to Samuel -- "the field of study that gives computers the ability to learn without being explicitly programmed" -- does not appear verbatim in any of his writings. It is a universally-cited paraphrase. The actual sentence from his 1959 paper is more cautious and more important:

> "Enough work has been done to verify the fact that a computer can be programmed so that it will learn to play a better game of checkers than can be played by the person who wrote the program."[^7]

A computer that learns to play better than its programmer. That was the 701, in 1956.

The 701 was not quite up to the task of reaching master-level play. In 1962, on the much more powerful IBM 7094, Samuel's program played a match against **Robert Nealey**, whom IBM press materials described as a checkers master. The program won the game. IBM's marketing department had a field day. In reality, Nealey was not a master at all -- he would not win the Connecticut state championship until 1966, four years later -- and when Samuel's program played actual world-class players **Walter Hellman** and **Derek Oldbury** in 1966, it lost **all eight games**. That result was not publicized.

The hype of 1962 and the rout of 1966 are a template for every AI cycle since. But the underlying science was real. And it started on an IBM 701 in Poughkeepsie.

---

### First #2: The Translation That Wasn't (January 7, 1954)

Eleven months after Oppenheimer blessed the 701, IBM's ground-floor showroom at 590 Madison Avenue played host to another demonstration. This one drew dozens of reporters from newspapers, magazines, and the new medium of television.

The date was **January 7, 1954**. The machine was an IBM 701. The cast at the console: **Cuthbert Hurd** of IBM Applied Science, **Thomas J. Watson** (Sr., making one of his last public appearances), **Peter Sheridan** (the IBM mathematician who had written the 701 program), **Paul Garvin** (the linguist from Georgetown University), and -- the real star of the show -- **Léon Dostert**.

![Léon Dostert (far right) at the Nuremberg trials, 1946. He had been Eisenhower's interpreter, invented the simultaneous-interpretation booth system still used at the United Nations, and in 1954 staged the first public demonstration of machine translation. Public domain photo via Wikimedia Commons.](/assets/images/Dostert_Nuremberg.jpg)

Dostert's life reads like a pulp novel. He had been born in 1904 in Longwy, France, near the Belgian border. Occupied by Germans during World War I, he worked as an interpreter for both sides as a teenager. Orphaned, sponsored by American GIs, he emigrated to Pasadena in 1921 and eventually earned degrees at Occidental College and Georgetown. During World War II he rose to Colonel in the U.S. Army and became personal interpreter to **General Dwight D. Eisenhower**. When de Gaulle decorated Eisenhower at the Arc de Triomphe in June 1945, it was Dostert who translated Eisenhower's speech. At the Nuremberg trials of 1945-1946, Dostert designed the **simultaneous-interpretation booth system** -- interpreters in sound-insulated booths translating in real time through headsets into English, French, German, and Russian. That system is still the standard at the United Nations, the European Parliament, and the European Commission. It is his most enduring invention.

In 1949, Georgetown invited Dostert to found the Institute of Languages and Linguistics. He accepted. And when **Warren Weaver** -- Vice President of the Rockefeller Foundation and one of the founding figures of information theory -- wrote his famous July 1949 memorandum proposing that machine translation was theoretically possible, Dostert decided to make it happen.

On January 7, 1954, in front of dozens of reporters at 590 Madison, he did.

An operator who did not know a single word of Russian sat at the keypunch. She was handed Russian sentences transliterated into the Latin alphabet. She punched them onto IBM cards. The cards went into the 701. Moments later, the high-speed line printer output English translations at **two and a half lines per second** -- about 80 characters every two seconds.

The three sentences that would be reproduced in every newspaper the next morning were:

- **"Mi pyeryedayem mislyi posryedstvom ryechyi."** → "We transmit thoughts by means of speech."
- **"Vyelyichyina ugla opryedyelyayetsya otnoshyenyiyem dlyini dugi k radyiusu."** → "Magnitude of angle is determined by the relation of length of arc to radius."
- **"Myezhdunarodnoye ponyimanyiye yavlyayetsya vazhnim faktorom v ryeshyenyiyi polyityichyeskix voprosov."** → "International understanding constitutes an important factor in decision of political questions."

More than 60 sentences were translated in total, across seven fields: politics, law, mathematics, chemistry, metallurgy, communications, and military affairs. The *New York Times* ran the story on the front page the next day, January 8, 1954: **"Russian is turned into English by a fast electronic translator."** The *Christian Science Monitor* headline was **"Robot translates nimbly."** The *Jamestown Post-Journal* simply said **"Electronic Brain Translates."**

Here was the trick. The system used a vocabulary of **250 words** and **six grammar rules**. That was it. The rules were mechanical operations on integer-coded dictionary entries: Rule 1 (reverse word order in some cases), Rule 2 (pick English equivalent I or II based on following word code), Rule 3 (same but with rearrangement), Rule 4 (choose based on preceding word), Rule 5 (insert an English word with no Russian counterpart), Rule 6 (drop a Russian word without translation). There was no morphological analyzer. No parser. No understanding of meaning in any form. It was, as the historian **John Hutchins** later put it, "a clever proof-of-concept engineered to make the 701 look miraculous to reporters."[^8]

And yet the hype was enormous. Dostert himself, quoted in the IBM press release of January 8, 1954, made a prediction that would follow him for the rest of his life:

> "Five, perhaps three years hence, interlingual meaning conversion by electronic process in important functional areas of several languages may well be an accomplished fact."[^9]

Five years. Three years. Maybe.

Behind the scenes, the project had a patron the press never mentioned. Historian **Michael Gordin** (Princeton) discovered from declassified records that **the CIA was funneling money to Georgetown's machine translation program through the National Science Foundation**. Of $411,000 in NSF awards to Georgetown between 1956 and 1958, $305,000 came from CIA funds. After 1958, the CIA paid Georgetown **directly** -- $1,314,869 in the years that followed, over $9.7 million in 2014 dollars. Georgetown's machine translation program became the largest MT effort in the world, and the CIA paid for most of it. They wanted Russian scientific literature translated. After Sputnik in 1957, they wanted it desperately.

And then, twelve years later, it all collapsed.

In November 1966, the **Automatic Language Processing Advisory Committee (ALPAC)**, chaired by Bell Labs executive **John R. Pierce**, published a report titled "Language and Machines: Computers in Translation and Linguistics." It was devastating. The committee concluded that "we do not have useful machine translation and there is no immediate or predictable prospect of useful machine translation."[^10] It singled out Georgetown for still requiring heavy human post-editing after eight years of funding. It recommended that federal money be redirected away from end-to-end MT and toward human translator tools.

U.S. government machine translation funding **collapsed for roughly twenty years**. Dostert had already left Georgetown -- the CIA cut its funding in 1963, and he went back to his alma mater at Occidental College. The first AI winter, when it came in the early 1970s, had already begun for machine translation in 1966.

But the sentence "We transmit thoughts by means of speech" had been printed by an IBM 701 on January 7, 1954. And everything that followed -- statistical machine translation in the 1990s, neural machine translation in the 2010s, the large language models of today -- can trace its public debut to that moment at 590 Madison Avenue.

---

### First #3: The Forecast That Was Disappointing (May 6, 1955)

![George Parmley Cressman (1919-2008), first Director of the Joint Numerical Weather Prediction Unit. Trained under Carl-Gustaf Rossby at the University of Chicago, he led the JNWPU from 1954 to 1964 and later headed the National Weather Service. NOAA portrait, public domain.](/assets/images/Cressman_portrait.jpg)

On **July 1, 1954**, in a plain government office building in Suitland, Maryland, the **Joint Numerical Weather Prediction Unit (JNWPU)** was established by order of the Joint Chiefs of Staff. It was staffed equally by three agencies -- the civilian **U.S. Weather Bureau**, the **Air Weather Service** (U.S. Air Force), and the **Naval Weather Service** (U.S. Navy) -- each with its own bureaucratic ambitions for operational numerical weather forecasting.

The compromise director was **George Parmley Cressman**, a civilian meteorologist who had studied under **Carl-Gustaf Rossby** at the University of Chicago and worked on weather predictions for the Nevada atomic bomb tests. Cressman was 34 years old when he took the job. He would lead the JNWPU for a decade, then run the National Weather Service itself from 1965 to 1979. Along the way he would invent the **Cressman objective analysis method** (1959), the technique for turning irregularly scattered weather observations into regular grid fields -- a foundational step in modern data assimilation.

The JNWPU was located in **Federal Office Building 4** at the Suitland Federal Center, a building that had been completed in 1947 at a cost of $2,327,280. It would house America's operational weather computing from 1954 until 1999. Suitland was not glamorous. It was bureaucratic, beige, government-issue, a few miles south of the Anacostia River.

In early 1954, the Joint Chiefs had commissioned a comparative trial between the **IBM 701** and the **Remington Rand UNIVAC 1103** for the new unit's computer. The machines were roughly comparable in computational speed, with a slight advantage to the 701. The decisive factor was **I/O speed**: weather forecasting requires ingesting thousands of teletype observations, running them through the model, and outputting charts for distribution, and the 701's faster card readers and printers made it the practical choice. The contract went to IBM. The JNWPU's own 701 was installed in **March 1955**.

The Swedes had already beaten them by a year.

In December 1954, on Rossby's BESK computer in Stockholm, **Sweden had run the world's first operational numerical weather forecasts** -- three times a week for the North Atlantic, using a simple barotropic model that was producing, in Rossby's words, "tremendously successful" results.[^13] The Americans absolutely knew about it. **Norman Phillips** had been personally invited to Stockholm by Rossby in 1953 to port the ENIAC/IAS code to BESK. **Philip Thompson** had run a U.S. Air Force research presence in Stockholm. **Bert Bolin** had been at IAS with Charney and von Neumann and then returned to Sweden to help run the BESK forecasts. **Aksel Wiin-Nielsen** and **Geirmundur Arnason** walked directly from Rossby's Stockholm group to JNWPU in Suitland.

Sweden had been the pilot project. JNWPU was going to be the factory.

The first operational computer weather forecast in the United States was issued on the afternoon of **Friday, May 6, 1955**. It was a 500-millibar height forecast for the Northern Hemisphere, produced using the **Charney three-level quasi-geostrophic model** running on the IBM 701. A team of meteorologists had hand-drawn the input analysis from teletype observations, punched it onto cards, loaded it into the 701, waited, and read out the gridded output. A human analyst then hand-smoothed the machine output into a finished prognostic chart.

It was, by Cressman's own admission, disappointing.

**Fred Shuman** -- the JNWPU's chief modeler, a 1951 MIT doctorate who would eventually succeed Cressman as director of the National Meteorological Center -- put it bluntly in his 1989 retrospective:

> "Within three years three agencies of the United States Government jointly created a numerical weather prediction service, but it was quickly discovered that **current models had very serious defects**. After considerable research, the first operationally effective model was achieved in 1958."[^11]

Three years of bad forecasts. The Environmental Modeling Center history page is even blunter: "When the model began running operationally later in 1955, the results were very disappointing and not usable by forecasters."[^12]

What went wrong? Several things. The three-level quasi-geostrophic model was too crude a vertical discretization to capture the jet stream structure properly. Its quasi-geostrophic assumptions broke down near the equator, where the Coriolis parameter approaches zero -- the 500 mb forecast had a garbage "tropical belt" problem that contaminated the rest of the solution every run. There was no objective analysis until Cressman's 1959 paper introduced one; before then, the input fields were hand-drawn. And the IBM 701's **mean time between failures was about 30 minutes**. A single 24-hour forecast run often took longer than that, which meant the forecast failed mid-computation and had to be restarted. The operational cycle was a race against the 701's Williams tubes -- which were, by this point, nearing the end of their useful life as computer memory.

![A close-up of an IBM 701 console and control panel. The operator at the console had to keep the Williams tube memory refreshed, watch for parity errors, and restart the forecast when the machine crashed -- which happened roughly every half hour. Photo: Wikimedia Commons (CC BY 2.0).](/assets/images/IBM_701_console.jpg)

In 1957, the 701 was replaced at JNWPU by the **IBM 704** -- the same machine we have met elsewhere in this series, with its magnetic core memory, hardware floating-point, and 7-to-9-hour mean time between failures. With the 704, and with the improved barotropic model of 1958, JNWPU finally began producing forecasts that beat the human competition. By 1960, numerical weather prediction was consistently outperforming subjective forecasts at 72 hours.

On **January 1, 1958**, JNWPU merged with the older **National Weather Analysis Center** (whose origins went back to 1947) to form the **National Meteorological Center (NMC)**. Cressman stayed on as director. Fred Shuman later succeeded him. And NMC -- which eventually became the modern **National Centers for Environmental Prediction (NCEP)** -- stayed in FOB 4 at Suitland until 1999, when the computers finally moved to a new facility in Bowie, Maryland.

The 701 had launched the program. The 704 had finished the job. But the whole workflow of American operational weather forecasting -- the daily ingestion of global observations, the objective analysis, the model run, the chart output, the dissemination to field offices -- was first established on the 701 at Suitland in 1955, by Cressman and Shuman and a handful of Navy and Air Force officers and civilians from the Weather Bureau, working in a drab federal office building that no one has ever called pretty.

The first forecast was disappointing. Every forecast since is descended from it.

---

## The End of the 701 -- and the Beginning of IBM

The IBM 701 had a short life. First customer delivery in early 1953. Replaced in IBM's product line by the **IBM 702** (business applications) and the **IBM 704** (scientific, with hardware floating-point) by 1955. By 1957, the last 701s were being retired from active service. Only 19 were ever built. No complete machine survives.

And yet, in those brief five years, the 701 did everything that mattered.

It proved that IBM could build an electronic computer. It established Rochester's Poughkeepsie lab as the design center that would produce the 704, the 709, the 7090, the System/360, and every other IBM mainframe for the next three decades. It put hundreds of new electrical engineers on IBM's payroll -- the company went from a handful to nearly 500 EEs within two years of launching the project. It delivered the first machine translation. The first machine learning. The first operational weather forecast in the United States. The first high-level programming system (Speedcode). And it launched the career of **John Backus**, who would go on to give the world FORTRAN.

Above all, it proved Watson Jr. right. In 1950, IBM had been a punch-card tabulator company worth about $200 million per year, with a sales force that did not believe in electronics and a founder who had initially thought computers would never matter. Seven years later, IBM controlled **85 percent of the U.S. computer market**. By 1970, IBM's revenue was over $7 billion. The company that had sold tabulators in 1950 was the unchallenged global leader in computing.

The 701 did that. Or rather, the 150 engineers in the tar-roofed Poughkeepsie tie factory did it, pushed by a young IBM president who had made his own father a promise:

> "We thought in those early days that we either had to win this one or fail as a company."[^2]

They won.

---

## Postscript: The Three Disappointments

There is a pattern in the 701's three great firsts that is worth sitting with.

**Samuel's checkers program** was publicly hyped in 1956 and again in 1962. It lost all eight games to world-class players in 1966. The hype and the rout are both part of the story. But the real legacy is Sutton's line of intellectual descent: **Samuel's 1959 temporal-difference learning → TD-Lambda → Q-learning → AlphaGo → AlphaZero.** The machine that learned to play checkers better than its programmer was the direct ancestor of the machine that beat Lee Sedol.

**Georgetown's machine translation** was publicly hyped in 1954 and again through the late 1950s. It was crushed by the ALPAC report in 1966, killing U.S. government funding for two decades. But the proof of concept had been delivered, and when funding returned -- first via statistical methods in the 1990s, then via neural methods in the 2010s -- the field knew the goal was real. The large language models of today translate between dozens of languages in real time. Dostert's "five years" prediction was wrong by a factor of about ten. He was off by an order of magnitude, not a category.

**JNWPU's operational forecasts** were disappointing from May 1955 until at least 1958. The first useful numerical weather forecast came from the IBM 704, not the 701. But the infrastructure, the workflow, the inter-agency cooperation, and the institutional habit of **running a computer forecast every single day no matter what** were all established on the 701. Today, NCEP's Global Forecast System runs on hundreds of thousands of cores in Bowie, Maryland, and its outputs ripple out to every smartphone, every commercial airline, every hurricane evacuation, every farmer's planting decision. The chain of descent goes from the GFS on Cray-class supercomputers today, backwards through decades of IBM mainframes, all the way to the IBM 701 at Suitland on the afternoon of Friday, May 6, 1955. The first forecast was bad. Every forecast since has been a refinement.

Three firsts. Three disappointments. Three worlds transformed.

That was the 701. That was the machine that built IBM. And that was the machine that quietly -- one disappointing demonstration at a time -- invented the future.

---

## Footnotes
[^1]: Bashe, C. J., Johnson, L. R., Palmer, J. H. & Pugh, E. W. (1986). *IBM's Early Computers*. MIT Press. See also Hurd, C. C., ed. (1983), Special Issue: The IBM 701 Thirtieth Anniversary, *Annals of the History of Computing*, 5(2).
[^2]: Watson, T. J. Jr. with Petre, P. (1990). *Father, Son & Co.: My Life at IBM and Beyond*. Bantam Books.
[^3]: Hurd, C. C., ed. (1983). Special Issue: The IBM 701 Thirtieth Anniversary. *Annals of the History of Computing*, 5(2). Birkenstock's recollection and Hurd's complaint are both preserved in this oral-history issue.
[^4]: Watson, T. J. Jr. (1953). Remarks at IBM annual stockholders' meeting, April 28, 1953. Quoted in Bashe et al. (1986), *IBM's Early Computers*, and in Watson & Petre (1990), *Father, Son & Co.*
[^5]: Goldstine, H. H. (1972). *The Computer from Pascal to von Neumann*. Princeton University Press, p. 332. [Internet Archive](https://archive.org/details/computerfrompasc00herm).
[^6]: Backus, J. W. (1954). "The IBM 701 Speedcoding System." *Journal of the ACM*, 1(1), 4-6. [CHM PDF](https://archive.computerhistory.org/resources/text/Fortran/102663108.05.01.acc.pdf).
[^7]: Samuel, A. L. (1959). "Some Studies in Machine Learning Using the Game of Checkers." *IBM Journal of Research and Development*, 3(3), 210-229. [PDF](https://www.cs.virginia.edu/~evans/greatworks/samuel.pdf).
[^8]: Hutchins, W. J. (2004). "The Georgetown-IBM experiment demonstrated in January 1954." In *Machine Translation: From Real Users to Research*, AMTA 2004. [PDF](https://aclanthology.org/www.mt-archive.info/00/AMTA-2004-Hutchins.pdf).
[^9]: IBM press release (January 8, 1954). Reproduced in the MT Archive. [PDF](https://mt-archive.net/IBM-1954.pdf).
[^10]: ALPAC (1966). *Language and Machines: Computers in Translation and Linguistics*. National Academy of Sciences, Publication 1416. [PDF](https://www.mt-archive.net/50/ALPAC-1966.pdf).
[^11]: Shuman, F. G. (1989). "History of Numerical Weather Prediction at the National Meteorological Center." *Weather and Forecasting*, 4(3), 286-296. [AMS](https://journals.ametsoc.org/view/journals/wefo/4/3/1520-0434_1989_004_0286_honwpa_2_0_co_2.xml).
[^12]: Environmental Modeling Center (NCEP/EMC). History. [EMC](https://www.emc.ncep.noaa.gov/emc/pages/ourhistory.php).
[^13]: Persson, A. (2005). "Early Operational Numerical Weather Prediction Outside the USA." *Meteorological Applications*, 12. [Wiley](https://rmets.onlinelibrary.wiley.com/doi/pdf/10.1017/S1350482705001593).

## References
**The IBM 701, Watson Jr., and the Defense Calculator:**
* Watson, T.J. Jr. with Petre, P. (1990). *Father, Son & Co.: My Life at IBM and Beyond*. Bantam Books. [Penguin Random House](https://www.penguinrandomhouse.com/books/187404/father-son-and-co-by-thomas-j-watson/)
* Bashe, C.J., Johnson, L.R., Palmer, J.H. & Pugh, E.W. (1986). *IBM's Early Computers*. MIT Press.
* IBM Corporate History. IBM 700 Series. [IBM](https://www.ibm.com/history/700)
* IBM Corporate History. Thomas J. Watson Jr. [IBM](https://www.ibm.com/history/thomas-watson-jr)
* Wikipedia. IBM 701. [Wikipedia](https://en.wikipedia.org/wiki/IBM_701)
* The IBM 701. Columbia University Computing History. [Columbia](https://www.columbia.edu/cu/computinghistory/701.html)
* Hurd, C.C., ed. (1983). Special Issue: The IBM 701 Thirtieth Anniversary. *Annals of the History of Computing*, 5(2).
* ETHW / IEEE History Center. The Computer Pioneers: Development of the IBM 701. [ETHW](https://ethw.org/Archives:The_Computer_Pioneers:_The_Development_of_the_IBM_701)
* Goldstine, H.H. (1972). *The Computer from Pascal to von Neumann*. Princeton University Press. [Internet Archive](https://archive.org/details/computerfrompasc00herm)

**Backus and Speedcode:**
* Backus, J.W. (1954). The IBM 701 Speedcoding System. *Journal of the ACM*, 1(1), 4-6. [CHM PDF](https://archive.computerhistory.org/resources/text/Fortran/102663108.05.01.acc.pdf)
* Speedcoding operations manual (1953). [CHM PDF](https://archive.computerhistory.org/resources/access/text/2018/02/102632810-05-01-acc.pdf)

**Arthur Samuel and machine learning:**
* Samuel, A.L. (1959). Some Studies in Machine Learning Using the Game of Checkers. *IBM Journal of Research and Development*, 3(3), 210-229. [CS Virginia PDF](https://www.cs.virginia.edu/~evans/greatworks/samuel.pdf)
* McCarthy, J. & Feigenbaum, E.A. (1990). In Memoriam -- Arthur Samuel: Pioneer in Machine Learning. *AI Magazine*, 11(3).
* Wikipedia. Arthur Samuel (computer scientist). [Wikipedia](https://en.wikipedia.org/wiki/Arthur_Samuel_(computer_scientist))
* University of Alberta Chinook Project. Arthur Samuel's Legacy. [UAlberta](https://webdocs.cs.ualberta.ca/~chinook/project/legacy.html)
* IBM. The Games That Helped AI Evolve. [IBM](https://www.ibm.com/history/early-games)

**Georgetown-IBM Machine Translation Experiment:**
* Hutchins, W.J. (2004). The Georgetown-IBM experiment demonstrated in January 1954. [AMTA PDF](https://aclanthology.org/www.mt-archive.info/00/AMTA-2004-Hutchins.pdf)
* Hutchins, W.J. (1994). The Georgetown-IBM demonstration, 7th January 1954. *MT News International*, 8. [mt-archive](https://mt-archive.net/90/MTNI-1994-Hutchins.pdf)
* Sheridan, P. (1955). Research in Language Translation on the IBM Type 701. *IBM Technical Newsletter*, 9. [mt-archive](https://aclanthology.org/www.mt-archive.info/Sheridan-1955.pdf)
* IBM press release (January 8, 1954). [mt-archive PDF](https://mt-archive.net/IBM-1954.pdf)
* Gordin, M.D. (2016). The Dostoevsky Machine in Georgetown: Scientific Translation in the Cold War. *Annals of Science*, 73(2). [Author PDF](https://static1.squarespace.com/static/5275adb7e4b0298e6ac6bc86/t/57837ff546c3c42c527c2de3/1468235767273/The+Dostoevsky+Machine+in+Georgetown+scientific+translation+in+the+Cold+War.pdf)
* ALPAC (1966). Language and Machines: Computers in Translation and Linguistics. National Academy of Sciences, Publication 1416. [mt-archive PDF](https://www.mt-archive.net/50/ALPAC-1966.pdf)
* Wikipedia. Georgetown-IBM experiment. [Wikipedia](https://en.wikipedia.org/wiki/Georgetown%E2%80%93IBM_experiment)
* Wikipedia. Leon Dostert. [Wikipedia](https://en.wikipedia.org/wiki/L%C3%A9on_Dostert)

**JNWPU, Cressman, Shuman, and Operational NWP:**
* Harper, K., Uccellini, L.W., Kalnay, E., Carey, K. & Morone, L. (2007). 50th Anniversary of Operational Numerical Weather Prediction. *Bulletin of the American Meteorological Society*, 88(5), 639-650. [AMS](https://journals.ametsoc.org/view/journals/bams/88/5/bams-88-5-639.xml)
* Shuman, F.G. (1989). History of Numerical Weather Prediction at the National Meteorological Center. *Weather and Forecasting*, 4(3), 286-296. [AMS](https://journals.ametsoc.org/view/journals/wefo/4/3/1520-0434_1989_004_0286_honwpa_2_0_co_2.xml)
* Shuman, F.G. (1957). Numerical Methods in Weather Prediction: II. Smoothing and Filtering. *Monthly Weather Review*, 85(11), 357-361.
* Cressman, G.P. (1959). An Operational Objective Analysis System. *Monthly Weather Review*, 87(10), 367-374.
* Cressman, G.P. (1992). Oral history interview, August 24, 1992. UCAR OpenSky. [UCAR](https://opensky.ucar.edu/islandora/object/:34962)
* NOAA Mariners Weather Log (December 2007). The History of Numerical Weather Prediction. [NOAA](https://www.vos.noaa.gov/MWL/dec_07/weatherprediction.shtml)
* Environmental Modeling Center (NCEP/EMC). History. [EMC](https://www.emc.ncep.noaa.gov/emc/pages/ourhistory.php)
* Yang, C. (2025). The First Compute Arms Race: The Early History of Numerical Weather Prediction. [arXiv](https://arxiv.org/abs/2506.21816)
* Persson, A. (2005). Early Operational Numerical Weather Prediction Outside the USA. *Meteorological Applications*, 12. [Wiley](https://rmets.onlinelibrary.wiley.com/doi/pdf/10.1017/S1350482705001593)

**Image Credits:**
* IBM 701 frame photo: Wikimedia Commons. [Wikimedia](https://commons.wikimedia.org/wiki/File:IBM_701_frame.jpg)
* IBM 701 console photo: Wikimedia Commons. [Wikimedia](https://commons.wikimedia.org/wiki/File:IBM_701console.jpg)
* Williams tube: agr, Computer History Museum. [Wikimedia](https://commons.wikimedia.org/wiki/File:Williams_tube.agr.jpg)
* Thomas J. Watson Jr., Brown University, 1937. Public domain. [Wikimedia](https://commons.wikimedia.org/wiki/File:Thomas_John_Watson_Jr.,_1937.jpg)
* Leon Dostert at Nuremberg Trials, 1946. Public domain. [Wikimedia](https://commons.wikimedia.org/wiki/File:Interpreters_section.jpg)
* George P. Cressman portrait. NOAA, public domain. [Wikimedia](https://commons.wikimedia.org/wiki/File:George_P._Cressman.jpg)

---

*Previously in this series: [The Man Who Forecasted Weather with a Pencil](/weather/hpc/history/2026/03/24/The-man-who-forecasted-weather-with-a-pencil.html) -- [The Number That Connects Turbulence to War](/weather/hpc/history/2026/03/25/The-number-that-connects-turbulence-to-war.html) -- [The Line That Models Cannot Draw (Part 1)](/weather/hpc/history/2026/03/26/The-line-that-models-cannot-draw.html) -- [Reading the Sky](/weather/hpc/history/2026/03/27/Reading-the-sky.html) -- [The Ghost in the Grid](/weather/hpc/history/2026/03/28/The-ghost-in-the-grid.html) -- [The Man Who Tamed the Equations](/weather/hpc/history/2026/03/29/The-man-who-tamed-the-equations.html) -- [The First Climate Model Had 5 KB of RAM](/weather/hpc/history/2026/03/30/The-first-climate-model-had-5KB-of-RAM.html) -- [The Butterfly That Broke the Forecast](/weather/hpc/history/2026/03/31/The-butterfly-that-broke-the-forecast.html) -- [From Cables to Chaos](/weather/hpc/history/2026/04/02/From-cables-to-chaos.html) -- [The Swedes Got There First](/weather/hpc/history/2026/04/03/The-swedes-got-there-first.html) -- [The Magician Who Told No Secrets](/weather/hpc/history/2026/04/04/The-magician-who-told-no-secrets.html) -- [The Blueprint Von Neumann Gave Away](/weather/hpc/history/2026/04/08/The-blueprint-von-Neumann-gave-away.html) -- [The Machine That Learned Too Early](/weather/hpc/history/2026/04/09/The-machine-that-learned-too-early.html)*
