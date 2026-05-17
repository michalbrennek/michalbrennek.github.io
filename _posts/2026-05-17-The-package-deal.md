---
layout: single
title: "The Package Deal"
date: 2026-05-17 10:00:00 +0100
categories: [Weather, HPC, History]
tags: [Phillips, Charney, Lorenz, MIT, NMC, NCEP, GCM, Sigma, Aliasing, History]
header:
  teaser: /assets/images/Norman_Phillips_2004_NWP50.jpg
  overlay_image: /assets/images/Norman_Phillips_2004_NWP50.jpg
  overlay_filter: "0.6"
excerpt: "Norman Phillips was twenty-one and a freshly commissioned weather officer when he met Martha Nissen at a Chicago operetta rehearsal in 1944 or 1945. They were both playing French horn. She would be his wife for the next seventy-three years. He would go on, between 1945 and 2019, to write the first general circulation model of the atmosphere, invent the vertical coordinate that almost every operational weather model on Earth still uses, diagnose the numerical instability that broke his own first GCM, chair the MIT meteorology department, and spend fourteen years at the National Meteorological Center as the senior theoretical voice in operational American weather prediction. This is the full-career portrait."
---

In the autumn of 1944 or the spring of 1945, in the orchestra pit of a Chicago amateur operetta company whose name has not survived in the obituary record, a freshly commissioned twenty-one-year-old second lieutenant of the Army Air Force put a French horn to his lips next to a young woman of about the same age, also playing French horn. The lieutenant had been commissioned on **5 June 1944, the day before D-Day**, fourth in a class of 391 from the meteorological cadet school at Chanute Field, Illinois.[^cadetdate] He was waiting at Grenier Field in New Hampshire to ship out for the Azores. The young woman next to him in the pit was named **Martha Nissen**. By the time he reached the Azores forecasting station that summer they were engaged. They were married in 1945 -- the family obituary does not give the exact date -- and the marriage would last until her death some seventy-three years later, after he had himself retired to Merrimack, New Hampshire, and was approaching ninety-five.[^operetta]

The lieutenant's name was **Norman A. Phillips**.

Sixty-three years after that first French-horn-and-French-horn encounter, in March 2019, Phillips died at a long-term care facility called Grace House in Windham, New Hampshire, age ninety-five.[^death] Between those two dates -- between two French horns in a Chicago operetta pit in 1944 and a New Hampshire deathbed in 2019 -- he wrote one of the founding papers of modern climate science (the 1956 *Quarterly Journal of the Royal Meteorological Society* paper that is the universally agreed birth certificate of the general circulation model), invented the vertical coordinate that almost every operational atmospheric model on Earth still uses (the **sigma coordinate**, 1957, a two-page communication), diagnosed and fixed the numerical instability that had broken his own first GCM (the 1959 paper on nonlinear computational instability), wrote the canonical 1963 review of quasi-geostrophic theory, chaired the MIT meteorology department for four years (1970-1974), left MIT in mid-chairmanship to take the senior scientific post at the National Meteorological Center in Maryland (1974-mid-1980s), designed there a regional model that the operational forecasters called "Norm's Great Model" (the **Nested Grid Model**, operational from 1985), trained the cohort of NMC scientists who would run the modern National Centers for Environmental Prediction (Eugenia Kalnay, Stephen Lord, Geoff DiMego, John Derber, Ronald McPherson, Joseph Sela), and contributed the 1986 *Tellus A* paper on forecast-error statistics that is still the foundational reference for operational data-assimilation covariance modelling.

<figure class="align-center" style="width: 60%;">
  <img src="{{ '/assets/images/Norman_Phillips_2004_NWP50.jpg' | relative_url }}" alt="Norman A. Phillips at the NWP-50 symposium, 16 June 2004." />
  <figcaption>Norman A. Phillips at the Symposium on the 50th Anniversary of Operational Numerical Weather Prediction, University of Maryland College Park, 16 June 2004. He is eighty years old here. Twenty-six years earlier he had retired from MIT to join the National Meteorological Center, just up the road in Camp Springs, as Principal Scientist of its Development Division; nine years before that he had won the Carl-Gustaf Rossby Research Medal for the 1956 paper "The general circulation of the atmosphere: a numerical experiment," and one year before this photograph he had shared, with his old IAS colleague Joseph Smagorinsky, the Benjamin Franklin Medal in Earth Science. Photo: William G. Collins, NCEP/NOAA, public domain (PD-USGov-NOAA).[^portraitcredit]</figcaption>
</figure>

Post 7 of this series, [*The First Climate Model Had 5 KB of RAM*](/weather/hpc/history/2026/03/30/The-first-climate-model-had-5KB-of-RAM.html), covered Phillips's 1956 GCM run on the IAS computer at Princeton as its central subject. The present post is the *career* portrait: the boyhood in chemistry-then-Army, the Azores wartime forecaster, the Chicago graduate student under Erik Palmen and George Platzman, the five productive years at the Institute for Advanced Study, the eighteen MIT years, the fourteen NMC years, the thirty-year retirement. The 1956 GCM occupies one section among many here -- the centrepiece of Post 7 becomes one chapter of the life. The post-1956 trajectory is the longer story and is where the bulk of the words go.

There is one organising thread, and it is the title of this post. Twice in his career Phillips was the second name on a transaction. He came to the IAS Meteorology Project in October 1951 because **Jule Charney**, who had seen Phillips's twenty-five-page Chicago dissertation drafted on the blackboard at a 1950 or 1951 visit and recognised it as the next computational step in numerical weather prediction, offered him a job on the spot. He came to MIT in summer 1956 because Charney, leaving the IAS as the Electronic Computer Project wound down, told MIT's department head **Henry Houghton** that he would come only on a **package deal** that included Phillips as a senior staff hire and the retention and promotion of **Edward Lorenz**.[^packagedeal] Twice in his career, on each of the two great moves of his life, Phillips travelled as someone else's condition for arrival. The 1956 package deal is the sentence that gives this post its title; it is also the sentence that, more than any single technical citation, opened the modern intellectual history of American academic meteorology. Charney, Phillips, and Lorenz, working three doors apart in the MIT Department of Meteorology for the next eighteen years, redefined what an atmospheric science department could do.

## Where Post 42 left off

[The previous post in this series](/weather/hpc/history/2026/05/15/The-first-in-Bracknell.html) covered the operational arrival of the **Cyber 205** vector supercomputer at the United Kingdom Met Office in July 1981 and its subsequent decade of production weather forecasting at Bracknell. That post was about the *hardware* on which late-twentieth-century operational NWP was run; this one is about the *theoretician* whose ideas the operational software was implementing. The 15-level global model that the Cyber 205 ran twice a day from 1981 to 1990 used Phillips's sigma coordinate. The successive-correction objective analysis it replaced was the one Phillips's NMC colleagues had spent the 1970s and 1980s migrating off, toward the optimal-interpolation methods that Phillips's 1986 *Tellus A* paper had theoretically grounded. The two-week predictability ceiling that constrained any Cyber 205 forecast was the one [Edward Lorenz](/weather/hpc/history/2026/05/15/The-coyote-who-found-chaos.html), two corridors down from Phillips at MIT through the 1960s and 1970s, had defined in 1963 and 1969. The Cyber 205 in Bracknell was running a software stack that, line for line, was the operational realisation of two decades of Phillips, Lorenz, and Charney at MIT.

That much is the institutional setup. The man himself, with his French horn and his Swedish-immigrant Chicago boyhood and his quiet stoicism in the face of half a dozen public scientific revolutions, asks for a longer look. Begin with the family origin.

## 1. Chicago, 1923-1942: chemistry interrupted

Norman A. Phillips was born in **Chicago, Illinois, on 9 July 1923**.[^birth] His father was **Alton Elmer Anton Phillips**, the son of Swedish immigrants. His mother was **Linnea (Larson) Phillips**, also Swedish by family origin. He had a sister, **Alice (Phillips) Westphal**, who predeceased him. The household was Chicago-Swedish-Lutheran by background, civic-minded, undemonstrative; the Rivet Funeral Home obituary records that Phillips kept "a fascination for Scandinavia and Swedish ancestry" all his life and was "an avid reader" with a particular interest in Scandinavian history.[^rivet] He kept the middle initial "A." not because he had a middle name but because his father's name was Alton; he used the paternal initial as a courtesy.

In autumn 1940, aged seventeen, Phillips enrolled at the **University of Chicago** to study chemistry.[^chicago40] Carl-Gustaf Rossby had only just arrived at Chicago, in 1940, to chair what would become in 1942 the independent Department of Meteorology -- spun off from Horace Byers's older Department of Geophysical Sciences with a separate budget and a separate faculty, but still housed in the same gothic-revival buildings on the south side of the Midway. Phillips was not yet a meteorology student. He was a chemistry student.

He would not finish the chemistry degree. On **15 March 1942**, three months after Pearl Harbor and three months into his sophomore year, he enlisted in the United States Army.[^enlist] The Army's meteorology cadet pipeline was just beginning to take shape: the same week he enlisted, the first pre-meteorology "B" school opened at the **University of Michigan** at Ann Arbor. Phillips, like several hundred other recent science-track college students that spring, elected the meteorology programme over the risk of a random combat assignment. From March through September 1942 he was one of 357 recruits in the Michigan B school, learning algebra, calculus, basic dynamics, and elementary atmospheric thermodynamics on an accelerated schedule. From September 1942 through June 1944 he was at the **Chanute Field Meteorological Cadet School** in Illinois, working through the nine-month "A" curriculum -- synoptic analysis, the Bjerknes frontal model in its standard Bergen-derived presentation, upper-air observation, basic dynamical equations.

Phillips graduated from Chanute **fourth out of a class of 391** on **5 June 1944**, the day before D-Day.[^chanutefour] He was commissioned second lieutenant in the Army Air Force. The graduation was a brief ceremony at the airfield outside Rantoul, Illinois, with the commissioned class -- nearly four hundred new weather officers, the bulk of them the Air Force's wartime requirement -- shipping out within weeks to forecasting stations across the global theatre. Phillips's first assignment was to the headquarters of the **8th Weather Region** at Grenier Field, just south of Manchester, New Hampshire, under **Lieutenant Colonel Arthur Merewether**.[^merewether] Merewether had been chief meteorologist of American Airlines before the war. The 8th Weather Region was the operational nucleus of weather support for the North Atlantic ferry route -- the corridor down which aircraft, crew, and materiel moved from American factories and training fields to the European theatre. Phillips was forwarded from Grenier Field to a forecasting station in the **Azores**, the Portuguese mid-Atlantic archipelago that was at that point the principal trans-Atlantic refuelling stop for both ferry flights and passenger traffic between the US and Britain. Phillips had carried the French horn into the Army; he had carried it out of Chicago when he enlisted in March 1942 and now carried it to the Azores. Music was a portable hobby.

Between graduation from Chanute and shipping out to the Azores -- somewhere in that summer or early autumn of 1944 -- or possibly during a brief Chicago leave, perhaps in spring 1945 after the European theatre was visibly winding down, Phillips met Martha Nissen at the operetta. The obituary record does not pin the date with any precision. The detail that survives is that they were both playing French horn. They were married in 1945, while Phillips was still in uniform.[^marriage] No published source records the wedding date or location.

The Azores forecasting station itself appears in Phillips's 1989 NCAR oral history with two cleanly remembered anecdotes that fix the texture of the work. Phillips, quoted in John Lewis's 1998 *BAMS* retrospective:

> I was sent to a station in the Azores where we had to consider the weather over the entire Atlantic Region in order to service the flights that came to and left the Azores.[^lewis1998]

And:

> I remember once one of the planes for which I gave a wind forecast got blown over the Normandy peninsula at the time the Germans were still in charge of St. Lo and they were shot at -- a passenger plane! Another time I sent a flight to Newfoundland, and Gander zeroed in and I wasn't sure myself whether the plane had enough fuel to go on to Stevensville [Stephenville] on the other side of the island.[^lewisplane]

The forecasts mattered, in other words. Phillips would carry the operational forecaster's sense of consequences for the rest of his career -- through the IAS years, through MIT, through the 1974 move back to operational meteorology at NMC. Lewis 1998 is explicit about this: the Azores experience pulled Phillips from chemistry to meteorology. After a stint at **Westover Field** in Massachusetts, Phillips was discharged from the Army Air Force as a **first lieutenant** in October 1946.[^discharge] He returned to the University of Chicago that autumn, no longer a chemistry undergraduate but now a meteorology major.

## 2. Chicago, 1946-1951: from Bergen to Rossby to Platzman

Phillips returned to a Chicago Department of Meteorology in some transition. **Rossby**, the founding chair, had begun the long process of pulling back toward Stockholm: in 1947 Rossby would be named founding director of the **International Meteorological Institute (IMI)** at Stockholm University, and from then on his Chicago presence would become episodic rather than continuous, a pattern of regular visits rather than residence. The formal succession to the Chicago meteorology chair would fall in 1948 to **Horace R. Byers**, the empirical-meteorologist who had been Rossby's deputy and who would chair the department for the next twelve years -- the entire span of Phillips's graduate work and well beyond.[^byers]

<figure class="align-center" style="width: 50%;">
  <img src="{{ '/assets/images/Rossby_1939.jpg' | relative_url }}" alt="Carl-Gustaf Rossby, Harris and Ewing studio portrait, 1939." />
  <figcaption>Carl-Gustaf Rossby in 1939, the year he became Assistant Chief of the United States Weather Bureau under Francis Reichelderfer. Rossby would found the Institute of Meteorology at the University of Chicago in 1940 and bring with him the synthesis -- Bergen frontal analysis combined with rigorous fluid-dynamical theory -- that defined Chicago meteorology in the 1940s. Phillips re-enrolled at Chicago in autumn 1946 specifically because of Rossby's programme, switched from chemistry to meteorology, and would credit Rossby's lecture-style two-layer model demonstrations as the inspiration for his own 1951 doctoral thesis. Photo: Library of Congress, Harris and Ewing Collection, public domain.[^rossbyphoto]</figcaption>
</figure>

This is the period in Phillips's biography that is most clearly documented in the available record. He took the **BSc in Meteorology** at Chicago in **1947**, an undergraduate degree compressed by his three-and-a-half years of cadet and operational training during the war. He took the **MSc in Meteorology** in **1948**, under **Erik Palmen** -- the Finnish dynamical synoptician who was at Chicago between 1946 and 1948 as a visiting professor on Rossby's ONR-funded jet stream contract.[^palmen] The MSc thesis was a synoptic study of the subsidence of a cold dome -- a textbook Chicago-school problem, the kind of detailed mid-tropospheric energetics that Bergen-school methods had not been able to pin down quantitatively. Palmen returned to Helsinki in late 1948; the supervision had been light-handed, with the master's-level thesis effectively chosen and executed by Phillips himself.

For doctoral work Phillips selected, or had selected for him, **George W. Platzman** as supervisor.[^platzman] Platzman had taken his own PhD at Chicago in 1947 under Rossby on a problem in the dynamical theory of long waves; he was a junior faculty member by 1948 when Phillips was looking for a doctoral home. Phillips's account of Platzman, given in his 1989 NCAR oral history and quoted by Lewis 1998, is one of the warmer tributes in his oral record:

> George, as you know, has a characteristic of being accurate as well as being right. And I think I've, I hope I've learned some of that from him.[^platzmanquote]

"Accurate as well as being right" -- the formula is Phillips on Platzman but it is also, on every available reading, Phillips on himself. It is the closest the Phillips literature comes to a one-line characterisation of his scientific style. The combination of *accuracy* (the formal property of getting the equations correct, the sign conventions right, the dimensional analysis closed) with *rightness* (the harder property of choosing the right equations to begin with, of seeing which approximation will preserve the physics that matters) is not a common combination, and Phillips's career is in part the story of someone who possessed it in unusual measure.

The thesis Phillips wrote under Platzman, **"A Simple Three-Dimensional Model for the Study of Large-Scale Extratropical Flow Patterns"** (PhD, University of Chicago, 1951), was twenty-five pages long.[^thesis25] He chose the topic himself. He had read Charney's 1948 *Geofysiske Publikasjoner* paper "On the Scale of Atmospheric Motions," in which Charney systematically derived the **quasi-geostrophic** approximation by scale analysis of the full hydrodynamic equations -- showing which terms could safely be neglected for the large-scale midlatitude motions that produce weather.[^charney48] Phillips's stated retrospective motivation, from the same NCAR oral history: "Charney presented this recipe for how to predict large-scale motions" and "I had seen Rossby use such kind of models in his lectures."[^phillipsoral]

What Phillips constructed in those twenty-five pages was **the simplest model that contained the essential features of the baroclinic atmosphere**: two superimposed layers of incompressible fluid of different densities, constrained to move between two rigid horizontal plates, governed in each layer by the conservation of quasi-geostrophic potential vorticity, with the layers communicating through hydrostatic adjustment of the layer interface. The model captured baroclinic instability -- the conversion of available potential energy in the mean north-south temperature gradient into the kinetic energy of growing midlatitude waves -- with the smallest possible vertical structure compatible with the physics. Two layers and one interface; the minimum.

Phillips derived the **two-layer baroclinic instability criterion** -- the threshold vertical wind shear above which the layer model goes unstable to small perturbations. He did this before reading **Eric Eady's** 1949 paper "Long waves and cyclone waves" in *Tellus*, which had derived the same instability criterion in a continuously stratified fluid; when Phillips later compared his two-layer result against Eady's continuous-stratification result he found the two threshold curves agreed within the limit appropriate to comparing a discrete vertical resolution against a continuum.[^eady] He then applied the model to a concrete case: the **Thanksgiving Day Storm of 23 November 1950** -- the Great Appalachian Storm, one of the most destructive winter cyclones in twentieth-century US East Coast history. Phillips's calculation of tendencies for sea-level pressure and vertical velocity was done by **hand**, using **Southwell's relaxation method** on a coarse grid -- no electronic computer was involved. The Thanksgiving Day forecast was, in Lewis's 1998 phrasing, "the first numerical weather forecast using a baroclinic model of the atmosphere."[^thanksgiving] It was also a forecast made entirely with pencil and paper by a Chicago graduate student before he had ever seen the IAS Princeton computer he was about to spend five years programming.

The blackboard moment came either late in 1950 or early in 1951. Charney was passing through Chicago on Rossby business, and Phillips was asked to present his dissertation work to a small audience that included Rossby, Charney, and Platzman. Charney's later recollection, given in the Lindzen-Lorenz-Platzman 1990 volume on Charney:

> Phillips just outlined very briefly on the blackboard what he had done. And what he had done, of course, was to develop a two-layer model. It was somewhat inspired by the geostrophic approximation [Charney 1948], but I think it would be historically of considerable interest to know what led him to do that... In any case, I recognized that right away as the next step. I hadn't proposed to do it in that way, but it turned out that the finite difference formulation in the simplest way, by vertical differencing of the quasi-geostrophic equations, one arrives at the same equations as one gets for a two-layer model.[^charneyblackboard]

Charney offered Phillips a position at the IAS on the spot. Phillips defended in summer 1951 (the exact date is not in any obituary, but the timing aligns with his arrival in Princeton). His thesis had been twenty-five pages and contained the operational two-layer model that would shape the next two decades of academic and operational atmospheric science. It was the first major piece of evidence -- before any IAS or MIT or NMC work -- of what Phillips could do when he was thinking carefully.

## 3. Princeton IAS, October 1951 - April 1956: the staff programmer

Phillips arrived at the **Institute for Advanced Study Meteorology Project** at Princeton in **October 1951**, on a five-year membership stipend.[^iasarrival] The Project was already three years past its founding crisis; Charney had taken it over from a series of false starts in 1948 and had, with **Ragnar Fjortoft** (Norwegian, visiting), produced the famous **April 1950 ENIAC forecast** at Aberdeen Proving Ground a year and a half before Phillips arrived. Charney, Fjortoft, and von Neumann had published the result that summer in *Tellus* as "Numerical integration of the barotropic vorticity equation"; the paper had transformed numerical weather prediction from an idea associated with Lewis Fry Richardson's 1922 failure into a working programme.[^charneyenwiac]

The IAS machine itself -- sometimes called MANIAC I, though the IAS engineers preferred just "the IAS machine" -- was nearly operational when Phillips arrived. **Julian Bigelow** and the engineering team had been building it since 1946, to a design that **John von Neumann** had specified in his June 1945 *First Draft of a Report on the EDVAC* and subsequent reports for the IAS Electronic Computer Project. The machine had 1024 words of Williams-tube memory, 40 bits per word, which works out to about 5 kilobytes by modern measure. It had 2048 words on a magnetic drum, doubling the storage. Input was punched paper tape in the early years; **Hewitt Crane** later persuaded IBM to modify a card reader so that punched cards could be used instead.[^iasmachine]

<figure class="align-center" style="width: 75%;">
  <img src="{{ '/assets/images/IAS_machine_Oppenheimer_vonNeumann.jpg' | relative_url }}" alt="J. Robert Oppenheimer and John von Neumann at the IAS machine dedication, 10 June 1952." />
  <figcaption>J. Robert Oppenheimer and John von Neumann standing in front of the IAS machine at its formal dedication on 10 June 1952. Phillips had been on the IAS Meteorology Project staff for eight months by this date and would spend the next four and a half years writing programs for this machine -- in hexadecimal machine code, on a 1024-word Williams-tube memory of about 5 kilobytes capacity, supplemented by a 2048-word magnetic drum. The 1955 general circulation experiment that won Phillips the first Napier Shaw Memorial Prize used about 500 numbers to specify the entire atmospheric state at any instant and took roughly eleven hours of IAS machine time to compute 31 days of simulated weather. Photo: Jeremy Norman Collection, historyofinformation.com, CC BY 4.0.[^iaslicense]</figcaption>
</figure>

Phillips's account of the IAS coding environment, given in his 1989 oral history and quoted by Lewis 1998, is worth reproducing for the texture:

> Code was written in what would now be called 'machine language' except that it was one step lower -- the 40 bits of an instruction word (two instructions) were written by us in a 16-character (hexadecimal) alphabet 0, 1, ..., 9, A, B, C, D, E, F instead of writing a series of 0's and 1's. For example, 'C' represented the four bits '1100'. There was no automatic indexing -- what we now call a 'DO-LOOP' was programmed explicitly with actual counting. Subroutines were used, but calls to them had to be programmed using explicitly stored return addresses. In the first year or so of the IAS machine, code and data were fed in by paper tape. Von Neumann eventually got IBM to allow one of their card readers to be modified so that punched cards could be used for input and output.[^iascode]

Phillips's role on the Meteorology Project, in three sentences: he was not Charney's theoretical equal and was not asked to be; he was the staff member who could turn quasi-geostrophic equations into running machine code; and he was the rare *long-tenured* member of an enterprise that otherwise rotated visitors at a rate of one or two a year. The 1952 group photograph that **Joseph Smagorinsky** took -- now reproduced in Lewis 1998 -- shows, left to right, Charney, Phillips, **Glenn Lewis**, **Norma Gilbarg**, and **George Platzman** in front of the IAS machine. Smagorinsky himself, who was a doctoral student visitor from NYU under **Bernhard Haurwitz** between 1950 and 1953, was behind the camera.[^iasphoto] (The original Smagorinsky photograph is held at the American Institute of Physics' Emilio Segrè Visual Archives and is not freely licensed; only a description survives in the open record.)

What Phillips actually did at the IAS, working back from his publications:

**1951-1952**: His first assignment was to translate the barotropic vorticity model from the ENIAC code (Charney-Fjortoft-von Neumann 1950) into running code on the IAS machine, then to extend that model to a **two-level baroclinic** formulation following Charney's vertical-differencing prescription. The test case for both barotropic and baroclinic models was the same Thanksgiving Day 1950 storm Phillips had used in his Chicago dissertation -- a deliberate continuity from the hand-computed thesis forecast to the machine-computed IAS forecast.

**1953**: The IAS work was published as **Charney and Phillips (1953), "Numerical integration of the quasi-geostrophic equations for barotropic and simple baroclinic flow," *Journal of Meteorology* 10, 71-99**.[^cp1953] This was Phillips's first major publication. It is the canonical reference for the IAS two-level model and remains, sixty years later, a standard pedagogical entry point for graduate students learning the structure of finite-difference baroclinic models.

**August 1953 - April 1954**: Phillips took a sabbatical visit to **Rossby's International Meteorological Institute at Stockholm**, with a two-month detour to the **Geophysical Institute at Oslo** on the return. Rossby had personally invited Phillips through Charney; the pretext was that the Swedes had built **BESK** (Binär Elektronisk SekvensKalkylator), an IAS-machine clone, and wanted American help getting NWP code running on it. In Stockholm Phillips collaborated with the Swedish team -- **Bert Bolin**, **Bo Doos**, **Aksel Wiin-Nielsen**, **Germund Dahlquist** -- and the Icelander **Gudmundur Arnason**. On **23-24 March 1954** the team produced what Wiin-Nielsen later called "the first forecasts finished in time to be of use in operation": twice-daily real-time NWP forecasts on BESK, more than a year before the United States Joint Numerical Weather Prediction Unit produced its first operational forecast on 6 May 1955.[^bolinforecast] Phillips's Stockholm winter is the bridge between the Chicago-Princeton intellectual line and the IMI Swedish line; it is also where his deep professional friendships with Bolin (later first Chair of the IPCC) and Wiin-Nielsen (later IMO Prize laureate) were formed.

**April 1954 - October 1955**: Back at Princeton, Phillips published the theoretical predecessor to the 1956 GCM -- **Phillips (1954), "Energy transformations and meridional circulations associated with simple baroclinic waves in a two-level, quasi-geostrophic model," *Tellus* 6, 273-286**.[^phillips54] The 1954 *Tellus* paper analysed the nonlinear extensions of the linear baroclinic-instability theory: where does the eddy energy go once the linear waves have grown to finite amplitude, and how do those eddies maintain a meridional mean-flow circulation? The 1954 paper is the dynamical blueprint for what the 1956 model would simulate. From mid-1954 through 1955 Phillips constructed and integrated the general circulation experiment itself.

**October 1955**: Phillips presented the GCM results at a **conference convened by von Neumann at Princeton** -- "Applications of Numerical Integration Techniques to the Problem of the General Circulation."[^vnconference] The conference was, as Smagorinsky later said, the moment when "a new era had been opened." Among the consequences was von Neumann's lobbying of the Weather Bureau, the Air Force, and the Navy to establish what became, in 1955, the **General Circulation Research Section** at the Weather Bureau -- the precursor to Smagorinsky's eventual **Geophysical Fluid Dynamics Laboratory**. Smagorinsky himself left the IAS in 1953 for the Weather Bureau, two years before Phillips's GCM was finished; the Section was created in 1955 explicitly to extend Phillips's experiment with a real-physics, real-geography GCM.

**April 1956**: Phillips's paper appeared in the *Quarterly Journal of the Royal Meteorological Society* as **Phillips (1956), "The general circulation of the atmosphere: a numerical experiment," *QJRMS* 82, 123-164**.[^qjrms56] On 20 June 1956 it was awarded the first **Napier Shaw Memorial Prize** of the Royal Meteorological Society -- a competition the RMetS had announced two years earlier with "the energetics of the atmosphere" as its declared subject.[^napiershaw]

I will not repeat at length here what [Post 7](/weather/hpc/history/2026/03/30/The-first-climate-model-had-5KB-of-RAM.html) covered: the 17-by-16 grid, the two layers at 250 hPa and 750 hPa, the periodic east-west boundary and the rigid walls at north and south, the symmetric linear heating function of plus-or-minus 0.23 °C/day at the walls, the 130-day spin-up plus 31-day forecast, the 11-12 hours of IAS computer time. The brief version: starting from a uniform isothermal atmosphere at rest with a small random temperature perturbation added, Phillips's model spontaneously generated a single growing baroclinic wave that organised itself into a midlatitude jet of order 60-80 m/s at 250 hPa, alternating bands of easterly and westerly surface winds, the three-cell meridional circulation (Hadley direct cell tropically, Ferrel indirect cell midlatitude, polar direct cell poleward), and surface frontogenesis -- all of it from *dry* dynamics, with no water vapour, no latent heat, no orography. The model was as close to a pure dynamical experiment as the technology of 1955 allowed.

<figure class="align-center" style="width: 75%;">
  <img src="{{ '/assets/images/Earth_Global_Circulation.svg' | relative_url }}" alt="Schematic of Earth's three-cell general circulation: Hadley, Ferrel, polar." />
  <figcaption>Schematic of the three-cell general atmospheric circulation -- Hadley, Ferrel, and polar cells, with trade winds at low latitudes, midlatitude westerlies, polar easterlies, and the upper-tropospheric jet streams. This is the textbook end state that Phillips's 1956 model recovered, on a beta-plane channel, from an atmosphere initially at rest. The fact that all of this emerged spontaneously from a quasi-geostrophic two-level integration with simple linear heating, without orography, without water vapour, and without specified zonal-mean flow was the demonstration that opened modern climate modelling. Diagram: Kaidor on Wikimedia Commons, 2013, CC BY-SA 3.0.[^circulationcredit]</figcaption>
</figure>

The result that closed the GCM session was less dramatic but more important for what followed: after about day 25 the simulation blew up. Phillips noted the failure carefully in the *QJRMS* paper. He did not yet know why it had blown up. The explanation -- nonlinear computational instability and its solution by spectral truncation -- would take him three more years to work out, and would be published in 1959 as a four-page contribution to the Rossby Memorial Volume. That is section 5 of this post.

After the October 1955 conference, the Stockholm conversation that **Aksel Wiin-Nielsen** later reconstructed has Rossby drawing Phillips into a discussion about the dynamics of the simulated cyclones:[^wnreconstr]

> **Rossby:** Norman, do you really think there are fronts there?
>
> **Phillips:** Yes, look at the temperature fields packed up very nicely.
>
> **Rossby:** But Norman, what's the process that creates these fronts? Where do they come from?
>
> **Phillips:** Well, they come out of a very simple dynamics.
>
> **Rossby:** And what is that?
>
> **Phillips:** I have very simple linear heating between the equator and pole, simple dissipation, but of course there is no water vapor or no precipitation, no clouds, totally dry model.
>
> **Rossby:** Yes, Norman, and it should be that! Because here we are getting this front -- and it has nothing to do with clouds/rising motion, it is a sheer dynamic effect that comes as a result of the development.

This is, in microcosm, the moment when the Bergen frontal-cyclone synthesis of the 1920s yielded to the Charney-Eady upper-wave instability synthesis. Rossby, who had carried the Bergen tradition to America in the 1920s, accepted in 1956 that Phillips's purely dynamical simulation was producing fronts as a *consequence* of the upper-level baroclinic instability rather than as a precondition for it. The synoptic intuition of the Bergen years would not be replaced; it would be embedded in a deeper theoretical framework, and Phillips's GCM was one of the first concrete demonstrations of that embedding.

Through the autumn of 1955 and the winter of 1955-1956 the IAS Meteorology Project was visibly winding down. Von Neumann had been named an Atomic Energy Commissioner in 1955 and was effectively absent from Princeton; he was diagnosed with cancer in late 1955 and would die in February 1957. **J. Robert Oppenheimer**, the IAS director, could not promise the meteorology group a permanent home; "pure mathematics was the preferred science there," in Phillips's own retrospective phrasing in his 1995 Charney memoir.[^charneymemoir] Charney's five-year IAS appointment was expiring in 1956. He began looking elsewhere. Phillips, on his own five-year appointment, was carried along in whatever negotiation Charney was about to enter into.

The negotiation Charney entered into is the title of this post.

## 4. The package deal, summer 1956

The defining piece of primary evidence is Phillips's own 1995 NAS biographical memoir of Charney, where -- in the impersonal third person standard for NAS memoirs, referring to himself throughout as "the writer" -- Phillips wrote:

> The Massachusetts Institute of Technology was the winner and offered a package deal including the writer and the retention at MIT of E. Lorenz. It was characteristic of Jule that he recommended to the MIT administration that V. Starr and Lorenz should be promoted as part of this enhancement of the meteorology department. The move was made in the summer of 1956, with a special personal grant of $5,000 to Jule from the Institute at Oppenheimer's urging.[^packagememoir]

The sentence has more in it than first reading suggests. Three observations.

*The structure of the deal.* MIT, in 1956, did not hire Charney alone. It hired Charney on terms that committed it to also hiring Phillips as a senior staff member and to retaining and promoting Lorenz (then a research scientist on Victor Starr's general-circulation programme) and promoting Starr himself. **Henry Houghton**, the MIT meteorology department head since 1945, agreed to all four terms. The MIT meteorology faculty in summer 1956 thus acquired its 1960s-defining shape: Houghton at the head; Starr running the observational general-circulation programme; **Hurd Willett** doing long-range forecasting; **Fred Sanders** teaching synoptic dynamics (PhD 1954 from MIT under Charney); Mollo-Christensen on boundary-layer turbulence; the new arrivals Charney, Phillips, and Lorenz. By the 1960s this department had no serious peer in academic atmospheric science.[^mitfaculty]

*The retention clause for Lorenz.* The 1956 package deal is the reason Lorenz stayed at MIT for the next sixty years. Without it Lorenz, who was still a research scientist rather than a tenure-track faculty member in 1955, might well have moved to UCLA or NCAR or elsewhere. The 1961 discovery of sensitive dependence on initial conditions, the 1963 publication of "Deterministic Nonperiodic Flow," the 1969 *Tellus* paper on predictability of flows with many scales of motion, the 1995 Lorenz 96 model -- all of them happened at MIT because Charney made Lorenz a condition of his own arrival. The intellectual history of [chaos in atmospheric science](/weather/hpc/history/2026/05/15/The-coyote-who-found-chaos.html) and the operational consequences in the 1992 ECMWF and NCEP ensemble systems both run, ultimately, through the 1956 retention-and-promotion clause that Charney attached to his own MIT appointment.

*The $5,000 grant.* Five thousand dollars in 1956 was about 60 percent of a senior MIT faculty member's annual salary; it was the kind of one-off personal payment that universities did not normally make. The transaction Phillips records -- with Oppenheimer urging it, the Institute providing the funds, and Charney accepting them on departure -- is unusual enough that it is worth pausing on. Oppenheimer was the IAS director; the IAS was paying its departing meteorology lead a substantial personal sum at the moment he and his junior colleague were transferring the entire Meteorology Project to MIT. The simplest reading is that the IAS, having decided not to extend the Meteorology Project, was buying out Charney's good will rather than letting him leave on bad terms. Phillips records the fact neutrally, in passing, in a 1995 memoir written nearly forty years later.

The Phillips-Charney-Lorenz move from Princeton to Cambridge in summer 1956 is the more important institutional consequence than any single technical citation in Phillips's life. The 1956 GCM was a paper, a brilliant paper, that would have been written wherever Phillips had been. The package deal was an institutional commitment that would shape an academic department for the next half-century. The 1970-1981 chairmanship sequence -- **Houghton (1942/45-1970)**, **Phillips (1970-1974)**, **Charney (1974-1977)**, **Lorenz (1977-1981)** -- is a sequence of four consecutive senior figures, three of them imported by Houghton in summer 1956, three of them giants of the field, all four of them running the same department for thirty-six years.[^chairseq] Such sequences do not happen by accident. They happen because, in summer 1956, somebody made a deal.

## 5. MIT 1956-1974: sigma, aliasing, and the chairmanship

Phillips and his family moved to Cambridge in the summer of 1956. He took up the position of **Research Associate** -- the entry-level MIT senior-staff rank, equivalent in 1956 to a tenured Associate Professor in many other research universities. By the early 1960s he had been promoted to **Professor**.[^mitpromotion] The department was housed at that point in **Building 24**, the older brick structure on the main MIT campus along Massachusetts Avenue. In 1964 the department moved into the brand-new **Cecil and Ida Green Building (Building 54)** -- I.M. Pei's 18-story reinforced-concrete tower at the eastern edge of the campus, which would remain the tallest building in Cambridge until 2019 and would house the Department of Earth, Atmospheric and Planetary Sciences (the post-1983 successor to the Department of Meteorology) to this day.

<figure class="align-center" style="width: 70%;">
  <img src="{{ '/assets/images/MIT_Green_Building_2017.jpg' | relative_url }}" alt="MIT Green Building (Building 54), I.M. Pei, 1964." />
  <figcaption>The Cecil and Ida Green Building -- MIT Building 54 -- designed by I.M. Pei and constructed 1962-1964. Eighteen stories, ninety metres, the tallest building in Cambridge from 1964 until 2019. The MIT Department of Meteorology moved in in 1964; Phillips's office and the rest of his career here belong to this building, including his chairmanship 1970-1974. Three of the four chairmen who served between 1956 and 1981 -- Phillips, Charney, Lorenz -- had their primary offices in the Green Building. The pre-1964 work, including Phillips's 1957 sigma-coordinate paper and the 1959 nonlinear-instability paper, was done across the campus in the older Building 24. Photo: Beyond My Ken on Wikimedia Commons, 2017, CC BY-SA 4.0.[^greencredit]</figcaption>
</figure>

Phillips's MIT scientific output between 1956 and 1974 is dense enough that a comprehensive treatment would itself require a separate post. The shape of it: he wrote roughly one major theoretical paper per year, served as co-editor of the *Journal of the Atmospheric Sciences* for substantial stretches, taught the graduate quasi-geostrophic dynamics course, supervised a small cohort of PhD students who would go on to senior positions across the field, and -- in 1970 -- accepted the department chairmanship from the retiring Houghton.

The major theoretical contributions during this period, in chronological order:

**(1) The sigma coordinate, 1957.** **Phillips (1957), "A coordinate system having some special advantages for numerical forecasting," *Journal of Meteorology* 14, 184-185**. The paper is *two pages long*. In those two pages Phillips defined what is now universally called the **sigma coordinate**:[^sigma57]

$$\sigma = \frac{p - p_T}{p_S - p_T}$$

where $p$ is pressure, $p_S$ is the surface pressure at that horizontal location, and $p_T$ is a fixed model-top pressure (zero in Phillips's original form). The coordinate ranges from $\sigma = 0$ at the model top to $\sigma = 1$ at the ground -- everywhere, regardless of orography. The plain-language picture: instead of using *pressure* as a vertical coordinate (which is what 1950s NWP had been doing, with the well-known problem that the 1000 hPa surface intersects the Rockies and the 700 hPa surface intersects the Tibetan Plateau, so that you have to interpolate "below ground" or apply elaborate boundary conditions at mountain ranges), use a coordinate that *follows* the topography. The price you pay is that the vertical advection operator picks up extra terms involving the time evolution of surface pressure; the benefit is that mountain boundaries become coordinate surfaces and the boundary condition is trivial.

Sigma became, within a decade, the standard vertical coordinate of essentially every operational atmospheric model in the world. NMC's six-layer primitive equation model (operational from 1966, see Post 40 on [Shuman at Suitland](/weather/hpc/history/2026/05/15/Seventeen-years-at-Suitland.html)), the [UK Met Office model on the IBM 360/195](/weather/hpc/history/2026/05/14/Thirty-eight-years-on-the-sphere.html), the [GFDL spectral GCMs of Smagorinsky and Manabe](/weather/hpc/history/2026/04/13/The-forecast-that-reached-the-Nobel.html), the early ECMWF spectral model (1979), the JMA models, the BMRC model in Melbourne, NMC's spectral GFS from 1980 onward -- all used sigma. The vertical coordinate of Phillips 1957 was the operational standard for roughly twenty-five years before it began to be superseded.

The successor: the **hybrid sigma-pressure coordinate** introduced by **Adrian Simmons and David Burridge** at ECMWF in **1981** -- "An energy and angular-momentum conserving vertical finite-difference scheme and hybrid vertical coordinates," *Monthly Weather Review* 109, 758-766.[^simmons81] The hybrid scheme blends pure sigma in the lower troposphere (where the terrain-following property is needed) with pure pressure in the upper atmosphere (where pure sigma's tilted-coordinate-surface problem causes pressure-gradient errors over high mountains). Modern ECMWF, NCEP GFS, and Met Office Unified Model all use hybrid sigma-pressure. The eta coordinate introduced by **Fedor Mesinger** in 1984 and operationalised in NMC's Eta model in June 1993 represents a different, step-mountain succession. All three coordinates -- pure sigma, hybrid sigma-pressure, eta -- descend from Phillips's 1957 two pages.

That a foundational coordinate system for atmospheric modelling came out of a two-page communication in *Journal of Meteorology* in 1957 is one of the more striking facts in the history of NWP. Phillips would later say that his sigma paper was "two pages, twice the length of the longest section in the average operational manual." The compactness is the point. He had not invented a new dynamical framework; he had invented a coordinate transformation that, by changing the variable in which the equations were expressed, eliminated the orographic boundary problem definitionally. The paper required no figures, no derivations of new theorems, no benchmarks; the transformation itself was the result, and it could be stated in a paragraph and used in a model the next afternoon.

**(2) Nonlinear computational instability, 1959.** **Phillips (1959), "An example of non-linear computational instability," in B. Bolin (ed.), *The Atmosphere and the Sea in Motion* (Rossby Memorial Volume), Rockefeller Institute Press, pp. 501-504**.[^nci59] The Rossby Memorial Volume was compiled to honour Rossby on his sixtieth birthday and published shortly after his death (Rossby died at his desk in Stockholm in August 1957 of a heart attack at age fifty-eight). Phillips's contribution, a four-page chapter in a thousand-page book, would turn out to be one of the most consequential pieces of the volume.

The problem Phillips diagnosed in the 1959 chapter was the one his own 1956 GCM had revealed: the model had blown up at about day 25 despite satisfying the von Neumann linear stability criterion. The blow-up was real -- the kinetic energy of the simulated atmosphere grew without bound -- and it was not a software bug or a hardware fault. Phillips initially suspected truncation error from finite differencing and tried adding lateral eddy viscosity to damp the smallest scales; this delayed the catastrophe by a few days but did not prevent it.

Three years of analysis produced the diagnosis: **aliasing**. The quasi-geostrophic vorticity equation contains *nonlinear advection terms* -- products of velocity gradients with vorticity. When two waves of wavenumber $k_1$ and $k_2$ interact through such a product, they generate waves at the sum and difference wavenumbers $k_1 + k_2$ and $|k_1 - k_2|$. On a discrete grid of spacing $\Delta x$, the maximum wavenumber that can be represented is **$k_{\max} = \pi/\Delta x$** (the Nyquist wavenumber). If $k_1 + k_2 > k_{\max}$, the resulting wave cannot be resolved by the grid. Instead it is **aliased** -- mapped onto a resolvable wavenumber $2k_{\max} - (k_1 + k_2)$. The aliased wave is a fiction. It does not exist in the continuous physical system. But the discrete equations propagate it forward in time, where it interacts again, generating still more aliased waves. Energy accumulates at the shortest resolvable scales. The simulation explodes.

This is not the linear stability problem that von Neumann's classical analysis addresses. The CFL condition (Courant-Friedrichs-Lewy 1928) governs the time-stepping of single waves; aliasing is a structural problem of the *spatial* discretisation in nonlinear systems and is invisible to single-wave analysis.

Phillips's fix in the 1959 paper: transform the grid-space solution into a Fourier series, truncate everything above $k_{\max}/2$, and transform back. This **dealiased** the grid representation -- since quadratic interaction now generated only wavenumbers up to $k_{\max}$, no aliasing was possible. With this filter Phillips's 1956-style GCM could be integrated indefinitely. The 1959 paper is the first foothold of spectral methods in atmospheric modelling. **William Bourke** at Australia's Bureau of Meteorology Research Centre in 1972 and **Steven Orszag** at MIT in 1970 would develop full spectral models exploiting the same dealiasing insight; **Akio Arakawa** at UCLA in 1966 would publish "Computational design for long-term numerical integration of the equations of fluid motion" (*J. Computational Physics* 1, 119-143), introducing an alternative grid-point cure -- the **energy- and enstrophy-conserving Arakawa Jacobian** -- that controls aliasing's consequences by ensuring the discrete operator inherits the conservation properties of the continuous system.[^arakawa66]

The Phillips-1959-versus-Arakawa-1966 division would shape the structure of every later atmospheric modelling group. Spectral models -- ECMWF, JMA, NCEP global, the Australian BMRC -- pursued Phillips's dealiasing route. Grid-point models -- the NCAR CCM and its CESM successor, GFDL, the UCLA Mintz-Arakawa line -- used Arakawa-conserving schemes. Both lineages descend from the 1959 four-page chapter. As **Steve Easterbrook** wrote in his 2019 Phillips memoir on his *Serendipity* blog, the 1959 NCI diagnosis is "the foundational discovery for all subsequent atmospheric modelling."[^easterbrook] Without it, no GCM-style integration could have been run beyond a few weeks on any computer of any era.

**(3) The 1960 Tellus paper on primitive-equation initialisation.** **Phillips (1960), "On the problem of initial data for the primitive equations," *Tellus* 12, 121-126**.[^tellus60] The full hydrostatic primitive equations admit both slow meteorological Rossby modes and fast gravity-inertia waves. If you initialise a model from observed wind and pressure fields that are not in geostrophic balance, the model immediately generates large-amplitude gravity-inertia oscillations that obscure the meteorological signal -- this had been the failure mode of Richardson's 1922 hand-computed forecast and the reason every numerical forecast through the 1950s had used the *filtered* quasi-geostrophic equations instead of the full primitive equations.

Phillips's 1960 paper analysed why **Karl Hinkelmann's** geostrophic initialisation (1951) reduced the gravity-wave noise but did not eliminate it: even with geostrophic initial winds, the gravity-inertia waves still had amplitude of order $\epsilon$ (the Rossby number, about 0.1 in midlatitudes); the amplitude could be driven to $\epsilon^2$ only by additionally specifying that the divergence is non-zero and matches the value implied by the quasi-geostrophic omega-equation. Phillips's 1960 result was the theoretical foundation for **balance-equation initialisation** -- the method **Charney** had used in his 1955 follow-up to the ENIAC forecasts to suppress gravity waves -- and is the seed of every modern initialisation procedure: **normal-mode initialisation** (Machenhauer 1977, Baer 1977, Daley 1979), **digital-filter initialisation** (Peter Lynch and Huang 1992), and modern **variational data assimilation** (3DVar from the early 1990s, 4DVar from the late 1990s).[^modernda] Lynch's 2006 textbook *The Emergence of Numerical Weather Prediction* devotes a chapter to Phillips 1960 as the origin point of all atmospheric initialisation theory.

**(4) The 1963 Reviews of Geophysics synthesis.** **Phillips (1963), "Geostrophic motion," *Reviews of Geophysics* 1, 123-176**.[^rev63] Fifty-four pages of comprehensive synthesis: scale analysis, derivation of the quasi-geostrophic system, energetics, geostrophic adjustment, Rossby-wave theory, applications to forecasting and to Gulf Stream meanders. The 1963 review distinguished **Type 1** geostrophic motion (horizontal scales much smaller than Earth's radius, classical QG, beta-plane derivable) from **Type 2** **planetary geostrophic motion** (horizontal scales comparable to Earth's radius, where the variation of the Coriolis parameter is leading-order and the beta-plane breaks down). The Type-2 framework would be central to the planetary-scale climate-theory work that followed in the 1970s and 1980s, including the ocean-circulation work of **Joseph Pedlosky** (Pedlosky's 1979 textbook builds on Phillips 1963) and **Geoffrey Vallis** (whose 2006 textbook builds on both Pedlosky and Phillips).

The 1963 review is, in effect, **the Phillips textbook**. He never wrote a stand-alone textbook in his career; the 1963 *Reviews of Geophysics* article became the de facto graduate-textbook synthesis of quasi-geostrophic theory and remained so for two decades, until **James Holton's** *An Introduction to Dynamic Meteorology* (first edition 1972, current fifth edition 2013) supplemented it in classroom use.

**(5) The 1958 Appalachian storm revisited.** **Phillips (1958), "Geostrophic errors in predicting the Appalachian storm of November 1950," *Geophysica* 6, 389-405**.[^appalach58] Published in a special issue commemorating Erik Palmen's sixtieth birthday. Phillips revisited the Thanksgiving 1950 storm one more time, comparing his original two-layer dissertation forecast against Charney's later three-level model results. The conclusion: Charney's three-level computations did not contain the additional resolution gains he had thought; the essential cyclogenesis had already been present in the two-level model, with the appearance of three-level superiority arising from a coincidental error in the geostrophic initial-winds estimate at the upper level. Phillips was correcting his former boss in print, civilly and quietly. Charney and Phillips remained intimate professional collaborators until Charney's death from lung cancer in June 1981.

**(6) The Charney-Phillips vertical grid.** A staggered finite-difference grid arrangement for the quasi-geostrophic equations -- streamfunction (or geopotential) at layer midpoints, temperature and vertical velocity at layer interfaces -- that minimises spurious computational modes. Implicit in the 1953 Charney-Phillips paper and later codified and named, in contrast to the alternative **Lorenz grid** (streamfunction and temperature on the same levels) introduced in Lorenz's 1960 paper "Energy and numerical weather prediction." The Charney-Phillips and Lorenz grids are still the two standard choices in modern modelling textbooks for the placement of thermodynamic variables in vertically discretised atmospheric models, with active debate over their relative merits continuing into the 2020s.[^cpgrid]

By **1970** Phillips's principal scientific contributions to NWP theory were largely behind him. He was forty-seven, a senior figure of the discipline, the author of the 1956 GCM paper and the sigma coordinate and the nonlinear-instability diagnosis and the primitive-equation initialisation theory and the comprehensive QG synthesis of 1963. He had been an Alfred P. Sloan Foundation Research Fellow in 1961.[^sloan] He was a regular consultant to NCAR and to the National Academy of Sciences panels on numerical weather prediction. He had supervised PhD students -- the publicly listed cohort includes **Peter J. Webster** (now at Georgia Tech, monsoon dynamics and ENSO), **Antonio Divino Moura** (Brazilian meteorologist, later 2018 IMO Prize laureate), **Anthony Hollingsworth** (later head of ECMWF data assimilation, co-leader of Phillips's 1989 oral history), **Mankin Mak** (Illinois, atmospheric frontal dynamics), and **William Blumen** (Colorado, mesoscale dynamics).[^students]

In 1970, when Houghton retired from the MIT meteorology chairmanship, Phillips agreed to succeed him. **Jule Charney**, the obvious internal candidate, was at that point deeply committed to **GARP** -- the **Global Atmospheric Research Programme** -- and had been head of its NAS US Committee since 1966. Charney was not available for administrative work. Phillips was the natural alternative: senior enough, sufficiently established scientifically (he would receive the **Rossby Medal** the following year), and willing to do the four-year stretch.

The Rossby Medal came in **1971**, awarded by the American Meteorological Society as its highest scientific honour. The citation -- the AMS Rossby Medal citation is one of the more direct lists of permanent contributions an individual citation has carried in twentieth-century atmospheric science -- read:[^rossbymedal]

> For his introduction of new lines of study which have served to enlarge the scope of dynamic meteorology, his construction of a two-layer model making numerical prediction of developing systems feasible, and his diagnosis of nonlinear instability and prescription for dealing with it, permitting numerical simulation of the general circulation, which he had previously pioneered to be extended to infinite range.

The citation enumerates three contributions in one sentence: the two-layer model (Chicago thesis 1951, Charney-Phillips 1953, Phillips 1954), the GCM experiment (1956), and the diagnosis-and-cure of nonlinear instability (1959). All three were behind Phillips by 1971. He was forty-seven when the medal was announced; he would have one more major intellectual phase ahead of him, but it would happen in an operational rather than an academic setting.

He was elected to the **National Academy of Sciences in 1976**, two years after he had left MIT for the operational world.[^nas76] The 1976 NAS election is the moment that the briefing for this post had originally mis-dated as the year of the Rossby Medal; the correction matters because the timing tells you something about the order in which the academy and the AMS chose to recognise his work.

Of all the years of Phillips's life, the four-year stretch as MIT chair (1970-1974) is the one for which the historical record is thinnest. Phillips himself wrote little about his chairmanship -- no published reminiscence, no archived recollection in the obituary literature. The likeliest interpretation is that he ran the department competently, presided over the move into the new fields of the late 1960s and early 1970s (data assimilation, satellite observations, climate sensitivity, the early ocean-atmosphere coupling work that would mature in the 1980s), and did not enjoy administrative work enough to extend his term. The natural sequel would have been to retire from the chair and continue his research at MIT through the rest of his career. He did not do that. He left.

## 6. Why Phillips left MIT in July 1974

The literature does not give a clean answer to the question that any reader of the foregoing should now be asking: why did a fifty-one-year-old full professor and former department chair, at the top US academic atmospheric-science department, with the Rossby Medal in his pocket and NAS election presumably imminent, leave Cambridge in mid-1974 for a senior staff position at a federal operational forecasting centre in Maryland?

The obituaries do not say. Phillips's 1989 oral history glosses the move pragmatically -- approached by the NMC, offer was attractive, operational pull was real -- but does not analyse the deeper motivation. The MIT News obituary written at his death in 2019 elides the question entirely.[^mitobit]

The best available reconstruction has three components.

*Operational pull.* Phillips had been an operational forecaster in the Azores in 1944-46. The experience had been formative; it was, by his own account in the 1989 oral history, what had pulled him from chemistry to meteorology. He had carried the operational forecaster's perspective through his Princeton and MIT years; his 1956 GCM paper itself contained the sentence "It was my understanding that it was the success with this storm [the 1953 Charney-Phillips two-layer forecasts] that convinced the Weather Bureau, the Air Force, and the Navy to set up the original version of the NMC in 1954." He was not a pure academic. The pull of operational meteorology was real and long-standing.

*A specific scientific problem.* The data-assimilation problem -- the coherent statistical-dynamical integration of observations and model into a continuously updated atmospheric analysis -- was the dominant open problem in operational NWP by 1974. The European Centre for Medium-Range Weather Forecasts was about to begin construction (the ECMWF convention had been signed in 1973; the centre would open in Bracknell, then move to Reading in 1979). Operational [optimal interpolation](/weather/hpc/history/2026/05/15/Seventeen-years-at-Suitland.html) was being deployed at multiple centres. The theoretical structure was wide open; nobody yet had a clean variational formulation, the statistical underpinnings of the geostrophic-mode covariance assumption were unworked, and the relationship between model balance and observation balance was a thicket. This was a problem on which Phillips's theoretical depth could be turned to operational benefit. From a university chair the work was hard; from inside an operational centre it was tractable.

*The MIT department was in good hands.* Charney was about to take the chairmanship (he served 1974-1977). Lorenz would succeed Charney (1977-1981). The intellectual life of the department was not going to suffer from Phillips's departure. He was leaving an academic department in robust health to enter an operational centre at a pivotal moment.

That said, the move was unusual enough to be worth noting in its own right. Most of the IAS-Princeton cohort had gone the other way: Smagorinsky to GFDL, Charney to MIT's theoretical seminars, Mintz at UCLA, Manabe at GFDL Princeton. **Phillips alone reversed direction in mid-career**, taking the operational job at age fifty-one and putting his theoretical authority in service of the daily forecast suite. The reversal is the second of the two distinctive structural moves of his career: in 1956 he went from operational meteorology (the Azores, the Stockholm BESK forecasts) to pure theory (IAS and MIT); in 1974 he went back. The career arc is a hairpin.

## 7. NMC, July 1974 - mid-1980s

Phillips joined the **National Meteorological Center** in Camp Springs, Maryland, in **July 1974** as **Principal Scientist** of its **Development Division**. The Director at his arrival was **Frederick G. Shuman**, who had been director since April 1964. (Post 40 of this series, [*Seventeen Years at Suitland*](/weather/hpc/history/2026/05/15/Seventeen-years-at-Suitland.html), covered Shuman's directorship in detail.) Shuman would retire in January 1981 and would be succeeded by **William D. Bonner**.[^nmcdirectors]

When Phillips arrived in July 1974, NMC was technically still housed at **Federal Office Building 4 (FOB-4) in Suitland**, Maryland -- the same location it had occupied since its founding in 1958. The big move was imminent. The **World Weather Building** at 5200 Old Auth Road in Camp Springs, about two miles south of FOB-4, was being completed; it was formally **dedicated on 22 October 1974** by NOAA Administrator **Robert M. White**.[^wwb74] The forecaster move began **in early 1975**; by the end of January about 260 NMC staff had relocated to the second, third, fourth, and sixth floors of the new building. The mainframes were too large to move and remained at FOB-4; output was transmitted electronically the two miles south to Camp Springs. (FOB-4 housed NMC's computers until 1999.) Phillips's office was in the World Weather Building in Camp Springs from early 1975 onward.

<figure class="align-center" style="width: 70%;">
  <img src="{{ '/assets/images/World_Weather_Building_1974.png' | relative_url }}" alt="The World Weather Building, Camp Springs, Maryland, ca. 1974." />
  <figcaption>The World Weather Building at 5200 Old Auth Road, Camp Springs, Maryland -- the NMC headquarters from early 1975 onward, with computers remaining at the older Federal Office Building 4 in Suitland two miles to the north. Phillips's office occupied the World Weather Building for his entire NMC career, from early 1975 through retirement in the mid-1980s. The building was dedicated on 22 October 1974 by NOAA Administrator Robert M. White and was the operational home of the National Meteorological Center -- and from 1995 onward of the National Centers for Environmental Prediction -- through to NCEP's 2012 relocation to College Park. Photo: NOAA, public domain (PD-USGov-NOAA).</figcaption>
</figure>

What did Phillips do at NMC? Three things, separable in retrospect though not always separable at the time.

### The Nested Grid Model

The most direct of Phillips's NMC technical contributions was the **Nested Grid Model (NGM)**, written up in **NOAA Technical Report NWS 22, "The Nested Grid Model"** in **April 1979** under sole authorship by Phillips.[^ngm79] The NGM was a **hemispheric primitive-equation model with one or two interior rectangular nested grids of progressively finer resolution over North America**, designed to provide higher-resolution forecasts over the United States without the prohibitive computational cost of a uniformly fine global mesh.

The technical specification: the outer **A grid** was a polar stereographic projection covering the Northern Hemisphere on a coarse mesh; the inner **B grid** was a rectangular nest of finer mesh inside A, fully two-way interactive (after each outer-grid time step the inner grid's boundary points were interpolated from A; after each inner-grid sub-step, A's interior points near the nesting boundary were updated from B); an optional innermost **C grid** could be embedded inside B at still finer resolution. The vertical coordinate was a variant of Phillips's own 1957 sigma -- specifically $\sigma = 1 - p/H$. The numerical scheme was a second-order accurate finite-difference Lax-Wendroff scheme. Special physics had to be added at the Himalayas, where the steep orography of the Tibetan Plateau caused gravity-wave radiation that the basic scheme could not properly damp.

The NGM was algorithmically novel for its two-way nesting. Static one-way embedding -- where a coarse outer grid forces the boundary conditions of a fine inner grid but receives no feedback -- had been standard practice. Phillips's NGM did the harder thing: the inner grid's effect on the outer-grid solution was iteratively fed back to keep the two consistent, requiring careful treatment of the interpolation operators to avoid generating spurious waves at the nest boundary. The 1979 NWS 22 report is the canonical technical reference for the algorithmic details.

NGM was implemented operationally at NMC in **March 1985** as the regional forecast component of the **Regional Analysis and Forecast System (RAFS)**. The development team -- credited in Hoke, Phillips, DiMego, Tuccillo, and Sela 1989 -- was **J. E. Hoke**, **N. A. Phillips**, **Geoff DiMego**, **J. J. Tuccillo**, and **Joseph Sela**.[^hokeetal89] The team membership is the cohort of NCEP scientists who would dominate operational US NWP through the 1990s. Geoff DiMego in particular would carry the regional-modelling line from NGM through the Eta model (operational June 1993) to the modern NAM, a continuous lineage of operational regional forecasting at NMC/NCEP that runs from 1985 to the present.

The nickname for the NGM in NMC corridors was **"Norm's Great Model"** -- a play on the NGM initials and Phillips's first name. The nickname appears in the MIT News obituary, in the Rivet Funeral Home obituary, and in the Nashua Telegraph obituary; it is documented in multiple independent sources and is the most direct piece of evidence about how Phillips was regarded by the operational forecasters who used the model.[^ngmnickname] The nickname is affectionate, not satirical; the operational forecasters liked the NGM, and they associated it personally with Phillips.

The NGM's operational lifetime was exceptional: **March 1985 until 3 March 2009**, when its Model Output Statistics products were finally discontinued (the model itself had been retired in the late 1990s after the Eta model replaced it as the primary regional guidance in June 1993, but its bias-corrected outputs continued to be produced as a verification baseline). Twenty-four years of operational regional forecasting on a single underlying model is a long run. By way of comparison, the LFM that NGM replaced ran 1971-1991 (twenty years); the Eta that replaced NGM as primary guidance ran 1993-2006 in its core form (thirteen years); the NAM (the Eta's WRF-NMM successor) has been operational since 2006 and is still running.

### Data assimilation: the senior scientific voice

The other major thread of Phillips's NMC work was data assimilation -- the integration of operational observations with the model first-guess into a continuously updated atmospheric analysis. The state of operational analysis at NMC in 1974 was **Cressman's successive correction method** (Cressman 1959, refined through the 1960s) -- a sequence of grid-point corrections each weighted by a radius-of-influence function. Cressman is local, ad-hoc in its weighting, and does not propagate observation information across long correlation lengths.[^cressman]

The transition to **optimal interpolation (OI)** -- the statistical objective-analysis framework that **Lev Gandin** had developed in the Soviet Union in 1963 -- was beginning to be implemented operationally at NMC in the late 1970s. The canonical implementation paper is **McPherson, Bergman, Kistler, Rasch, and Gordon (1979), "The NMC operational global data assimilation system," *Monthly Weather Review* 107, 1445-1461**, with the companion theoretical paper **Bergman (1979), "Multivariate analysis of temperatures and winds using optimum interpolation," *Monthly Weather Review* 107, 1423-1444**.[^mcpherson79] Phillips was not a co-author on either of these papers; the day-to-day work was Ronald McPherson's, Kenneth Bergman's, and their team's. But Phillips was the Principal Scientist of the Development Division whose office signed off on the development direction. The strategic decision to migrate from Cressman to OI -- a decade-long programme that gradually replaced the legacy analysis system -- was made under Phillips's scientific leadership.

His own most-cited contribution to operational OI theory came later in his NMC tenure: **Phillips (1986), "The spatial statistics of random geostrophic modes and first-guess errors," *Tellus A* 38, 314-332**.[^tellus86] This is the closest Phillips came to publishing a result that was simultaneously theoretically deep and operationally consequential. The 1986 paper analysed the **statistical structure of forecast errors** in operational OI -- a critical theoretical input because OI requires a model for the error covariance of the first-guess (background) field.

Phillips's hypothesis: in a data-assimilation system with excellent forecast and analysis components and frequent access to good data, the first-guess errors should be statistically similar to an ensemble of random *slow modes* (the linearised slow-Rossby-wave modes of the model) with **equipartition of energy** among the modes. He then computed the covariance statistics that this hypothesis implied on a constant-Coriolis-parameter plane and derived several specific predictions:

- First-guess errors should have wind and geopotential variance **increasing with elevation**.
- The horizontal velocity scale of the error field should also **increase with elevation**.
- The vertical correlation should be **sharper for wind than for geopotential**.
- The "separable mathematical models used to represent correlations in operational practice" should **misrepresent some important features** of the error field.

The last finding is the load-bearing one. Operational OI in the early 1980s used **separable correlation models** -- the horizontal and vertical correlations were factored into independent functions, in part because that was computationally tractable. Phillips 1986 showed that the slow-mode equipartition assumption produces fundamentally *non-separable* correlations, and that real first-guess errors observed over North America fit the non-separable model better than the separable one. The implication was that NMC's operational OI system needed retuning, and -- in retrospect -- that the entire separable-correlations framework was a transitional state that the field would need to move past.

The 1986 *Tellus A* paper is, in the technical literature, what might be called **"the Phillips correction"** to vertical-correlation models in operational forecast-error covariance estimation. The terminology is not universally used; the canonical text on background-error covariance modelling, **Bannister (2008), "A review of forecast error covariance statistics in atmospheric variational data assimilation. I: Characteristics and measurements of forecast error covariances," *QJRMS* 134, 1951-1970**, treats Phillips 1986 as a foundational reference.[^bannister] The paper is the bridge between the 1956 GCM Phillips of the IAS-MIT years and the operational data-assimilation Phillips of the NMC years. It is also, conceptually, the bridge from Post 43 (the present post) to the future of data assimilation in this series.

### The NMC trainee cohort

Phillips's third major NMC contribution -- harder to document with single citations but visible in the lineage of operational American NWP -- was the cohort he trained or directly mentored at NMC in the 1970s and 1980s. The list:[^trainees]

- **Ronald McPherson** -- NMC scientist, lead author of the 1979 operational OI paper; later Acting Director of NMC, then Director of NCEP from 1990 to 1998.
- **Eugenia Kalnay** -- joined NMC in 1987 from GSFC; would be appointed NMC/NCEP Director in 1994 and remain in the role until 1997; subsequently led the NCEP/NCAR Reanalysis Project (one of the most-cited climate-science datasets in history) and joined the University of Maryland as Distinguished University Professor.
- **Stephen Lord** -- NMC scientist from the late 1970s; would lead NCEP's Environmental Modeling Center (EMC) from 2003 to 2010, presiding over the modernisation of the GFS during the 2000s.
- **Geoff DiMego** -- NMC scientist; NGM development team member with Phillips on the 1985 implementation; would lead EMC's regional modelling branch and the Eta-to-NAM transition through the 1990s and 2000s.
- **John Derber** -- NMC scientist, the principal architect of the 3DVar and later GSI (Gridpoint Statistical Interpolation) data-assimilation systems that succeeded OI at NMC/NCEP through the 1990s and 2000s.
- **Joseph Sela** -- NMC scientist from 1975 onward, the architect of the **spectral Global Forecast System** at NMC. Sela's spectral model went operational in August 1980 with R30 triangular truncation and 12 vertical sigma layers; it became the GFS, which has been the US operational global model in continuous evolution from 1980 to the present.[^selagfs] Sela worked at NMC until his death in 2010.
- **Joseph Brown, William Bourke** (Australian visitor), **Jordan Alpert**, **Glenn White** -- the broader Development Division core.

This is the **NCEP lineage**. Through it, Phillips's influence flows into every operational US numerical forecast made today. The current **GFS, NAM, GEFS, HRRR, RAP** -- every NOAA operational model in 2026 -- runs sigma or hybrid-sigma coordinates (Phillips 1957), uses dealiasing or energy-conserving schemes (Phillips 1959 or Arakawa 1966), employs balance-equation initialisation theory in its data-assimilation cycle (Phillips 1960), and uses statistical objective analysis with first-guess covariances structured along lines that Phillips 1986 made explicit.

### The retirement year

Phillips retired from NMC in the mid-1980s. The exact year is genuinely disputed in the published record and cannot be resolved from public sources.[^retirement] The MIT News obituary published at his death is internally inconsistent on the point: it contains the sentence "In July of 1974, Phillips left for the National Weather Service at the National Meteorological Center... retired in 1984" *and* the separate sentence "He stayed there for four years before retiring in 1988." (1974 + 4 = 1978, not 1988; the arithmetic does not close.) The Rivet Funeral Home obituary gives 1984; the family obituary on the Nashua Telegraph site is silent on the date. The most defensible reconstruction is that Phillips formally retired from his full-time NMC appointment in **1984** (the Rivet obituary date, which fits with his sixty-fifth birthday in July 1988 as a possible federal-retirement marker), but continued in a research-emeritus or consulting capacity through 1988. His 1986 *Tellus A* paper carries the NMC affiliation, confirming active scientific engagement through at least mid-1986. The implementation of NGM in 1985 and its operational entry under his name in the corridor nickname suggest continuing engagement at least through 1987.

For purposes of this post the safer phrasing is **"the mid-1980s."** A federal-personnel record could resolve the question; the published obituary literature cannot.

## 8. Personality, family, and the music

The dominant adjective in the available record on Phillips's personality is *quiet*. The Rivet Funeral Home obituary, written by the family in 2019, is the most direct biographical document:[^rivetdetail]

> [He] will be remembered for his mischievous sense of humor, his intellect, his great integrity and his deep commitment to the wellbeing of this earth.

The Peter Lynch tribute in the *Irish Times* and on his *ThatsMaths* blog at Lynch's death-month memorial added a personal recollection:[^lynch2019]

> I had the privilege to meet Phillips -- known to all as Norm -- at a conference in Potsdam in 2000 and greatly enjoyed his brilliant insights into complex aspects of the earth's climate system.

The four-word phrase that runs through these accounts -- "known to all as Norm" -- is the only nickname that surfaces in any obituary. He was Phillips on the title page of every paper he wrote; he was Norm to his colleagues and friends. The MIT obituary, the Nashua Telegraph obituary, the Franklin Institute citation, and Lynch's blog all use the diminutive interchangeably with the surname.

There are three sub-themes worth pulling out separately.

### The French horn

Phillips's life-long musical hobby is the most consistently mentioned biographical detail outside the scientific record. He played French horn at amateur orchestral and operetta level throughout his life. He met Martha through music. He continued playing in Camp Springs, Maryland, during his NMC years (the precise ensemble he played in there is not recorded), and in Merrimack, New Hampshire, after retirement (the family obituary specifically mentions continuing musical activity).

The 1944-1945 Chicago operetta where he met Martha was -- the family obituary records -- a community amateur production. Phillips would have been a uniformed Army Air Force second lieutenant on home leave from Chanute Field or possibly already at Grenier Field; Martha would have been a Chicago resident of the same age, the daughter of (the record does not say what occupation her parents had, but the family obituary is silent on professional standing, suggesting an ordinary background). They were both there to play French horn in the orchestra. That is essentially everything the obituary record preserves of the meeting.

The music kept going. In Camp Springs, in Merrimack, in his eighties, the French horn was always in the house. Music was not a hobby in the casual sense; it was a parallel mode of existence, as central to him as his quiet morning reading habit. Lynch in his 2019 tribute notes Phillips's musical activity in passing as a defining personality detail.

### Family

Phillips and Martha had three daughters:[^daughters]

- **Ruth (Phillips) Walsh** -- married to Stephen Walsh; predeceased her father.
- **Janet (Phillips) Grigsby** -- married to Phillip Grigsby; mother of Matthew and Christopher Grigsby.
- **Ellen (Phillips) Chasse** -- married to Dennis Chasse; mother of Derek (wife Jessica) and Keith Chasse.

There were grandchildren -- Stephen Walsh (wife Stefanie), Matthew Grigsby, Christopher Grigsby, Derek Chasse (wife Jessica), Keith Chasse -- and great-grandchildren Ryan Walsh, Riley Walsh, Morgan Chasse, and Travis Chasse. The family obituary closes: "all of whom gave him great delight."

The biographical record is conspicuously focused on the daughters; no son. The closely held family character of the Phillips household is consistent across multiple obituary sources: a long, stable marriage, three daughters, the grand- and great-grandchildren, the regular Sunday afternoon visits.

### Civic life in Merrimack

After retirement Phillips and Martha moved to **Merrimack, New Hampshire** -- a town of about 25000 on the Merrimack River, between Manchester and the Massachusetts border. The reasons for choosing Merrimack rather than (say) Cambridge or Princeton or Falmouth, Maine (the latter incorrectly given in some secondary sources) are not in the public record. New Hampshire is closer to Boston and to the Boston cultural and family network than (say) New Mexico or Florida would be; it has a quiet civic life that suits a reserved couple in their seventies. The family obituary mentions specifically Phillips's service on the **Merrimack Town Budget Committee** and his participation in **Exchange Club scholarship fundraising**. The civic engagement is in keeping with the Chicago-Swedish-Lutheran civic-mindedness that runs through every biographical layer of him.

Phillips's late years were spent in Merrimack with Martha. The family obituary states that Martha predeceased him; the date is not given. Phillips remained in Merrimack until late life and was at Grace House -- a long-term care facility in Windham, New Hampshire -- at the time of his death.

## 9. The thirty-year retirement, 1984/1988 - 2019

The retirement was substantively the longest phase of Phillips's life. He was sixty-one or sixty-five (depending on which retirement-year reading you accept) when he left NMC; he was ninety-five when he died at Grace House on **15 March 2019**.[^deathdate] Between those two dates, three or four decades, Phillips remained intellectually active, engaged with the AMS and NAS, and -- by the standards of long retirements in academic atmospheric science -- unusually productive.

### The Charney memoir, 1995

When Charney died on 16 June 1981, the National Academy of Sciences commissioned Phillips to write his **NAS Biographical Memoir**.[^chmemoir] It appeared in 1995 -- fourteen years later, a long gestation -- as **Phillips (1995), "Jule Gregory Charney, 1917-1981," *Biographical Memoirs* 66, 80-113**. The memoir is a substantial thirty-three-page essay that traces Charney's path through UCLA, Oslo, the IAS, and MIT; details the ENIAC forecast and its consequences; covers Charney's later work on monsoon dynamics, ocean circulation, and climate sensitivity (the 1979 Charney Report on CO2-induced climate change); and -- in passing, in the third person -- contains the "package deal" sentence that gives this post its title.

The Charney memoir is the single most important primary source for the history of the IAS Meteorology Project, of the 1956 MIT recruitment, and of the relationship between theoretical and operational meteorology in the postwar United States. It has been mined extensively by historians of NWP -- by **Frederik Nebeker** in his 1995 *Calculating the Weather*, by **Paul Edwards** in his 2010 *A Vast Machine*, by Lewis in his 1998 BAMS Phillips retrospective. Phillips drew on his personal experience as Charney's IAS colleague, his Chicago graduate-school overlap with Charney's visits, and decades of correspondence. The memoir is also, in a quiet way, **as much a self-portrait of Phillips's scientific worldview as it is of Charney's**: it returns again and again to Rossby waves, quasi-geostrophic theory, baroclinic instability; it is appreciative of synoptic meteorology but unsentimental about what it can and cannot do; it argues throughout that the mathematical physics of the atmosphere is the central explanatory framework. Charney's contribution, in Phillips's reading, is the demonstration that mathematical physics can predict atmospheric behaviour.

### The 2003 Benjamin Franklin Medal

In 2003 Phillips and **Joseph Smagorinsky**, his old IAS colleague from the 1951-1953 years, were jointly awarded the **Benjamin Franklin Medal in Earth Science** by the **Franklin Institute** in Philadelphia.[^franklin] The citation:[^franklincite]

> With Joseph Smagorinsky, for their major contributions to the prediction of weather and climate using numerical methods. Their seminal and pioneering studies led to the first computer models of weather and climate, as well as to an understanding of the general circulation of the atmosphere.

Smagorinsky and Phillips had been on the IAS Meteorology Project together from October 1951 (Phillips's arrival) to 1953 (Smagorinsky's departure for the Weather Bureau). They had taken different paths after 1953 -- Smagorinsky to GFDL where he led the first three-dimensional moist-physics general-circulation models of the 1960s, Phillips to MIT and then to NMC -- but their work had been complementary throughout. The 2003 medal, given to both jointly, acknowledged that complementarity. It was the last of Phillips's major scientific honours. Smagorinsky died two years later, in 2005.

### The 2005 Foucault pendulum paper

At age eighty-two Phillips published what would be his last academic publication: **Phillips (2005), "What Makes the Foucault Pendulum Move among the Stars?"** as a chapter in **M. R. Matthews, C. F. Gauld, and A. Stinner (eds.), *The Pendulum: Scientific, Historical, Philosophical and Educational Perspectives*, Springer, Dordrecht**.[^foucault] The chapter was a revised version of a paper Phillips had first published in French in *La Météorologie* in 2001 and in English in *Science & Education* in 2004.

The Foucault paper was a careful pedagogical treatment of the Foucault pendulum problem: why does the plane of oscillation appear to rotate in an Earth-fixed frame, what is the appropriate inertial reference frame, and how does the physics connect to the **Coriolis force** that drives atmospheric and oceanic circulation? Phillips treated the question with the same care he had given the 1957 sigma-coordinate question -- a small, well-defined problem in the foundations of classical mechanics, expounded in the form that would teach a physics student how to think about rotation. It is a quiet way for an eighty-two-year-old to spend his time. Some obituaries note that Phillips published a "final professional paper at age 90" (so c. 2013); this claim has not been verified against a specific publication and may refer to the 2004-2005 Foucault paper as remembered in obituary writing. The 2005 chapter is the latest readily verifiable major publication.

### The 1989 NCAR oral history

In **1989**, Phillips sat for an **85-page oral history interview** at the NCAR Archives in Boulder. The interviewers were **Anthony Hollingsworth** (Phillips's former MIT PhD student, by then head of ECMWF data assimilation), **Warren Washington** (NCAR), **Joseph Tribbia** (NCAR), and **Akira Kasahara** (NCAR). The transcript is held in the NCAR Archives and is accessible through OpenSky; Lewis 1998 quotes from it extensively.[^oralhist]

The oral history is the principal first-person Phillips source we have. The 1995 Charney memoir is Phillips on Charney; the 1989 oral history is Phillips on himself, in his own words, recorded at age sixty-six (so probably already retired from NMC at the time of the interview, depending on which retirement-year reading one accepts). The texture and detail of the Chicago years, the Azores wartime, the IAS arrival in 1951, the 1953 Stockholm visit, and the 1956 MIT move are all preserved in the 1989 transcript.

## 10. Death, 15 March 2019

Phillips died on **Friday, 15 March 2019, at Grace House in Windham, New Hampshire**, age ninety-five. He had suffered a stroke roughly two years earlier (so around 2017); the family obituary states that he died "peacefully," with his daughters present.[^deathfinal]

The memorial service was held on **Saturday, 29 June 2019, at 11:00 a.m., at Rivet Funeral Home, 425 Daniel Webster Highway, Merrimack, New Hampshire**. The family requested memorial donations to the **Michael J. Fox Foundation for Parkinson's Research** (suggesting that Parkinson's may have contributed to his decline; the family obituary does not state the cause of death explicitly) or to the **American Meteorological Society**.

Predeceased by him: Martha (Nissen) Phillips, his wife of seventy-three years; daughter Ruth Walsh; sister Alice (Phillips) Westphal. Surviving: daughters Janet Grigsby and Ellen Chasse; the grandchildren and great-grandchildren listed above.

The **MIT News obituary**, written on 16 May 2019 by Lauren Hinkel, called Phillips "a renowned atmospheric scientist who pioneered theoretical and computational approaches to numerical weather prediction" and quoted **Kerry Emanuel**: "Norm Phillips, with his colleagues Jule Charney and Edward Lorenz, brought MIT meteorology to international prominence. His seminal demonstration that one could simulate the general circulation of the atmosphere using a digital computer changed the face of weather and climate science forever."[^mitobitquote]

Lynch's *ThatsMaths* tribute appeared on **4 April 2019**, three weeks after Phillips's death, under the title "A Pioneer of Climate Modelling and Prediction." The *Irish Times* version, "A pioneer of climate modelling -- and maths," appeared the same week.[^lynchpost]

**Steve Easterbrook's** *Serendipity* tribute appeared **a few months later**, in May 2019, focusing on Phillips's foundational contributions to climate model design -- specifically the 1956 GCM, the 1957 sigma coordinate, and the 1959 nonlinear-instability diagnosis as the "three pillars" on which all subsequent atmospheric modelling rests.[^easterbrooktribute]

No published *Bulletin of the American Meteorological Society* memorial obituary surfaced in the standard searches for this post; the AMS may have one in preparation, or it may have appeared in a 2020-2021 volume that has not been indexed in the obituary searches consulted here.

## 11. The package deal in retrospect

Three threads worth pulling together at the end.

**First**: the 1956 package deal that gives this post its title was the institutional move on which the next thirty years of American academic atmospheric science depended. Without it, Lorenz might not have been at MIT in 1961 to discover chaos; without it, Charney would not have had Phillips to bounce ideas off through the GARP planning years; without it, the MIT chairmanship sequence Houghton-Phillips-Charney-Lorenz from 1942 to 1981 would not have been the sequence it was. The package deal is the institutional pivot point of the modern field.

**Second**: the 1974 reverse-direction move from MIT to NMC was the second of Phillips's two great structural choices. It was the move that made him not just a theoretical meteorologist but a theoretician of operational meteorology -- the rare figure who carried decades of academic depth into a daily-forecast operational setting. The NGM, the 1986 *Tellus A* first-guess error paper, the trainee cohort (Kalnay, Lord, DiMego, Derber, Sela, McPherson) -- all of these are consequences of the 1974 move. The thirty years of NCEP operational forecasting in the United States that followed Phillips's NMC arrival are, in lineage, his second career legacy. The first legacy was the 1956 GCM and the MIT department it helped catalyse. The second legacy was operational NCEP.

**Third**: the man himself, with his Chicago-Swedish heritage, his French horn, his quiet humour, his civic-mindedness, his Merrimack budget-committee service in retirement, was -- on every available reading -- precisely the kind of figure the discipline did not always know how to celebrate at the moment but came to value in retrospect. He was not Charney, who electrified rooms; he was not Lorenz, who quietly invented chaos in his office. He was the steady one in the corridor, the one who made the equations work on the machine, the one who took the chairmanship when it needed to be taken, the one who left Cambridge for Maryland when the operational problem needed someone of his depth, the one who wrote the 1995 Charney memoir that became the principal historical source for the field. The man, in his own quiet way, was the bridge.

And there is the closing motif. Sixty-three years after he sat in the orchestra pit of a Chicago operetta with a French horn next to a young woman named Martha Nissen, Phillips died at ninety-five in a New Hampshire long-term care facility. In the years between, he had built the first GCM, invented the sigma coordinate, diagnosed nonlinear computational instability, chaired the MIT meteorology department, designed Norm's Great Model at NMC, written the foundational covariance theory paper for operational OI, trained the NCEP cohort, written Charney's NAS memoir, and -- in retirement in Merrimack -- continued to play French horn, read about Sweden, serve on the town budget committee, and watch his three daughters and their families come and go on Sunday afternoons. The 1944 orchestra pit, in retrospect, was the first chapter of all of it. Two French horns in a Chicago operetta. He played French horn his whole life. So did Martha. There is something true and quiet about a discipline whose intellectual history begins, for one of its central figures, with music.

---

## Footnotes

[^cadetdate]: Phillips's 1989 NCAR oral history (interview by A. Hollingsworth, W. Washington, J. Tribbia, and A. Kasahara) records the Chanute commissioning date as 5 June 1944, the day before D-Day. The detail is also given in the Lewis 1998 BAMS appendix on Phillips's wartime service. Lewis, J. M., 1998: "Clarifying the Dynamics of the General Circulation: Phillips's 1956 Experiment," *Bulletin of the American Meteorological Society* 79(1): 39-60, accessed at https://journals.ametsoc.org/view/journals/bams/79/1/1520-0477_1998_079_0039_ctdotg_2_0_co_2.xml. The Lewis Appendix B is the published source for the wartime chronology.

[^operetta]: Rivet Funeral Home & Crematorium, Inc., "Obituary | Norman A. Phillips of Windham, New Hampshire," 2019, accessed at https://www.rivetfuneralhome.com/obituary/norman-phillips. The relevant sentence: "Phillips was also an accomplished French horn player, having met his beloved Martha when they both performed for an operetta in Chicago." The Nashua Telegraph obituary at https://www.nashuatelegraph.com/obituaries-memorials/obituaries/2019/03/24/norman-a-phillips/ contains the same detail.

[^death]: MIT News, "Norman Phillips, former meteorology department head, dies at 95," 16 May 2019, accessed at https://news.mit.edu/2019/norman-phillips-former-meteorology-department-dead-dies-0516. Wikipedia, "Norman A. Phillips," accessed at https://en.wikipedia.org/wiki/Norman_A._Phillips, gives the date as 15 March 2019. Both sources agree on Grace House in Windham, NH.

[^portraitcredit]: Wikimedia Commons file page, "Norman Phillips at Symposium on the 50th Anniversary of Operational NWP," accessed at https://commons.wikimedia.org/wiki/File:Norman_Phillips_at_Symposium_on_the_50th_Anniversary_of_Operational_NWP.jpg. The original source is the NCEP NWP-50 photo album at http://www.ncep.noaa.gov/nwp50/Photos/Wednesday/. The image is in the public domain as a work of a US federal employee (William G. Collins, NCEP/NOAA) acting in the course of official duties.

[^packagedeal]: Phillips, N. A., 1995: "Jule Gregory Charney, 1917-1981," in *Biographical Memoirs* (National Academy of Sciences) 66, 80-113. The "package deal" passage is on page 99. PDF accessed at https://www.nasonline.org/wp-content/uploads/2024/06/charney-jule-g.pdf.

[^birth]: Wikipedia, "Norman A. Phillips," accessed at https://en.wikipedia.org/wiki/Norman_A._Phillips, gives the birth date as 9 July 1923. The MIT News obituary at https://news.mit.edu/2019/norman-phillips-former-meteorology-department-dead-dies-0516 corroborates. The original briefing for this post gave 9 March 1923 in error; the July date is confirmed across multiple independent sources.

[^rivet]: Rivet Funeral Home, "Obituary | Norman A. Phillips," cited in footnote 2.

[^chicago40]: Lewis 1998, BAMS, p. 56: Phillips enrolled at the University of Chicago in autumn 1940 intending to major in chemistry. The detail is also in the Nashua Telegraph obituary.

[^enlist]: Lewis 1998, BAMS, Appendix B (the wartime chronology), gives the enlistment date as 15 March 1942.

[^chanutefour]: Lewis 1998, BAMS, p. 56, citing Phillips 1989 oral history: "Phillips graduated fourth in a class of 391" at Chanute Field on 5 June 1944. The detail is also in the MIT News obituary.

[^merewether]: Lewis 1998, BAMS, p. 56, footnote 5. Merewether's pre-war role as chief meteorologist of American Airlines is documented in Lewis's appendix.

[^marriage]: MIT News obituary, "Norman Phillips, former meteorology department head, dies at 95," 16 May 2019: "Martha (Nissen) Phillips, whom he married in 1945." No more precise date is given in the published record.

[^lewis1998]: Lewis 1998, BAMS, p. 56, citing Phillips 1989 NCAR oral history p. 4.

[^lewisplane]: Lewis 1998, BAMS, p. 56, citing Phillips 1989 NCAR oral history p. 6. The "Stevensville" in the original quote is presumably "Stephenville," Newfoundland; Lewis transcribes Phillips's spoken pronunciation.

[^discharge]: Lewis 1998, BAMS, p. 56, gives the discharge date as October 1946, with Phillips returning to Chicago that autumn. The MIT News obituary also gives October 1946.

[^byers]: National Academies of Sciences, Engineering, and Medicine, *Biographical Memoirs* Vol. 79, "Horace Robert Byers," accessed at https://www.nationalacademies.org/read/10169/chapter/5. Byers was associate professor (1940-1945), professor (1945-1965), and department chair (1948-1960).

[^palmen]: Palmen's Chicago years 1946-1948 are documented in Eliassen, A. (1986), "Erik H. Palmen 1898-1985," *Tellus A* 38, 99-104. Phillips's MSc work under Palmen is referenced in Lewis 1998, p. 56.

[^platzman]: Lewis 1998, BAMS, Appendix B (footnote 5 and footnote 6), confirms Platzman as Phillips's PhD advisor.

[^platzmanquote]: Phillips 1989 NCAR oral history, quoted in Lewis 1998 p. 60.

[^thesis25]: Phillips, N. A., 1951: "A Simple Three-Dimensional Model for the Study of Large-Scale Extratropical Flow Patterns," PhD dissertation, University of Chicago, 25 pp. The 25-page length is documented in Lewis 1998, p. 57.

[^charney48]: Charney, J. G., 1948: "On the Scale of Atmospheric Motions," *Geofysiske Publikasjoner* 17(2), 17 pp.

[^phillipsoral]: Phillips 1989 NCAR oral history, p. 10, quoted in Lewis 1998 p. 56.

[^eady]: Eady, E. T., 1949: "Long waves and cyclone waves," *Tellus* 1, 33-52. Phillips's independent derivation of the two-layer baroclinic instability criterion before reading Eady is documented in Lewis 1998, p. 57, footnote 6.

[^thanksgiving]: Lewis 1998, BAMS, p. 57: "Phillips's two-layer model of the Thanksgiving Day Storm was the first numerical weather forecast using a baroclinic model of the atmosphere." The case study would reappear in Charney-Phillips 1953 and in Phillips 1958.

[^charneyblackboard]: Lindzen, R. S., E. N. Lorenz, and G. W. Platzman (eds.), 1990: *The Atmosphere -- A Challenge: The Science of Jule Gregory Charney*, American Meteorological Society. The blackboard recollection is on p. 54 of the Lindzen-Lorenz-Platzman volume; the passage is quoted (and the source given) in the Phillips_scientific_arc research notes for this post.

[^iasarrival]: Institute for Advanced Study, "Norman Phillips" scholar profile, accessed at https://www.ias.edu/scholars/norman-phillips. Phillips's IAS record gives October 1951 to April 1956 as his Project membership dates. Lewis 1998 gives the arrival as August 1951, which is probably the date Phillips and family physically arrived in Princeton; October 1951 is the formal start of the IAS stipend cycle.

[^charneyenwiac]: Charney, J. G., R. Fjortoft, and J. von Neumann, 1950: "Numerical integration of the barotropic vorticity equation," *Tellus* 2, 237-254. Cross-link: this is the subject of [Post 1 of this series, on the man who tamed the equations](/weather/hpc/history/2026/03/29/The-man-who-tamed-the-equations.html).

[^iasmachine]: The hardware specifications of the IAS machine are documented in Nebeker, F., 1995: *Calculating the Weather: Meteorology in the 20th Century*, Academic Press, Chapter 5. The 1024-word, 40-bit Williams-tube memory and the 2048-word magnetic drum are standard references.

[^iaslicense]: Wikimedia Commons, "File:Oppenheimer_and_von_Neumann_in_front_of_the_IAS_machine.jpg," CC BY 4.0, accessed at https://commons.wikimedia.org/wiki/File:Oppenheimer_and_von_Neumann_in_front_of_the_IAS_machine.jpg. The original photographer credit is Jeremy Norman Collection / historyofinformation.com.

[^iascode]: Phillips 1989 NCAR oral history, quoted in Lewis 1998 p. 47.

[^iasphoto]: Lewis 1998, BAMS, Fig. 2 caption (p. 47): "The Princeton Meteorology Group, ca. 1952. Left to right: J. Charney, N. Phillips, G. Lewis, N. Gilbarg, and G. Platzman. Photographer: J. Smagorinsky."

[^cp1953]: Charney, J. G., and N. A. Phillips, 1953: "Numerical integration of the quasi-geostrophic equations for barotropic and simple baroclinic flows," *Journal of Meteorology* 10, 71-99. AMS metadata at https://journals.ametsoc.org/view/journals/atsc/10/2/1520-0469_1953_010_0071_niotqg_2_0_co_2.xml. NASA ADS at https://ui.adsabs.harvard.edu/abs/1953JAtS...10...71C/abstract.

[^bolinforecast]: Wiin-Nielsen, A., 1991: "The birth of numerical weather prediction," *Tellus B* 43(4), 36-52. The Stockholm BESK forecasts of 23-24 March 1954 are documented as the first operational NWP forecasts in continental Europe, preceding the US JNWPU operational forecast of 6 May 1955 by more than a year.

[^phillips54]: Phillips, N. A., 1954: "Energy transformations and meridional circulations associated with simple baroclinic waves in a two-level, quasi-geostrophic model," *Tellus* 6, 273-286.

[^vnconference]: The October 1955 Princeton conference is documented in Smagorinsky, J., 1983: "The beginnings of numerical weather prediction and general circulation modeling: Early recollections," *Advances in Geophysics* 25, 3-37. The conference was the institutional moment when Phillips's GCM results were presented in public scientific session and when von Neumann began the lobbying that would establish the Weather Bureau's General Circulation Research Section.

[^qjrms56]: Phillips, N. A., 1956: "The general circulation of the atmosphere: a numerical experiment," *Quarterly Journal of the Royal Meteorological Society* 82(352), 123-164. NASA ADS at https://ui.adsabs.harvard.edu/abs/1956QJRMS..82..123P/abstract. PDF at https://empslocal.ex.ac.uk/people/staff/gv219/classics.d/Phillips56.pdf.

[^napiershaw]: Royal Meteorological Society Napier Shaw Memorial Prize, awarded 20 June 1956 to Phillips for the 1956 GCM paper. The competition had been announced by the RMetS in April 1954 with "the energetics of the atmosphere" as the declared subject; Phillips's was the first award.

[^circulationcredit]: Wikimedia Commons, "File:Earth_Global_Circulation_-_en.svg," CC BY-SA 3.0, accessed at https://commons.wikimedia.org/wiki/File:Earth_Global_Circulation_-_en.svg. Author: Wikimedia user Kaidor, 16 January 2013.

[^wnreconstr]: The Rossby-Phillips dialogue is reconstructed in Wiin-Nielsen's correspondence with John Lewis and quoted in Lewis 1998, p. 52. Wiin-Nielsen, who had been in Stockholm with Phillips during the 1953-1954 visit, retained vivid memories of Rossby's intellectual reaction to the GCM presentation.

[^charneymemoir]: Phillips 1995 Charney NAS memoir, p. 99, accessed at https://www.nasonline.org/wp-content/uploads/2024/06/charney-jule-g.pdf.

[^packagememoir]: Phillips 1995 Charney NAS memoir, p. 99. The full passage is reproduced verbatim in the body of this post.

[^mitfaculty]: MIT PAOC department history, accessed at http://paocweb.mit.edu/about/history. The chair sequence Houghton (1942-1969 or 1970), Phillips (1970-1974), Charney (1974-1977), Lorenz (1977-1981) is documented in this institutional record.

[^chairseq]: The MIT chair sequence is corroborated by the MIT News Phillips obituary at https://news.mit.edu/2019/norman-phillips-former-meteorology-department-dead-dies-0516, which records Phillips's chair as 1970-1974, and by the AMS Henry G. Houghton Award page, which records Houghton's chair through 1970.

[^mitpromotion]: The exact year of Phillips's MIT promotion to associate and to full professor is not documented in the publicly accessible record. Lewis 1998 (Appendix B) refers to him as "Professor" by the early 1960s without giving a specific date.

[^greencredit]: Wikimedia Commons, "File:2017_Green_Building_(MIT_Building_54).jpg," CC BY-SA 4.0, accessed at https://commons.wikimedia.org/wiki/File:2017_Green_Building_(MIT_Building_54).jpg. Photographer: Beyond My Ken, 12 August 2017.

[^sigma57]: Phillips, N. A., 1957: "A coordinate system having some special advantages for numerical forecasting," *Journal of Meteorology* 14(2), 184-185. AMS metadata at https://journals.ametsoc.org/view/journals/atsc/14/2/1520-0469_1957_014_0184_acshss_2_0_co_2.xml. NASA ADS at https://ui.adsabs.harvard.edu/abs/1957JAtS...14..184P/abstract. The 1957 paper, originally published in *Journal of Meteorology*, is now indexed under *Journal of the Atmospheric Sciences* because the journal was renamed in 1962.

[^simmons81]: Simmons, A. J., and D. M. Burridge, 1981: "An energy and angular-momentum conserving vertical finite-difference scheme and hybrid vertical coordinates," *Monthly Weather Review* 109(4), 758-766. NASA ADS at https://ui.adsabs.harvard.edu/abs/1981MWRv..109..758S. ECMWF open PDF at https://www.ecmwf.int/sites/default/files/elibrary/1981/12284-energy-and-angular-momentum-conserving-finite-difference-scheme-hybrid-coordinates-and-medium.pdf.

[^nci59]: Phillips, N. A., 1959: "An example of non-linear computational instability," in B. Bolin (ed.), *The Atmosphere and the Sea in Motion* (Rossby Memorial Volume), Rockefeller Institute Press, pp. 501-504. The Rossby Memorial Volume is not available online; the chapter is cited via Lewis 1998 (p. 50) and via the AMS Rossby Medal citation language.

[^arakawa66]: Arakawa, A., 1966: "Computational design for long-term numerical integration of the equations of fluid motion: Two-dimensional incompressible flow. Part I," *Journal of Computational Physics* 1, 119-143.

[^easterbrook]: Easterbrook, S., 2019: "In memory of Norman Phillips," *Serendipity* blog, accessed at https://www.easterbrook.ca/steve/2019/05/in-memory-of-norman-phillips/. The 1959 NCI diagnosis is framed there as the foundational discovery for atmospheric modelling.

[^tellus60]: Phillips, N. A., 1960: "On the problem of initial data for the primitive equations," *Tellus* 12(2), 121-126. Open access via Wiley at https://onlinelibrary.wiley.com/doi/abs/10.1111/j.2153-3490.1960.tb01289.x. Direct PDF at https://tellusjournal.org/articles/3446/files/65717cc29af65.pdf.

[^modernda]: The Phillips 1960 lineage into normal-mode initialisation, digital-filter initialisation, and modern variational data assimilation is laid out in Lynch, P., 2006: *The Emergence of Numerical Weather Prediction: Richardson's Dream*, Cambridge University Press, especially Chapter 10.

[^rev63]: Phillips, N. A., 1963: "Geostrophic motion," *Reviews of Geophysics* 1(2), 123-176.

[^appalach58]: Phillips, N. A., 1958: "Geostrophic errors in predicting the Appalachian storm of November 1950," *Geophysica* 6, 389-405. Published in the Erik Palmen 60th birthday festschrift.

[^cpgrid]: The Charney-Phillips versus Lorenz vertical-grid distinction is discussed in standard modelling textbooks; see for instance Holton, J. R., 2004: *An Introduction to Dynamic Meteorology*, 4th edition, Academic Press, and Vallis, G. K., 2017: *Atmospheric and Oceanic Fluid Dynamics*, 2nd edition, Cambridge University Press.

[^sloan]: Phillips was awarded an Alfred P. Sloan Foundation Research Fellowship in 1961. The fellowship is referenced in the Phillips_institutional_arc research notes for this post; the precise primary citation has not been independently verified in this session.

[^students]: Wikidata entry for Norman A. Phillips, https://www.wikidata.org/wiki/Q19661421, lists Webster, Moura, Hollingsworth, Mak, and Blumen among his publicly listed PhD students. The list is not exhaustive.

[^rossbymedal]: Wikipedia, "Carl-Gustaf Rossby Research Medal," accessed at https://en.wikipedia.org/wiki/Carl-Gustaf_Rossby_Research_Medal, gives the 1971 award to Phillips with the citation language reproduced verbatim in the post body.

[^nas76]: Wikipedia, "Norman A. Phillips," at https://en.wikipedia.org/wiki/Norman_A._Phillips: "Phillips was elected to the National Academy of Sciences in 1976." The NAS member directory at https://www.nasonline.org/member-directory/ also lists 1976.

[^mitobit]: MIT News, "Norman Phillips, former meteorology department head, dies at 95," 16 May 2019, accessed at https://news.mit.edu/2019/norman-phillips-former-meteorology-department-dead-dies-0516. The article does not analyse Phillips's motivations for leaving MIT.

[^nmcdirectors]: The NMC director sequence -- Cressman (1954-1964), Shuman (1964-1981), Bonner (1981-1990), McPherson (1990-1998) -- is documented in the NCEP history page at https://www.emc.ncep.noaa.gov/emc/pages/ourhistory.php and in the *Mariners Weather Log* Vol. 51 No. 3 (December 2007) NCEP directors retrospective at https://vos.noaa.gov/MWL/dec_07/legacy.shtml.

[^wwb74]: NWS Heritage Project, "The World Weather Building," accessed at https://vlab.noaa.gov/web/nws-heritage/-/the-world-weather-building. The dedication date 22 October 1974 and the dedicating Administrator Robert M. White are both documented in this NWS Heritage record. The forecaster move began in early 1975; specific January-1975 timing is supported by the NOAA Magazine adaptation cited in the same source.

[^ngm79]: Phillips, N. A., 1979: "The Nested Grid Model," NOAA Technical Report NWS 22, U.S. Department of Commerce, NOAA, National Weather Service, Silver Spring, Maryland, April 1979. The report is held by the NOAA Central Library at https://repository.library.noaa.gov/.

[^hokeetal89]: Hoke, J. E., N. A. Phillips, G. J. DiMego, J. J. Tuccillo, and J. G. Sela, 1989: "The Regional Analysis and Forecast System of the National Meteorological Center," *Weather and Forecasting* 4(3), 323-334.

[^ngmnickname]: The "Norm's Great Model" nickname is documented in the MIT News obituary (https://news.mit.edu/2019/norman-phillips-former-meteorology-department-dead-dies-0516), the Rivet Funeral Home obituary (https://www.rivetfuneralhome.com/obituary/norman-phillips), and the Nashua Telegraph obituary (https://www.nashuatelegraph.com/obituaries-memorials/obituaries/2019/03/24/norman-a-phillips/).

[^cressman]: Cressman, G. P., 1959: "An operational objective analysis system," *Monthly Weather Review* 87, 367-374. Cressman was NMC's first director (1954-1964) and the developer of the successive-correction objective-analysis method that bore his name through the 1970s.

[^mcpherson79]: McPherson, R. D., K. H. Bergman, R. E. Kistler, G. E. Rasch, and D. S. Gordon, 1979: "The NMC operational global data assimilation system," *Monthly Weather Review* 107(11), 1445-1461. Companion paper: Bergman, K. H., 1979: "Multivariate analysis of temperatures and winds using optimum interpolation," *Monthly Weather Review* 107, 1423-1444.

[^tellus86]: Phillips, N. A., 1986: "The spatial statistics of random geostrophic modes and first-guess errors," *Tellus A* 38(4), 314-332. Wiley at https://onlinelibrary.wiley.com/doi/abs/10.1111/j.1600-0870.1986.tb00418.x.

[^bannister]: Bannister, R. N., 2008: "A review of forecast error covariance statistics in atmospheric variational data assimilation. I: Characteristics and measurements of forecast error covariances," *Quarterly Journal of the Royal Meteorological Society* 134, 1951-1970. Bannister 2008 treats Phillips 1986 as a foundational reference for non-separable vertical-correlation modelling.

[^trainees]: The list of NMC scientists trained or mentored by Phillips during his Development Division tenure is reconstructed from the NCEP history page (https://www.emc.ncep.noaa.gov/emc/pages/ourhistory.php), the *Mariners Weather Log* December 2007 NCEP directors retrospective, and individual biographical records.

[^selagfs]: Sela, J. G., 1980: "Spectral modeling at the National Meteorological Center," *Monthly Weather Review* 108, 1279-1292. Sela's spectral model went operational at NMC in August 1980 with R30 triangular truncation and 12 sigma layers; this is the lineal ancestor of the modern GFS.

[^retirement]: The NMC retirement year disagreement is between the MIT News obituary (https://news.mit.edu/2019/norman-phillips-former-meteorology-department-dead-dies-0516), which contains internally inconsistent passages giving both 1984 and 1988, and the Rivet Funeral Home obituary (https://www.rivetfuneralhome.com/obituary/norman-phillips), which gives 1984. A federal personnel record (FOIA-able) would resolve the question; the published sources do not.

[^rivetdetail]: Rivet Funeral Home obituary, https://www.rivetfuneralhome.com/obituary/norman-phillips.

[^lynch2019]: Lynch, P., 2019: "A pioneer of climate modelling -- and maths," *The Irish Times*, accessed at https://www.irishtimes.com/news/science/a-pioneer-of-climate-modelling-and-maths-1.3839204. The companion *ThatsMaths* post is at https://thatsmaths.com/2019/04/04/a-pioneer-of-climate-modelling-and-prediction/.

[^daughters]: Family obituary in the Rivet Funeral Home record, https://www.rivetfuneralhome.com/obituary/norman-phillips.

[^deathdate]: Wikipedia, "Norman A. Phillips," at https://en.wikipedia.org/wiki/Norman_A._Phillips; Rivet Funeral Home obituary at https://www.rivetfuneralhome.com/obituary/norman-phillips. Both sources give 15 March 2019 at Grace House, Windham, NH.

[^chmemoir]: Phillips, N. A., 1995: "Jule Gregory Charney, 1917-1981," *Biographical Memoirs* (National Academy of Sciences) 66, 80-113. PDF at https://www.nasonline.org/wp-content/uploads/2024/06/charney-jule-g.pdf.

[^franklin]: The Franklin Institute Laureates page, "Norman A. Phillips," at https://fi.edu/en/awards/laureates/norman-phillips. Phillips and Smagorinsky shared the 2003 Benjamin Franklin Medal in Earth Science.

[^franklincite]: The Franklin Institute citation language is quoted verbatim from the laureate page at https://fi.edu/en/awards/laureates/norman-phillips.

[^foucault]: Phillips, N. A., 2005: "What Makes the Foucault Pendulum Move among the Stars?" in M. R. Matthews, C. F. Gauld, and A. Stinner (eds.), *The Pendulum: Scientific, Historical, Philosophical and Educational Perspectives*, Springer, Dordrecht. The chapter was preceded by a 2001 French version in *La Météorologie* and a 2004 English version in *Science & Education*.

[^oralhist]: Phillips, N. A., 1989: Oral history interview conducted by A. Hollingsworth, W. Washington, J. Tribbia, and A. Kasahara, NCAR Archives, 85 pp. Transcript at NCAR OpenSky, accessed at https://opensky.ucar.edu/islandora/object/archives:7626.

[^deathfinal]: Rivet Funeral Home obituary, https://www.rivetfuneralhome.com/obituary/norman-phillips.

[^mitobitquote]: MIT News, "Norman Phillips, former meteorology department head, dies at 95," 16 May 2019, accessed at https://news.mit.edu/2019/norman-phillips-former-meteorology-department-dead-dies-0516. The Kerry Emanuel quote is from the MIT News article.

[^lynchpost]: Lynch, P., 2019: "A pioneer of climate modelling and prediction," *ThatsMaths* blog, 4 April 2019, accessed at https://thatsmaths.com/2019/04/04/a-pioneer-of-climate-modelling-and-prediction/.

[^easterbrooktribute]: Easterbrook, S., 2019: "In memory of Norman Phillips," *Serendipity* blog, May 2019, accessed at https://www.easterbrook.ca/steve/2019/05/in-memory-of-norman-phillips/.

[^rossbyphoto]: Wikimedia Commons, "File:Carl_G._A._Rossby_LCCN2016875745_(cropped).jpg," public domain (Harris & Ewing collection, Library of Congress), accessed at https://commons.wikimedia.org/wiki/File:Carl_G._A._Rossby_LCCN2016875745_(cropped).jpg.

---

## Sources

**Primary autobiographical and personal**

- Phillips, N. A., 1989: Oral history interview by A. Hollingsworth, W. Washington, J. Tribbia, and A. Kasahara, NCAR Archives, 85 pp. https://opensky.ucar.edu/islandora/object/archives:7626
- Phillips, N. A., 1995: "Jule Gregory Charney, 1917-1981," *Biographical Memoirs* (NAS) 66, 80-113. https://www.nasonline.org/wp-content/uploads/2024/06/charney-jule-g.pdf
- Phillips, N. A., 2005: "What Makes the Foucault Pendulum Move among the Stars?" In *The Pendulum*, M. R. Matthews et al. (eds.), Springer.

**Phillips's key scientific papers**

- Phillips, N. A., 1951: "A Simple Three-Dimensional Model for the Study of Large-Scale Extratropical Flow Patterns," PhD dissertation, University of Chicago, 25 pp.
- Charney, J. G., and N. A. Phillips, 1953: "Numerical integration of the quasi-geostrophic equations for barotropic and simple baroclinic flow," *J. Meteorology* 10, 71-99.
- Phillips, N. A., 1954: "Energy transformations and meridional circulations associated with simple baroclinic waves in a two-level, quasi-geostrophic model," *Tellus* 6, 273-286.
- Phillips, N. A., 1956: "The general circulation of the atmosphere: a numerical experiment," *Quarterly Journal of the Royal Meteorological Society* 82, 123-164.
- Phillips, N. A., 1957: "A coordinate system having some special advantages for numerical forecasting," *J. Meteorology* 14, 184-185.
- Phillips, N. A., 1958: "Geostrophic errors in predicting the Appalachian storm of November 1950," *Geophysica* 6, 389-405.
- Phillips, N. A., 1959: "An example of non-linear computational instability," in *The Atmosphere and the Sea in Motion* (Rossby Memorial Volume), B. Bolin (ed.), Rockefeller Institute Press, 501-504.
- Phillips, N. A., 1960: "On the problem of initial data for the primitive equations," *Tellus* 12, 121-126.
- Phillips, N. A., 1963: "Geostrophic motion," *Reviews of Geophysics* 1, 123-176.
- Phillips, N. A., 1979: "The Nested Grid Model," NOAA Technical Report NWS 22.
- Phillips, N. A., 1986: "The spatial statistics of random geostrophic modes and first-guess errors," *Tellus A* 38, 314-332.

**Biographies and obituaries**

- Lewis, J. M., 1998: "Clarifying the Dynamics of the General Circulation: Phillips's 1956 Experiment," *Bulletin of the American Meteorological Society* 79, 39-60.
- MIT News, 16 May 2019: "Norman Phillips, former meteorology department head, dies at 95." https://news.mit.edu/2019/norman-phillips-former-meteorology-department-dead-dies-0516
- Rivet Funeral Home, 2019: "Obituary | Norman A. Phillips of Windham, New Hampshire." https://www.rivetfuneralhome.com/obituary/norman-phillips
- Nashua Telegraph, 24 March 2019: "Norman A. Phillips." https://www.nashuatelegraph.com/obituaries-memorials/obituaries/2019/03/24/norman-a-phillips/
- Lynch, P., 2019: "A pioneer of climate modelling -- and maths," *Irish Times*. https://www.irishtimes.com/news/science/a-pioneer-of-climate-modelling-and-maths-1.3839204
- Easterbrook, S., 2019: "In memory of Norman Phillips," *Serendipity* blog. https://www.easterbrook.ca/steve/2019/05/in-memory-of-norman-phillips/

**Institutional and contextual**

- Smagorinsky, J., 1983: "The beginnings of numerical weather prediction and general circulation modeling: Early recollections," *Advances in Geophysics* 25, 3-37.
- Wiin-Nielsen, A., 1991: "The birth of numerical weather prediction," *Tellus B* 43, 36-52.
- Nebeker, F., 1995: *Calculating the Weather: Meteorology in the 20th Century*, Academic Press.
- Lindzen, R. S., E. N. Lorenz, and G. W. Platzman (eds.), 1990: *The Atmosphere -- A Challenge: The Science of Jule Gregory Charney*, American Meteorological Society.
- Shuman, F. G., 1989: "History of Numerical Weather Prediction at the National Meteorological Center," *Weather and Forecasting* 4, 286-296.
- NWS Heritage Project, "The World Weather Building." https://vlab.noaa.gov/web/nws-heritage/-/the-world-weather-building
- MIT PAOC department history. http://paocweb.mit.edu/about/history

**Related scientific descendants**

- Simmons, A. J., and D. M. Burridge, 1981: "An energy and angular-momentum conserving vertical finite-difference scheme and hybrid vertical coordinates," *Monthly Weather Review* 109, 758-766.
- Arakawa, A., 1966: "Computational design for long-term numerical integration of the equations of fluid motion: Two-dimensional incompressible flow. Part I," *J. Computational Physics* 1, 119-143.
- Hoke, J. E., N. A. Phillips, G. J. DiMego, J. J. Tuccillo, and J. G. Sela, 1989: "The Regional Analysis and Forecast System of the National Meteorological Center," *Weather and Forecasting* 4, 323-334.
- Bannister, R. N., 2008: "A review of forecast error covariance statistics in atmospheric variational data assimilation. I," *QJRMS* 134, 1951-1970.
- Lynch, P., 2006: *The Emergence of Numerical Weather Prediction: Richardson's Dream*, Cambridge University Press.

**Award and citation verification**

- AMS Carl-Gustaf Rossby Research Medal list. https://en.wikipedia.org/wiki/Carl-Gustaf_Rossby_Research_Medal
- Franklin Institute Laureates page, Phillips entry. https://fi.edu/en/awards/laureates/norman-phillips
- WMO IMO Prize winners list. https://wmo.int/about-wmo/awards/international-meteorological-organization-imo-prize/imo-prize-winners (Phillips not on list)
- Symons Gold Medal Wikipedia list. https://en.wikipedia.org/wiki/Symons_Gold_Medal (Phillips not on list)

**Encyclopaedic**

- Wikipedia, "Norman A. Phillips." https://en.wikipedia.org/wiki/Norman_A._Phillips
- Wikidata, "Norman A. Phillips" (Q19661421). https://www.wikidata.org/wiki/Q19661421
- Institute for Advanced Study, "Norman Phillips" scholar profile. https://www.ias.edu/scholars/norman-phillips
