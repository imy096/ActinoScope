# ActinoScope

**From bacterial genomes to enzymes and natural products**

ActinoScope is a **local-first research workspace** for organizing bacterial genome analyses, validating sequence inputs, exploring biosynthetic gene cluster (BGC) and enzyme-related evidence, and reviewing reproducible computational outputs. Its Windows launcher starts a local Python/Streamlit interface; scientific analyses depend on separately configured command-line tools, reference databases, and suitable hardware.

> **Status — Beta 1 private test candidate, version `0.6.0.dev23`. No public installer or general-availability release has been published.** This public repository hosts documentation and release information; development source is kept in a separate private repository.

## Current evidence

- Windows launcher, local graphical startup, isolated install and a corrected Windows job/process probe passed development-machine tests.
- A 37-wheel offline Python package passed ZIP integrity and individual wheel checksum verification.
- Three current user-interface source files matched the application wheel byte-for-byte.
- A synthetic, small-genome **QC-only** execution and a scientific dry run passed.
- The broader test suite reported **256 passed, 37 failed, 1 skipped**. The failures include historical UI/installer expectations and Windows/WSL portability, and remain to be classified or resolved.
- WSL tool versions and large antiSMASH database component directories were detected, but **a complete fresh-genome Bakta-to-antiSMASH run has not passed scientific acceptance**, and database readiness has not been established by complete tool preflight.
- Installation on a second clean Windows computer is still unverified.

These results demonstrate partial functional readiness, **not** general scientific validity, support for every optional tool, or release approval.

## Documentation

- [Windows installation requirements and private-test procedure](docs/INSTALL_WINDOWS.md)
- [Quick start and checked workflows](docs/QUICKSTART.md)
- [Scientific scope, evidence, and limitations](docs/SCIENTIFIC_SCOPE.md)
- [Beta 1 release-readiness checklist](docs/RELEASE_READINESS.md)
- [Beta 1 release-note draft](docs/BETA1_RELEASE_NOTES_DRAFT.md)
- [Software dependencies and licensing considerations](docs/DEPENDENCIES_AND_LICENSING.md)
- [Citation status](docs/CITATION.md)
- [Security](SECURITY.md) · [Support](SUPPORT.md) · [Changelog](CHANGELOG.md)

## Download and release policy

**There is no approved public installer to download here yet.** Do not download or redistribute development binaries from unofficial sources. A public release requires a distributable installer or test-kit archive, accurately documented prerequisites, a third-party license review, release-critical acceptance evidence, and published checksums. The GitHub *Releases* section will be updated only when a release has actually been created.

The developer is **Imene Maallem**. The stated research affiliation is **FLORET Center for Advanced Genomics and Bioinformatics Research, Nigeria**; affiliation alone does not imply institutional ownership or endorsement.

## Research integrity

Genome annotations, predicted BGCs, enzyme assignments, and natural-product hypotheses are **computational outputs**, not demonstrated biochemical activities or experimentally confirmed compounds. Researchers must report the input assembly, software versions, tool options, reference databases, and evidence limitations. ActinoScope is **not for clinical or diagnostic use**.

**License status:** A public distribution license for ActinoScope has not yet been selected or published. The absence of a license does not grant unrestricted reuse or redistribution.
