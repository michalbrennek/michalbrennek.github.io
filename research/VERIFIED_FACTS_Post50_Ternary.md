# VERIFIED FACTS — Post 50: "The Prettiest Number System of All" (ternary computing)

Verification date: 2026-08-25. Method: 5 parallel research agents (patents / Setun history / mathematics / modern revival / NWP precision bridge), each curl-verifying its URLs, followed by an independent pass in the main session: every URL in the post re-curled (all resolve; IEEE DOIs return 202/302 bot responses, Royal Society and ACM DOIs 403 to bots but live in browsers with open mirrors cited), and every quoted phrase grepped at its source (web pages, and pdftotext for the EDVAC report, Malinovsky, and Palmer PDFs; ka2.ru checked through windows-1251 conversion).

## Corrections made during verification

- The Register standfirst reads "the first off-the-shelf general-purpose ternary hardware since c 1965" — post initially paraphrase-quoted "since circa 1965"; corrected to the exact wording.

## Patents (all checked on Google Patents, 2026-08-25)

- Huawei CN119652311A "Ternary logic gate circuit, computing circuit, chip and electronic device": filed 2023-09-18, published 2025-03-18, status PENDING (application, not grant; no known silicon). Benefit quote is the Google Patents machine translation — flagged as such in the post.
- Ternell (ex-UNIST) US12154950B2: granted 2024-11-26, priority 2019-12-30.
- KAIST US12334922B2: granted 2025-06-17.
- POSTECH US11533054B2 (granted 2022-12-20) and US11868740B2 (granted 2024-01-09).
- Kyungpook National University US12530514B2: granted 2026-01-20.
- Press: SCMP 2025-04-04 (Zhou Xin) headline verified at source.
- 5500FP ternary FPGA CPU: The Register 2026-03-18 (Liam Proven), Hackaday 2026-03-16. No patent involved — the post does not claim one.

## Balanced ternary mathematics (independently computed by research agent, Python, 2000 random cases)

- 8 = +0- (9-1); negation = trit-flip; truncation = round-to-nearest (tail symmetric about zero, ties impossible); comparison lexicographic; n trits cover ±(3^n-1)/2.
- Radix economy: r/ln r minimized at e; 3 beats 2 by ~5.7% (2.731 vs 2.885); 2 and 4 tie exactly. Hayes's 60/40/39 example verified.
- 18 trits ≈ 28.5 bits (18×log2(3)); log2(3) ≈ 1.585 = BitNet's "1.58".
- USB4: 2^11 = 2048 ≤ 3^7 = 2187; 139 spare codewords.

## Quotes verified verbatim at source

- Knuth "Perhaps the prettiest number system of all...", "flip-flap-flop", Moore School 1945-46 consideration, CACM 3 (1960) 149-150 Setun note — InformIT official TAOCP vol. 2 3rd ed. excerpt (grep hits).
- Hayes "Third Base": "only a hypothesis that such an advantage exists", "squandered" (two-cores-per-trit), Grosch/Whirlwind, ERA 1950 provenance — Williams College full-text mirror.
- von Neumann EDVAC §5.1: "disproportionately more involved", "suggests the use of the binary" — Carleton PDF via pdftotext.
- Łukasiewicz "I have declared a spiritual war upon all coercion..." — SEP entry. Farewell lecture date 7 March 1918 (SEP bibliography + original Polish title; SEP prose "17 March" is a typo — NOT propagated). Publication: Ruch Filozoficzny 5 (1920) 170-171.
- Fowler to Airy: "had the Ternary instead of the binary Notation been adopted in the Infancy of Society..." — thomasfowler.org.uk.
- Malinovsky (sigcis PDF): "enveloped in sunlight", "faithfully worked for seventeen years... barbarically destroyed and carted off to the dump", "ended his attempts to thwart the production", sewing-needle/fifty-two coils detail.
- Rumyantsev interview (ka2.ru, windows-1251): "Нам не надо ни видеть, ни знать — должна быть авторитетная бумага с печатями и подписями", "оболваненным" (stupefied-by-binary line), "печатями и подписями".
- Computer museum English article: "fruit of university fantasy", "annihilate 'ugly duckling'"; also corroborates Czech production plan ("The planned manufacture of Setun in Czechoslovakia was also broken"), 1965 stop despite unsatisfied requests, binary replacement 2.5× more expensive.
- Váňa et al. 2017 (AMS page): "approximately 40%", "early days of numerical weather prediction... considerable interest" (Baede et al. 1976).
- Nakano et al. 2018 (AMS page): "wavenumber-5 structure becomes dominant in both hemispheres", "grid cell geometrics".
- Palmer Nature 2015 (PDF): title "Build imprecise supercomputers", "no point, however, in being more deterministic", "waste of computing and energy resources".
- ECMWF 11 May 2021 news: "frees up about 40% of computing power".
- Klöwer et al. 2021 (nature.com): "fewer than 7 bits of real information per value" (thin-space entity &#8201; in source).
- JEDEC GDDR7 PR: "3 levels (+1, 0, -1)... 3 bits over 2-cycles" sentence.
- Micron GDDR7 blog: "50% higher voltage margin" vs PAM-4.
- Synopsys USB4 v2: 11b/7t, "7 ternary digits".
- Nature Electronics 2019 abstract: "from a binary to a ternary logic system".
- Science Advances 2025 (PMC): "more than 70% of the total dynamic power".
- BitNet abs/HTML: "matches the full-precision", 71.4× matmul energy, call for 1-bit-optimized hardware; GitHub README: 100B on single CPU, "5-7 tokens per second".

## Setun facts — sourcing discipline applied

- Dates: seminar task 23 April 1956 (machine then still planned binary; ternary turn autumn 1956 after Gutenmakher internship); working December 1958 after TEN DAYS adjustment (the "worked at once without debugging" version rejected); state trials April 1960, 95% useful time; Kazan acceptance act signed 30 November 1961; production stopped 1965.
- Numbers: ~50 machines total incl. prototypes, 30 to universities; output "ten to twenty a year" (sources disagree: 10-12 interview / 10-15 museum / 15-20 Malinovsky — post uses the honest range); price 27500 rubles; elements 3.50 rubles (Astrakhan); replacement binary machine 2.5× cost; 2.5 kVA; 37 vacuum tubes; 200 kHz; 81 words RAM / drum 1944 nine-trit cells; 24 of 27 opcodes.
- Speed: stated as range (several hundred–~1000 avg incl. drum; 2000-4500 compute-bound) per setun2.htm; flat "4500 ops/s" explicitly flagged as top-of-range, not spec.
- Single-witness material (1959 blacklist + Aleksandrov "stamps and signatures" quote, Czech license details, Yakutsk anecdote, "everyone builds binary" counterfactual) attributed in-text to Brusentsov's telling per the honesty rule; Czech story partially corroborated by museum article.
- MSU rector who exiled lab to attic NOT named (no source names one).
- Hayes "squandered" vs Brusentsov "7× fewer elements" presented as measuring different things (information-per-core vs element count against LEM-1-style binary design).
- Brusentsov: b. 7 Feb 1925 Kamianske, d. 4 Dec 2014 Moscow; drafted Feb 1943; For Bravery + Order of the Red Star; 5 of 25 survivors; MEI graduation 1953 (Malinovsky; museum bio says 1952 — Malinovsky used); Setun-70 experimental model April 1970; trytes = 6 trits; TERNAC 1973 = emulator only.

## Deliberate omissions / hedges

- No Setun-meteorology link exists in English-language sources — post makes no such claim.
- TLC flash explicitly flagged as NOT ternary (3 bits, 8 levels).
- Knuth page number (p. 207 3rd ed.) NOT printed — cited as §4.1 + edition (secondary-sourced page numbers only).
- RTX 5090 bandwidth figure omitted (MEDIUM confidence); only GDDR7-in-RTX-50 stated.
- Samsung funder named loosely as "Samsung" in body (precise: Samsung Research Funding & Incubation Center, grant SRFC-TA1703-07 — grant number MEDIUM confidence, not printed).
- Qutrits omitted for scope.
- "2021 Huawei ternary patent" rumor: no such distinct filing found; all traces lead to the 2023 filing published 2025 — post uses only the verified filing.

## Images

- Post50_Setun_1959.png — Wikimedia Commons "Setun computer, from Sputnik in 1959", PD (PD-RU-exempt), USSR state publisher Sputnik.
- Post50_Brusentsov_2009.jpg — Wikimedia Commons, photographer "Nadir of Moscow", 23 Oct 2009, CC BY-SA 4.0, attributed in caption.
