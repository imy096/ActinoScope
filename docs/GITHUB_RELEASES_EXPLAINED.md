# What is a GitHub Release, and how will researchers download ActinoScope?

## A GitHub repository and a GitHub Release are different

- **Repository:** The project's public landing page, documentation, release history and links. This repository does **not** include the private development source or a downloadable installer today.
- **GitHub Release:** A dated, versioned page associated with a Git tag, with release notes and optional downloadable **Assets** such as a Windows installation ZIP.
- **Release asset:** The **actual file** the maintainer uploads (for example an approved Windows ZIP). An asset is not automatically generated from the software currently installed on the maintainer's computer.
- **Source code (zip) / Source code (tar.gz):** GitHub automatically provides snapshots of the **public repository content** for a tag. Because this public repository primarily contains documentation, those downloads **are not ActinoScope installers**.

## What will a researcher do once a release is published?

1. Visit https://github.com/imy096/ActinoScope.
2. Open **Releases**, or go directly to https://github.com/imy096/ActinoScope/releases.
3. Select the appropriate software version and read its **pre-release** or general-availability label, prerequisites, known limitations and supported functions.
4. Under **Assets**, download the **explicitly labeled Windows installation archive**. Do **not** select the auto-generated source-code archive by mistake.
5. Verify the archive SHA-256 against the checksum in that specific release.
6. Extract all files, follow the **matching version-specific** installation instructions, and configure any separately required WSL scientific tools and reference databases.
7. Launch the locally installed ActinoScope application. A GitHub Release does **not** make ActinoScope available as an online website.

## Is ActinoScope already downloadable through Releases?

**No public installer has been approved or published as part of this Beta 1 preparation.** A private local candidate exists on the developer's Windows machine. Merely updating the README or release-note draft does not attach that archive or create a public Release.

## What must the maintainer do to publish a real release?

When a scientifically and legally appropriate distribution artifact has been prepared:

1. Prepare and approve the final ZIP, its **own** SHA-256 checksum, and an installation/test report.
2. Select a public software license and complete a third-party dependency and data-license review.
3. From the GitHub repository, open **Releases → Draft a new release** (GitHub interface wording can evolve).
4. Choose/create an appropriate tag such as `v0.6.0-beta.1` **only after** final version decisions and release acceptance. Use a clear title and the final, evidence-based release notes.
5. Attach the **actual ZIP** under release assets and publish its SHA-256 checksum with it. The source code does not have to be made public merely to attach an asset, although installed Python wheels can contain inspectable source.
6. Mark it **Pre-release** when releasing an experimental beta whose limits are clearly disclosed. Do not mark a beta as fully validated or stable unless that claim is justified.
7. Verify the newly published download link, archive checksum and clean installation procedure on the intended target platform.

**Publishing a Release is a distribution action**, not just a documentation edit. Do not upload the verified **private-test ZIP unchanged** as a general public release when its installer expressly prints `PUBLIC_RELEASE_READY=NO` and essential scientific acceptance remains outstanding.

## Can a researcher evaluate ActinoScope today?

Researchers can study the documentation, scientific scope and limitations now. Selected invited testers may obtain the private candidate directly from the maintainer and follow its private-test instructions, but general public users currently have no official installer to download.

Read [How researchers use ActinoScope](HOW_USERS_CAN_USE_ACTINOSCOPE.md), [Warnings](IMPORTANT_WARNINGS.md), and [Release readiness](RELEASE_READINESS.md).
