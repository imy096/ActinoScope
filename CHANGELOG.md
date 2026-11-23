# ActinoScope changelog

## Beta 1 — `0.6.0.dev23` (private candidate; not publicly released)

- Built an isolated Windows local application test kit with a C# launcher, ActinoScope application wheel and offline Python dependency wheels.
- Integrated the Botanical Motion RC7.7-based interface with subsequent Beta 1 startup, header and loading refinements.
- Corrected Windows running-process detection/job management and passed its targeted regression checks.
- Verified installed Python imports, UI startup, ZIP integrity, all 37 wheels and current UI source/wheel correspondence.
- Tested a synthetic FASTA QC-only workflow and project dry-run behavior.
- Recorded results of the complete Windows test suite: **256 passed, 37 failed, 1 skipped**.
- Confirmed WSL tool presence and large antiSMASH database folders; full real-genome scientific workflow acceptance remains outstanding.
- Maintained source history and UI provenance in the private repository.

### Pending before general availability

- Classify and resolve release-critical failures.
- Accept a real bacterial genome through the claimed full workflow with suitable hardware.
- Validate scientific reference databases and external integrations sufficiently for the documented workflow.
- Test a clean Windows installation.
- Finalize licensing, third-party dependency notices and public release checksums.
- Create an actual GitHub Release; no public installer or DOI is claimed at this stage.

See [Beta 1 release-readiness record](docs/RELEASE_READINESS.md) and [draft notes](docs/BETA1_RELEASE_NOTES_DRAFT.md).
