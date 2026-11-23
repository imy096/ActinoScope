# Install ActinoScope on Windows

**Status: Installation-test documentation; a public installer is not yet approved.**

## Beta 1 prerequisites

- 64-bit Windows and 64-bit Python 3.11 for the current preview installation kit.
- Sufficient storage for the program, dependency wheels and scientific databases.
- For genome annotation or BGC prediction, separately installed and configured WSL2/Ubuntu, Bakta, antiSMASH and the appropriate reference databases.
- Prefer at least **16 GB of physical RAM** for full genome analysis; exact needs vary by data and tools.

## Current private-preview installation workflow

1. Obtain the complete, approved **ActinoScope Beta 1 installation test kit** directly from the maintainer. The kit contains a launcher, application wheel, offline Python dependencies and an installation script.
2. Do **not** install from unverified sources or download only the EXE from an unknown website.
3. Install 64-bit Python 3.11 if not present.
4. Run `INSTALL_ACTINOSCOPE_BETA1.bat` as a normal user from the full kit folder.
5. Once installed, open **ActinoScope.exe** and click **Start ActinoScope**.
6. The local browser opens at `http://127.0.0.1:8501`. Only one running copy should use this port.
7. Configure the scientific WSL executables and reference databases for **your own computer** using Advanced settings. The test kit does not install them.

## What has and has not been verified

The private kit installed into an isolated environment and opened the interface on its development machine. It **has not yet passed a fresh clean-computer installation**. A complete end-to-end genome analysis on adequate RAM is also pending.

## Updating

Official later versions will be published by the maintainer. Back up local project data and follow version-specific release instructions. Do not replace installation files manually unless a trusted maintainer directs a documented fix.
