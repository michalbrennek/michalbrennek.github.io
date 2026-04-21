---
layout: single
title: "The Language That Refused to Die"
date: 2026-04-21 08:00:00 +0100
categories: [Weather, HPC, History]
tags: [FORTRAN, Fortran2023, ECMWF, NOAA, NCAR, LAPACK, Dongarra, Manabe, Julia, Python, Computing]
header:
  teaser: /assets/images/header-fortran-afterlife.jpg
  overlay_image: /assets/images/header-fortran-afterlife.jpg
  overlay_filter: "0.6"
excerpt: "In 2026, a language designed in 1954 for a ten-ton vacuum-tube machine still runs every operational weather forecast, every major climate model, and -- through a chain that most Python programmers have never traced -- every matrix-inverse call you make from NumPy. This post is about how that happened, and why nobody can stop it."
---

This is the third and last post in a short series on the history of FORTRAN. Part 1, [God Is Real (Unless Declared Integer)](/weather/hpc/history/2026/04/19/God-is-real-unless-declared-integer.html), covered the birth of the language at IBM between 1954 and 1957. Part 2, [The Empire That Its Creator Repudiated](/weather/hpc/history/2026/04/20/The-empire-that-its-creator-repudiated.html), covered the thirty years between 1957 and 1990 in which FORTRAN took over scientific computing, was attacked by everyone who taught programming in the universities, and was publicly disowned by its own inventor in his 1977 Turing Award lecture. Part 3 is about what happened when the language that everyone kept predicting would be obsolete in five years instead outlived its critics and became, by 2026, what programming-language theorists call an **ABI** -- a stable machine-level contract that makes an entire scientific software ecosystem possible without most of its users ever knowing.

It is not a story about Fortran winning arguments. Fortran did not win any arguments. What it did was keep shipping, keep compiling, keep producing correct answers inside the operational codes of ECMWF, NOAA, NCAR, DWD, Meteo-France, the U.S. Department of Energy, Princeton's GFDL, Argonne National Laboratory, CERN, NASA, and about four hundred other institutions whose work is to compute things. Every day. At machine precision. Faster than its replacements.

I will come to the Python secret, and to Jack Dongarra's 2021 Turing Award, and to the moment somebody at MIT decided to rewrite a climate model in Julia and got a three-times speedup instead of the three-times slowdown they had budgeted for. First I want to tell you what the 1991 standards committee did, and why, of all things, it was the thing that made the rest of this possible.

---

## The Rewrite That Didn't Kill It

Part 2 ended in 1990 with the X3J3 committee deep in work on what everyone at the time was calling "Fortran 8X," because they had been hoping to ship it in 1988. They did not ship it in 1988. They shipped it in 1991, as **ISO/IEC 1539:1991** -- informally **Fortran 90** -- and it was the first fundamental redesign of the language since the ANSI X3.9-1966 standard that I wrote about in [Part 2](/weather/hpc/history/2026/04/20/The-empire-that-its-creator-repudiated.html).

The twelve-year gestation had been bruising. Some US compiler vendors had tried to derail the whole revision, fearing the cost of implementing the new features. Enormous Fortran 77 installations had lobbied against breaking changes. The committee won a critical concession from both sides: Fortran 90 was a pure superset of Fortran 77. Every valid F77 program -- including the million-line atmospheric models and reactor-physics codes that ran on every supercomputer in the world -- was still a valid F90 program on the day the standard shipped. Nothing was deleted. The old features were marked "obsolescent" (a new word in Fortran standards) but they were not removed. Someone whose 1978 code had worked on IBM, CDC, Cray, Fujitsu, and DEC compilers in 1989 could send the same source file to a Fortran 90 compiler in 1991 and get the same answer.[^1]

That was the political miracle. The technical content of Fortran 90 is more important.

Fortran 90 killed the punched-card layout. For thirty-three years -- from 1957 through 1990 -- every FORTRAN source file in the world had been structured as if it were going to be punched onto an 80-column card. Column 1 was reserved for a comment mark (`C`) or for statement labels. Columns 1 through 5 held an optional label number. Column 6 was the continuation marker. Columns 7 through 72 held the actual statement. Columns 73 through 80 held a sequence number for the card. Fortran 90 introduced **free-form source**: no more columns, no more fixed structure, lowercase keywords, identifiers up to 31 characters. The fixed-form syntax was still accepted -- again, the superset rule -- but the future would not look like punched cards any more.

Fortran 90 added `MODULE` and `INTERFACE` constructs that finally gave the language modularity and typed procedure calls. Before 1991, a Fortran subroutine's type signature was a handshake: you called `CALL SGEMV(A, X, Y, N, ALPHA, BETA, ...)` and the compiler trusted that you had the arguments in the right order. After 1991, an `INTERFACE` block let you declare what the signature was, and the compiler could actually check that the caller and the callee agreed. Modules bundled related declarations, data, and procedures into a single compilable unit with explicit import and export semantics. An entire generation of "header file" diseases in C was skipped, because Fortran had the right abstraction from the start.

Fortran 90 added `ALLOCATE` and `DEALLOCATE` -- dynamic memory management at last. Before 1991, every array in a Fortran program was sized at compile time (either fixed in a dimension statement or passed in through a subroutine's dummy argument). After 1991, a program could ask the runtime for an array of a size computed at runtime. The cost of doing this in a 1970s atmospheric model was usually a collection of clever hacks involving `COMMON` blocks, manual subscript arithmetic, and very large preallocated scratch arrays. Those hacks were, in 1991, about to stop being necessary.

Fortran 90 added **whole-array operations**. This is the feature that really matters for scientific computing. An expression like `a = b + c`, where `a`, `b`, and `c` are arrays of the same shape, means what it says. The 1977 version of this expression was three nested `DO` loops. The 1991 version is one line, and the compiler is free to choose the loop order, the vectorisation strategy, and the cache-blocking pattern. For a language whose primary job is to add arrays of floating-point numbers, this is the most important change since the 1962 introduction of hardware floating-point.

Fortran 90 added `RECURSIVE` procedures, a feature that had been explicitly forbidden by the 1957 standard because the IBM 704 had no stack. It added derived data types, giving scientists a way to group related data (a coordinate, say, or a point in a three-dimensional field) into a named record. It added structured control: `SELECT CASE`, `DO WHILE`, `EXIT`, `CYCLE`. It added `POINTER` variables with strict aliasing rules -- the single language-design decision, taken in 1991, that would turn out to still give Fortran a performance edge over C in numerical code in 2026. We will come back to this.

The first Fortran 90 compiler was written by **Malcolm Cohen** at the Numerical Algorithms Group in Oxford. He wrote it alone, in 1990 and 1991, and NAG shipped it in September 1991, less than six months after the standard was approved. He is still, in 2026, the Project Editor of the ISO/IEC Fortran standard.[^2]

---

## The Committee's Steady Hand

The thirty-three years from 1991 to 2026 saw six more revisions of the standard:

- **Fortran 95** (ISO/IEC 1539-1:1997). A minor revision. Added `FORALL`, nested `WHERE`, `PURE` and `ELEMENTAL` procedures. Most of these features came straight from the **High Performance Fortran Forum**, a 1991-1993 effort led by Ken Kennedy at Rice University to extend Fortran with data-parallel constructs. HPF itself was a commercial failure -- its compilers were too hard to optimise well -- but Fortran 95 absorbed the good ideas and the bad ones were forgotten.[^3]

- **Fortran 2003** (ISO/IEC 1539-1:2004, published after the target year, hence the discrepancy in names). Object-oriented programming, forty-seven years after the language's first compiler shipped. Type extension with single inheritance, polymorphism via the `CLASS` keyword, type-bound procedures, abstract interfaces, and procedure pointers. It also added the `ISO_C_BINDING` intrinsic module, the first time a Fortran standard formally described how to call C from Fortran -- an acknowledgement that the numerical ecosystem had become polyglot and that a Fortran program needed to talk to C libraries without heroic workarounds. Malcolm Cohen designed the OO features.[^4]

- **Fortran 2008** (ISO/IEC 1539-1:2010). The parallel-programming standard. It added **coarrays**, `DO CONCURRENT`, submodules, the `CONTIGUOUS` attribute, the `BLOCK` construct. Coarrays were invented in the 1990s by **Robert Numrich** at Cray Research and jointly developed with **John Reid** of the Rutherford Appleton Laboratory (by then already the Convener of the ISO Fortran committee, a role he would hold from 2000 through 2017). Cray had shipped coarrays in its compilers from CFT release 3.1 onward and had run them in production for roughly ten years. In May 2005, the ISO committee voted to incorporate them into the next standard. When Fortran 2008 shipped, the rest of the Fortran-using world got a production-tested feature that was already a decade old on the day it became standard.[^5]

- **Fortran 2018** (ISO/IEC 1539:2018). Absorbed two separate Technical Specifications: TS 29113 on further C interoperability, and TS 18508 on additional parallel features. The parallel extensions added `TEAMS` (subsets of images), `EVENTS` (point-to-point synchronisation), collective subroutines (`CO_SUM`, `CO_BROADCAST`, and company), and fault-tolerance primitives (`FAILED_IMAGES`, `STOPPED_IMAGES`) aimed at exascale machines where the mean-time-between-failure of a thousand-thousand-core machine becomes a real concern.[^6]

- **Fortran 2023** (ISO/IEC 1539-1:2023, published November 2023). Conditional expressions (`x = (a > b ? a : b)`), enumerated types, typeof/classof for generic programming, degree-based trigonometric intrinsics (`sind`, `cosd`, `tand`). A smaller revision, by design; the next big one, tentatively called Fortran 2028, is already in committee work.[^7]

The people who have steered this process through seven revisions and thirty-three years are not household names even in computing. **John Reid** at Rutherford Appleton spent seventeen consecutive years as Convener of the ISO committee (2000-2017). **Malcolm Cohen** at NAG has been Project Editor of the standard since the mid-1990s. **Michael Metcalf**, retired from CERN, is the author -- with Reid, Cohen, and Reinhold Bader -- of **Modern Fortran Explained**, Oxford University Press, which has been through a new edition for every major standard since Fortran 90. **Jeanne Martin** at NCAR was Convener of WG5 during the Fortran 90 development period. **Jerrold Wagener** at Amoco chaired X3J3 through part of the Fortran 90 and 95 work. These are the people who kept a language most of computer science had declared dead moving forward, in small disciplined increments, for a third of a century. They did it, as far as I can tell, mostly because the people using the language in operational weather services and national laboratories kept asking them for specific improvements that would make their lives easier.[^8]

---

## Why the Forecast Is Still Fortran

I work, day to day, on numerical weather prediction. The reason I am writing this series at all is that the software the field runs on is one of the great living fossils of computing. The **Integrated Forecasting System** at the European Centre for Medium-Range Weather Forecasts is, in 2026, one of the most sophisticated pieces of scientific software on Earth. Its daily job is to take the current state of the atmosphere -- observations from about forty million satellite and in-situ measurements per day -- and use it to predict, in four-dimensional variational data assimilation, what the atmosphere will do for the next ten to fifteen days. The IFS is jointly developed and maintained by ECMWF in Reading and Meteo-France in Toulouse. It has several hundred contributors across a forty-year history. The operational cycle label, as of 2024, is CY49R1.[^9]

![The CSCS Alps supercomputer in Lugano, Switzerland. Machines like this -- several hundred thousand cores across a bank of racks, with NVIDIA or AMD GPUs behind high-bandwidth interconnect -- are where twenty-first-century numerical weather prediction happens. The atmospheric model running on them is still written in Fortran. Photo: CSCS (CC BY-SA 3.0).](/assets/images/CSCS_Alps_supercomputer.jpg)

It is written in Fortran. Millions of lines of Fortran. ECMWF's own coding-standards document is titled **IFS/ARPEGE Fortran Coding Standard** -- the name is primary evidence.[^10]

The people at ECMWF are not pretending that keeping the IFS in Fortran is a stable long-term strategy. In the February 2025 ECMWF Newsletter, an article titled **Modernisation of the Integrated Forecasting System** stated plainly: "It will become more difficult to find software engineers who are willing to work on 'old' software frameworks and computing languages, such as Fortran. [...] Maintaining and updating the IFS has also led to the accumulation of a great deal of technical debt."[^11] They are right. Young computer-science graduates are not arriving at ECMWF having learned Fortran in university. The same is true, with minor variations, at NOAA, at NCAR, at the UK Met Office, at the German DWD, at every major operational weather centre in the world.

What ECMWF is doing about it is worth paying attention to, because it is not "rewrite in another language." It is a coordinated, incremental programme of modernisation that is trying to buy the IFS another decade or two without paying the enormous cost of a ground-up rewrite. The programme has several parts.

**The Scalability Programme** (started 2015) has been ECMWF's umbrella for GPU-readiness work. It has absorbed more than ten million euros of European Union project funding across roughly fifteen projects, and it has produced most of the technical infrastructure that the next decade of IFS evolution will run on.[^12]

**Loki** is a source-to-source Fortran-to-Fortran translator written in Python. It takes a scientist-friendly Fortran kernel and applies transformations -- Single Column Abstraction, Single Column Coalesced -- to produce a GPU-tuned version automatically. The scientist writes something readable and physically meaningful; Loki produces the hardware-tuned version the compiler eats. It is a clever, very Fortran-specific answer to the usual "rewrite in a DSL" pressure.[^13]

**ESCAPE** and **ESCAPE-2** were EU Horizon 2020 projects (2015-2021) that built "dwarfs" -- self-contained mini-applications extracted from IFS kernels -- and used them to experiment with DSLs, MPI+X hybrid programming, and accelerator offload. Dwarfs are a good idea: they let a supercomputer vendor benchmark the thing your operational code actually does without having to port the whole operational code.

In 2022 ECMWF **open-sourced several IFS components** on GitHub: **FIAT** (Fortran IFS and ARPEGE Toolkit, the common utilities), **CLOUDSC** (the cloud microphysics kernel, now used as a GPU benchmark across the community), **ecRad** (Robin Hogan's radiation scheme), and **ecTrans** (the spectral transform library). This is a different model of engagement with the wider HPC community than ECMWF has historically practised. The common thread is that all of these components are Fortran, and opening the source does not change that.[^14]

**Destination Earth** (DestinE) is the EU's digital-twin initiative for the planet. It went live on June 10, 2024, from the LUMI supercomputer in Kajaani, Finland. The Weather-Induced Extremes Digital Twin is built on top of the IFS -- that is, on Fortran. The DestinE Digital Twin Engine uses Loki to retarget IFS kernels across the hardware mix (CPU, NVIDIA GPU, AMD GPU, Cerebras CS-2 for some experiments). A kilometre-scale global weather simulation, in 2024, running on the largest European public supercomputer, driven from Python, is a Fortran code underneath.[^15]

Why is the operational centre not doing a clean rewrite? The answer from Newsletter 182 is candid. It would take decades. The scientific users cannot absorb a multi-year freeze on new physics and new data streams. The verified physics of the IFS, tested against twenty years of observations, would have to be re-verified in a new language. The HPC libraries the IFS depends on -- LAPACK, FFTW, custom MPI collectives, the ECMWF-specific parallel framework -- are either Fortran-native or have Fortran-first interfaces. The cost-benefit arithmetic, run against any serious alternative, has never pencilled out in favour of a rewrite. The compromise is to keep the operational code in Fortran, move the tuning into Python-driven domain-specific languages, and let the scientists keep writing kernels that look like the equations they were trained to think in.

ECMWF is the vanguard. NOAA and NCAR are doing similar things, with local variations.

---

## Why the Climate Is Still Fortran

The **Global Forecast System** at NOAA is the United States' operational weather model, run four times a day from the National Centers for Environmental Prediction. Since June 12, 2019 -- with the transition to GFSv15 -- its dynamical core has been **FV3**, the Finite-Volume Cubed-Sphere Dynamical Core. FV3 was developed at Princeton's Geophysical Fluid Dynamics Laboratory by a team led by **Shian-Jiann Lin**, whose original work at NASA Goddard in the 1990s was on transport modelling for atmospheric chemistry. Lin spent most of the 2000s and 2010s refining FV3 at GFDL until it was good enough to be the dynamical core of the entire Unified Forecast System, which is NOAA's umbrella architecture for all its operational models.[^16]

FV3 is open-source, released by NOAA at github.com/NOAA-GFDL/fv3gfs-fortran. The filename ends in `fortran` because it is Fortran. There is, separately, a Python project called **PyFV3** that rewrites FV3's kernels into a Python-driven DSL called GT4Py, but the operational US weather forecast runs the Fortran version.[^17] The Unified Forecast System, which couples FV3 to the sea-ice model, the ocean model, the land-surface model, and the chemistry model, is open-source and Fortran-based; all the coupling interfaces (the NUOPC caps, standing for National Unified Operational Prediction Capability) are Fortran modules.

![A GFS 850 hPa forecast map. The operational global forecast of the United States is produced every six hours by a model whose dynamical core -- FV3 -- is written in Fortran, and whose descendants trace directly to Syukuro Manabe's 1960s code at GFDL. Photo: NOAA/NWS (public domain).](/assets/images/GFS_forecast.png)

NCAR's climate model, the **Community Earth System Model**, is the descendant of a sequence of community-developed climate models stretching back to the **Community Climate Model** at NCAR in 1983. CCM became CSM in 1996, CCSM in 2004, CESM1 in 2010, CESM2 in 2018, and CESM3 during 2024. Each revision modernised the code base, but the through-line is Fortran. CESM's atmospheric component, CAM (now CAM7 in CESM3), has a published coding standard that requires the compiler to support at least Fortran 2003 features. The code has been modernised from the FORTRAN IV of the Manabe-Smagorinsky era, through Fortran 90 in the 1990s, to Fortran 95 in the 2000s, to Fortran 2003 in the 2010s, and some of CESM now uses Fortran 2008 features. What has not changed is the language.[^18]

![Global surface-temperature anomaly from NASA's GISTEMP 2024 analysis. The Earth-system models that quantify what is happening to this curve -- what will happen to it in 2050, 2100 -- run on Fortran code whose algorithmic lineage traces directly to Syukuro Manabe's 1967 paper on radiative-convective equilibrium. Photo: NASA Scientific Visualization Studio (public domain).](/assets/images/NASA_temperature_anomaly.png)

In 2026, the honest statement is this. Every major operational numerical weather prediction centre on Earth runs a Fortran model. Every major coupled Earth-system climate model on Earth is a Fortran code. ECMWF IFS, NOAA GFS, NCAR CESM, DWD ICON, Meteo-France ARPEGE, the UK Met Office Unified Model, the Japanese Meteorological Agency model, the Australian Bureau of Meteorology model, the Chinese GRAPES model -- every one. There is one notable exception, and I will come to it, which is the Julia-based CLiMA project at Caltech, which has built a research model from scratch in a new language but has not (yet) been adopted by any operational centre. Everything else is Fortran.

There is a lineage that connects the 1967 Manabe-Wetherald radiative-convective paper to the atmosphere component of CESM3 in 2026. I want to be careful about this, because the popular phrasing -- "Manabe's 1967 code still runs inside CESM" -- is stronger than what is actually true. Lines of code do not survive unchanged across sixty years of compiler evolution, standard revisions, and institutional moves. What does survive is the algorithmic lineage: the radiative transfer templates, the moist convection parameterisations, the vertical coordinate treatments, the finite-difference stencil patterns. These trace directly from Manabe and Wetherald 1967, through Manabe-Bryan 1969 (the first coupled ocean-atmosphere general circulation model), through the three-dimensional GFDL GCMs of the 1970s and 1980s, into the NCAR Community Atmosphere Model of the 1990s, and from there into the CESM of 2024. Each generation has been re-implemented for new hardware and in newer Fortran, but the bones of the programs -- the algorithms Manabe pioneered -- are where the line goes. The 2021 Nobel Prize in Physics, which went to Manabe for the physical modelling of Earth's climate, is an award for a lineage of Fortran code as much as for a lineage of scientific ideas.[^19]

---

## The Python Secret

I want to tell you something that most Python programmers I meet do not know. If you import NumPy in 2026 and call `numpy.linalg.solve(A, b)` to solve a linear system -- something most working data scientists do several times a week without thinking about it -- the computation that actually does the work is a FORTRAN subroutine called **DGESV**. It was written in 1992 at Argonne National Laboratory, the University of Tennessee, Oak Ridge National Laboratory, and Cray Research, as part of a library called **LAPACK**.[^20]

The name decodes. **D** is for double precision. **GE** is for a general (non-structured) matrix. **SV** is solve. The body of DGESV is about two hundred lines of Fortran 77 (upgraded to Fortran 90 conventions in LAPACK 3.2, in 2008) that call down to **Level 3 BLAS** -- the Basic Linear Algebra Subprograms, specifically `DGEMM` for matrix multiplication and `DTRSM` for triangular solves -- to do the actual arithmetic. The vendor-tuned implementation of BLAS on your laptop -- Intel MKL, OpenBLAS, AMD AOCL-BLIS, or Apple's Accelerate framework -- is the thing that turns your `@` operator from Python into close to the peak performance of your CPU. Every one of those BLAS implementations exposes a Fortran ABI, because that is the interface LAPACK was written to, and because LAPACK is the interface NumPy was written to, and because nobody has ever found it worthwhile to rebuild the ecosystem on any other contract.

![Jack Dongarra in 2022. Chicago State University physics undergraduate, 1970 Argonne National Laboratory intern on EISPACK, 2021 ACM Turing Award winner for numerical libraries that every data scientist on Earth uses every day without knowing. Photo: Clay Banks, 2022 (CC BY-SA 4.0).](/assets/images/Jack_Dongarra.jpg)

The life of **Jack Dongarra** is the life of this stack. He was a physics undergraduate at Chicago State University in the late 1960s. In 1970 his physics professor, Harvey Leff, suggested he apply for an internship at nearby Argonne National Laboratory. Dongarra walked into a computing workshop there and was told they needed help debugging EISPACK, a FORTRAN library of eigenvalue routines. He stayed. Over the next two decades at Argonne, and then at the University of Tennessee and Oak Ridge, Dongarra was the author or co-author of **LINPACK** (1970s, NSF-funded, with Jim Bunch, Cleve Moler, and Pete Stewart), of **BLAS Level 2** (1988, matrix-vector operations), of **BLAS Level 3** (1990, matrix-matrix operations, the most important performance primitive in modern numerical computing), of **LAPACK** (1992, the successor to LINPACK and EISPACK), and of the **LINPACK Benchmark** on which the TOP500 supercomputer list -- the canonical ranking of the world's fastest machines -- is based. In March 2022 he was announced as the winner of the 2021 ACM Turing Award "for pioneering contributions to numerical algorithms and libraries that enabled high performance computational software to keep pace with exponential hardware improvements for over four decades."[^21]

Between Dongarra's Fortran at Argonne and your Python on your laptop sits one small but crucial piece of glue. In late 1999, an Estonian physics graduate student named **Pearu Peterson**, working at the University of Tartu, wrote a tool called **f2py**. It takes a Fortran source file (77 or 95), parses the subroutine signatures, generates C wrappers that translate NumPy arrays to Fortran's column-major array-with-descriptor conventions, and compiles the result into a Python extension module. Peterson released f2py version 1.116 on January 25, 2000. He integrated it into SciPy in 2005 and into the NumPy source tree in 2006. Since 2011 it has been maintained by the NumPy developers. Every numerical Python library of any significance -- NumPy, SciPy, scikit-learn's numerical kernels, and most of the specialized astronomy and biomedical imaging stacks -- is, at some level, a user of f2py. In a quarter of a century, one Estonian graduate student's parsing tool became the load-bearing bridge between Python and a Fortran stack that predated Python by two decades.[^22]

If you write Python for a living in 2026 and you do any numerical work, there is an overwhelming probability that your program, through NumPy or SciPy or their descendants, spends most of its time in Fortran subroutines written by Jack Dongarra and colleagues between 1979 and 1992, compiled into highly-tuned vendor BLAS implementations in 2026, and wrapped into Python by Pearu Peterson's parser. You did not know this. Dongarra did not get famous. The reason you can compute an eigenvalue on a matrix of a million floats in under a second is a chain of careful engineering that most of the people who use it every day have never traced. Fortran is not just the language of weather models. It is the ABI that scientific Python runs on.

---

## The Aliasing Argument

There is a sub-question hidden inside the previous paragraph. Why is Fortran still faster than C, or C++, or Julia, for this kind of numerical code? It ought not to be. C and C++ have better compilers, better tooling, more users, more books, and a larger ecosystem of corporate investment. Julia was designed in 2012 by people who had explicitly set out to be "as fast as Fortran, as dynamic as Python."[^23] And yet, on the benchmarks that matter for BLAS-style numerical kernels, vendor-tuned Fortran BLAS implementations have consistently edged out equivalent C implementations by roughly 5 to 15 percent on the same CPU, across decades of hardware evolution. The Intel MKL BLAS is faster than Intel's C BLAS on Intel processors. The IBM ESSL BLAS is faster on POWER processors. The HPE Cray LibSci BLAS is faster on HPE Slingshot-connected supercomputers.

The reason is a language-design decision that Backus and his 1954 team made, accidentally, when they were not thinking about optimising compilers. In Fortran, the standard forbids two dummy arguments of a subroutine from aliasing each other -- that is, from pointing to overlapping regions of memory. If you write

```fortran
subroutine update(a, b, n)
    real, intent(inout) :: a(n), b(n)
    ...
```

the Fortran compiler is allowed to assume that `a` and `b` are disjoint. The compiler can reorder loads and stores, vectorise, fuse loops, and block for cache without having to prove that `a(i)` and `b(j)` do not refer to the same memory location. In C, by contrast, two pointer arguments to a function might legally point to overlapping memory, and until the C99 `restrict` keyword the compiler had no way to assume otherwise. Even in modern C99 and C11, the `restrict` annotation has to be added by hand, and a huge quantity of existing C code does not use it.

This is boring as a language-design observation and load-bearing as a performance argument. It is the reason BLAS in Fortran consistently beats BLAS in C. It is the reason the numerical community has remained content with the 1991 superset-of-1977 language rather than rewriting in a fancier one. James Demmel at Berkeley has made this point in print many times over thirty years: as long as arrays are what you are operating on, Fortran's aliasing rules will give you a compiler that can be more aggressive than any C compiler, for free.[^24]

There is a second, newer argument. Fortran 2008 introduced a construct called `DO CONCURRENT`. It is a loop that the programmer promises has no iteration dependencies. The compiler is free to parallelise it, vectorise it, reorder it, or offload it to a GPU, without the programmer having to say how. When NVIDIA acquired The Portland Group in 2013 and absorbed its Fortran compiler into the NVIDIA HPC SDK, NVIDIA began building a flag called `-stdpar=gpu`. With this flag, the NVIDIA Fortran compiler automatically takes any `DO CONCURRENT` loop in a Fortran program and offloads it to a GPU. On benchmark kernels, a single-line change -- replacing `do i = 1, n` with `do concurrent (i = 1, n)` -- can take a legacy CPU code from 4 gigaflops per second to 112 gigaflops per second on a modern NVIDIA GPU. That is a 25-times speedup, no directives, no library, no rewrite. Standard Fortran 2008, compiled with standard options.[^25]

This is a feature NVIDIA has no equivalent for in C or C++. OpenACC directives exist, OpenMP target offload exists, CUDA exists. All of them require source modifications. `DO CONCURRENT` plus `-stdpar` requires, in the ideal case, one character changed. The practical consequence is that Fortran codes from 2008 can be, on 2026 hardware, automatically GPU-accelerated without their authors having foreseen GPUs at all.

---

## The Rewrite That Never Happens

Every five years for the last thirty years, someone has stood up in a conference hall and declared that Fortran is about to be replaced. In the 1990s it was going to be replaced by C++. In the 2000s it was going to be replaced by C++ with Kokkos or with Boost. In the 2010s it was going to be replaced by Julia. In the 2020s, various people have proposed Rust. None of these replacements has happened, in the sense of an operational weather centre or a major climate-modelling group rewriting its production code from Fortran into another language. What has happened is a more complicated story, and worth telling carefully.

**Julia** was announced in 2012. Jeff Bezanson, Stefan Karpinski, Viral Shah, and Alan Edelman at MIT designed it, explicitly and in public, to combine the performance of Fortran with the dynamism of Python. Julia 1.0 shipped in 2018. The language's two-language-problem argument -- that scientific computing had been split between slow-friendly (Python) and fast-unfriendly (Fortran, C++) and that Julia would collapse the split -- resonated in the scientific computing community.[^26]

In 2018, the **Climate Modeling Alliance** (CLiMA) was founded at Caltech, with collaborators at MIT, the Naval Postgraduate School, and JPL. Their mission was to build, from scratch, a new Earth-system model in Julia. Their flagship ocean component is **Oceananigans.jl**, whose GitHub repository is one of the most active scientific Julia projects in the world. The CLiMA team includes Ali Ramadhan, Gregory Wagner, Andre Souza, Valentin Churavy, Simone Silvestri, Navid Constantinou, Keaton Burns, John Marshall, and Raffaele Ferrari -- serious people, good scientists. They have built a beautiful research model. As of 2026 no operational weather centre has adopted it.[^27]

There is a widely reported story from MIT, which I have not been able to pin to a single publication with a specific citation but which has been repeated in many places in slightly different versions. A group at MIT decided to rewrite part of their Fortran climate model into Julia. They budgeted for a three-times slowdown, as a reasonable price for the gains in readability and student accessibility. They got a three-times speedup. The *Register* covered the anecdote in 2022 under the headline "Climate model code is so old students can't read it."[^28] The speedup is plausible for reasons that have more to do with the age of the original Fortran code than with Julia's intrinsic performance; some of the climate code in question was written in the FORTRAN 77 or early Fortran 90 era, before modern optimising compilers were available, and a careful re-implementation in any language with a modern compiler would likely have produced a similar improvement.

Julia is a real thing. It has not displaced Fortran for production weather and climate modelling, and my honest assessment in 2026 is that it will not. The reasons are conservative but strong. Fortran 2018's coarrays, combined with OpenMP 5 target offload and with `DO CONCURRENT` plus `-stdpar`, now give the language most of what Julia originally offered as a differentiator, without requiring the atmospheric science community to rewrite millions of lines of validated physics code. Julia's first-class HPC story still lags Fortran on MPI collectives, on vendor-tuned BLAS integration, and on the twenty-year ABI stability that operational codes need. Operational weather centres have a zero-tolerance policy for numerical regressions. Language swaps are not free.

**C++** has had more sustained attempts. The US Department of Energy's Exascale Computing Project has invested heavily in C++-based performance-portability layers, particularly **Kokkos** from Sandia. The **Energy Exascale Earth System Model** (E3SM), which is the Department of Energy's coupled climate model, has had part of its atmosphere component rewritten from Fortran into C++ plus Kokkos. The resulting component, called **EAMxx**, became the atmosphere component of E3SM v4 in 2024 and claims 8 to 30 times GPU speedups over the Fortran version it replaced.[^29] E3SM is the best-funded, most sustained attempt to replace Fortran with C++ in the history of numerical climate modelling. After roughly a decade of effort, the result is not "Fortran retired." The result is a heterogeneous code base of C++, Fortran, and domain-specific languages coexisting, with EAMxx as one component of a larger system that still has plenty of Fortran in it. The rewrite, where it happened, was selective.

**Rust** is not a contender as of 2026. There are research projects: Rust-based data assimilation prototypes, Rust for I/O orchestration, Rust for scientific workflow engines. No operational weather or climate model's dynamical core is in Rust. The language's borrow checker is a poor fit for the in-place array update patterns that dominate numerical Fortran, and Rust's numerical ecosystem is decades behind LAPACK/BLAS/FFTW.

**Python** deserves a separate sentence, because it is the language most outsiders think has displaced Fortran in scientific computing, and it is in fact the language that most completely depends on Fortran. Python never replaces Fortran. It wraps Fortran. f2py, ctypes, pybind11, Cython are all bridges to compiled code -- and in scientific work that compiled code is usually Fortran. The Python rewrites of atmospheric models that exist (PyFV3 at GFDL, FVM-Python at ECMWF, the various GT4Py-based projects) are fundamentally driver layers that generate and orchestrate kernels compiled into CUDA, C++, or Fortran. The scientific Python stack is, architecturally, a Fortran user.

---

## Manabe's Nobel

On October 5, 2021, the Royal Swedish Academy of Sciences awarded half of the Nobel Prize in Physics to **Syukuro Manabe** and **Klaus Hasselmann**, "for the physical modelling of Earth's climate, quantifying variability and reliably predicting global warming." Giorgio Parisi took the other half of the prize for unrelated work on spin-glass disorder. At ninety years old, Manabe became the first person to win a Nobel Prize in Physics for computational climate modelling.[^30]

![Syukuro Manabe in 2021, shortly after the announcement of his Nobel Prize in Physics. Manabe's 1967 radiative-convective model produced a climate sensitivity of +2.3 degrees Celsius for a doubling of atmospheric CO2. That number sits inside the 2021 IPCC likely range, fifty-four years later. His code was FORTRAN IV on an IBM 7090 at GFDL. Photo: Cabinet Office of Japan, 2021 (CC BY 4.0).](/assets/images/Syukuro_Manabe.jpg)

Manabe had been at the US Weather Bureau's Geophysical Fluid Dynamics Laboratory, in Princeton, since 1958. His 1967 paper with Richard Wetherald, "Thermal Equilibrium of the Atmosphere with a Given Distribution of Relative Humidity," was a one-dimensional radiative-convective model that predicted a climate sensitivity of plus 2.3 degrees Celsius for a doubling of atmospheric carbon dioxide. That number sits, unflinchingly, inside the 2021 IPCC Sixth Assessment Report's likely range of 2.5 to 4 degrees, fifty-four years later. Manabe's later work -- with Kirk Bryan in 1969 on the first coupled ocean-atmosphere general circulation model, and a chain of three-dimensional GCMs in the 1970s and 1980s -- is the direct ancestor of every major modern Earth-system model. I have already [written about all of this at length](/weather/hpc/history/2026/04/13/The-forecast-that-reached-the-Nobel.html), so I will not re-walk that ground here.

What I want to note is the language. The 1967 single-column radiative-convective code was FORTRAN IV. It ran on an IBM 7090-class machine at GFDL. The 1969 coupled model was FORTRAN IV on a UNIVAC 1108. The descendants, in 2026, are Fortran 90/95/2003 on HPE Cray machines at Princeton, NCAR, and Oak Ridge. The lineage of Manabe's work is, from 1961 through 2026, unbroken in the Fortran family.

At his Nobel press conference in Princeton on October 5, 2021, at the age of ninety, Manabe said things that a scientist is allowed to say when the Swedes have given them a medal. The version of the press conference I have listened to has him coming back, repeatedly, to one theme. He had not worked on climate modelling because he was trying to save the world. He had worked on it because he was curious. "I was doing it just because of my curiosity. I really enjoyed studying climate change. Curiosity is the thing which drives all my research activity," he said.[^31] In the March 2022 interview with the Nobel Foundation, he said: "Looking back at the last six decades of my career, I really enjoyed what I was doing and being curious. I never imagined that this thing I was beginning to study would have such huge consequences."[^32]

There is a thing buried in those sentences that I want to name. The reason the 2021 Nobel Prize cites Manabe's computational work -- not a field experiment, not a laboratory measurement, but a set of numerical models run on successive generations of supercomputers across six decades -- is that those models turned out to be the only instrument humanity had for predicting what was going to happen to the Earth's climate. The Fortran code Manabe and his colleagues wrote in the 1960s was not intended to be a prediction device. It was a toy, by Manabe's own cheerful admission, to let him play with the equations and satisfy his curiosity. It became, over sixty years, the basis for every major climate projection that now informs every major international climate agreement. The Fortran code grew up. Manabe lived long enough to see it given a Nobel Prize.

The language he used to build it is still, in 2026, the language that runs the descendants of his 1967 model. That is perhaps the most remarkable continuity in the history of scientific computing.

---

## What FORTRAN Became

If you have read this far through three posts, you have read about a language that was invented in 1954, shipped in 1957, criticised continuously from 1968 to the present day, publicly repudiated by its own inventor in 1977, and predicted to die, on reasonable timescales, every year since the mid-1960s. You have read about why it is still, in 2026, the language on which every serious operational weather forecast and every major climate model is written, and the language on which Python's scientific stack secretly runs.

I want to end with a thought about what Fortran became. It is not, in 2026, a programming language in the same sense that Python or Rust or Julia are. It is not a language that new people learn in order to start working in computing. It is not a language that startups reach for, or that teaches computer-science undergraduates, or that drives the next generation of web applications or mobile apps or machine-learning frameworks. All of that territory belongs to the descendants of ALGOL, C, and Smalltalk, to the languages Dijkstra and Wirth and their heirs designed. Dijkstra's argument won in the classroom, comprehensively. Backus's argument lost in the classroom, comprehensively.

But what Fortran became, instead of those things, is an **ABI**. An ABI is an application binary interface -- a stable contract, at the level of compiled code, that lets programs in different languages talk to each other as if they were all written in the same one. Fortran, in 2026, is not a language you write in. It is a language you call **through**. NumPy calls it. SciPy calls it. Julia wrappers call it. Modern C++ scientific code calls it. The ECMWF IFS driver layer, increasingly written in Python, calls it. Thirty years of vendor-tuned BLAS implementations are optimised against the Fortran ABI, not the C ABI. Thirty years of supercomputer vendor compiler investment are focused on a language whose standards committee has shipped, on average, one revision every five years since 1990, each one a modest incremental improvement on the last.

Fortran, in other words, became the thing that other languages are standing on when they do serious numerical work. Most of the people standing on it do not know they are standing on it. Most of the people maintaining it do not have the marketing budget to tell the people standing on it that they are doing so. It is not a flashy role. It is not the role Backus thought his language would play. It is, however, the role that has kept it alive and shipping, fifty-two years after Dijkstra wrote that he prayed daily for his fellow-programmers to find the means of freeing themselves from the curse of compatibility.[^33]

In 2024 something interesting happened in the popularity ranking of programming languages that the TIOBE Index tries to track. Fortran, for the first time since the early 2000s, re-entered the top ten. The trade press was surprised. Various explanations circulated: the AI boom had driven renewed interest in numerical libraries; Fortran 2023 had shipped with a handful of small but genuine improvements; the fortran-lang.org community had coordinated a modest revival of the language's online presence; NVIDIA was pushing Fortran as a first-class language for GPU computing. None of these is the whole story. The whole story is that Fortran, in 2024, was finally visible to the people measuring programming-language popularity as the thing it had quietly been since 1991: the language on which most of the numerical work of the scientific world continues to ride.[^34]

I have spent three long posts on this history because I am a meteorologist and because the language is, for the field I work in, load-bearing. If I wanted to know the exact value of a field quantity, in Fortran 77 from 1985 or Fortran 2023 from last year, I would write the same line of code, because the language has chosen -- deliberately, through seven ISO revisions -- to remain backward-compatible. I could send my 1985 source file to a colleague in 2026 running GFortran 15 on an Apple M5 laptop and they would read it into the compiler and it would run. This is not universal, in software. It is not even common. Most programming languages are younger than my car. Fortran is old enough to have outlived its inventor, many of its inventors' colleagues, most of the hardware it originally ran on, and every serious attempt to replace it. It shipped in April 1957 on a reel of magnetic tape delivered, unannounced, to a nuclear-reactor research laboratory outside Pittsburgh. It is still shipping.

That is the story. The language refused to die.

---

## Footnotes

[^1]: ISO/IEC 1539:1991 (Fortran 90). [ISO catalogue entry](https://www.iso.org/standard/6128.html). The superset-of-Fortran-77 principle is documented in the standard's foreword and in Adams, Brainerd, Martin, Smith, and Wagener, *Fortran 90 Handbook* (McGraw-Hill, 1992). [PDF mirror](http://micro.ustc.edu.cn/fortran/Fortran%2090%20Handbook.pdf).

[^2]: Cohen's role as the 1991 NAG Fortran 90 compiler author is documented at [NAG -- Malcolm Cohen biography](https://www.nag.com/people/malcolm-cohen); his ongoing role as ISO/IEC Fortran Project Editor is documented in the most recent standard's frontmatter ([ISO/IEC 1539-1:2023](https://www.iso.org/standard/82170.html)) and at [Modern Fortran Explained, Oxford University Press](https://global.oup.com/academic/product/modern-fortran-explained-9780198876588).

[^3]: ISO/IEC 1539-1:1997 (Fortran 95). The HPF story is told in Kennedy, Koelbel, and Zima, "The Rise and Fall of High Performance Fortran," *Communications of the ACM* 54(11), November 2011. [CACM article](https://cacm.acm.org/magazines/2011/11/138217-the-rise-and-fall-of-high-performance-fortran/fulltext).

[^4]: ISO/IEC 1539-1:2004 (Fortran 2003). Malcolm Cohen's role as designer of the OO features is documented at [NAG -- Malcolm Cohen](https://www.nag.com/people/malcolm-cohen). A summary of the new features is in WG5 document N1648, "The New Features of Fortran 2003." [PDF](https://wg5-fortran.org/N1601-N1650/N1648.pdf).

[^5]: ISO/IEC 1539-1:2010 (Fortran 2008). The coarray story is told in Numrich and Reid, "History of coarrays and SPMD parallelism in Fortran," *Proceedings of the ACM on Programming Languages* 4 (HOPL), 2020. [ACM DL entry](https://dl.acm.org/doi/abs/10.1145/3386322). John Reid's ECMWF 2008 presentation on coarrays is at [PDF](https://www.ecmwf.int/sites/default/files/elibrary/2008/15363-parallel-programming-fortran-coarrays.pdf).

[^6]: ISO/IEC 1539:2018 (Fortran 2018). Draft interpretation document J3/18-007r1. [PDF](https://j3-fortran.org/doc/year/18/18-007r1.pdf).

[^7]: ISO/IEC 1539-1:2023 (Fortran 2023). [ISO entry](https://www.iso.org/standard/82170.html). WG5 document N2212, "The new features of Fortran 2023," by John Reid. [PDF](https://wg5-fortran.org/N2201-N2250/N2212.pdf). Draft standard at [J3/23-007r1](https://j3-fortran.org/doc/year/23/23-007r1.pdf).

[^8]: Biographical sketches of Reid, Cohen, Metcalf, Martin, and Wagener are assembled from [John Reid's page at the Numerical Analysis Group, Rutherford Appleton](https://www.numerical.rl.ac.uk/people/john-reid/); [NAG -- Malcolm Cohen](https://www.nag.com/people/malcolm-cohen); [Oxford University Press -- Modern Fortran Explained](https://global.oup.com/academic/product/modern-fortran-explained-9780198876588); the Computer History Museum finding aid for Jeanne Martin's papers, [Fortran Standardization records, 1957-2015](https://oac.cdlib.org/findaid/ark:%2F13030%2Fc8t4417d); and [MIT Press's author page for Jerrold L. Wagener](https://mitpress.mit.edu/author/jerrold-l-wagener-1864/). All accessed 2026-04-19.

[^9]: [Wikipedia -- Integrated Forecast System](https://en.wikipedia.org/wiki/Integrated_Forecast_System); ECMWF IFS Documentation Cy49r1 -- Part VI: Technical and Computational Procedures, November 2024. [PDF](https://www.ecmwf.int/sites/default/files/elibrary/112024/81628-ifs-documentation-cy49r1-part-vi-technical-and-computational-procedures.pdf).

[^10]: [ECMWF IFS/ARPEGE Fortran Coding Standard](https://sites.ecmwf.int/docs/ifs-arpege-coding-standards/fortran/).

[^11]: "Modernisation of the Integrated Forecasting System," *ECMWF Newsletter* 182, 2025. [Newsletter page](https://www.ecmwf.int/en/newsletter/182/computing/modernisation-integrated-forecasting-system).

[^12]: "From the Scalability Programme to Destination Earth," *ECMWF Newsletter* 171. [Newsletter page](https://www.ecmwf.int/en/newsletter/171/earth-system-science/scalability-programme-destination-earth).

[^13]: Loki documentation and source: [ecmwf-ifs/loki on GitHub](https://github.com/ecmwf-ifs/loki); [Loki documentation site](https://sites.ecmwf.int/docs/loki/main/getting_started.html).

[^14]: "Making some of the Integrated Forecasting System open source," ECMWF News 2022. [News page](https://www.ecmwf.int/en/about/media-centre/news/2022/making-some-integrated-forecasting-system-open-source).

[^15]: Destination Earth portal: [destination-earth.eu](https://destination-earth.eu/); [destine.ecmwf.int](https://destine.ecmwf.int/). News item announcing demonstration products: [ECMWF 2023](https://www.ecmwf.int/en/about/media-centre/news/2023/destination-earth-demonstration-products-be-ready-mid-2024). The Digital Twin Engine: [ECMWF Stories](https://stories.ecmwf.int/the-digital-twin-engine/).

[^16]: GFDL FV3 homepage: [gfdl.noaa.gov/fv3](https://www.gfdl.noaa.gov/fv3/). FV3 team roster: [gfdl.noaa.gov/fv3/fv3-the-team/](https://www.gfdl.noaa.gov/fv3/fv3-the-team/). FV3 Technical Description PDF: [gfdl.noaa.gov](https://www.gfdl.noaa.gov/wp-content/uploads/2020/02/FV3-Technical-Description.pdf).

[^17]: GFS FV3 Fortran source: [github.com/NOAA-GFDL/fv3gfs-fortran](https://github.com/NOAA-GFDL/fv3gfs-fortran). PyFV3 parallel implementation: [github.com/NOAA-GFDL/PyFV3](https://github.com/NOAA-GFDL/PyFV3). Unified Forecast System: [ufs.epic.noaa.gov](https://www.ufs.epic.noaa.gov/about/).

[^18]: NCAR CESM: [cesm.ucar.edu](https://www.cesm.ucar.edu/); [ncar.ucar.edu/what-we-offer/models/community-earth-system-model-cesm](https://ncar.ucar.edu/what-we-offer/models/community-earth-system-model-cesm). CAM Fortran standards: [ncar.github.io/CAM](https://ncar.github.io/CAM/doc/build/html/users_guide/introduction.html). [Wikipedia -- Community Earth System Model](https://en.wikipedia.org/wiki/Community_Earth_System_Model).

[^19]: Manabe, S., and Wetherald, R. T. (1967). "Thermal Equilibrium of the Atmosphere with a Given Distribution of Relative Humidity." *Journal of the Atmospheric Sciences* 24, 241-259. Covered in my earlier post, [The Forecast That Reached the Nobel](/weather/hpc/history/2026/04/13/The-forecast-that-reached-the-Nobel.html).

[^20]: [Netlib -- LAPACK home](https://www.netlib.org/lapack/); [Wikipedia -- LAPACK](https://en.wikipedia.org/wiki/LAPACK). LAPACK 1.0 shipped in 1992 in FORTRAN 77; moved to Fortran 90 in LAPACK 3.2 (2008).

[^21]: Dongarra's biography and Turing Award citation: [amturing.acm.org -- Dongarra](https://amturing.acm.org/award_winners/dongarra_3406337.cfm); [ACM Turing Award 2021 announcement, March 2022](https://www.acm.org/media-center/2022/march/turing-award-2021); [Wikipedia -- Jack Dongarra](https://en.wikipedia.org/wiki/Jack_Dongarra); [CACM -- Always Improving Performance, June 2022](https://cacm.acm.org/magazines/2022/6/261165-always-improving-performance/fulltext).

[^22]: Peterson, P. "f2py history and future," blog post, July 2006. [Link](http://pearu.blogspot.com/2006/07/f2py-history-and-future.html). [NumPy -- Using F2PY](https://numpy.org/doc/stable/f2py/).

[^23]: Julia's stated design goals are in the 2012 announcement blog post: [julialang.org/blog/2012/02/why-we-created-julia/](https://julialang.org/blog/2012/02/why-we-created-julia/).

[^24]: The aliasing argument is discussed in many places. A succinct summary is in the *Fortran Discourse* forum thread "Performance, C vs. Fortran," [fortran-lang.discourse.group](https://fortran-lang.discourse.group/t/performance-c-vs-fortran/1461), and in the comparison document at [fweber.sdsu.edu](https://fweber.sdsu.edu/p317/comparison.pdf).

[^25]: NVIDIA, "Accelerating Fortran DO CONCURRENT with GPUs and the NVIDIA HPC SDK," developer blog. [Link](https://developer.nvidia.com/blog/accelerating-fortran-do-concurrent-with-gpus-and-the-nvidia-hpc-sdk/). The 25-times speedup figure comes from the kernel benchmark in that post.

[^26]: [Wikipedia -- Julia (programming language)](https://en.wikipedia.org/wiki/Julia_(programming_language)); [julialang.org](https://julialang.org/).

[^27]: CLiMA: [clima.caltech.edu](https://clima.caltech.edu/); CLiMA 0.1 milestone: [clima.caltech.edu/2020/06/08/clima-0-1](https://clima.caltech.edu/2020/06/08/clima-0-1-a-first-milestone-in-the-next-generation-of-climate-models/). Oceananigans.jl: [github.com/CliMA/Oceananigans.jl](https://github.com/CliMA/Oceananigans.jl).

[^28]: "Climate model code is so old students can't read it," *The Register*, April 13, 2022. [Link](https://www.theregister.com/2022/04/13/climate_mit_fortran/). The specific MIT 3x story is widely repeated in the Julia community; I have been unable to pin it to a single published paper.

[^29]: "Introduction to EAMxx and its Superior GPU Performance," E3SM blog. [Link](https://e3sm.org/introduction-to-eamxx-and-its-superior-gpu-performance/). HOMMEXX 1.0 paper: Bertagna et al., "HOMMEXX 1.0: a performance-portable atmospheric dynamical core for the Energy Exascale Earth System Model," *Geoscientific Model Development* 12, 1423-1441, 2019. [GMD paper](https://gmd.copernicus.org/articles/12/1423/2019/).

[^30]: [Nobel Prize in Physics 2021](https://www.nobelprize.org/prizes/physics/2021/manabe/facts/).

[^31]: Princeton press conference, October 5, 2021. [Great fun: Manabe wins Nobel -- Princeton](https://www.princeton.edu/news/2021/10/05/great-fun-manabe-wins-nobel-prize-physics-modeling-climate-change).

[^32]: Interview with Syukuro Manabe, Nobel Foundation, March 2022. [Link](https://www.nobelprize.org/prizes/physics/2021/manabe/185163-manabe-interview-march-2022/).

[^33]: Dijkstra, E. W. (1972). "The Humble Programmer," ACM Turing Award Lecture. EWD 340. [Full transcription](https://www.cs.utexas.edu/~EWD/transcriptions/EWD03xx/EWD340.html).

[^34]: TIOBE Index coverage of Fortran's 2024 top-ten return: [TechRepublic, May 2024](https://www.techrepublic.com/article/tiobe-index-may-2024/); [fortran-lang discourse -- Fortran in the TIOBE Top 10](https://fortran-lang.discourse.group/t/fortran-in-the-tiobe-top-10/8155); [InfoWorld -- Fortran, Delphi rise in Tiobe popularity index](https://www.infoworld.com/article/3842376/fortran-delphi-rise-in-tiobe-popularity-index.html).

---

## References

**Standards (primary):**

* ISO/IEC 1539:1991 (Fortran 90). [ISO catalogue](https://www.iso.org/standard/6128.html).
* ISO/IEC 1539-1:1997 (Fortran 95).
* ISO/IEC 1539-1:2004 (Fortran 2003). WG5 N1648: [The New Features of Fortran 2003](https://wg5-fortran.org/N1601-N1650/N1648.pdf).
* ISO/IEC 1539-1:2010 (Fortran 2008).
* ISO/IEC 1539:2018 (Fortran 2018). [J3/18-007r1](https://j3-fortran.org/doc/year/18/18-007r1.pdf).
* ISO/IEC 1539-1:2023 (Fortran 2023). [ISO entry](https://www.iso.org/standard/82170.html); WG5 N2212: [New features of Fortran 2023, by John Reid](https://wg5-fortran.org/N2201-N2250/N2212.pdf).
* ISO WG5 document index: [wg5-fortran.org/documents.html](https://wg5-fortran.org/documents.html).
* J3 (US) committee: [j3-fortran.org](https://j3-fortran.org/).

**Books:**

* Metcalf, M., Reid, J., Cohen, M., Bader, R. (2024). *Modern Fortran Explained: Incorporating Fortran 2023.* Oxford University Press. [OUP page](https://global.oup.com/academic/product/modern-fortran-explained-9780198876588).
* Adams, J., Brainerd, W. S., Martin, J. T., Smith, B. T., Wagener, J. L. (1992). *Fortran 90 Handbook: Complete ANSI/ISO Reference.* McGraw-Hill. [PDF mirror](http://micro.ustc.edu.cn/fortran/Fortran%2090%20Handbook.pdf).
* Numrich, R. W. and Reid, J. (2020). "History of coarrays and SPMD parallelism in Fortran." *Proceedings of the ACM on Programming Languages* 4 (HOPL). [ACM DL entry](https://dl.acm.org/doi/abs/10.1145/3386322).
* Kennedy, K., Koelbel, C., Zima, H. (2011). "The Rise and Fall of High Performance Fortran." *Communications of the ACM* 54(11). [CACM entry](https://cacm.acm.org/magazines/2011/11/138217-the-rise-and-fall-of-high-performance-fortran/fulltext).

**ECMWF / IFS:**

* *Modernisation of the Integrated Forecasting System*, ECMWF Newsletter 182, 2025. [Link](https://www.ecmwf.int/en/newsletter/182/computing/modernisation-integrated-forecasting-system).
* *From the Scalability Programme to Destination Earth*, ECMWF Newsletter 171. [Link](https://www.ecmwf.int/en/newsletter/171/earth-system-science/scalability-programme-destination-earth).
* *Making some of the Integrated Forecasting System open source*, ECMWF News 2022. [Link](https://www.ecmwf.int/en/about/media-centre/news/2022/making-some-integrated-forecasting-system-open-source).
* ECMWF IFS Documentation, Cy49r1 Part VI. [PDF](https://www.ecmwf.int/sites/default/files/elibrary/112024/81628-ifs-documentation-cy49r1-part-vi-technical-and-computational-procedures.pdf).
* ECMWF IFS/ARPEGE Fortran Coding Standard. [Docs](https://sites.ecmwf.int/docs/ifs-arpege-coding-standards/fortran/).
* Bauer, P., Thorpe, A., Brunet, G. (2015). "The quiet revolution of numerical weather prediction." *Nature* 525, 47-55. [Nature paper](https://www.nature.com/articles/nature14956).
* Reid, J. (2008). "Parallel programming in Fortran with Coarrays," ECMWF presentation. [PDF](https://www.ecmwf.int/sites/default/files/elibrary/2008/15363-parallel-programming-fortran-coarrays.pdf).
* ecmwf-ifs GitHub: [github.com/ecmwf-ifs](https://github.com/ecmwf-ifs); Loki: [github.com/ecmwf-ifs/loki](https://github.com/ecmwf-ifs/loki).
* Destination Earth: [destination-earth.eu](https://destination-earth.eu/); [destine.ecmwf.int](https://destine.ecmwf.int/).

**NOAA / GFDL / UFS:**

* GFDL FV3: [gfdl.noaa.gov/fv3](https://www.gfdl.noaa.gov/fv3/).
* FV3 Technical Description: [PDF](https://www.gfdl.noaa.gov/wp-content/uploads/2020/02/FV3-Technical-Description.pdf).
* Unified Forecast System: [ufs.epic.noaa.gov](https://ufs.epic.noaa.gov/); [github.com/ufs-community](https://github.com/ufs-community).
* GFS FV3 source: [github.com/NOAA-GFDL/fv3gfs-fortran](https://github.com/NOAA-GFDL/fv3gfs-fortran).
* PyFV3: [github.com/NOAA-GFDL/PyFV3](https://github.com/NOAA-GFDL/PyFV3).

**NCAR / CESM:**

* [cesm.ucar.edu](https://www.cesm.ucar.edu/); [ncar.ucar.edu/what-we-offer/models/community-earth-system-model-cesm](https://ncar.ucar.edu/what-we-offer/models/community-earth-system-model-cesm).
* CAM documentation: [ncar.github.io/CAM](https://ncar.github.io/CAM/doc/build/html/users_guide/introduction.html).
* [GitHub ESCOMP/CESM](https://github.com/ESCOMP/CESM).

**DOE / E3SM:**

* [e3sm.org](https://e3sm.org/). EAMxx: [Introduction to EAMxx](https://e3sm.org/introduction-to-eamxx-and-its-superior-gpu-performance/).
* Bertagna, L. et al. (2019). "HOMMEXX 1.0." *Geoscientific Model Development* 12, 1423-1441. [GMD paper](https://gmd.copernicus.org/articles/12/1423/2019/).

**LAPACK / BLAS / Python bridge:**

* Netlib LAPACK: [netlib.org/lapack](https://www.netlib.org/lapack/); BLAS: [netlib.org/blas](https://www.netlib.org/blas/).
* [Wikipedia -- LAPACK](https://en.wikipedia.org/wiki/LAPACK).
* ACM Turing Award 2021 for Dongarra: [amturing.acm.org](https://amturing.acm.org/award_winners/dongarra_3406337.cfm); [ACM press release](https://www.acm.org/media-center/2022/march/turing-award-2021); [CACM -- Always Improving Performance](https://cacm.acm.org/magazines/2022/6/261165-always-improving-performance/fulltext).
* f2py: [Pearu Peterson's history and future](http://pearu.blogspot.com/2006/07/f2py-history-and-future.html); [NumPy F2PY documentation](https://numpy.org/doc/stable/f2py/).

**Compilers and tooling:**

* GFortran / GCC: [gcc.gnu.org/fortran](https://gcc.gnu.org/fortran/); [Wikipedia -- GNU Fortran](https://en.wikipedia.org/wiki/GNU_Fortran).
* Intel ifx / ifort: [Porting Guide](https://www.intel.com/content/www/us/en/developer/articles/guide/porting-guide-for-ifort-to-ifx.html); [ifort deprecation](https://community.intel.com/t5/Blogs/Tech-Innovation/Tools/Deprecation-of-The-Intel-Fortran-Compiler-Classic-ifort/post/1541699).
* NVIDIA HPC SDK: [docs.nvidia.com/hpc-sdk](https://docs.nvidia.com/hpc-sdk/index.html); [The Portland Group on Wikipedia](https://en.wikipedia.org/wiki/The_Portland_Group).
* LFortran: [lfortran.org](https://lfortran.org/); [Wikipedia -- LFortran](https://en.wikipedia.org/wiki/LFortran). Čertík's blog post: [Resurrecting Fortran, 2021](https://ondrejcertik.com/blog/2021/03/resurrecting-fortran/).
* LLVM Flang: [LLVM blog -- Goodbye flang-new, Hello flang](https://blog.llvm.org/posts/2025-03-11-flang-new/); [The Register -- LLVM's Fortran compiler finally drops the training wheels](https://www.theregister.com/2025/03/17/llvm_20_flang/).
* NAG: [nag.com/fortran-compiler](https://nag.com/fortran-compiler/); [NAG 7.2 Release PDF](https://support.nag.com/nagware/np/r72_doc/compiler.pdf).
* HPE Cray CCE: [cpe.ext.hpe.com](https://cpe.ext.hpe.com/docs/latest/cce/index.html).

**GPU / parallel:**

* OpenACC: [Wikipedia](https://en.wikipedia.org/wiki/OpenACC); [NVIDIA newsroom announcement](https://nvidianews.nvidia.com/news/nvidia-cray-pgi-caps-unveil-openacc-programming-standard-for-parallel-computing-6622866).
* OpenMP 5.0: [OpenMP Accelerator Support for GPUs](https://www.openmp.org/updates/openmp-accelerator-support-gpus/).
* Coarray Fortran: [Wikipedia](https://en.wikipedia.org/wiki/Coarray_Fortran); [coarrays.sourceforge.io](https://coarrays.sourceforge.io/doc.html).
* DO CONCURRENT + stdpar: [NVIDIA blog -- Accelerating Fortran DO CONCURRENT](https://developer.nvidia.com/blog/accelerating-fortran-do-concurrent-with-gpus-and-the-nvidia-hpc-sdk/); [arXiv 2408.07843](https://arxiv.org/html/2408.07843v1).

**Julia / CLiMA:**

* [julialang.org](https://julialang.org/); [Wikipedia -- Julia](https://en.wikipedia.org/wiki/Julia_(programming_language)).
* CLiMA: [clima.caltech.edu](https://clima.caltech.edu/); [Oceananigans.jl](https://github.com/CliMA/Oceananigans.jl).
* [Nature -- Julia: come for the syntax, stay for the speed](https://www.nature.com/articles/d41586-019-02310-3).
* [The Register -- Climate model code is so old students can't read it](https://www.theregister.com/2022/04/13/climate_mit_fortran/).

**Manabe and the Nobel:**

* [Nobel Prize in Physics 2021 -- Manabe facts](https://www.nobelprize.org/prizes/physics/2021/manabe/facts/); [Manabe biographical](https://www.nobelprize.org/prizes/physics/2021/manabe/biographical/); [2022 interview with Manabe](https://www.nobelprize.org/prizes/physics/2021/manabe/185163-manabe-interview-march-2022/).
* [Princeton -- Great fun: Manabe wins Nobel](https://www.princeton.edu/news/2021/10/05/great-fun-manabe-wins-nobel-prize-physics-modeling-climate-change).
* [APS -- November 1966: Syukuro Manabe makes the first modern climate model](https://www.aps.org/apsnews/2025/11/syukuro-manabe-modern-climate-model).
* [Wikipedia -- Syukuro Manabe](https://en.wikipedia.org/wiki/Syukuro_Manabe).

**Biographies of key people:**

* John Reid: [RAL Numerical Analysis Group](https://www.numerical.rl.ac.uk/people/john-reid/).
* Malcolm Cohen: [NAG page](https://www.nag.com/people/malcolm-cohen).
* Michael Metcalf: [OUP Modern Fortran Explained](https://global.oup.com/academic/product/modern-fortran-explained-9780198876588).
* Steve Lionel: [Doctor Fortran](https://stevelionel.com/drfortran/).
* Ondřej Čertík: [ondrejcertik.com](https://ondrejcertik.com/).
* Van Snyder: [LinkedIn profile](https://www.linkedin.com/in/van-snyder-14ab17/).

**fortran-lang community:**

* [fortran-lang.org](https://fortran-lang.org/); [community history](https://fortran-lang.org/community/history/).

**TIOBE coverage:**

* [TIOBE Index](https://www.tiobe.com/tiobe-index/).
* [TechRepublic -- TIOBE Index News May 2024](https://www.techrepublic.com/article/tiobe-index-may-2024/).
* [fortran-lang discourse -- Fortran in the TIOBE Top 10](https://fortran-lang.discourse.group/t/fortran-in-the-tiobe-top-10/8155).

---

*This concludes the three-part FORTRAN series. Part 1: [God Is Real (Unless Declared Integer)](/weather/hpc/history/2026/04/19/God-is-real-unless-declared-integer.html). Part 2: [The Empire That Its Creator Repudiated](/weather/hpc/history/2026/04/20/The-empire-that-its-creator-repudiated.html). Part 3: The Language That Refused to Die.*
