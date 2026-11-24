# ActinoScope Beta 1 — release-readiness and acceptance record

**Report date:** 2026-11-23  
**Version under review:** `0.6.0.dev23`  
**Candidate build source commit:** `c0590b6` (private source repository)  
**Repository:** `imy096/ActinoScope` (public documentation only)  
**Distribution state:** PRIVATE CANDIDATE — NO PUBLIC INSTALLER RELEASED

This is a transparency record, **not** certification of a complete scientific pipeline. The source of truth for individual checks is the developer's retained Windows CMD logs, application wheel and build manifest; this public summary does not contain confidential data.

## Completed checks

| Check | Evidence/observed result | Scope |
| --- | --- | --- |
| Windows candidate build | `CANDIDATE_BUILD=PASS` | Rebuilt application from source commit `c0590b6` |
| Isolated local installation | `CANDIDATE_INSTALL=PASS`, `ISOLATED_IMPORTS=PASS` | Development Windows PC only |
| Current UI in runtime | `LATEST_UI_INSTALLED=YES` | Local installation |
| Windows process detection | `WINDOWS_PROCESS_CHECK=PASS` | Temporary subprocess checked without unintended termination |
| Offline ZIP integrity | `WINDOWS_FIX_PACKAGE=PASS`, 37/37 wheels verified | Private test ZIP; not a public download |
| UI source/wheel correspondence | `BETA1_SOURCE_WHEEL_MATCH=PASS` | Current `app.py`, `visual_style.py`, stable CSS |
| Synthetic FASTA QC-only pipeline | `QC_ONLY_PIPELINE=PASS` | Small input; annotation and BGC callers deliberately disabled |
| Scientific dry run | `SCIENTIFIC_DRY_RUN=PASS` | No full new-genome execution |
| Existing WSL tool probes | Bakta 1.12.2, antiSMASH 8.0.4, GECCO 0.11.0 and additional tools recognized | Version and environment detection, not validated scientific end-to-end execution |
| antiSMASH component directories | 10 named database directories with files, totaling approximately 9.4 GiB | File presence/size only; not formal readiness/compatibility |
| Current CSS structural validation | CSS syntax, breakpoints, header/sidebar selectors and reduced-motion rules: PASS | Static structure, not a substitute for visual or accessibility evaluation |
| Two restored helper-script tests | 10 passed | Bakta low-memory / MA15 helper behavior |
| Private source backup | Latest public-reported source commit `21d258f`; private GitHub copy | Source maintained separately from public docs |

### Package identity

- Private candidate ZIP: `ActinoScope_Beta1_WinFix_Private_TestKit.zip` — **91,283,828 bytes**, kept locally by maintainer.
- App wheel SHA-256: `43a230e35e4199cc2aebe1924809b3743412ffb9e6f06ddcfca3a3ed4f7b9d08`.
- The above checksum applies to the **application wheel**, NOT to the full ZIP. Do **not** present it as a download ZIP checksum. The ZIP's own SHA-256 should be computed and published when authorized distribution becomes available.
- The `BETA1_UI_FILE_MANIFEST.json` with the corresponding three UI source hashes resides in the **private** source repository.
- The generated installer contains an explicit `PUBLIC_RELEASE_READY=NO` warning. That is an accurate statement of the tested candidate's current release state.

## Outstanding verification and known failures

The broader Windows pytest run produced:

**256 passed, 37 failed, 1 skipped** (294 total).

The failed modules include prior Dev20–Dev22 installation-script tests, RC5–RC7 UI-specific expectations, Unix/bash path assumptions under Windows, a Windows default text-encoding issue, external BiG-SCAPE test-command portability, and a historical RC7.7 manifest mismatch. A module-by-module provisional classification is recorded in [Beta 1 test failure triage](BETA1_TEST_FAILURE_TRIAGE.md). The precise release relevance of each must be assessed; some failures might represent genuine implementation or portability defects. Do not mark them all irrelevant without review.

An additional four-test CSS check initially produced 2 passed, 2 failed after installing `tinycss2`. The remaining failures require layout strings from older RC7.3/RC7.4 versions; a separate current-CSS structural check passed 5/5. Neither result alone establishes current UI usability or complete compliance.

**Open release gates:**

1. **Scientific acceptance:** Execute and inspect at least one legitimate bacterial genome through the claimed core workflow with appropriate tools, versions, complete databases, and resources; record outputs, integrity, failures and limitations.
2. **Test disposition:** Classify the 37 failures and resolve release-critical issues, explicitly retaining test exceptions and remaining known limitations.
3. **Installation acceptance:** Test a clean second Windows system or clearly disclose the unverified portability limitations if issuing a constrained preview.
4. **Dependency and distribution audit:** A [proprietary research-use license](../ACTINOSCOPE_RESEARCH_USE_LICENSE.md) has been documented; ensure the **downloadable package includes that license**, review third-party wheels/databases and their notices, and accept that a shipped Python wheel may reveal readable source. Review installer security and version-specific terms.
5. **Release packaging:** Prepare an appropriately named distribution artifact with complete instructions, build provenance and independent checksums. Avoid publishing a private test archive unchanged when its metadata says it is not publicly approved.

## Scientific capacity warning

The development WSL environment has been observed with approximately **1.82 GiB RAM and 1 GiB swap**. It is not adequate evidence for robust full-genome execution of memory-intensive workflows. Scientific acceptance on a higher-memory host is strongly preferable. Checking the mere presence of antiSMASH database files (approximately 9.4 GiB) is **not** a substitute for dependency/database preflight or execution.

## Ownership and affiliation

Software developer and author: **Imene Maallem**. Research affiliation: **FLORET Center for Advanced Genomics and Bioinformatics Research, Nigeria**. The developer has stated that ActinoScope is their work and FLORET is an affiliation. The affiliation is not an ownership or endorsement claim; relevant agreements and third-party rights still determine permissible redistribution. Public software license remains **undecided**.

## Decision

**NO-GO for a general-availability scientific installer as of this report.** Documentation is ready to support a carefully qualified future release. The software is usable as a **private Beta 1 test candidate** within its documented, verified limits. This report should be updated with concrete evidence before a public release is marked accepted.
