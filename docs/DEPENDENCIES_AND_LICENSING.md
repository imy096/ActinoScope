# ActinoScope — dependencies, licenses and redistribution guidance

**Status:** Distribution-readiness checklist for an unpublished private Beta 1 candidate.

## Software distribution is not the same as installation

The currently tested ZIP contains the Windows launcher, an ActinoScope Python wheel, 36 dependency wheels, installation scripts and hash metadata. It **does not** bundle WSL2 Ubuntu, the Linux scientific executables, or their large scientific reference databases.

These scientific resources are typically installed separately by users or provisioned by institutional infrastructure.

## External components to review

| Component | Role | Check before public release |
| --- | --- | --- |
| Python 3.11 | Runtime used for isolated Windows installation | Supported platform and redistribution claims |
| Streamlit | Local browser UI | Version, license notices and vulnerabilities |
| Biopython, NumPy, pandas, PyArrow, Pillow, PyYAML, etc. | Application dependencies | Exact wheel inventory, source/license notices and security review |
| Bakta | Bacterial genome annotation | Correct executable, compatible database release and tool/database licensing |
| antiSMASH | BGC analysis | Correct version, prepared databases, and third-party data/licensing requirements |
| GECCO | BGC analysis option | Environment, tool and data licensing |
| BLAST+, MMseqs2, MAFFT, IQ-TREE2, HMMER | Comparative analysis and homology tools | Tool compatibility, licenses and dataset provenance |
| BiG-SCAPE | Optional BGC family grouping | Optional installation and scientific acceptance; not part of the validated core |
| C# Windows launcher | Opens local application | Provenance, runtime dependencies and signing/reputation checks |

**This is an audit checklist, not a declaration that any specific component or its data may be redistributed.** Check actual license files/version-specific conditions from the corresponding upstream publishers. Do not assume research-use availability automatically permits bundling, repackaging or commercial distribution.

## ActinoScope licensing

The developer identifies **Imene Maallem** as author and FLORET Center as a **research affiliation**, not necessarily owner. The desired license for ActinoScope has **not been selected** in this repository. The absence of a public `LICENSE` file is deliberate until the maintainer selects an appropriate license and verifies redistribution rights. Do not describe the software as open source in the meantime. Public documentation does not imply permission to redistribute the proprietary or unpublished Python implementation.

If distributing only a binary installation kit, remember that Python wheels can contain readable source; a private GitHub repository alone is not a source-code protection mechanism.

## Release audit

Before release:

1. Establish author/ownership details and any applicable contractual restrictions.
2. Choose the software license and specify what artifacts it covers.
3. Capture a complete Software Bill of Materials (SBOM) and licenses for the **exact** shipped versions.
4. Verify external tool/database licenses and make clear whether users must obtain them independently.
5. Verify checksum and malware/security inspection of final package.
6. Verify accurate public instructions, limitations and support policy.

See [Release readiness](RELEASE_READINESS.md) and [Windows installation](INSTALL_WINDOWS.md).
