# MOGAligner: Methylation Optimized Genomic Aligner

A bisulfite sequencing (WGBS) short-read aligner written in Rust. It aims to match or beat the established
aligners on accuracy while aligning a whole human methylome in under 12 GB of memory, so the job fits an
ordinary 16 GB machine.

## Status

**MOGAligner is under active development and not yet released.** The source code is in a private
repository for now.

For private developer access in the meantime, email **nathaniellcronin@gmail.com**.

## In brief

- Rust, with no `unsafe` code; SIMD kernels chosen at run time for AVX-512, AVX2 or SSE4.2.
- A bisulfite-aware minimizer index of GRCh38 that builds and aligns in about 7 GB of memory.
- Mapping quality read from error rates measured on simulated reads of known origin.
- SAM/BAM output with Bismark's XM/XR/XG tags, for Bismark's extractor, MethylDackel and MethHero.
- A built-in trimmer whose output is byte-identical to Trim Galore 2.3.0's, and which can trim while it aligns.

Benchmarks against minibwa, bwa-mem3, bwa-meth, BISCUIT, Bismark, BSBolt, BSMAP and ARYANA-BS will be
published with the release.

Sister project: **MEWAligner** (Massively Efficient Workflow Aligner), optimised for AI laptops.

Claude Code was instrumental in the build and design of MOGAligner.

Licence: MIT or Apache-2.0 (on release).
