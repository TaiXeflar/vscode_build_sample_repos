
```
                         Intel(R) Fortran Compiler Help
                         ==============================
  Intel(R) Compiler includes compiler options that optimize for instruction
  sets that are available in both Intel(R) and non-Intel microprocessors, but
  may perform additional optimizations for Intel microprocessors than for
  non-Intel microprocessors. In addition, certain compiler options for
  Intel(R) Compiler are reserved for Intel microprocessors. For a detailed
  description of these compiler options, including the instructions they
  implicate, please refer to "Intel(R) Compiler User and Reference Guides >
  Compiler Options."
   usage: ifort -qnextgen [options] file1 [file2 ...] [/link linker_options]
      where options represents zero or more compiler options
      fileN is a Fortran source (.f .for .ftn .f90 .fpp .i .i90),
      assembly (.asm), object (.obj), static library (.lib), or
      other linkable file
      linker_options represents zero or more linker options
Notes
-----
1. Many FL32 options are supported; a warning is printed for unsupported
   options.
2. Intel Fortran compiler options may be placed in your ifort -qnextgen.cfg file.
   Some options listed are only available on a specific system
   i32 indicates the feature is available on systems based on IA-32
          architecture
   i64em indicates the feature is available on systems using Intel(R) 64
          architecture
                             Compiler Option List
                             --------------------
Optimization
------------
/O1       optimize for maximum speed, but disable some optimizations which
          increase code size for a small speed benefit
/O2       optimize for maximum speed (DEFAULT)
/O3       optimize for maximum speed and enable more aggressive optimizations
          that may not improve performance on some programs
/Ox       enable maximum optimizations (same as /O2)
/Os       enable speed optimizations, but disable some optimizations which
          increase code size for small speed benefit (overrides /Ot)
/Ot       enable speed optimizations (overrides /Os)
/Od       disable optimizations
/Oy[-]    enable/disable using EBP as a general purpose register (no frame
          pointer) (i32 only)
/Ofast    enable /O3 /Qprec-div- /fp:fast=2 optimizations
/Oa[-]    assume no aliasing in program
Code Generation
---------------
/Qx<code>
          generate specialized code to run exclusively on processors
          indicated by <code> as described below
            SSE2 May generate Intel(R) SSE2 and SSE instructions for Intel
[press RETURN to continue]
                    processors. Optimizes for the Intel NetBurst(R)
                    microarchitecture.
            SSE3 May generate Intel(R) SSE3, SSE2, and SSE instructions for
                    Intel processors. Optimizes for the enhanced Pentium(R) M
                    processor microarchitecture and Intel NetBurst(R)
                    microarchitecture.
            SSSE3 May generate Intel(R) SSSE3, SSE3, SSE2, and SSE
                    instructions for Intel processors. Optimizes for the
                    Intel(R) Core(TM) microarchitecture.
            SSE4.1 May generate Intel(R) SSE4 Vectorizing Compiler and Media
                    Accelerator instructions for Intel processors. May
                    generate Intel(R) SSSE3, SSE3, SSE2, and SSE instructions
                    and it may optimize for Intel(R) 45nm Hi-k next generation
                    Intel Core(TM) microarchitecture.
            SSE4.2 May generate Intel(R) SSE4 Efficient Accelerated String
                    and Text Processing instructions supported by Intel(R)
                    Core(TM) i7 processors. May generate Intel(R) SSE4
                    Vectorizing Compiler and Media Accelerator, Intel(R) SSSE3,
                    SSE3, SSE2, and SSE instructions and it may optimize for
                    the Intel(R) Core(TM) processor family.
            AVX May generate Intel(R) Advanced Vector Extensions (Intel(R)
                    AVX), Intel(R) SSE4.2, SSE4.1, SSSE3, SSE3,
                    SSE2, and SSE instructions for Intel(R) processors.
            CORE-AVX2
                    May generate Intel(R) Advanced Vector Extensions 2
                    (Intel(R) AVX2), Intel(R) AVX, SSE4.2, SSE4.1, SSSE3, SSE3,
                    SSE2, and SSE instructions for Intel(R) processors.
            CORE-AVX-I
                    May generate Intel(R) Advanced Vector Extensions (Intel(R)
                    AVX), including instructions in Intel(R) Core 2(TM)
                    processors in process technology smaller than 32nm,
                    Intel(R) SSE4.2, SSE4.1, SSSE3, SSE3, SSE2, and SSE
                    instructions for Intel(R) processors.
            ATOM_SSE4.2
                    May generate MOVBE instructions for Intel(R) processors,
                    depending on the setting of option /Qinstruction.
                    May also generate Intel(R) SSE4.2, SSE3, SSE2, and SSE
                    instructions for Intel processors. Optimizes for Intel(R)
                    Atom(TM) processors that support Intel(R) SSE4.2 and MOVBE
                    instructions.
            ATOM_SSSE3
                    May generate MOVBE instructions for Intel(R) processors,
                    depending on the setting of option /Qinstruction.
                    May also generate Intel(R) SSSE3, SSE3, SSE2, and SSE
                    instructions for Intel processors. Optimizes for the
                    Intel(R) Atom(TM) processor that support Intel(R) SSE
                    and MOVBE instructions.
            MIC-AVX512
                    May generate Intel(R) Advanced Vector Extensions 512
                    (Intel(R) AVX-512) Foundation instructions, Intel(R)
[press RETURN to continue]
                    AVX-512 Conflict Detection instructions, Intel(R) AVX-512
                    Exponential and Reciprocal instructions, Intel(R) AVX-512
                    Prefetch instructions for Intel(R) processors, and the
                    instructions enabled with CORE-AVX2. Optimizes for Intel(R)
                    processors that support Intel(R) AVX-512 instructions.
            KNM
                    May generate Quad Fused Multiply Add (QFMA) and Quad
                    Virtual Neural Network Instruction (QVNNI) and the
                    instructions enabled with MIC-AVX512. Optimizes for
                    Intel(R) Xeon Phi(TM) product family processor code named
                    Knights Mill.
            CORE-AVX512
                    May generate Intel(R) Advanced Vector Extensions 512
                    (Intel(R) AVX-512) Foundation instructions, Intel(R)
                    AVX-512 Conflict Detection instructions, Intel(R) AVX-512
                    Doubleword and Quadword instructions, Intel(R) AVX-512
                    Byte and Word instructions and Intel(R) AVX-512 Vector
                    Length Extensions for Intel(R) processors, and the
                    instructions enabled with CORE-AVX2. Optimizes for Intel(R)
                    processors that support Intel(R) AVX-512 instructions.
            COMMON-AVX512
                    May generate Intel(R) Advanced Vector Extensions 512
                    (Intel(R) AVX-512) Foundation instructions, Intel(R)
                    AVX-512 Conflict Detection instructions, as well as the
                    instructions enabled with CORE-AVX2. Optimizes for Intel(R)
                    processors that support Intel(R) AVX-512 instructions.
            BROADWELL
            CANNONLAKE
            HASWELL
            ICELAKE-CLIENT (or ICELAKE)
            ICELAKE-SERVER
            IVYBRIDGE
            KNL
            KNM
            SANDYBRIDGE
            SILVERMONT
            GOLDMONT
            GOLDMONT-PLUS
            TREMONT
            SKYLAKE
            SKYLAKE-AVX512
            CASCADELAKE
            KABYLAKE
            COFFEELAKE
            AMBERLAKE
            WHISKEYLAKE
            TIGERLAKE
            SAPPHIRERAPIDS
                    May generate instructions for processors that support the
                    specified Intel(R) microarchitecture code name. Optimizes
[press RETURN to continue]
                    for Intel(R) processors that support the specified Intel(R)
                    microarchitecture code name.
                    Keywords KNL and SILVERMONT are only available on Windows*
                    and Linux* systems.
/QxHost   generate instructions for the highest instruction set and processor
          available on the compilation host machine
            SSE4.2 May generate Intel(R) SSE4.2, SSE4.1, SSSE3, SSE3, SSE2,
                    and SSE instructions for Intel processors.
            AVX May generate Intel(R) Advanced Vector Extensions (Intel(R)
                    AVX), Intel(R) SSE4.2, SSE4.1, SSSE3, SSE3,
                    SSE2, and SSE instructions for Intel(R) processors.
            CORE-AVX2
                    May generate Intel(R) Advanced Vector Extensions 2
                    (Intel(R) AVX2), Intel(R) AVX, SSE4.2, SSE4.1, SSSE3, SSE3,
                    SSE2, and SSE instructions for Intel(R) processors.
            CORE-AVX-I
                    May generate Intel(R) Advanced Vector Extensions (Intel(R)
                    AVX), including instructions in Intel(R) Core 2(TM)
                    processors in process technology smaller than 32nm,
                    Intel(R) SSE4.2, SSE4.1, SSSE3, SSE3, SSE2, and SSE
                    instructions for Intel(R) processors.
            CORE-AVX512
                    May generate Intel(R) Advanced Vector Extensions 512
                    (Intel(R) AVX-512) Foundation instructions, Intel(R)
                    AVX-512 Conflict Detection instructions, Intel(R) AVX-512
                    Doubleword and Quadword instructions, Intel(R) AVX-512
                    Byte and Word instructions and Intel(R) AVX-512 Vector
                    Length Extensions for Intel(R) processors, and the
                    instructions enabled with CORE-AVX2.
            BROADWELL
            CANNONLAKE
            HASWELL
            ICELAKE-CLIENT (or ICELAKE)
            ICELAKE-SERVER
            IVYBRIDGE
            KNL
            KNM
            SANDYBRIDGE
            SILVERMONT
            GOLDMONT
            GOLDMONT-PLUS
            TREMONT
            SKYLAKE
            SKYLAKE-AVX512
            CASCADELAKE
            KABYLAKE
            COFFEELAKE
            AMBERLAKE
            WHISKEYLAKE
            TIGERLAKE
[press RETURN to continue]
            SAPPHIRERAPIDS
                    May generate instructions for processors that support the
                    specified Intel(R) microarchitecture code name. Optimizes
                    for Intel(R) processors that support the specified Intel(R)
                    microarchitecture code name.
                    Keywords KNL and SILVERMONT are only available on Windows*
                    and Linux* systems.
/arch:<code>
          generate specialized code to optimize for processors indicated by
          <code> as described below
            BROADWELL
            CANNONLAKE
            HASWELL
            ICELAKE-CLIENT (or ICELAKE)
            ICELAKE-SERVER
            IVYBRIDGE
            KNL
            KNM
            SANDYBRIDGE
            SILVERMONT
            GOLDMONT
            GOLDMONT-PLUS
            TREMONT
            SKYLAKE-AVX512
            SKYLAKE
            CASCADELAKE
            KABYLAKE
            COFFEELAKE
            AMBERLAKE
            WHISKEYLAKE
            TIGERLAKE
            SAPPHIRERAPIDS
                       May generate instructions for processors that support
                       the specified Intel(R) microarchitecture code name
            CORE-AVX2 May generate Intel(R) Advanced Vector Extensions 2
                       (Intel(R) AVX2), Intel(R) AVX, SSE4.2, SSE4.1, SSE3,
                       SSE2, SSE, and SSSE3 instructions
            CORE-AVX-I May generate Float-16 conversion instructions and the
                       RDRND instruction, Intel(R) Advanced Vector Extensions
                       (Intel(R) AVX), Intel(R) SSE4.2, SSE4.1, SSE3, SSE2,
                       SSE, and SSSE3 instructions
            AVX May generate Intel(R) AVX, SSE4.2, SSE4.1, SSSE3, SSE3,
                       SSE2 and SSE instructions
            SSE4.2 May generate Intel(R) SSE4.2, SSE4.1, SSSE3, SSE3, SSE2
                       and SSE instructions
            SSE4.1 May generate Intel(R) SSE4.1, SSSE3, SSE3, SSE2 and SSE
                       instructions
            SSSE3 May generate Intel(R) SSSE3, SSE3, SSE2 and SSE
                       instructions
            SSE3 May generate Intel(R) SSE3, SSE2 and SSE instructions
[press RETURN to continue]
            SSE2 May generate Intel(R) SSE2 and SSE instructions
/tune:<cpu>
          optimize for a specific <cpu>
            generic - Optimizes code for the compiler's default behavior
            broadwell
            haswell
            ivybridge
            knl
            knm
            sandybridge
            silvermont
            cannonlake
            icelake
            skylake-avx512
            skylake - Optimizes code for processors that support the
                         specified Intel(R) microarchitecture code name.
                         knl and silvermont are only available on Windows* and
                         Linux* systems
            core-avx2 - Optimizes code for processors that support Intel(R)
                         Advanced Vector Extensions 2 (Intel(R) AVX2), Intel(R)
                         AVX, SSE4.2 SSE4.1, SSE3, SSE2, SSE, and SSSE3
                         instructions
            core-avx-i - Optimizes code for processors that support Float-16
                         conversion instructions and the RDRND instruction,
                         Intel(R) Advanced Vector Extensions (Intel(R) AVX),
                         Intel(R) SSE4.2, SSE4.1, SSE3, SSE2, SSE, and SSSE3
                         instructions
            corei7-avx - Optimizes code for processors that support Intel(R)
                         Advanced Vector Extensions (Intel(R) AVX), Intel(R)
                         SSE4.2, SSE4.1, SSE3, SSE2, SSE, and SSSE3
                         instructions
            corei7 - Optimizes code for processors that support Intel(R)
                         SSE4 Efficient Accelerated String and Text Processing
                         instructions. May also generate code for Intel(R) SSE4
                         Vectorizing Compiler and Media Accelerator, Intel(R)
                         SSE3, SSE2, SSE, and SSSE3 instructions
            atom - Optimizes code for processors that support MOVBE
                         instructions, depending on the setting of option
                         -minstruction (Linux and macOS*) or /Qinstruction
                         (Windows). May also generate code for SSSE3
                         instructions and Intel(R) SSE3, SSE2, and SSE
                         instructions
            core2 - Optimizes for the Intel(R) Core(TM) 2 processor
                         family, including support for MMX(TM), Intel(R) SSE,
                         SSE2, SSE3, and SSSE3 instruction sets.
            pentium-mmx - Optimizes for Intel(R) Pentium(R) with MMX technology
            pentiumpro - Optimizes for Intel(R) Pentium(R) Pro, Intel Pentium
                         II, and Intel Pentium III processors
            pentium4m - Optimizes for Intel(R) Pentium(R) 4 processors with
                         MMX technology
[press RETURN to continue]
            pentium-m
            pentium4
            pentium3
            pentium - Optimizes code for Intel(R) Pentium(R) processors.
                         Value pentium3 is only available on Linux systems
/guard:cf
          enable control flow protection mechanism
/Qm64     generate code for Intel(R) 64 architecture
/Qcf-protection[:<arg>]
          Enables Control-flow Enforcement Technology (CET) protection, which
          defends your program from certain attacks that exploit
          vulnerabilities.
            shadow_stack - Enables shadow stack protection
            branch_tracking - Enables endbranch (EB) generation
            full - Enables both shadow stack protection and
                              endbranch (EB) generation (same as no <arg>)
            none - Disables Control-flow Enforcement Technology
                              protection
Interprocedural Optimization (IPO)
----------------------------------
/Qipo[n]  enable multi-file IP optimization between files
Advanced Optimizations
----------------------
/Qunroll[n]
          set maximum number of times to unroll loops. Omit n to use default
          heuristics. Use n=0 to disable the loop unroller
/Qpad[-]  enable/disable(DEFAULT) changing variable and array memory layout
/Qsafe-cray-ptr
          Cray pointers do not alias with other variables
/Qansi-alias[-]
          enable(DEFAULT)/disable use of ANSI aliasing rules optimizations;
          user asserts that the program adheres to these rules
/reentrancy:<keyword>
          specify whether the threaded, reentrant run-time support should be
          used
          Keywords: none (same as /noreentrancy), threaded(DEFAULT), async
/noreentrancy
          do not use threaded, reentrant run-time support
/heap-arrays[:n]
          temporary arrays of minimum size n (in kilobytes) are allocated in
          heap memory rather than on the stack. If n is not specified,
          all temporary arrays are allocated in heap memory.
/heap-arrays-
          temporary arrays are allocated on the stack (DEFAULT)
/Qvec[-]  enables(DEFAULT)/disables vectorization
/Qvec-threshold[n]
          sets a threshold for the vectorization of loops based on the
          probability of profitable execution of the vectorized loop in
          parallel
/Qopt-jump-tables[-]
[press RETURN to continue]
          control the generation of jump tables
/Qmkl[:<arg>]
          link to the Intel(R) Math Kernel Library (Intel(R) MKL) and bring
          in the associated headers
            parallel - link using the threaded Intel(R) MKL libraries. This
                         is the default when /Qmkl is specified
            sequential - link using the non-threaded Intel(R) MKL libraries
            cluster - link using the Intel(R) MKL Cluster libraries plus
                         the sequential Intel(R) MKL libraries
/Qcoarray[:<keyword>]
          Coarrays are not yet supported with ifx
/Qcoarray-num-images:n
          Coarrays are not yet supported with ifx
/Qopt-mem-layout-trans[:<level>]
          controls the level of memory layout transformations performed by the
          compiler
           0 - disable memory layout transformations (same as
               /Qopt-mem-layout-trans-)
           1 - enable basic memory layout transformations
           2 - enable more memory layout transformations (DEFAULT when the
               option is specified)
           3 - enable aggressive memory layout transformations
/Qopt-dynamic-align
          enable dynamic data alignment optimizations. Specify
          /Qopt-dynamic-align- to disable(DEFAULT)
/Qopt-zmm-usage:<keyword>
          Specifies the level of zmm registers usage. You can specify one of
          the following:
            low - Tells the compiler that the compiled program is unlikely to
                   benefit from zmm registers usage. It specifies that the
                   compiler should avoid using zmm registers unless it can
                   prove the gain from their usage.
            high - Tells the compiler to generate zmm code without restrictions
/Qoverride-limits
          provides a way to override certain internal compiler limits that are
          intended to prevent excessive memory usage or compile times for very
          large, complex compilation units.
/Qopt-multiple-gather-scatter-by-shuffles[-]
          Enables or disables the optimization for multiple adjacent
          gather/scatter type vector memory references.
/Qbranches-within-32B-boundaries[-]
          align branches and fused branches on 32 byte boundaries
/Qopt-for-throughput:<arg>
          Using 'multi-job', which is the default, the compiler will optimize
          for throughput performance, assuming multiple jobs are running.
          The memory optimizations for single job versus multiple jobs can be
          tuned in different ways by the compiler.
Profile Guided Optimization (PGO)
---------------------------------
/Qinstrument-functions[-]
[press RETURN to continue]
          determine whether function entry and exit points are instrumented
Optimization Reports
--------------------
/Qopt-report[:n]
          generate an optimization report. Default destination is
          <target>.optrpt. Levels of 0 - 5 are valid.
          Please see documentation for additional details of
          information provided by phase per level.
            0 disable optimization report output
            2 DEFAULT when enabled
OpenMP* and Parallel Processing
------------------------------
/Qopenmp  enable the compiler to generate multi-threaded code based on the
          OpenMP* directives (same as /openmp)
          Use /Qopenmp- to disable
/Qopenmp-stubs
          enables the user to compile OpenMP programs in sequential mode. The
          OpenMP directives are ignored and a stub OpenMP library is linked
          (sequential)
/Qopenmp-threadprivate:<ver>
          choose which threadprivate implementation to use
            compat - use the Microsoft compatible thread local storage
            legacy - use the Intel compatible implementation
                     (DEFAULT)
/Qparallel-source-info[:n]
          enable(DEFAULT)/disable the emission of source location information
          for parallel code generation with OpenMP and auto-parallelization
            0 - disable (same as /Qparallel-source-info-)
            1 - emit routine name and line information (DEFAULT)
            2 - emit path, file, routine name and line information
/Qopenmp-simd
          Enables OpenMP* SIMD compilation. Enabled by default with
          /Qopenmp. Use /Qopenmp-simd- to disable.
/[no-]device-math-lib:<arg>
          Control the addition of device math libraries when compiling for
          OpenMP* offloading.
            fp64 - FP64 based libraries
            fp32 - FP32 based libraries
Floating Point
--------------
/fp:<name>
          enable <name> floating point model variation
            fast - enables more aggressive floating point optimizations
            precise - allows value-safe optimizations
            strict - enables /fp:precise, disables
                          contractions and enables pragma stdc fenv_access
/Qfp-speculation:<mode>
          enable floating point speculations with the following <mode>
          conditions:
            fast - speculate floating point operations (DEFAULT)
[press RETURN to continue]
            safe - speculate only when safe
            strict - same as off
            off - disables speculation of floating-point operations
/Qpc32    set internal FPU precision to 24 bit significand
/Qprec-sqrt[-]
          determine if certain square root optimizations are enabled
/Qfast-transcendentals[-]
          generate a faster version of the transcendental functions
/Qrcd     rounding mode to enable fast float-to-int conversions
/rounding-mode:chopped
          set internal FPU rounding control to truncate
/Qftz[-]  enable/disable flush denormal results to zero
/fpe:{0|1|3}
          specifies program-wide behavior on floating point exceptions
/fpe-all:{0|1|3}
          specifies floating point exception behavior on all functions
          and subroutines. Also sets /assume:ieee_fpe_flags
/[no]fltconsistency
          specify that improved floating-point consistency should be used
/Qfma[-]  enable/disable the combining of floating point multiplies and
          add/subtract operations
/[no]recursive
          compile all procedures for possible recursive execution
/Qimf-absolute-error:value[:funclist]
          define the maximum allowable absolute error for math library
          function results
            value - a positive, floating-point number conforming to the
                       format [digits][.digits][{e|E}[sign]digits]
            funclist - optional comma separated list of one or more math
                       library functions to which the attribute should be
                       applied
/Qimf-accuracy-bits:bits[:funclist]
          define the relative error, measured by the number of correct bits,
          for math library function results
            bits - a positive, floating-point number
            funclist - optional comma separated list of one or more math
                       library functions to which the attribute should be
                       applied
/Qimf-arch-consistency:value[:funclist]
          ensures that the math library functions produce consistent results
          across different implementations of the same architecture
            value - true or false
            funclist - optional comma separated list of one or more math
                       library functions to which the attribute should be
                       applied
/Qimf-max-error:ulps[:funclist]
          defines the maximum allowable relative error, measured in ulps, for
          math library function results
            ulps - a positive, floating-point number conforming to the
                       format [digits][.digits][{e|E}[sign]digits]
[press RETURN to continue]
            funclist - optional comma separated list of one or more math
                       library functions to which the attribute should be
                       applied
/Qimf-precision:value[:funclist]
          defines the accuracy (precision) for math library functions
            value - defined as one of the following values
                       high - equivalent to max-error = 1.0
                       medium - equivalent to max-error = 4 (DEFAULT)
                       low - equivalent to accuracy-bits = 11 (single
                                precision); accuracy-bits = 26 (double
                                precision)
                       reference - equivalent to 'high' accuracy with correct
                                signaling of exceptional conditions through
                                the errno and status flags settings. This
                                setting is initially available only on Linux*
                                systems
            funclist - optional comma separated list of one or more math
                       library functions to which the attribute should be
                       applied
/Qimf-domain-exclusion:classlist[:funclist]
          indicates the input arguments domain on which math functions
          must provide correct results.
            classlist - defined as one of the following values:
                          nans, infinities, denormals, zeros
                          all, none, common
            funclist - optional list of one or more math library functions to
                       which the attribute should be applied.
/Qfinite-math-only
          Allow optimizations for floating point arithmetic that assume
          arguments and results are not NaNs or Infinities
Inlining
--------
/Ob<n>    control inline expansion:
            n=0 disable inlining (same as /inline:none)
            n=1 inline functions declared with ATTRIBUTES INLINE or
                   FORCEINLINE
            n=2 inline any function, at the compiler's discretion
/inline[:keyword]
          Specifies the level of inline function expansion
            keywords: all (same as /Ob2 /Ot), size (same as /Ob2 /Os)
                      speed (same as /Ob2 /Ot), none or manual (same as /Ob0)
Output, Debug, PCH
------------------
/c        compile to object (.obj) only, do not link
/nolink, /compile-only
          same as /c
/S        compile to assembly (.asm) only, do not link
/FA       produce assembly file
/Fa[file]
          name assembly file (or directory for multiple files; i.e. /FaMYDIR\)
[press RETURN to continue]
/Fo[file]
          name object file (or directory for multiple files; i.e. /FoMYDIR\)
/Fe[file]
          name executable file or directory
/Fi[file]
          name preprocessed file (or directory for multiple files; i.e.
          /FiMYDIR\)
/object:<filename>
          specify the name of the object file, or the directory to which object
          file(s) should be written. (e.g. /object:MYOBJ or /object:MYDIR\)
/exe:<filename>
          specifies the name to be used for the built program (.exe) or
          dynamic-link (.dll) library
/map:<filename>
          specify that a link map file should be generated
/list[:<filename>]
          specify that a listing file should be generated
/list-line-len:#
          overrides the default line length (80) in a listing file
/list-page-len:#
          overrides the default page length (66) in a listing file
/show:<keyword>
          controls the contents of the listing file
          keywords: all, none, [no]include, [no]map, [no]options
/Zi, /ZI, /Z7
          Produce symbolic debug information. The /Zi and /ZI flags emit the
          debug information for types into a separate PDB file.
/debug:offload
          Generate debug information for offload target
/nodebug  Disable emission of debug information.
/debug-parameters[:keyword]
          Control output of debug information for PARAMETERS.
          Valid [keyword] values:
             none - Disables generation of debug information for PARAMETERs.
             used - Generates debug information for referenced PARAMETERs only.
             all - Generates debug information for all PARAMETERs.
/nodebug-parameters
          Same as "/debug-parameters:none".
/Qd-lines, /[no]d-lines
          compile debug statements (indicated by D in column 1)
/pdbfile[:filename]
          Specify that debug related type information should be generated to a
          program database file at link time.
/nopdbfile
          Do not generate debug related information to a program database file.
/Qtrapuv  trap uninitialized variables
/RTCu     report use of variable that was not initialized
/Qmap-opts
          enable option mapping tool
/Qeliminate-unused-debug-types[-]
[press RETURN to continue]
          When disabled, debug information for all types present in the
          sources will be emitted. Using this option may cause a large
          increase in the size of the debug information.
Preprocessor
------------
/D<name>[{=|#}<text>]
          define macro
/define:symbol[=<value>]
          same as /D
/nodefines
          specifies that any /D macros go to the preprocessor only, and not to
          the compiler
/U<name>  remove predefined macro
/undefine:<name>
          remove predefined macro (same as /U)
/allow:nofpp-comments
          If a Fortran end-of-line comment is seen within a #define, treat it
          as part of the definition. Default is allow:fpp-comments
/E        preprocess to stdout
/EP       preprocess to stdout, omitting #line directives
/EP /P    preprocess to file, omitting #line directives
/P        preprocess to file
/preprocess-only
          same as /P
/[no]keep  keep/remove preprocessed file generated by preprocessor as input to
           compiler stage. Not affected by /Qsave-temps. Default is /nokeep
/[no]fpp   run Fortran preprocessor on source files prior to compilation
/fpp-name:name
           Name an alternate preprocessor executable. The name can
           include the full path.
/module:path
           specify path where mod files should be placed and first location to
           look for mod files
/u        remove all predefined macros
/I<dir>   add directory to include file search path
/[no]include:<dir>
          same as /I
/X        remove standard directories from include file search path
/gen-dep[:filename]
          generate dependency information.
          If no filename is specified, output is to stdout.
           Similar to /QMD or /QMMD
          If a filename is specified, output is to filename.
           Similar to /QMF filename
/gen-dep-
          do not generate dependency information (default)
/gen-depshow:keyword
          control what dependency information is output.
          [no]intr_mod Intrinsic modules. Default is nointr_mod.
/gen-depformat:keyword
[press RETURN to continue]
          generate dependency information in the specified format.
          One of: make, nmake
Component Control
-----------------
/Qoption,<tool>,<opts>
          pass options <opts> to tool specified by <tool>
/Qlocation,<tool>,<dir>
          set <dir> as the location of tool specified by <tool>
Language
--------
/[no]altparam
          specify if alternate form of parameter constant declarations
          (without parenthesis) is recognized. Default is to recognize
/assume:<keyword>
          specify assumptions made by the optimizer and code generator
          keywords: none, [no]byterecl, [no]buffered_io,
                    [no]buffered_stdout,
                    [no]bscc (nobscc same as /nbs),
                    [no]contiguous_assumed_shape, [no]contiguous_pointer,
                    [no]cc_omp, [no]failed_images, [no]minus0,
                    [no]dummy_aliases (same as /Qcommon-args),
                    [no]ieee_fpe_flags, [no]ieee_compares, [no]fpe_summary,
                    [no]nan_compares,
                    [no]old_boz, [no]old_complex_align,
                    [no]old_inquire_recl,
                    [no]old_logical_ldio, [no]old_logical_assign,
                    [no]old_ldout_format, [no]old_ldout_zero,
                    [no]old_maxminloc, [no]old_unit_star, [no]old_xor,
                    [no]protect_allocates,
                    [no]protect_constants, [no]protect_parens,
                    [no]recursion, [no]realloc_lhs, [no]2underscore,
                    [no]underscore (same as /us),
                    [no]std_intent_in, [no]std_minus0_rounding,
                    [no]std_mod_proc_name, [no]std_value,
                    [no]source_include,
                    [no]split_common, [no]writeable_strings
/ccdefault:<keyword>
          specify default carriage control for units 6 and *
          keywords: default, fortran, list or none
/[no]check:<keyword>
          check run-time conditions. Default is /nocheck
          keywords: all (same as /4Yb, /C), none (same as /nocheck, /4Nb),
                    [no]arg_temp_created, [no]bounds (same as /CB),
                    [no]assume, [no]contiguous,
                    [no]format, [no]output_conversion,
                    [no]pointers (same as /CA),
                    [no]shape, [no]stack, [no]teams,
                    [no]udio_iostat, [no]uninit (same as /CU)
/Qcommon-args
          assume "by reference" subprogram arguments may alias one
[press RETURN to continue]
          another. Same as /assume:dummy_aliases
/[no]extend-source[:<keyword>]
          specify rightmost column for fixed form sources
          keywords: 72 (same as /noextend-source and /4L72),
                    80 (same as /4L80),
                   132 (same as /4L132. Default if you specify
                        /extend-source without a keyword.)
/fixed    specify source files are in fixed format. Same as /FI and /4Nf
          /nofixed indicates free format
/free     specify source files are in free format. Same as /FR and /4Yf
          /nofree indicates fixed format
/names:<keyword>
          specify how source code identifiers and external names are
          interpreted.
          keywords: as_is, lowercase, uppercase
/[no]pad-source, /Qpad-source[-]
          make compiler acknowledge blanks at the end of a line
/stand[:<keyword>]
          specifies level of conformance with ANSI standard to check
          for. If keyword is not specified, level of conformance is f18
          keywords: f90 (same as /4Ys), f95,
                    f03, f08, f18,
                    none (same as /nostand)
/standard-semantics
          explicitly sets assume keywords to conform to the semantics
          of the Fortran standard. May result in performance loss.
          assume keywords set by /standard-semantics:
            byterecl, failed_images, fpe_summary, ieee_compares, minus0,
            noold_inquire_recl, noold_ldout_format, noold_ldout_zero,
            noold_maxminloc, noold_unit_star, noold_xor, protect_parens,
            realloc_lhs, recursion, std_intent_in, std_minus0_rounding,
            std_mod_proc_name, std_value
          also sets /fpscomp:logicals
          If /fp:strict or /fp:except is set
            then this also sets assume keyword ieee_fpe_flags
/[no]standard-realloc-lhs
          explicitly sets assume keyword realloc_lhs to conform to the
          standard, or to override the default. Sets /assume:[no]realloc_lhs
/syntax-only, /Zs
          perform syntax and semantic checking only (no object file produced)
/wrap-margin[-]
          controls right margin wrapping in list-directed output. By default,
          list-directed output is wrapped at 80 characters.
Compiler Diagnostics
--------------------
/w        disable all warnings
/W<n>     disable warnings (n = 0) or show warnings (n = 1 DEFAULT, same as
          /warn:general)
/warn:<keyword>
          specifies the level of warning messages issued
[press RETURN to continue]
            keywords: all, none (same as /nowarn)
                      [no]alignments, [no]declarations,
                      [no]errors, [no]externals,
                      [no]general, [no]ignore_loc, [no]interfaces,
                      [no]shape, [no]stderrors, [no]truncated_source,
                      [no]uncalled, [no]unused, [no]usage
/nowarn   suppress all warning messages
/WB       turn a compile-time bounds check into a warning
/[no]traceback
          specify whether the compiler generates PC correlation data used to
          display a symbolic traceback rather than a hexadecimal traceback at
          runtime failure
/[no]gen-interfaces [[no]source]
          generate interface blocks for all routines in the file. Can be
          checked using -warn interfaces
          nosource indicates temporary source files should not be saved
/error-limit:<size>
          specify the maximum number of error-level or fatal-level compiler
          errors allowed
/noerror-limit
          set no maximum number on error-level or fatal-level error messages
          All diagnostic options (/Qdiag*) are only valid for driver specific
          diagnostics.
/Qdiag-enable:<v1>[,<v2>,...]
          enable the specified diagnostics or diagnostic groups
/Qdiag-disable:<v1>[,<v2>,...]
          disable the specified diagnostics or diagnostic groups
/Qdiag-error:<v1>[,<v2>,...]
          output the specified diagnostics or diagnostic groups as errors
/Qdiag-warning:<v1>[,<v2>,...]
          output the specified diagnostics or diagnostic groups as warnings
/Qdiag-remark:<v1>[,<v2>,...]
          output the the specified diagnostics or diagnostic groups as remarks
/Qdiag-dump
          display the currently enabled diagnostic messages to stdout
/Qdiag-file[:<file>]
          <file> where diagnostics are emitted to. Not specifying this causes
          messages to be output to stderr
/Qdiag-file-append[:<file>]
          <file> where diagnostics are emitted to. When <file> already exists,
          output is appended to the file
/Qdiag-id-numbers[-]
          enable(DEFAULT)/disable the diagnostic specifiers to be output in
          numeric form
/Qdiag-error-limit:<num>
          specify the maximum number of errors emitted
Miscellaneous
-------------
/[no]logo
          display compiler version information. /nologo disables the output
[press RETURN to continue]
/QV       display compiler version information
/Qsave-temps
          store the intermediate files in current directory and name them
          based on the source file. Only saves files that are generated by
          default
/what     display detailed compiler version information
/watch:<keyword>
          tells the driver to output processing information
            keywords: all, none (same as /nowatch), [no]source,
                      [no]cmd
                      [no]offload-cmd
/nowatch  suppress processing information output (DEFAULT)
/Tf<file>
          compile file as Fortran source
/extfor:<ext>
           specify extension of file to be recognized as a Fortran file
/extfpp:<ext>
           specify extension of file to be recognized as a preprocessor file
/libdir[:keyword]
          control the library names that should be emitted into the object file
            keywords: all, none (same as /nolibdir), [no]automatic, [no]user
/nolibdir
          no library names should be emitted into the object file
/MP[<n>]  create multiple processes that can be used to compile large numbers
          of source files at the same time
-f[no-]openmp-device-lib=<arg>
          Control inclusion of device libraries into device binary linkage.
          Valid arguments are: libc, libm-fp32, libm-fp64, all
-fsycl    Enable SYCL kernel compilation for device. This is for link-time
          only, consuming Fortran and DPC++ objects.
-fsycl-device-code-split=<arg>
          Perform SYCL device code split.
            per_kernel - device code module is created for each SYCL kernel
            per_source - device code module is created for each source
                         (translation unit)
            off - no device code split
            auto - use heuristic to select the best way of splitting
                         device code (DEFAULT)
-f[no-]sycl-device-lib=<arg>
          Control inclusion of device libraries into device binary linkage.
          Valid arguments are: libc, libm-fp32, libm-fp64, all
-f[no-]sycl-instrument-device-code
          Add ITT instrumentation intrinsics calls
-f[no-]sycl-dead-args-optimization
          Enables elimination of DPC++ dead kernel arguments
/Qopenmp-targets:<arg>
          Enables offloading to a specified GPU target if OpenMP* features have
          been enabled.
/Qopenmp-target-buffers:<arg>
          Enables a way to overcome the problem where some OpenMP* offload
[press RETURN to continue]
          SPIR-V* devices produce incorrect code when a target object is
          larger than 4GB.
            default - use default heuristics
            4GB - Allow access to target objects of 4GB or larger in
                      target code
Data
----
/4I{2|4|8}
          set default KIND of integer and logical variables to 2, 4, or 8
/integer-size:<size>
          specifies the default size of integer and logical variables
            size: 16, 32, 64
/4R{8|16}
          set default size of real to 8 or 16 bytes
/real-size:<size>
          specify the size of REAL and COMPLEX declarations, constants,
          functions, and intrinsics
            size: 32, 64, 128
/Qautodouble
          same as /real-size:64 or /4R8
/double-size:<size>
          defines the size of DOUBLE PRECISION and DOUBLE COMPLEX declarations,
          constants, functions, and intrinsics
            size: 64, 128
/[no]fpconstant
          extends the precision of single precision constants assigned to
          double precision variables to double precision
/[no]intconstant
          use Fortran 77 semantics, rather than Fortran 90/95, to determine
          kind of integer constants
/auto     make all local variables AUTOMATIC
/Qauto-scalar
          make scalar local variables AUTOMATIC (DEFAULT)
/Qsave    save all variables (static allocation) (same as /noauto,
          opposite of /auto)
/Qzero[-]
          enable/disable(DEFAULT) implicit initialization to zero of local
          scalar variables of intrinsic type INTEGER, REAL, COMPLEX, or
          LOGICAL that are saved and not initialized
/Qinit:<keyword>
          enable/disable(DEFAULT) implicit initialization of local
          variables of intrinsic type INTEGER, REAL, COMPLEX, or
          LOGICAL that are saved and not initialized
          The <keyword> specifies the initial value
            keywords: zero (same as /Qzero),
                      snan (valid only for floating point variables),
                      infinity, minus_infinity (valid only for floating point)
                      tiny, minus_tiny (valid only for floating point)
                      huge, minus_huge
                      arrays
[press RETURN to continue]
/Qdyncom<common1,common2,...>
          make given common blocks dynamically-allocated
/Zp[n]    specify alignment constraint for structures (n=1,2,4,8,16
          /Zp16 DEFAULT)
/[no]align
          analyze and reorder memory layout for variables and arrays
/align:<keyword>
          specify how data items are aligned
            keywords: all (same as /align), none (same as /noalign),
                      [no]commons, [no]dcommons,
                      [no]qcommons, [no]zcommons,
                      rec1byte, rec2byte, rec4byte,
                      rec8byte, rec16byte, rec32byte,
                      array8byte, array16byte, array32byte,
                      array64byte, array128byte, array256byte,
                      [no]records, [no]sequence
/Qcommon  Enables the compiler to treat common variables as if they were
          defined. That in turn allows the use of gprel addressing of common
          data variables. /Qcommon- disables
/GS       enable overflow security checks. Optional <arg> can specify:
            partial - provide a stack protection level that is compatible with
                      Microsoft* Visual Studio 2008.
            strong - provide full stack security level checking. This setting
                      is compatible with recent Microsoft* Visual Studio stack
                      protection heuristics. This is the same as specifying /GS
                      with no keyword.
            off - Same as /GS- (DEFAULT)
/Qpatchable-addresses
           generate code such that references to statically assigned addresses
           can be patched with arbitrary 64-bit addresses.
/Qkeep-static-consts[-]
          enable/disable(DEFAULT) the ability to preserve allocation of
          variables that are not referenced in the source
/Qzero-initialized-in-bss[-]
          put explicitly zero initialized variables into the DATA section
          instead of the BSS section
/convert:<keyword>
          specify the format of unformatted files containing numeric data
            keywords: big_endian, cray, ibm, little_endian, native, vaxd, vaxg
/Qfnalign:<n>
          align the start of functions on a 2 (DEFAULT) or <n> byte boundary
          where <n> is a power of 2
/Qfnalign
          align the start of functions to an optimal machine-dependent value.
          /Qfnalign- (DEFAULT) aligns on a 2-byte boundary
Compatibility
-------------
/fpscomp[:<keyword>]
          specify the level of compatibility to adhere to with Fortran
          PowerStation
[press RETURN to continue]
            keywords: all, none (same as /nofpscomp), [no]filesfromcmd,
                      [no]general, [no]ioformat, [no]ldio_spacing,
                      [no]libs, [no]logicals
/nofpscomp
          no specific level of compatibility with Fortran PowerStation
/f66      allow extensions that enhance FORTRAN-66 compatibility
/f77rtl   specify that the Fortran 77 specific run-time support should be used
          /nof77rtl disables
/vms      enable VMS I/O statement extensions
Linking/Linker
--------------
/link     specify that all options following '/link' are for the linker
/extlnk:<ext>
          specify extension of file to be passed directly to linker
/F<n>     set the stack reserve amount specified to the linker
/dbglibs  use the debug version of runtime libraries, when appropriate
/libs:<keyword>
          specifies which type of run-time library to link to.
          keywords: static, dll, qwin, qwins
/LD[d]    produce a DLL instead of an EXE ('d' = debug version)
/dll      same as /LD
/MD[d]    use dynamically-loaded, multithread C runtime
/MDs[d]   use dynamically-loaded, singlethread Fortran runtime,
          and multithread C runtime
/MT[d]    use statically-linked, multithread C runtime (DEFAULT with
          Microsoft Visual Studio 2005 and later)
/MG, /winapp
          use Windows API runtime libraries
/Zl       omit library names from object file
/threads  specify that multi-threaded libraries should be linked against
          /nothreads disables multi-threaded libraries
/Qno-intel-lib[:<arg>]
          Restrict linking of Intel provided libraries. Arguments can be
          specified via a comma separated list. Valid arguments are:
          libirc, libimf, libsvml, libirng, libipgo
Deprecated Options
------------------
/Quse-asm No replacement
/Qvc11 No replacement
/Qcilk-serialize No replacement
/arch:ICELAKE use /arch:ICELAKE-CLIENT
/QxICELAKE use /QxICELAKE-CLIENT
/QaxICELAKE use /QaxICELAKE-CLIENT
/arch:SSE use /arch:IA32
/help, /? [category] print full or category help message
Valid categories include
       advanced - Advanced Optimizations
       codegen - Code Generation
       compatibility - Compatibility
       component - Component Control
[press RETURN to continue]
       data - Data
       deprecated - Deprecated Options
       diagnostics - Compiler Diagnostics
       float - Floating Point
       help - Help
       inline - Inlining
       ipo - Interprocedural Optimization (IPO)
       language - Language
       link - Linking/Linker
       misc - Miscellaneous
       opt - Optimization
       output - Output
       pgo - Profile Guided Optimization (PGO)
       preproc - Preprocessor
       reports - Optimization Reports
       openmp - OpenMP and Parallel Processing
Copyright (C) 1985-2022, Intel Corporation. All rights reserved.
* Other names and brands may be claimed as the property of others.
```