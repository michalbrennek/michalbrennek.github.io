# Post on Akio Arakawa, Yale Mintz & the UCLA GCM — Image Research & Licensing Report

All images downloaded to `/home/michal/repos/michalbrennek.github.io/assets/images/`.

## Image: Arakawa_grids.svg
- Source URL: https://commons.wikimedia.org/wiki/File:Discretization_for_the_different_Arakawa_grids_correct.svg
- Direct file: https://upload.wikimedia.org/wikipedia/commons/8/8a/Discretization_for_the_different_Arakawa_grids_correct.svg
- License: Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)
- Author: Rpnl ocn (Wikimedia Commons user), 2016
- Credit line (for figcaption): The five Arakawa grids (A, B, C, D, E) as introduced in Arakawa & Lamb (1977). Diagram by Wikimedia Commons user Rpnl ocn, CC BY-SA 4.0.
- Dimensions: 535 x 343 (nominal SVG viewport; vector scales losslessly)
- Notes: The canonical schematic used on the Wikipedia "Arakawa grids" article. This is the single most important illustrative image for the post — shows placement of mass (h), u-velocity and v-velocity points on all five grid staggerings. Vector format means it is sharp at any rendered size. CC BY-SA requires attribution **and** share-alike; safe for blog use with credit in figcaption.

## Image: UCLA_campus.jpg
- Source URL: https://commons.wikimedia.org/wiki/File:UCLA_Mathematical_Sciences_Building.jpg
- Direct file: https://upload.wikimedia.org/wikipedia/commons/1/10/UCLA_Mathematical_Sciences_Building.jpg
- License: Public domain (released by the copyright holder)
- Author: Oleg Alexandrov, 21 June 2007
- Credit line (for figcaption): The UCLA Mathematical Sciences Building, where the Department of Atmospheric and Oceanic Sciences (formerly Meteorology) has been housed since 1967 — Arakawa and Mintz's home institution. Photo by Oleg Alexandrov, 2007, public domain via Wikimedia Commons.
- Dimensions: 2576 x 1932 px
- Notes: Exact building where Arakawa and Mintz actually worked, not a generic UCLA shot. Strong choice for context. Public-domain release means no attribution is legally required, but crediting the photographer is courteous and standard practice.

## Image: Jacob_Bjerknes.jpg
- Source URL: https://commons.wikimedia.org/wiki/File:Jacob_bjerknes_headshot.jpg
- Direct file: https://upload.wikimedia.org/wikipedia/commons/5/59/Jacob_bjerknes_headshot.jpg
- License: Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)
- Author: Hedvig Bjerknes (Bjerknes Family collection, 1968)
- Credit line (for figcaption): Jacob Bjerknes, founder of the UCLA Department of Meteorology (1940) and Mintz's doctoral advisor, photographed in 1968. Photo by Hedvig Bjerknes, Bjerknes Family collection, CC BY-SA 4.0 via Wikimedia Commons.
- Dimensions: 1443 x 2073 px
- Notes: Included because Bjerknes is the connective tissue between this post and earlier norwegian-school material — he brought Mintz into meteorology and is the reason UCLA had an atmospheric-dynamics department at all. Use optionally if the post references Bjerknes; skip if it doesn't.

## Image: NASA_GEOS5_clouds.jpg
- Source URL: https://svs.gsfc.nasa.gov/3657/
- Direct file: https://svs.gsfc.nasa.gov/vis/a000000/a003600/a003657/sc09cloud_still_persp_c1440.0500.jpg
- License: Public domain (NASA Scientific Visualization Studio; NASA material is not subject to copyright in the United States). Credit is requested.
- Author: NASA/Goddard Space Flight Center Scientific Visualization Studio (simulation by GMAO, GEOS-5 nature run)
- Credit line (for figcaption): Clouds from a GEOS-5 7-km global simulation (August 2009) — a direct descendant of the Mintz-Arakawa UCLA GCM tradition, now resolving individual storm systems. Visualization: NASA/Goddard Space Flight Center Scientific Visualization Studio.
- Dimensions: 4096 x 4096 px
- Notes: Perspective view of the whole globe with clouds resolved at 7 km — visually shows what a modern GCM produces, a direct lineage from UCLA's coarse 1963 run (7° x 9°) to today. Serves as a "descendant" figure if one wants to show how far the field travelled. Also used as the source for `header-arakawa.jpg`.

## Image: header-arakawa.jpg
- Source URL: derived from https://svs.gsfc.nasa.gov/3657/ (same GEOS-5 still as above)
- Direct file (source): https://svs.gsfc.nasa.gov/vis/a000000/a003600/a003657/sc09cloud_still_persp_c1440.0500.jpg
- License: Public domain (NASA SVS). Credit requested.
- Author: NASA/Goddard Space Flight Center Scientific Visualization Studio
- Credit line (for figcaption, if header caption is used): Header: NASA/Goddard SVS GEOS-5 global cloud simulation.
- Dimensions: 1600 x 900 px (16:9), processed from the 4096 x 4096 source by centering-crop to 16:9 then resizing to 1600 x 900 with Lanczos resampling (PIL/Pillow 12.1.1)
- Notes: Dramatic curved-Earth perspective with swirling storm systems — visually atmospheric and computational at once, fits the blog's aesthetic (similar in feel to `header-climate.jpg`, `header-model-clouds.jpg`). Square-to-16:9 crop preserves the planet in the frame.

---

## Images considered and NOT downloaded

### Akio Arakawa portrait — NOT AVAILABLE under free license
- Searched: Wikimedia Commons (no results), UCLA AOS obituary page (WebFetch denied; page is presumably copyrighted UCLA content anyway), AIP Niels Bohr Library (has oral history from 1997 but no freely-licensed portrait indexed), AMS Bulletin (no freely-licensed obituary portrait found).
- Status: No CC or PD portrait of Arakawa exists on any platform I could verify. The UCLA AOS memorial page (https://atmos.ucla.edu/news/dr-akio-arakawa-distinguished-research-professor-emeritus/) reportedly carries an institutional photo, but UCLA does not publish a blanket reuse license on departmental news pages; using it would require explicit written permission from UCLA AOS communications.
- Recommendation: Skip the Arakawa portrait, or email UCLA AOS (atmos.ucla.edu/contact) for permission — they have been cooperative about posthumous tributes. Do not fabricate or substitute an AI-generated image.

### Yale Mintz portrait — NOT AVAILABLE under free license
- Searched: Wikimedia Commons (no results), NCAR Archives Yale Mintz Collection (https://aspace.archives.ucar.edu/repositories/2/resources/40 — three films, but "materials have not been reformatted to a digital medium" and no online imagery), UCLA In Memoriam records (text only), Hebrew University archives (no digital portrait indexed).
- Status: Mintz died in 1991 in Jerusalem; his era predates routine online photographic archiving, and no family-donated image has surfaced on a free platform. Even the 1993 UC In Memoriam entry is text-only on OAC.
- Recommendation: Proceed without a Mintz portrait and note it in the text. This is the same situation as several other mid-century figures in the series (e.g., Charney-era collaborators).

### Arakawa-Schubert cumulus parameterization schematic — NOT DOWNLOADED
- No CC-licensed schematic of the convective-ensemble / quasi-equilibrium concept found on Wikimedia. Papers that contain the figure (JAS 1974) are behind the AMS paywall/copyright. Recreating it would require an original diagram, out of scope for image research.
- Recommendation: Skip, or commission an original SVG later.

### Phillips 1956 nonlinear instability figure — NOT DOWNLOADED
- Not re-researched (already covered in earlier image rounds for post 15). If needed, the existing `header-phillips.jpg` or `Frankel_portrait.jpg` covers the Phillips-era context.

### IBM 7090 / early-computer era — NOT DOWNLOADED
- The repo already contains `NASA_7090.jpg` and various 1960s-era machine photos. No new download needed.

### Early UCLA GCM output figure — NOT DOWNLOADED
- NASA Technical Reports Server (https://ntrs.nasa.gov/citations/19730012781, "Design of the UCLA general circulation model") hosts the 1973 Arakawa technical report, which is a federal-government publication and in principle public domain, but the report's figures are rasterized inside the PDF and the NTRS license statement is ambiguous for contractor-authored content. Would need a deeper dive to extract a clean figure. The repo already has `early_GCM.jpg` which may serve.
- Recommendation: If a specific UCLA GCM output figure is needed, extract one page from the NTRS PDF with `pdftotext`/`pymupdf` in a follow-up pass and verify the license statement on that particular report first.

---

## Summary
- 5 images downloaded and verified: `Arakawa_grids.svg`, `UCLA_campus.jpg`, `Jacob_Bjerknes.jpg`, `NASA_GEOS5_clouds.jpg`, `header-arakawa.jpg` (derived).
- 2 planned images (Arakawa portrait, Mintz portrait) could not be obtained under CC/PD terms — both gaps documented above; the post should note "no free portrait available" rather than substitute copyrighted material.
- All licenses verified at source page before download; all files passed `file` sanity check (valid SVG / JPEG).
