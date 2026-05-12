# Image Research: William Bourke and the Spectral Transform Method

Research compiled 2026-05-12 for the upcoming NWP-history post on William Bourke
and the spectral transform method in numerical weather prediction.

All candidates below have been verified via direct fetch of their Wikimedia
Commons / source pages. Licenses are free-use (CC BY, CC BY-SA, CC0, or PD).
Fair-use candidates are explicitly excluded as per project policy.

## Summary of negative findings

- **No verifiable free photo of William Bourke exists.** ResearchGate hosts his
  publication list but no portrait. The Bureau of Meteorology has not released
  a free-license portrait, and Obituaries Australia / National Library of
  Australia / Trove searches do not surface one. The post will need to proceed
  without a portrait of Bourke, or rely on a verbal portrait + an institutional
  photo as the visual anchor.
- **Bureau of Meteorology image archive does not appear to provide
  CC-licensed historical photos.** The BoM website hosts material under standard
  Australian Commonwealth copyright; the only CC0 file on Wikimedia is the
  2022 logo, which is too generic to use as a post image.
- **ECMWF imagery is NOT free-licensed.** ECMWF's terms of use require explicit
  permission for image reuse. Their data products are CC BY 4.0, but the
  imagery on their corporate site is not. **Exclude all ECMWF-hosted images.**
- **No Cyber 205 photograph exists on Wikimedia Commons.** A Cray X-MP (the
  successor that ECMWF actually ran in the 1980s) is a viable substitute.
- **No vintage BMRC computer-room photo could be located** under a free license.

---

## Candidate 1: Spherical harmonics 3D visualisation (high quality, MATLAB)

- **Source page:** https://commons.wikimedia.org/wiki/File:Spherical_Harmonics_deg5.png
- **Direct file URL:** https://upload.wikimedia.org/wikipedia/commons/b/ba/Spherical_Harmonics_deg5.png
- **License:** CC BY-SA 3.0 (Creative Commons Attribution-ShareAlike 3.0 Unported)
- **Author:** Dr Franz Zotter (Institut für Elektronische Musik und Akustik, Graz)
- **Date:** 19 December 2013
- **Dimensions:** 3,438 x 1,875 px, ~1 MB
- **Depicts:** Spherical harmonics up to degree 5, plotted as 3D surfaces with
  alternating positive/negative lobes. Created in MATLAB.
- **Suggested filename:** `Spherical_Harmonics_deg5.png`
- **Suggested caption (Polish):**
  "Sferyczne harmoniki do stopnia 5 - zbior funkcji bazowych, na ktorych
  spektralna metoda transformacji rozwija pole meteorologiczne. Wyzsze stopnie
  oddaja coraz drobniejsze szczegoly. _Dr Franz Zotter, CC BY-SA 3.0, via
  Wikimedia Commons._"

## Candidate 2: Spherical harmonics overview (cleaner, fewer plots)

- **Source page:** https://commons.wikimedia.org/wiki/File:Representative-spherical_harmonics.png
- **Direct file URL:** https://upload.wikimedia.org/wikipedia/commons/9/90/Representative-spherical_harmonics.png
- **License:** CC BY-SA 3.0 + GFDL 1.2+
- **Author:** P.wormer (Wikipedia user)
- **Date:** 6 December 2010
- **Dimensions:** 800 x 600 px, 174 KB
- **Depicts:** Six 3D plots of representative spherical harmonics
  (Y_0^0, Y_1^0, Y_2^0 and others), each labelled with its formula.
- **Suggested filename:** `Representative_spherical_harmonics.png`
- **Suggested caption (Polish):**
  "Szesc reprezentatywnych funkcji harmonik sferycznych z formulami. Bourke
  zbudowal model atmosfery, w ktorym kazde pole - cisnienie, wiatr,
  temperatura - jest suma takich funkcji ze swoimi wspolczynnikami.
  _P.wormer, CC BY-SA 3.0, via Wikimedia Commons._"
- **Note:** Alternative to Candidate 1 if a smaller, less busy diagram is
  preferred. Use one, not both.

## Candidate 3: Rotating spherical harmonics (animated)

- **Source page:** https://commons.wikimedia.org/wiki/File:Rotating_spherical_harmonics.gif
- **Direct file URL:** https://upload.wikimedia.org/wikipedia/commons/1/12/Rotating_spherical_harmonics.gif
- **License:** CC BY-SA 3.0 + GFDL 1.2+
- **Author:** Cyp (2005), enhanced by Chemmix (2016)
- **Dimensions:** 445 x 445 px, ~800 KB
- **Depicts:** Animated GIF showing harmonics from l=0 to l=4 (rows) and
  m=0 to ±4 (columns), rotating around the z-axis.
- **Suggested filename:** `Rotating_spherical_harmonics.gif`
- **Note:** Animated GIFs render fine in Minimal Mistakes; this is the
  pedagogically clearest "what is a spherical harmonic" image in the post.
  Use this OR Candidate 1, not both.

## Candidate 4: Gaussian grid (the actual reason for the name)

- **Source page:** https://commons.wikimedia.org/wiki/File:NCEP_T62_gaussian_grid.png
- **Direct file URL:** https://upload.wikimedia.org/wikipedia/commons/a/a9/NCEP_T62_gaussian_grid.png
- **License:** CC BY 4.0
- **Author:** M. W. Toews
- **Date:** 28 August 2007
- **Dimensions:** 795 x 795 px, 100 KB
- **Depicts:** NCEP/NCAR T62 Gaussian grid: 192 longitudes uniformly spaced,
  94 latitudes unequally spaced (Gauss-Legendre quadrature points). This is
  exactly the kind of physical-space grid Bourke's spectral transform method
  produces when it returns to grid space.
- **Suggested filename:** `NCEP_T62_gaussian_grid.png`
- **Suggested caption (Polish):**
  "Siatka Gaussa T62 - 192 dlugosci geograficznych rownomiernie rozmieszczonych
  i 94 szerokosci geograficznych rozmieszczonych zgodnie z kwadratura
  Gaussa-Legendrea. Tu wlasnie siatka spotyka spektrum: na tej siatce model
  oblicza wartosci nieliniowe, ale calkowanie wraca do harmonik sferycznych.
  _M. W. Toews, CC BY 4.0, via Wikimedia Commons._"

## Candidate 5: Latitude-longitude graticule on sphere (for comparison)

- **Source page:** https://commons.wikimedia.org/wiki/File:Latitude_and_longitude_graticule_on_a_sphere.svg
- **Direct file URL:** https://upload.wikimedia.org/wikipedia/commons/8/83/Latitude_and_longitude_graticule_on_a_sphere.svg
- **License:** Public domain (released by author)
- **Author:** Peter Mercator
- **Date:** 5 December 2010
- **Format:** SVG (scalable, perfect for the white-frame CSS)
- **Depicts:** Classic 10-degree lat-lon graticule, shown in perspective.
- **Suggested filename:** `Latitude_longitude_graticule_sphere.svg`
- **Suggested caption (Polish):**
  "Regularna siatka geograficzna - poludniki i rownoleznika co 10 stopni.
  Wlasnie ta siatka byla problemem: bieguny to osobliwosc, a punkty siatki
  zageszczaja sie tam tak gesto, ze krok czasowy musi byc absurdalnie krotki.
  _Peter Mercator, public domain, via Wikimedia Commons._"
- **Use case:** Pair with Candidate 4 to show "lat-lon vs Gaussian" or with
  Candidate 6 to show "lat-lon vs icosahedral" - the visual contrast is the
  point.

## Candidate 6: Geodesic / icosahedral polyhedron

- **Source page:** https://commons.wikimedia.org/wiki/File:Geodesic_Polyhedron.svg
- **Direct file URL:** https://upload.wikimedia.org/wikipedia/commons/c/c3/Geodesic_Polyhedron.svg
- **License:** CC BY-SA 4.0
- **Author:** Pota12
- **Date:** 31 October 2021
- **Format:** SVG
- **Depicts:** A geodesic polyhedron (20 hexagons + 12 pentagons) - the same
  topology used by modern icosahedral atmospheric models (ICON, GME).
- **Suggested filename:** `Geodesic_icosahedral_polyhedron.svg`
- **Suggested caption (Polish):**
  "Siatka ikosaedralno-szesciokatna - dzisiejszy nastepca i siatki Gaussa, i
  spektralnej metody. Brak osobliwosci na biegunach, prawie jednorodne pola.
  Wspolczesne modele DWD (ICON) zbudowane sa wlasnie na takiej geometrii.
  _Pota12, CC BY-SA 4.0, via Wikimedia Commons._"
- **Use case:** Closing image / forward-looking visual - what came after
  Bourke's spectral method.

## Candidate 7: Cray-1 (Computer Museum of America, sharp museum photo)

- **Source page:** https://commons.wikimedia.org/wiki/File:Cray-1_at_Computer_Museum_of_America.jpg
- **Direct file URL:** https://upload.wikimedia.org/wikipedia/commons/a/a8/Cray-1_at_Computer_Museum_of_America.jpg
- **License:** CC BY-SA 4.0 (also available as CC BY-SA 3.0)
- **Author:** Jud McCranie (Wikimedia: Bubba73)
- **Date:** 11 August 2019
- **Dimensions:** 6,016 x 4,016 px, ~20 MB original
- **Depicts:** The iconic Cray-1 in its C-shaped cabinet with padded bench
  seating, at the Computer Museum of America (Roswell, Georgia).
- **Suggested filename:** `Cray-1_Computer_Museum_of_America.jpg`
- **Note:** We have used Cray-1 images in earlier posts. Check
  /home/michal/repos/michalbrennek.github.io/research/INDEX.md and
  IMAGE_SOURCE_AUDIT.md to make sure this exact file has not been used yet.
  If a fresh angle is needed, **Candidate 7b** below is an alternative.

## Candidate 7b: Cray-1 (Science Museum London, alternative angle)

- **Source page:** https://commons.wikimedia.org/wiki/File:Cray1LondonScienceMuseum.jpg
- **Direct file URL:** https://upload.wikimedia.org/wikipedia/commons/e/ea/Cray1LondonScienceMuseum.jpg
- **License:** CC BY 3.0
- **Author:** Cth103
- **Date:** 14 March 2018
- **Dimensions:** 983 x 1,751 px (portrait orientation)
- **Depicts:** The Cray-1 at the Science Museum, London.
- **Suggested filename:** `Cray-1_Science_Museum_London.jpg`
- **Note:** Portrait orientation is good if a sidebar / mid-paragraph layout
  is wanted, since most museum Cray photos are landscape.

## Candidate 8: Cray X-MP at Linköping University (1989-1993)

- **Source page:** https://commons.wikimedia.org/wiki/File:Linköping_University_CRAY_X-MP.jpeg
- **Direct file URL:** https://upload.wikimedia.org/wikipedia/commons/c/ca/Linköping_University_CRAY_X-MP.jpeg
- **License:** CC BY-SA 2.5
- **Author:** Jens Ayton (Wikimedia: Ahruman)
- **Date:** 7 April 2006 (photo of machine that was in service 1989-1993)
- **Dimensions:** 1,024 x 640 px
- **Depicts:** Cray X-MP/416 at Linköping University, Sweden - the machine
  ECMWF actually ran in the 1980s when Bourke's spectral method went
  operational there.
- **Suggested filename:** `Cray_X-MP_Linkoping.jpeg`
- **Suggested caption (Polish):**
  "Cray X-MP/416 na Uniwersytecie w Linköping, w sluzbie 1989-1993. ECMWF
  uruchomil swoj pierwszy operacyjny model spektralny wlasnie na takiej
  maszynie - bo bez wektorowego superkomputera transformacja Legendrea
  bylaby zbyt droga, by sie oplacic. _Jens Ayton, CC BY-SA 2.5, via Wikimedia
  Commons._"
- **Note:** Strong substitute for the (unavailable) Cyber 205 - the X-MP is
  actually the more historically accurate machine for the ECMWF spectral
  story.

## Candidate 9: Cray X-MP at NASA Glenn (1989, PD-USGov)

- **Source page:** https://commons.wikimedia.org/wiki/File:Cray_XMP_SSD_Nasa_1989_10084.jpg
- **Direct file URL:** https://upload.wikimedia.org/wikipedia/commons/b/b0/Cray_XMP_SSD_Nasa_1989_10084.jpg
- **License:** Public domain (NASA work of US federal government - PD-USGov-NASA)
- **Author:** NASA (uncredited photographer)
- **Date:** 1 September 1989
- **Dimensions:** 2,880 x 3,600 px, ~1.6 MB
- **Depicts:** NASA's Cray X-MP with Solid State Storage Device (SSD) at the
  Glenn Research Center.
- **Suggested filename:** `Cray_XMP_NASA_1989.jpg`
- **Note:** Higher resolution than Candidate 8 and PD-USGov is the cleanest
  possible license. Good alternative if a US-coded image is preferred over a
  Swedish one.

---

## Recommended selection (6 images)

For a typical post layout, I suggest:

1. **Lead image:** Candidate 7 or 7b - vintage Cray-1 as visual hook (the
   physical icon of the era when spectral methods went operational).
2. **Concept image 1:** Candidate 3 (rotating animated harmonics) OR
   Candidate 2 (static representative harmonics) - to introduce what a
   spherical harmonic actually is.
3. **Concept image 2:** Candidate 4 (Gaussian grid) - to show what the
   "Gaussian" in T62 / T106 etc. means physically.
4. **Comparison image:** Candidate 5 (lat-lon graticule) - paired with
   Candidate 4 in the discussion of why spectral methods avoided the polar
   singularity.
5. **Operational machine:** Candidate 8 or 9 (Cray X-MP) - when discussing
   ECMWF putting Bourke's method into operational forecasting in the 1980s.
6. **Closing / forward look:** Candidate 6 (icosahedral polyhedron) - what
   replaced spectral methods at DWD and other centres in the 2010s.

If only 4-5 images are wanted, drop either the second Cray or the
icosahedral closing image.

---

## Negative results documented (do NOT use)

- **ECMWF historical forecast charts** - corporate site, not CC-licensed.
- **Bureau of Meteorology institutional photos** - not on Wikimedia under free
  licenses. The only CC0 BoM file is the 2022 logo (generic, not useful).
- **William Bourke portrait** - no free-licensed photo found anywhere
  (ResearchGate, Obituaries Australia, Trove, NLA, BoM staff pages).
- **CDC Cyber 205** - no Wikimedia Commons file located. Science Museum Group
  has a "divide panel" object but it's an internal panel, not the machine,
  and licensing is not confirmed CC.
- **BMRC computer room (vintage)** - no free image found.
