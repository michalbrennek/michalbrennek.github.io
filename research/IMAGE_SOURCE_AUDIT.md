# Image Source Audit -- 2026-04-27

## Summary
- Posts checked: 26
- Total embedded images: 90
- Images with proper attribution: 76
- Images flagged: 14

(Header overlay images set in YAML frontmatter under `header.overlay_image` /
`header.teaser` are intentionally excluded from this audit per scope rules.)

## Flagged images (missing or unclear source)

### Post: 2026-04-09-The-machine-that-learned-too-early.md, line 24
Image path: `/assets/images/Rosenblatt_portrait.jpg`
Current alt or figcaption: "Frank Rosenblatt with the Mark I Perceptron at the Cornell Aeronautical Laboratory. Cornell University photo."
Issue: Source is given ("Cornell University photo") but no licence / public-domain status is stated. Cornell is a private university, so PD cannot be assumed.
Suggested fix: Verify licence on the image used and append the appropriate tag, e.g. "Cornell University photo, fair use" or replace with a Wikimedia/PD alternative and credit accordingly.

### Post: 2026-04-09-The-machine-that-learned-too-early.md, line 56
Image path: `/assets/images/Mark_I_Perceptron.jpg`
Current alt or figcaption: "The Mark I Perceptron -- 400 photocells, 512 association units, and electric motors that turned potentiometers to learn. Now in the Smithsonian. Photo: Smithsonian National Museum of American History."
Issue: Credit names the holding institution but no licence / PD statement. Smithsonian holdings have a mix of licences (some CC0 via Open Access, others restricted).
Suggested fix: Confirm the Smithsonian Open Access status and append, e.g. "Photo: Smithsonian National Museum of American History (CC0)" or the actual licence found on the source page.

### Post: 2026-04-09-The-machine-that-learned-too-early.md, line 78
Image path: `/assets/images/NYT_perceptron_1958.jpg`
Current alt or figcaption: "The New York Times coverage of the Perceptron, July 1958. The Navy's promise of a machine that could 'walk, talk, see, write, reproduce itself and be conscious of its existence' would haunt AI for decades."
Issue: No source, photographer, or licence given at all. New York Times articles from 1958 are still under copyright in the United States.
Suggested fix: Either remove the image, replace with a public-domain primary source (the NYT clipping is not PD), or append a fair-use credit, e.g. "Source: The New York Times, July 8, 1958 (fair use)."

### Post: 2026-04-10-The-machine-that-built-IBM.md, line 74
Image path: `/assets/images/IBM_701_frame.jpg`
Current alt or figcaption: "The IBM 701 Electronic Data Processing Machine. ... Photo: IBM Archives via Wikimedia Commons."
Issue: Source ("IBM Archives via Wikimedia Commons") is given but no licence is stated. IBM Archives images are not automatically public domain.
Suggested fix: Check the Wikimedia Commons licence tag and append it explicitly, e.g. "Photo: IBM Archives via Wikimedia Commons (CC BY-SA 4.0)" or similar matching the actual file's licence.

### Post: 2026-04-10-The-machine-that-built-IBM.md, line 82
Image path: `/assets/images/Williams_tube.jpg`
Current alt or figcaption: "A Williams tube from an IBM 701. ... Photo: Computer History Museum via Wikimedia Commons."
Issue: Source given but licence missing.
Suggested fix: Append the Wikimedia Commons licence, e.g. "Photo: Computer History Museum via Wikimedia Commons (CC BY-SA 3.0)."

### Post: 2026-04-10-The-machine-that-built-IBM.md, line 272
Image path: `/assets/images/IBM_701_console.jpg`
Current alt or figcaption: "A close-up of an IBM 701 console and control panel. ... Photo: Wikimedia Commons."
Issue: "Photo: Wikimedia Commons" is a host attribution, not a licence. No licence stated.
Suggested fix: Append the actual Wikimedia Commons licence found on the file page, e.g. "Photo: Wikimedia Commons, CC BY-SA 4.0."

### Post: 2026-04-12-Three-mathematicians-from-Poznan.md, line 30
Image path: `/assets/images/Enigma_machine.jpg`
Current alt or figcaption: "A military Enigma I machine ... Photo: Museo Scienza e Tecnologia, Milan, via Wikimedia Commons."
Issue: Source given but licence missing.
Suggested fix: Append the Wikimedia Commons licence (likely CC BY-SA 4.0 for the Museo Scienza files), e.g. "Photo: Museo Scienza e Tecnologia, Milan, via Wikimedia Commons (CC BY-SA 4.0)."

### Post: 2026-04-12-Three-mathematicians-from-Poznan.md, line 94
Image path: `/assets/images/Bomba_Polish.jpg`
Current alt or figcaption: "A 3D reconstruction of the Polish bomba kryptologiczna. ... Image via Wikimedia Commons."
Issue: Source pointer only ("via Wikimedia Commons"); no creator, no licence.
Suggested fix: Add the file's creator and licence as listed on Wikimedia Commons, e.g. "Image: Karsten Sperling via Wikimedia Commons (CC BY-SA 4.0)" (verify actual creator/licence on the file).

### Post: 2026-04-12-Three-mathematicians-from-Poznan.md, line 190
Image path: `/assets/images/Poznan_monument.jpg`
Current alt or figcaption: "The Enigma Codebreakers Monument in Poznan, unveiled in 2007. ... Photo: Wikimedia Commons."
Issue: Host attribution only; no licence stated.
Suggested fix: Append the Wikimedia Commons licence, e.g. "Photo: Wikimedia Commons, CC BY-SA 3.0" (verify actual licence on the file).

### Post: 2026-04-13-The-forecast-that-reached-the-Nobel.md, line 70
Image path: `/assets/images/Manabe_portrait.jpg`
Current alt or figcaption: "Syukuro 'Suki' Manabe (born 1931). ... Princeton University/Wikimedia."
Issue: Princeton University is a private institution; "Princeton University/Wikimedia" gives source but no licence, and Princeton work is not automatically PD.
Suggested fix: Add the Wikimedia Commons licence found on the file, e.g. "Photo: Princeton University via Wikimedia Commons (CC BY-SA 4.0)" or replace with the Cabinet Office of Japan / Royal Society photo if a clearer-licensed alternative exists.

### Post: 2026-04-17-The-decade-the-forecast-got-good.md, line 130
Image path: `/assets/images/CDC_6600.jpg`
Current alt or figcaption: "The CDC 6600, designed by Seymour Cray. ... Photo: Computer History Museum via Wikimedia Commons."
Issue: Source given but licence missing.
Suggested fix: Append the Wikimedia Commons licence (commonly CC BY-SA 4.0 for CHM files), e.g. "Photo: Computer History Museum via Wikimedia Commons (CC BY-SA 4.0)."

### Post: 2026-04-18-The-women-they-wrote-out-of-the-photo.md, line 20
Image path: `/assets/images/ENIAC_women_programming.jpg`
Current alt or figcaption: "Two of the ENIAC programmers at work on the machine. ... U.S. Army photograph."
Issue: Bare "U.S. Army photograph" with no explicit licence/PD statement. The convention used elsewhere on the same blog (post 2026-04-02) is "U.S. Army photo, public domain."
Suggested fix: Append "public domain", i.e. "U.S. Army photograph, public domain."

### Post: 2026-04-18-The-women-they-wrote-out-of-the-photo.md, line 58
Image path: `/assets/images/Jean_Bartik_ENIAC.jpg`
Current alt or figcaption: "Jean Bartik at the ENIAC. ... U.S. Army photograph."
Issue: Same as above -- no explicit licence / PD statement.
Suggested fix: "U.S. Army photograph, public domain."

### Post: 2026-04-18-The-women-they-wrote-out-of-the-photo.md, line 70 (figcaption)
Image path: `/assets/images/Betty_Holberton.jpg`
Current alt or figcaption: "Betty Holberton. She invented the breakpoint, designed the UNIVAC console, helped write the COBOL and FORTRAN standards, and changed the color of computers from black to gray-beige. Photo: U.S. Army."
Issue: Bare "Photo: U.S. Army" with no explicit licence / PD statement.
Suggested fix: "Photo: U.S. Army, public domain."

## Per-post summary

| Post | Images | Flagged |
|------|--------|---------|
| 2026-03-24-The-man-who-forecasted-weather-with-a-pencil | 1 | 0 |
| 2026-03-25-The-number-that-connects-turbulence-to-war | 1 | 0 |
| 2026-03-26-The-line-that-models-cannot-draw | 0 | 0 |
| 2026-03-27-Reading-the-sky | 0 | 0 |
| 2026-03-28-The-ghost-in-the-grid | 0 | 0 |
| 2026-03-29-The-man-who-tamed-the-equations | 0 | 0 |
| 2026-03-30-The-first-climate-model-had-5KB-of-RAM | 0 | 0 |
| 2026-03-31-The-butterfly-that-broke-the-forecast | 0 | 0 |
| 2026-04-02-From-cables-to-chaos | 9 | 0 |
| 2026-04-03-The-swedes-got-there-first | 6 | 0 |
| 2026-04-04-The-magician-who-told-no-secrets | 4 | 0 |
| 2026-04-08-The-blueprint-von-Neumann-gave-away | 9 | 0 |
| 2026-04-09-The-machine-that-learned-too-early | 3 | 3 |
| 2026-04-10-The-machine-that-built-IBM | 6 | 3 |
| 2026-04-12-Three-mathematicians-from-Poznan | 6 | 3 |
| 2026-04-13-The-forecast-that-reached-the-Nobel | 3 | 1 |
| 2026-04-16-The-man-who-caught-the-computer-disease | 3 | 0 |
| 2026-04-17-The-decade-the-forecast-got-good | 3 | 1 |
| 2026-04-18-The-women-they-wrote-out-of-the-photo | 4 | 3 |
| 2026-04-19-God-is-real-unless-declared-integer | 6 | 0 |
| 2026-04-20-The-empire-that-its-creator-repudiated | 5 | 0 |
| 2026-04-21-The-language-that-refused-to-die | 5 | 0 |
| 2026-04-22-The-fireman-and-the-visionary | 3 | 0 |
| 2026-04-23-The-man-who-fit-the-entire-ocean-in-half-a-megabyte | 5 | 0 |
| 2026-04-24-He-made-Walker-right | 5 | 0 |
| 2026-04-27-The-machine-that-looked-like-furniture | 3 | 0 |
| **TOTAL** | **90** | **14** |

## Clean (all images sourced)

(Posts that contain at least one body image and have no flags. Posts with zero
body images are listed separately below.)

- 2026-03-24-The-man-who-forecasted-weather-with-a-pencil.md
- 2026-03-25-The-number-that-connects-turbulence-to-war.md
- 2026-04-02-From-cables-to-chaos.md
- 2026-04-03-The-swedes-got-there-first.md
- 2026-04-04-The-magician-who-told-no-secrets.md
- 2026-04-08-The-blueprint-von-Neumann-gave-away.md
- 2026-04-16-The-man-who-caught-the-computer-disease.md
- 2026-04-19-God-is-real-unless-declared-integer.md
- 2026-04-20-The-empire-that-its-creator-repudiated.md
- 2026-04-21-The-language-that-refused-to-die.md
- 2026-04-22-The-fireman-and-the-visionary.md
- 2026-04-23-The-man-who-fit-the-entire-ocean-in-half-a-megabyte.md
- 2026-04-24-He-made-Walker-right.md
- 2026-04-27-The-machine-that-looked-like-furniture.md

## No body images (header overlay only, not in audit scope)

- 2026-03-26-The-line-that-models-cannot-draw.md
- 2026-03-27-Reading-the-sky.md
- 2026-03-28-The-ghost-in-the-grid.md
- 2026-03-29-The-man-who-tamed-the-equations.md
- 2026-03-30-The-first-climate-model-had-5KB-of-RAM.md
- 2026-03-31-The-butterfly-that-broke-the-forecast.md

## Notes / patterns observed

- The most common defect (10 of 14 flags) is **"X via Wikimedia Commons"
  without a licence**. Wikimedia Commons hosts many licences (CC0, CC BY,
  CC BY-SA at multiple versions, PD-old, PD-USGov, GFDL, fair-use), so the
  hosting platform alone is not a licence. Each Wikimedia Commons file page
  states the licence; that string is what should appear in the credit.
- Three flags on post 2026-04-18 are all "U.S. Army photograph" / "Photo: U.S.
  Army" with no "public domain" suffix. Posts 2026-04-02 and 2026-04-16 use
  the same source correctly ("U.S. Army photo, public domain" / "U.S. Army
  photo, ARL Technical Library, public domain"). The fix on 04-18 is just a
  matter of appending the standard PD tag.
- Post 2026-04-09 has the only image that is **wholly unsourced** (NYT
  perceptron clipping, line 78) and the only image that may be a copyright
  problem rather than just an attribution-style problem -- 1958 NYT articles
  are still under copyright in the U.S. and would need a fair-use rationale
  or a different source.
- "NASA" / "NOAA" / "Los Alamos National Laboratory" / "U.S. Army" written
  with an accompanying ", public domain" tag is the consistent house style
  and is treated as proper attribution throughout this audit.
