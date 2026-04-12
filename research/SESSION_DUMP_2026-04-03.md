# Session Dump — 2026-04-03/04

## What Was Done This Session

### Blog Posts Written
1. **Part 4** (2026-04-02): "From Cables to Chaos: Four Computers That Changed the Weather"
   - ENIAC → IAS Machine → IBM 704 → LGP-30
   - Added EDVAC bridge section (mercury delay lines, EDSAC beating EDVAC)
   - 10 images from 6 sources (ARL, IAS archives, NASA, CHM, Stuttgart Museum, Flickr)
   - Fixed Daisy Bell: IBM 704 → IBM 7094
   - Fixed LGP-30 ownership language (institutions bought, scientists used)

2. **Part 5** (2026-04-03): "The Swedes Got There First"
   - Sweden ran first operational NWP in Dec 1954 on BESK, a year before US
   - BESK computer (briefly world's fastest), Rossby's return, Conny Palm, Bert Bolin
   - September 1954 military exercise (45000 troops), "tremendously successful"
   - Personal Swedish intro (köttbullar, IKEA, Swedish Chef "bork bork bork")
   - 6 images from Wikimedia/Tekniska museet/Library of Congress

3. **Part 6** (2026-04-04): "The Magician Who Told No Secrets"
   - Arne Beurling cracked Geheimschreiber T52 in 2 weeks with pen and paper (1940)
   - Polish codebreakers parallel (Rejewski/Różycki/Zygalski, teased for future post)
   - Beurling → FRA → BESK → weather thread
   - Ahlfors friendship (Fields Medal in pawn shop), Princeton Room 115
   - 4 images: Beurling portrait, T-52D at NSA museum, Lorenz SZ42, Uppsala memorial

### Fixes to Existing Posts
- Parts 3 & 4: Softened Sweden hints to preserve Part 5 surprise
- Part 4: Added EDVAC section, corrected Daisy Bell, added Sweden acknowledgment
- **All posts**: Replaced 250 em dashes (—) with -- and 67 curly quotes with straight quotes
- **All history**: Force-pushed to remove Co-Authored-By from all 55 commits

### Deep Research Campaign (59+ files initially, expanded to 71)
All stored in `/home/michal/repos/michalbrennek.github.io/research/`

**Computers (21 files):**
ENIAC, EDVAC, Whirlwind, IAS Machine, MANIAC, JOHNNIAC, ILLIAC, ORDVAC, WEIZAC, SILLIAC, BESM, IBM 701, IBM 704, IBM 709/7090, LGP-30, LGP-21, RPC-4000, Cray-1, Cray-2, BESK, + EDVAC_additional, IBM_701_NWP_detail

**People (38+ files):**
Richardson, V.Bjerknes, J.Bjerknes, Charney, Phillips, Lorenz, Bergeron, Rossby, Petterssen, Solberg, Holmboe, Eady, von Neumann, Klara von Neumann, Mauchly, Eckert, Bigelow, H.Goldstine, A.Goldstine, ENIAC programmers (collective), Backus, Forrester, Amdahl, Frankel, Metropolis, Ulam, Rochester, Barricelli, Smagorinsky, Manabe, Platzman, Fjortoft, Browning, Saltzman, Arakawa, Cressman, Emanuel, Peter Lynch, Bolin, Conny Palm, Stemme, Neovius, Fröberg, Beurling (+additional), Swedish_NWP, Geheimschreiber_crypto, Polish_codebreakers

**Cross-references:**
- INDEX.md — master index of all 59+ files
- CROSS_REFERENCES.md — 472-line synthesis (people→machines, people→people, machines→science, timeline, institution map)

### Key Decisions & Preferences Established
- No Co-Authored-By in blog commits (saved to memory)
- No comma thousands separator (Polish convention) — use scientific notation or spaces
- Full sentences for quote attributions
- Cross-link recurring characters between posts
- Parenthetical plain-language for jargon
- Em dashes → -- (keyboard-typeable only)
- Curly quotes → straight quotes
- Images from diverse original sources, not just Wikimedia

### Narrative Threads Open for Future Posts
1. **Polish codebreakers** (Rejewski/Różycki/Zygalski) — teased in Part 6, "personal for me"
2. **The Women Who Wired the Weather** — 6 ENIAC programmers, Klara, Adele, Hamilton, core threaders
3. **IAS Clone Diaspora** — MANIAC/JOHNNIAC/ILLIAC/WEIZAC/SILLIAC/BESM, each found its own science
4. **IBM 7090 and 1960s NWP** — the actual workhorse decade
5. **Cray-1 at NCAR** — supercomputer era for weather
6. **Smagorinsky → Manabe → Nobel** — GFDL institutional story
7. **Stan Frankel's arc** — Los Alamos → ENIAC → LGP-30 → chaos

### Git State
- Branch: main
- Latest commit: `1f03284` "Interpunction corrections and orthography"
- All pushed, clean working tree (except research/ which is untracked)
- History rewritten: all Co-Authored-By removed via filter-branch + force push

### Images Downloaded (not previously in repo)
New images added across sessions:
- ENIAC: Glen Beck/Betty Snyder, tube replacement, four generations boards
- IAS: Bigelow/Goldstine/Oppenheimer/vonNeumann, Pomerene Williams tube
- IBM 704: NACA Langley
- LGP-30: with skins, drum memory
- Flexowriter, core memory closeup
- BESK: console+memories, control panel, Williams tube rack, operator panel
- Rossby 1939 (Library of Congress)
- Conny Palm with BARK (Tekniska museet)
- Beurling 1940s portrait (TT)
- Geheimschreiber T-52D (NSA museum)
- Lorenz SZ42 (Bletchley Park)
- Beurling memorial Uppsala
- Unused: IAS_machine_Oppenheimer_vonNeumann.jpg (replaced, still in assets/)
