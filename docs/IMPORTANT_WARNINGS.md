# Important warnings, limitations and responsible research use

**Release state:** ActinoScope Beta 1 `0.6.0.dev23` is a **private test candidate**. Public documentation is available, but a public installer has **not** been released. Read this page before testing or interpreting any computational output.

## Scientific interpretation — not experimental confirmation

- ActinoScope is a **research software workspace**. Predicted genes, annotation functions, biosynthetic gene clusters (BGCs), enzyme classifications and natural-product connections are **hypotheses** informed by algorithms and databases. A prediction is not proof of gene expression, biological activity, actual metabolite production, molecular structure or discovery of a novel compound.
- Absence of a BGC prediction **does not establish absence** of a biosynthetic pathway. Genome assembly quality, databases, software version and thresholds influence results.
- Comparisons across strains or with other tools must use consistent parameters and document differences in tool/database versions.
- **Not for medical diagnosis, clinical decision-making, pathogen surveillance decisions or other safety-critical applications.** Independent scientific and, where applicable, laboratory validation is required.

## Validation limitations of the current candidate

- Windows build/installation, local graphical interface, a synthetic FASTA QC-only workflow, and private package integrity have been tested on the development machine.
- A full **new real-genome annotation and antiSMASH BGC run** has not been accepted end to end; large antiSMASH database directories were found but their completeness and compatibility remain unverified by complete scientific acceptance.
- Full Windows test suite: **256 passed, 37 failed, 1 skipped**. Some failures concern historical test files and Windows/Linux differences; their release relevance has not all been resolved. Do not treat this as an all-green test report.
- The package has **not** passed a clean-PC installation acceptance test or independent validation on other hardware.
- The candidate installer explicitly reports `PUBLIC_RELEASE_READY=NO` and is not approved for public use as a general-availability scientific distribution.

## Hardware and storage risks

- Extensive annotations and BGC prediction can require substantial physical memory and **many gigabytes** of reference databases. For planning, 16+ GB RAM is recommended for many full-genome workflows; some analyses may need more.
- Analysis may slow dramatically, fail, use swap, fill disks, or leave partial outputs if insufficient resources are available.
- Keep ample free storage **beyond** the private installer's initial 750 MiB local-installation check. That check is not an estimate of scientific database size.
- Record failures and partial outputs instead of interpreting incomplete analysis as a completed result.

## Installation, privacy and security

- Download only approved versioned artifacts from the [official Releases page](https://github.com/imy096/ActinoScope/releases) **once an actual release exists**. The GitHub-generated `Source code (zip)` download is not a Windows application installer.
- Check the **exact downloaded artifact's** SHA-256 against the maintainer-published checksum. Never substitute a Python-wheel checksum for the ZIP checksum.
- The user interface starts as a **local web application**, normally on `127.0.0.1`. **Do not publish the local port on the internet** or expose it through public networking/tunnelling.
- Treat genomic sequences, local project metadata and results as potentially sensitive. Do not upload confidential data to public issues, screenshots, third-party services or shared cloud folders without permission.
- Keep backups of valuable outputs. Installation, updates and failed scientific jobs may create files or leave partial states; examine output manifests and run statuses.
- A local UI does **not** prove all third-party scientific tools operate without internet access. Verify each tool's network and data-handling behavior separately.
- No public code-signing certificate or official installer signature is claimed for the current private candidate.

## Third-party software and licensing

- Windows ZIP dependencies are **not** the same as the Linux scientific stack. WSL Ubuntu, Bakta, antiSMASH, GECCO and their databases must be configured separately according to the chosen workflow.
- External scientific software and reference data have independent licenses, citation requirements and redistribution constraints. Not all tools/databases can be bundled or redistributed by ActinoScope.
- The ActinoScope developer is **Imene Maallem**; FLORET Center for Advanced Genomics and Bioinformatics Research, Nigeria is the stated **research affiliation**. Affiliation alone does not establish ownership or endorsement.
- An ActinoScope distribution license has **not** yet been published. Do not assume public availability of documentation grants permission to redistribute the software, copy the source or commercialize it.

## Reporting research with ActinoScope

For a scientifically interpretable result, retain:

- Genome accession, version and assembly-quality notes.
- ActinoScope version / build identifier.
- Command-line tool versions, enabled modules, configurations and thresholds.
- Database identity, version and date.
- Run manifests, warnings, errors, file hashes and output paths.
- Independent controls or comparator analyses, where relevant.

**Beta testing is not scientific certification.** Report observed results and failures transparently. Consult [release readiness](RELEASE_READINESS.md) for the actual verification evidence and [support](../SUPPORT.md) for safe bug reports.
