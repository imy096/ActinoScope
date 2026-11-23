# ActinoScope Beta 1 — Windows installation and prerequisites

**Version:** `0.6.0.dev23`  
**Status:** Documentation for the **verified private test candidate**. No installer is available publicly yet.

## Requirements

- 64-bit Windows.
- **64-bit Python 3.11**, accessible as `py -3.11` or `python`, to run the current private installation kit.
- Free disk space for the isolated Python runtime, application, and any separately installed scientific environments. The candidate installer checks for at least **750 MiB free** at the installation location; scientific databases need much more space.
- For scientific annotation or BGC analysis, **WSL2 with Ubuntu** plus independently configured scientific executables and databases, as relevant (for example, Bakta, antiSMASH, GECCO).
- **16 GB or more RAM is recommended** when attempting whole-genome annotation/BGC analysis; actual resource requirements depend on genome, selected algorithms, tools and databases. The low-memory development PC is **not** a basis for claiming full-genome performance.

The offline Python wheels do **not** contain scientific Linux programs or their reference databases.

## Exact procedure for the current private candidate

Only use a complete test kit supplied directly by the maintainer. Keep all extracted files in a single folder. The currently verified archive is identified privately as `ActinoScope_Beta1_WinFix_Private_TestKit.zip`; it is **not** a public downloadable release.

1. Verify that the archive came from the maintainer and that the maintainer-provided SHA-256 checksum matches. Extract the complete archive.
2. Install 64-bit Python 3.11, if needed.
3. Close any previous ActinoScope instance that might use the local web port.
4. In the extracted folder, run **`INSTALL_PRIVATE_TEST.bat`** as your usual Windows user (not the obsolete filename `INSTALL_ACTINOSCOPE_BETA1.bat`).
5. Look for `ISOLATED_IMPORTS=PASS`, `LATEST_UI_INSTALLED=YES` and `CANDIDATE_INSTALL=PASS`.
6. The candidate targets `%LOCALAPPDATA%\Programs\ActinoScope-Beta1-Candidate\ActinoScope.exe`. The script deliberately refuses to overwrite an existing installation at that location.
7. Launch `ActinoScope.exe` and use the local interface. A browser may connect to `http://127.0.0.1:8501` if that port is available. It must remain a local-only service.
8. Configure WSL, the individual scientific tools, database paths, and any optional modules for the destination computer. These are **not installed by the candidate kit**.

**Installation warning:** The private script's `PUBLIC_RELEASE_READY=NO` status is intentional. Do not remove or disregard this warning to market the build as a validated public release.

## Verification scope and known limitations

The candidate built and installed successfully on the development machine, and its launcher/interface were checked. The 37 Python wheels passed integrity checks. The Windows process manager check passed. However:

- A **clean second Windows PC** has not yet passed installation acceptance.
- Full new-genome scientific execution and database prerequisite validation are incomplete.
- The full pytest suite reported **37 failures** out of 294 outcomes; release-critical defects and historical tests still need triage.
- Optional scientific tools and databases may be large, memory-intensive, or separately licensed.

## Security and support

Keep the local browser bound to loopback, do not expose the Streamlit port to the internet, and avoid confidential genome input on shared machines without appropriate controls. Check [security guidance](../SECURITY.md) and [release readiness](RELEASE_READINESS.md). Neither a private repository nor a compiled launcher guarantees that the installed Python code cannot be inspected.
