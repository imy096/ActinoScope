# DRAFT — ActinoScope Beta 1 release notes

**Version:** `0.6.0.dev23`  
**Release status:** PRIVATE TEST CANDIDATE — **NOT YET PUBLISHED**  
**Intended release repository:** https://github.com/imy096/ActinoScope

> This document is a draft for the maintainer. It is **not** a GitHub Release, a public download or a declaration of scientific acceptance. Update the checks and replace the private-test references before any actual publication.

## Overview

ActinoScope is a local-first Windows research workspace for bacterial genome analysis, biosynthetic gene cluster (BGC) investigation, and evidence-centered exploration of enzyme and natural-product hypotheses. Its Windows launcher starts a local Streamlit interface. Relevant scientific stages require separately configured Linux/WSL command-line tools and reference databases.

## Candidate capabilities

- Windows launcher and Botanical Motion RC7.7-based responsive local interface.
- Input organization, bacterial FASTA validation and QC.
- Project and run management, status reporting, output manifests and inspection.
- Configurable integration pathways for Bakta, antiSMASH, GECCO and other scientific software, subject to environment readiness.
- Evidence-oriented downstream readers and reporting pathways; per-module scientific acceptance must be checked independently.

## Verification snapshot (2026-11-23)

- Windows candidate build, local isolated installation and process-management smoke check: PASS.
- 37-wheel private test ZIP: checksum/integrity verification PASS.
- Current interface source files match built app wheel: PASS.
- Small synthetic FASTA QC-only pipeline and scientific dry run: PASS.
- Automated testing: **256 passed / 37 failed / 1 skipped**.
- WSL executable/tool-version probes: observed, **not scientific end-to-end acceptance**.
- A clean-PC installation and complete new-genome Bakta→antiSMASH analysis: **NOT YET ACCEPTED**.

Full details: [Release readiness](RELEASE_READINESS.md).

## Installation requirements

64-bit Windows, 64-bit Python 3.11 for this specific test-kit installer, and available disk space. Scientific workflows require WSL2 Ubuntu, separately installed scientific tools and substantial reference databases; 16+ GB RAM is recommended for typical full-genome work, subject to actual workloads.

**Current private archive:** `ActinoScope_Beta1_WinFix_Private_TestKit.zip`. Its installer is named `INSTALL_PRIVATE_TEST.bat`, intentionally signals `PUBLIC_RELEASE_READY=NO`, and must not be advertised as an approved general-release installer.

## Important limitations

- A full real-genome scientific run and scientific database validation have not passed complete acceptance.
- The 37 broad-suite failures have not all been classified or corrected.
- A clean second-PC installation has not been completed.
- Not a fully self-contained offline scientific software stack: scientific tools and reference databases are separate.
- Predictions are computational hypotheses; they do not establish metabolite presence, enzyme activity, or experimental confirmation.
- Not for clinical or diagnostic use.

## Publication tasks remaining

Before releasing a public installer, finalize the release acceptance evidence, external dependency/terms audit, ActinoScope license, exact distribution instructions, approved ZIP checksum, final software version/tag and maintainer-provided checksums. Publish the artifact through GitHub Releases **only** after these conditions are appropriately met.

## Credits and citation

Developer/author: **Imene Maallem**. Research affiliation: **FLORET Center for Advanced Genomics and Bioinformatics Research, Nigeria**. Affiliation does not by itself indicate institutional ownership or endorsement. See [Citation](CITATION.md).

**No DOI is assigned to this unpublished candidate.**
