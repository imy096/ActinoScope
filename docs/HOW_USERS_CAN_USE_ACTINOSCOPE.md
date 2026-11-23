# How researchers can obtain, install and use ActinoScope

**ActinoScope version in development:** `0.6.0.dev23` (Beta 1).  
**Availability today:** Public documentation only; the verified application archive is a **private test candidate**, not an approved public download.

If you arrived here looking for the program, please do not mistake the GitHub-generated `Source code (zip)` download for a Windows installation package. The development source is stored separately and privately, and no official public installer has been published.

## 1. How do I obtain ActinoScope?

**Now:** Read the [README](../README.md), [quick start](QUICKSTART.md), [technical requirements](INSTALL_WINDOWS.md), and [known limitations](IMPORTANT_WARNINGS.md). Private testing is coordinated by the maintainer; do not use unofficial binary copies.

**After an approved download is made available:** Open the repository's [Releases page](https://github.com/imy096/ActinoScope/releases), choose the latest release appropriate to your use case, expand **Assets**, and download the explicitly named **Windows installation ZIP** published by the maintainer. Check its version, installation instructions, SHA-256 checksum, release status (stable or pre-release), and known limitations. The auto-generated `Source code (zip)` and `Source code (tar.gz)` links are **not installers**.

A GitHub Release is a versioned download page with attached files; it is **not an online application**. ActinoScope runs on your computer.

## 2. Prepare your Windows computer

For the current **private test kit**, you need:

- 64-bit Windows.
- **64-bit Python 3.11**, normally installed from the official Python distributor, for the private installer script.
- Disk space for the app and isolated Python runtime: the current installer checks for **at least 750 MiB free at the target location**. Separate Linux scientific environments and databases require substantially more storage.
- For full bacterial genome annotation and BGC prediction: WSL2, an Ubuntu distribution, working scientific tools (for example Bakta and antiSMASH), and the correct reference databases. These are **not included** in the Windows ZIP.
- Adequate system resources. **16 GB RAM or more is recommended** as a planning baseline for many full-genome workflows, but actual needs vary greatly by tools, genome size, options and reference databases.

Do not interpret 'offline Python dependencies' as 'complete offline scientific analysis.' Upstream scientific tools can require separate downloads or setup, depending on their settings.

## 3. Install the current private test kit (invited testers only)

These instructions describe the **tested private candidate**, not a public download:

1. Obtain the complete `ActinoScope_Beta1_WinFix_Private_TestKit.zip` from the maintainer using an authorized private channel, together with its **ZIP-specific SHA-256 checksum**. The published application-wheel checksum does not serve as a ZIP checksum.
2. Confirm the archive checksum before extracting it; do not launch untrusted binaries.
3. Extract **all** files to an ordinary writable folder. Keep `ActinoScope.exe`, `install_runtime.py`, `INSTALL_PRIVATE_TEST.bat`, `wheelhouse`, and the integrity inventory together.
4. Ensure Python 3.11 64-bit is installed. Run **`INSTALL_PRIVATE_TEST.bat`** as your usual Windows user.
5. Successful installation prints `ISOLATED_IMPORTS=PASS`, `LATEST_UI_INSTALLED=YES`, and `CANDIDATE_INSTALL=PASS`. Installation failures must not be ignored.
6. The **unmodified private kit** installs to `%LOCALAPPDATA%\Programs\ActinoScope-Beta1-Candidate\ActinoScope.exe`. It deliberately refuses to overwrite an existing directory of that name. Do not delete an existing installation or research data without backing them up first.
7. Double-click the **installed** `ActinoScope.exe`. Use the launcher to start the local interface. When available, the local browser address is `http://127.0.0.1:8501`; this must stay on the local machine.

This private kit prints `PUBLIC_RELEASE_READY=NO` by design. It must **not** be represented as a fully validated public scientific release.

## 4. First use — a safe starting workflow

1. Start ActinoScope using the installed launcher and open the local browser interface.
2. Create a new project or select an existing one. Confirm the **actual project folder shown in the app** and arrange a backup for any valuable results. ActinoScope project files are not automatically synchronized to GitHub.
3. For an initial smoke test, use a **small, non-confidential bacterial FASTA example** whose provenance is known and for which you have permission. Select input validation/QC-only functions that the current build has tested.
4. Read the status and generated run manifest. Do not infer that Bakta, antiSMASH or optional analysis modules executed when they were disabled or configured only for dry run.
5. To attempt an advanced module, first configure WSL paths, executable versions, databases and appropriate resources. Test tool/database readiness separately. The current Beta 1 core scientific workflow **has not yet passed complete real-genome acceptance**.
6. Retain the genome accession/version, app version, tool/database versions, run parameters, output files and checksums before reporting results.

Predicted BGCs, enzymes or natural products are computational evidence only, **not experimentally verified discoveries**.

## 5. Troubleshooting

| Symptom | What to check |
| --- | --- |
| `ERROR=Install 64-bit Python 3.11 first` | Confirm that the correct Python 3.11 64-bit version is installed and accessible to CMD. |
| `Candidate already installed; will not overwrite` | This candidate deliberately protects existing installations. Preserve the old directory; consult the maintainer for an approved upgrade or separate test. |
| `CANDIDATE_INSTALL=FAIL` | Inspect the reported error and ensure the complete, unmodified ZIP is extracted; do not continue as though installation succeeded. |
| Browser fails to open or local port unavailable | Close existing ActinoScope instances. The default `127.0.0.1:8501` may be occupied by another process. |
| Bakta / antiSMASH / GECCO not found | The ZIP does not bundle these Linux tools; check WSL2 Ubuntu, selected environments, paths and external databases. |
| Tool responds to `--version` but analysis fails | Version detection is **not** proof that scientific databases are complete, compatible or that a run will fit in RAM. |
| Very slow performance / terminated scientific job | Examine available RAM, swap, genome size, output storage and relevant tool logs. Do not repeatedly retry a large run on an insufficient machine. |
| Unexpected scientific result | Preserve run files and logs, compare against established references, and seek independent biological validation before drawing conclusions. |

For private reports, share **sanitized** logs only; never post confidential genomic data, user directory paths, passwords or API tokens to public GitHub Issues. See [Support](../SUPPORT.md) and [Security](../SECURITY.md).

## 6. What is not yet guaranteed?

- Successful fresh-genome Bakta → antiSMASH → downstream scientific acceptance.
- Reliable use on every Windows PC or WSL2 distribution.
- All optional modules, data resources or scientific algorithms.
- Validated enzyme activity, antimicrobial efficacy or chemical structure.
- Clinical, diagnostic, regulatory or safety-sensitive interpretations.

See the full [verification status](RELEASE_READINESS.md) and [warnings](IMPORTANT_WARNINGS.md).
