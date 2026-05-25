# Reanalysis Lineage from Kalnay 1996

Agent #4 research for Post 46. The lineage of global atmospheric reanalysis products that descended from — or paralleled — Kalnay et al. 1996.

## Status: IN PROGRESS

## Timeline of major global reanalyses

| Year | Product | Center | Anchor publication | Period covered |
|---|---|---|---|---|
| 1996 | **NCEP/NCAR R1** | NCEP + NCAR | Kalnay et al. 1996 BAMS 77:437–471 | 1948–present (rolling) |
| 1996 | **ERA-15** | ECMWF | Gibson et al. 1997 | 1979–1993 |
| 2002 | **NCEP/DOE R2** | NCEP + DOE | Kanamitsu et al. 2002 BAMS | 1979–present (fixes R1) |
| 2005 | **ERA-40** | ECMWF | Uppala et al. 2005 QJRMS | 1957–2002 |
| 2007 | **JRA-25** | JMA | Onogi et al. 2007 J. Meteor. Soc. Japan | 1979–2004 |
| 2010 | **CFSR** | NCEP | Saha et al. 2010 BAMS 91:1015–1058 | 1979–2009 (later extended) — first coupled atm-ocean-land-ice reanalysis |
| 2011 | **ERA-Interim** | ECMWF | Dee et al. 2011 QJRMS 137:553–597 | 1979–2019 (bridge product) |
| 2011 | **20CR v2** | NOAA-CIRES-DOE | Compo et al. 2011 QJRMS | 1871–2008 (later v3 1806–2015) — surface-pressure-only DA |
| 2011 | **MERRA** | NASA GMAO | Rienecker et al. 2011 J. Climate | 1979–2016 |
| 2015 | **JRA-55** | JMA | Kobayashi et al. 2015 J. Meteor. Soc. Japan — first 4D-Var Japanese reanalysis | 1958–Jan 2024 |
| 2017 | **MERRA-2** | NASA GMAO | Gelaro et al. 2017 J. Climate | 1980–present |
| 2020 | **ERA5** | ECMWF | Hersbach et al. 2020 QJRMS 146:1999–2049 | 1940–present (back-extension to 1940; original release 1979–) |
| 2023 | **JRA-3Q** | JMA | Kosaka et al. 2024 J. Meteor. Soc. Japan | Sep 1947–present — successor to JRA-55 |
| ~2026+ | **ERA6** | ECMWF | (in development) | TBD |

## Key features by product

### NCEP/DOE R2 (Kanamitsu et al. 2002)
A "second look" reanalysis that corrected human-known errors in R1: the snow-cover bug, the PAOBs bug in the Southern Hemisphere, improved parameterizations. Same model resolution (T62L28). Not a wholesale replacement — R1 continues to be updated alongside.

### CFSR (Saha et al. 2010)
First **coupled** atmosphere-ocean-land-ice reanalysis. T382 (~38 km) atmosphere, 64 vertical levels, GSI variational DA, satellite radiances assimilated. Provided the climatological baseline for NCEP's operational CFSv2 forecasts.

### ERA-Interim (Dee et al. 2011)
The ECMWF "bridge product" between ERA-40 and ERA5. 4D-Var, T255 (~80 km), 60 levels. Ran 1979–August 2019 — explicitly retired when ERA5 superseded it.

### MERRA-2 (Gelaro et al. 2017)
NASA's reanalysis with aerosol assimilation (first reanalysis to do so), GEOS-5 model, ~50 km. Replaced MERRA (Rienecker et al. 2011).

### ERA5 (Hersbach et al. 2020)
The current global reference. ~31 km horizontal (TL639), 137 vertical levels, hourly output, 4D-Var. Originally 1979–present at release in 2018–2019; back-extension to 1950 published later (Bell et al. 2021), then to 1940.

### 20CR v3 (Slivinski et al. 2019 update)
NOAA-CIRES-DOE. Assimilates **only surface synoptic pressure** + SST/sea-ice boundary conditions — radically thin observation network lets the system reach back to 1806. Uses ensemble Kalman filter. The deep-time complement to satellite-era products.

### JRA-3Q (Kosaka et al. 2024)
The Q stands for "Quality." Succeeds JRA-55 from Sep 1947. JRA-55 near-real-time updates terminated January 2024 — JRA-3Q is now JMA's flagship.

## Citation impact of Kalnay et al. 1996

| Metric | Value | Source |
|---|---|---|
| Approximate Google Scholar / aggregator citation count (2025) | ~29,937 | scispace.com / Semantic Scholar |
| Often described as | one of the most highly cited papers in atmospheric science | multiple sources |

## Citation table

| Claim | Primary URL | Wayback URL |
|---|---|---|
| Kanamitsu et al. 2002 NCEP/DOE R2 reference | https://en.wikipedia.org/wiki/Atmospheric_reanalysis | https://web.archive.org/web/2024/https://en.wikipedia.org/wiki/Atmospheric_reanalysis |
| Uppala et al. 2005 ERA-40 reference | https://en.wikipedia.org/wiki/Atmospheric_reanalysis | https://web.archive.org/web/2024/https://en.wikipedia.org/wiki/Atmospheric_reanalysis |
| Saha et al. 2010 CFSR — first coupled reanalysis | https://journals.ametsoc.org/view/journals/bams/91/8/2010bams3001_1.xml | https://web.archive.org/web/2024/https://journals.ametsoc.org/view/journals/bams/91/8/2010bams3001_1.xml |
| ERA5 published Hersbach et al. 2020 QJRMS 146:1999-2049 | https://rmets.onlinelibrary.wiley.com/doi/10.1002/qj.3803 | https://web.archive.org/web/2024/https://rmets.onlinelibrary.wiley.com/doi/10.1002/qj.3803 |
| 20CR v3 covers 1836–2015 (experimental to 1806) | https://psl.noaa.gov/data/20thC_Rean/ | https://web.archive.org/web/2024/https://psl.noaa.gov/data/20thC_Rean/ |
| 20CR uses surface pressure only DA | https://psl.noaa.gov/data/20thC_Rean/ | https://web.archive.org/web/2024/https://psl.noaa.gov/data/20thC_Rean/ |
| JRA-55 — first 4D-Var Japanese reanalysis covering 1958– | https://jra.kishou.go.jp/JRA-55/index_en.html | https://web.archive.org/web/2024/https://jra.kishou.go.jp/JRA-55/index_en.html |
| JRA-3Q covers Sep 1947–present, successor to JRA-55 | https://www.data.jma.go.jp/jra/html/JRA-3Q/index_en.html | https://web.archive.org/web/2024/https://www.data.jma.go.jp/jra/html/JRA-3Q/index_en.html |
| Kalnay 1996 ~29,937 citations | https://scispace.com/papers/the-ncep-ncar-40-year-reanalysis-project-yeggi2oyjq | https://web.archive.org/web/2024/https://scispace.com/papers/the-ncep-ncar-40-year-reanalysis-project-yeggi2oyjq |
