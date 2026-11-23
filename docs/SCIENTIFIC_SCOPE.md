# Scientific scope and validation status

ActinoScope integrates local project organization with scientific analysis tools and evidence readers. Depending on configured dependencies, workflows can use Bakta, antiSMASH, GECCO, HMMER and Pfam-related resources.

### Successfully checked in the current development process

- Native Windows launcher and Botanical Motion RC7.7 interface startup.
- Independent Python wheel build, integrity checks, and isolated local runtime installation.
- Project input handling and raw bacterial-genome FASTA upload.
- WSL tool detection and path conversion for a configured Bakta reference database.
- Synthetic FASTA and NCBI *Micrococcus luteus* NCTC 2665 workflow dry-runs.
- Read-only inspection of historical project manifests and reports.

### Outstanding acceptance tests

- Complete execution of Bakta and antiSMASH on a newly supplied genuine bacterial genome using suitable hardware.
- Review of actual newly generated GenBank, BGC predictions, reports, provenance and scientific interpretation.
- Independent clean-Windows installation and dependency setup.
- Security, third-party license and distribution audit.

A successful **dry-run** demonstrates planned workflow construction and input checks, **not** that annotation or BGC algorithms successfully executed. Historical manifests represent existing research evidence and should not be presented as independent validation of any new input.

**Not for clinical or diagnostic use.** Treat computational outputs as hypotheses requiring appropriate scientific validation.
