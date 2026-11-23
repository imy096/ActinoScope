# ActinoScope Beta 1 — quick start

**Current status:** Private Beta 1 test candidate. Not a public general-availability release.

1. Install the **complete** private test kit following [Windows installation instructions](INSTALL_WINDOWS.md), then open the installed `ActinoScope.exe`.
2. Start the local analysis interface; keep the browser connection local.
3. Create or choose a project, then supply a bacterial genome FASTA assembly (`.fna`, `.fa`, or `.fasta`, as supported by the selected input path).
4. Record the organism, strain, assembly accession/version, origin and metadata. Prefer assemblies with known provenance and appropriate permission for your research.
5. Validate the genome input. A small **QC-only** example and dry-run planning were successfully tested on the development machine; they do not establish full scientific pipeline acceptance.
6. Before selecting annotation or BGC analysis, ensure WSL Ubuntu, Bakta, antiSMASH, relevant databases and any other chosen tools are installed and correctly configured. Check actual available RAM and disk space.
7. Review the run status, generated files and manifests; retain software versions, parameters, database versions and checksums with each analysis.
8. Treat BGCs, enzymes and compound associations as **computational hypotheses**, not biochemical confirmation.

## Not yet validated

A complete **new bacterial genome → Bakta annotation → antiSMASH output → downstream ActinoScope review** execution has not been fully accepted on suitable hardware, and independent clean-PC installation remains pending. Optional discovery and comparison modules have different prerequisites and verification states.

For a complete evidence summary and restrictions, read [scientific scope](SCIENTIFIC_SCOPE.md) and [release readiness](RELEASE_READINESS.md).
