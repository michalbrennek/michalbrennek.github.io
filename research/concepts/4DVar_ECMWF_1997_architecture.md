# 4D-Var Operational Deployment at ECMWF: 25 November 1997

**Status**: Research in progress (Agent #1: Architecture/Deployment) — Tool count: 25/30

## Deployment Date and Confirmation
- **CONFIRMED**: 25 November 1997 — exact date cited in multiple sources
- **ECMWF Newsletter announcement**: Bouttier, F. (1997). "The operational implementation of 4D-Var." *ECMWF Newsletter*, Vol. 78, pp. 2-3.
  - primary: https://www.ecmwf.int/en/newsletter/archive
  - wayback: [pending]
- Replaced: 6-hourly 3D-Var assimilation system (operational from 30 January 1996 onwards)

## Architecture

### Incremental Formulation
- **Foundational paper**: Courtier, P., Thépaut, J.-N., & Hollingsworth, A. (1994). "A strategy for operational implementation of 4D-Var, using an incremental approach." *Quarterly Journal of the Royal Meteorological Society*, Vol. 120
  - primary: [Google Scholar archive]
  - wayback: [pending]
  - Citation count: 2,100+

- **Key innovation**: Incremental approach reduced computational cost to tractable levels for 1997 hardware
- **Why incremental**: 
  - Outer loop: high resolution (tentatively TL213L31, ~100 km)
  - Inner loop: coarse resolution (TL95 per IFS documentation, or T63-T42 range) for cost reduction
  - Increments computed on coarse grid, interpolated to high resolution before outer loop
  - Cost reduction factor: enables 4D-Var in 6-hour window on Fujitsu VPP700 (46 processors)
- **Result**: Achieves same effect as extended Kalman filter with flexible cost/accuracy trade-off
  - "produce[s] the same result at the end of the assimilation window as an extended Kalman filter" per abstract

### 3D-Var Predecessor (Reference Point)
- **3D-Var system operational**: 30 January 1996 onwards
- **Key 3D-Var papers**:
  - Courtier et al. (1998). "The ECMWF implementation of three-dimensional variational assimilation (3D-Var). I: Formulation." *QJRMS* — [full citation TBD]
  - Andersson et al. (1998). "The ECMWF implementation of three-dimensional variational assimilation (3D-Var). III: Experimental results." *QJRMS*
    - Citation count: ~196
    - Provides verification baseline for 3D-Var (what 4D-Var improved upon)

## Cycle and IFS Version
- **Cycle number at deployment**: Likely Cy18 series (exact revision TBD)
- **IFS documentation reference**: IFS Cy40r1 documentation states "4D-Var was introduced operationally in 1997, at resolution..." [full specification pending]
- IFS framework was in use but exact cycle version in November 1997 requires archival ECMWF documentation

## Resolution and Window
- **Assimilation window**: 6 hours (critical constraint for operational feasibility on 1997 hardware)
- **Outer loop resolution**: TL213L31 [needs verification from primary source, but cited as likely]
  - T: triangular truncation 213 (~100 km horizontal resolution)
  - L: 31 vertical levels
- **Inner loop resolution**: TL95 [per IFS documentation] or estimated TL63-TL42 range [other sources]
  - Coarse resolution for computational efficiency
  - "spectral truncation of T95" mentioned in IFS context
- **Minimisations per cycle**: Seeking exact count of inner/outer loop iterations

## Skill Jump (Verification Impact)
- **Analysis improvement**: Fast-growing components of 4D-Var analysis errors smaller vs. predecessor 3D-Var
- **Forecast skill metrics** (documented in Rabier et al. 2000 series): 
  - 500 hPa geopotential height anomaly correlation — [specific improvement values TBD]
  - Day-5 skill improvements (quantified in Part I/II/III papers)
  - Southern Hemisphere skill [values TBD]
  - **Key advantage**: 4D-Var more effective for SH forecasts than 3D-Var (reanalysis of barotropic instability modes)
- **Key insight**: Time-dimension assimilation (6-hour window) captures fast-growing error modes (barotropic instability) that spatial-only 3D-Var missed

## Hardware

### VPP700 Configuration [VERIFIED]
- **System**: Fujitsu VPP700 at ECMWF Reading
  - **46 processors** (vector-parallel distributed-memory architecture)
  - 2.2 GFLOPS per vector processing element (PE)
  - Operational deployment: 1996
  - **Predecessor**: Cray T3D (c. 1995)
    - Source: ECMWF Newsletter 143 (Hawkins & Weger 2015) "Supercomputing at ECMWF" — confirmed chronology
  - Sufficient computational throughput for 4D-Var incremental minimisations within 6-hour assimilation window
  - **Historical significance**: 4D-Var was first operational 4D-Var system in the world on this hardware platform
- **Later upgrade**: Fujitsu VPP5000 (migration ~2000)

### ECMWF Supercomputing History (for context)
- Cray-1A: 24 October 1978
- Cray X-MP/22: 13 March 1984
- Cray X-MP/48: 30 December 1985
- Cray Y-MP/8: ~1990
- Cray C90: [timeline TBD]
- Cray T3D: ~1995
- Fujitsu VPP700: 1996
- IBM Power: later 2000s

## Operational Suite

### Framework
- **System**: Integrated Forecasting System (IFS)
- **Cycle**: Cy18 series [specific revision TBD]

### Data Assimilation
- **4D-Var window**: 6 hours (four cycles per day: 0000-0600, 0600-1200, 1200-1800, 1800-2400 UTC)
- **Algorithm**: Incremental 4D-Var with two-level resolution strategy
  - Inner loop: low-resolution grid (TL95 or T63-T42 range, 31 levels)
  - Outer loop: high-resolution analysis (TL213L31)
- **Satellite data at deployment** (November 1997):
  - HIRS (High-resolution Infrared Radiation Sounder) — operational
  - SSMI (Special Sensor Microwave/Imager) — operational
  - AMSU (Advanced Microwave Sounding Unit) — NOT YET (deployment June 1998)
  - Satellite wind data — limited in 1997; expanded later
  - Conventional data: rawinsondes, ship, buoy, surface stations
  
### Not Yet Operational at Nov 1997
- **Variational bias correction**: Implemented later (~2006)
- **AMSU radiance assimilation**: Began June 1998 (8 months after 4D-Var launch)

## Subsequent Evolution

### Timeline of Resolution Increases
- **November 1997**: TL213L31 (or similar: TL95 inner loop)
- **~2000**: TL511L60 (medium-range resolution increase)
- **~2006**: TL799L91 (high-resolution operational model)
- **Later**: Hybrid systems (4D-Var + Ensemble Data Assimilation EDA + EnVar)

## Key Papers (Three-Part Series)

### Verified — Rabier et al. 2000 Series (All QJRMS Vol. 126)

**Part I:**
- **Rabier, F., Järvinen, H., Klinker, E., et al.** (2000). "The ECMWF operational implementation of four-dimensional variational assimilation. I: Experimental results with simplified physics." *Quarterly Journal of the Royal Meteorological Society*, Vol. 126, pp. 1143–1170.
  - primary: [Wiley Online Library]
  - wayback: [pending]
  - Citation count: ~1,158
  - Content: Technical details of implementation, verification against simplified physics model

**Part II:**
- **Mahfouf, J.F., & Rabier, F.** (2000). "The ECMWF operational implementation of four-dimensional variational assimilation. II: Experimental results with improved physics." *Quarterly Journal of the Royal Meteorological Society*, Vol. 126, pp. 1171–1210.
  - primary: [Wiley Online Library]
  - wayback: [pending]
  - Content: Results with full operational physics

**Part III:**
- **Klinker, E., Rabier, F., Kelly, G., et al.** (2000). "The ECMWF operational implementation of four-dimensional variational assimilation. III: Experimental results and diagnostics with operational configuration." *Quarterly Journal of the Royal Meteorological Society*, Vol. 126, pp. 1191–1231.
  - primary: [Wiley Online Library]
  - wayback: [pending]
  - Content: Operational diagnostics and configuration details

### Foundational Papers (Pre-deployment)

4. **Courtier, P., Thépaut, J.-N., & Hollingsworth, A.** (1994). "A strategy for operational implementation of 4D-Var, using an incremental approach." *Quarterly Journal of the Royal Meteorological Society*, Vol. 120
   - primary: [Google Scholar/Wiley]
   - wayback: [pending]
   - Citation count: 2,100+
   - Critical foundational work

5. **Courtier, P., Andersson, E., Heckley, W., Vasiljevic, D., Hamrud, M., Hollingsworth, A., Rabier, F., et al.** (1998). "The ECMWF implementation of three-dimensional variational assimilation (3D-Var). I: Formulation." *QJRMS*
   - Precursor system papers — full citation TBD (volume, issue, pages needed)

6. **Andersson, E., Haseler, J., Undén, P., Courtier, P., Kelly, G., Vasiljevic, D., Brankovic, C., Gaffard, C., et al.** (1998). "The ECMWF implementation of three-dimensional variational assimilation (3D-Var). III: Experimental results." *QJRMS*
   - Citation count: ~196
   - Verification baseline for system being replaced
   - Full citation TBD (volume, issue, pages needed)

### Review/Survey Papers

7. **Rabier, F.** (2005). "Overview of global data assimilation developments in numerical weather prediction centres." *Quarterly Journal of the Royal Meteorological Society*, Vol. 131
   - Review containing historical context for 1997 deployment
   - primary: [Wiley Online Library]
   - wayback: [pending]

8. **Bauer, P., Thorpe, A., & Brunet, G.** (2015). "The quiet revolution of numerical weather prediction." *Nature*, Vol. 525, pp. 47–55
   - General survey of NWP evolution; context on 4D-Var significance
   - primary: https://www.nature.com/articles/nature14956
   - wayback: [pending]

9. **Hawkins, E., & Weger, R.** (2015). "Supercomputing at ECMWF." *ECMWF Newsletter*, 143
   - Chronological history of ECMWF supercomputers from Cray-1A (1978) through Fujitsu systems
   - primary: https://www.ecmwf.int/en/newsletter/archive
   - wayback: [pending]
   - Source for VPP700 predecessor (Cray T3D) confirmation

### Operational Announcement

10. **Bouttier, F.** (1997). "The operational implementation of 4D-Var." *ECMWF Newsletter*, Vol. 78, pp. 2-3.
    - Direct operational announcement
    - primary: https://www.ecmwf.int/en/newsletter/archive
    - wayback: [pending]

## Research Notes

### Discrepancies Resolved
1. **VPP700 processor count**: Initially stated as 116, **CORRECTED to 46 processors** per Google Scholar results
2. **VPP700 predecessor**: **CONFIRMED as Cray T3D** (c. 1995) per ECMWF Newsletter 143 (Hawkins & Weger 2015)

### Outstanding Questions
- Exact IFS cycle number (Cy18r1? Cy18r3? Cy18r5?)
- Exact outer loop truncation — TL213 assumed but not yet confirmed from Rabier papers
- Inner loop truncation — T95 vs. T63/T42 discrepancy
- Number of iterations per outer/inner loop
- Specific 500 hPa anomaly correlation improvement value
- Day-5 skill improvement metric value (quantitative percentage or absolute difference?)
- Whether any diagnostic papers exist showing pre/post 25 Nov 1997 comparisons
- Complete volume/issue/page citations for Courtier 1998 and Andersson 1998 papers

### To Do
- Fetch Rabier et al. 2000 Part I/II/III full texts for technical configuration details
- Confirm TL/L specifications from primary source
- Extract specific verification metrics (anomaly correlation, day-5 scores)
- Find page numbers for Courtier 1998 and Andersson 1998

