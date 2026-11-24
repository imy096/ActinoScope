# ActinoScope Beta 1 — broad-suite failure triage (provisional)

**Reference run:** Windows, Python 3.11, `pytest -q -rs`, 23 November 2026  
**Reported outcome:** **256 passed, 37 failed, 1 skipped** (294 total)  
**Status:** This is a triage document, **not evidence that the 37 failed tests have passed**.

## Overview of the 37 failures

| Group | Modules | Failed tests | Interpretation | Next action |
| --- | --- | ---: | --- | --- |
| Historic Dev20–Dev22 installation tests | `test_dev20_windows_short_venv_hotfix.py` (3), `test_dev21_windows_score_hotfix.py` (2), `test_dev22_release.py` (4) | **9** | Many require obsolete *.bat and config examples not included in the private source snapshot. Their applicability to the current candidate must be explicitly decided. | Preserve the historical tests; inspect whether the missing files are intended to be archived and compare current installer acceptance separately. |
| Prior RC5–RC7 UI tests | `test_rc5_approved_layout.py` (1), `test_rc6_responsive_sidebar.py` (2), `test_rc7_1_targeted_refinement.py` (2), `test_rc7_2_visual_guardrails.py` (3), `test_rc7_3_focused_header.py` (3), `test_rc7_4_final_header_sidebar.py` (3), `test_rc7_5_stable_editorial_shell.py` (1), `test_rc7_6_sidebar_editorial_type.py` (1), `test_rc7_7_botanical_motion.py` (2) | **18** | Includes old CSS/header expectations, old splash slogans, missing historical BAT/README files, Windows default-encoding issues, and a historical RC7.7 manifest checksum mismatch. Not all failures imply a current UI defect. | Maintain historical tests for provenance; write current Beta 1 tests for live UI behavior and accessibility without blindly weakening guardrails. |
| Shell/WSL helper tests on native Windows | `test_discovery_installer.py` (5), `test_preflight_scripts.py` (2) | **7** | Several use `bash` with native `C:\...\` paths; some shell helpers are absent from the source snapshot. | Test from Linux/WSL with correct POSIX paths; verify files intended for the current distribution; separately test current WSL integration. |
| Optional BiG-SCAPE subprocess tests | `test_bigscape.py` (2), `test_bigscape_project_integration.py` (1) | **3** | Tests use executable `#!/usr/bin/env python3` mock scripts that do not launch the same way on native Windows. One result is a failed executable probe. | Make mock execution portable (e.g. explicit Python interpreter) and retest before calling optional module supported. |

**Total: 9 + 18 + 7 + 3 = 37.**

## Completed checks that narrow the scope

1. The restored `prepare_bakta_overlay.py` and `create_ma15_bakta_lowmem_config.py` helper scripts passed **10/10** targeted tests.
2. Installing the previously missing `tinycss2` library removed a dependency blocker. In a follow-up four-test selection, **2 passed and 2 still failed** on the exact old header CSS expectations.
3. A *current* stylesheet structural check passed **5/5** criteria: CSS syntax, responsive rules, header, sidebar, and reduced motion.
4. Current `app.py`, `visual_style.py`, and stable CSS files all matched the verified **Beta 1 application wheel** byte-for-byte. The historical RC7.7 checksum manifest was preserved; a new Beta 1 UI provenance manifest was recorded privately.
5. A Windows running-process probe passed, with no unwanted process termination.
6. The tested private ZIP contained **37** Python wheels whose SHA-256 hashes matched the package inventory.

These observations **do not mean 37 failures are fixed or irrelevant**. They narrow the likely causes and show which current-build checks have independently passed.

## Release-critical gates still open

| Gate | Required evidence | Current disposition |
| --- | --- | --- |
| Core scientific execution | Real, openly documented bacterial genome processed with the intended annotation/BGC toolchain, validated databases, run manifest and inspected outputs | **Not accepted**; synthetic QC and dry run only |
| Current UI acceptance | Startup, navigation, import, run submission, status, results, and error cases on the actual packaged version | **Partially tested** |
| Native Windows / WSL integration | Proper WSL path handling, error reporting, tool/database readiness, safe subprocess lifecycle | **Partial**; test cases require repair |
| Installer portability | Installation on an independent clean 64-bit Windows system including prerequisites and recovery | **Not accepted** |
| Optional modules | Correct execution or explicit disablement of unverified optional integrations, including BiG-SCAPE | **Not accepted** for all modules |
| Distribution security | Review package contents for inadvertent data/credentials, dependency license audit, unsafe exposure of local service, and relevant vulnerabilities | **Pending final audit** |
| Research-use license | License included in the downloadable package and accepted as appropriate for the intended distribution | **Policy published; packaging in preparation** |

## Release strategy

A public **experimental** pre-release, if the maintainer decides to issue one, must clearly state that scientific end-to-end acceptance, clean-PC acceptance and some automated tests remain incomplete. It must not be labeled as validated, stable or a complete reproducible scientific result.

Before publishing that pre-release, verify the actual new archive, inspect the bundled third-party licenses, and test the modified installer in a separate installation directory. The existence of a Python wheel may expose readable source even when the development GitHub repository remains private. Maintain a clear versioned record of accepted and unverified functionality.

**No scientific result, benchmarking figure or Q1 publication claim should be derived from these local software smoke checks alone.**
