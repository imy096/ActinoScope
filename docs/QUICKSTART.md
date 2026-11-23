# ActinoScope quick start

1. Open the official ActinoScope launcher and click **Start ActinoScope**.
2. Select **Start Analysis**, then **Upload my genome FASTA**.
3. Upload a bacterial genome assembly, e.g. `.fna`, `.fa`, `.fasta` or supported compressed form.
4. Enter a project name and strain identifier.
5. Choose analysis modules. The raw-genome pathway uses **Bakta** annotation; **antiSMASH** can predict BGCs. Other modules require their own configured dependencies.
6. Set CPU threads according to available hardware and verify external command and database paths for your computer.
7. Check resource requirements before any full execution. The current Beta 1 has only passed **dry-run planning** on a separately downloaded real bacterial genome, not complete new-genome scientific execution.
8. Review run manifests, files, evidence summaries and status reports. Keep source assembly accession, software versions, parameters and database versions for reproducibility.

**Interpret results carefully:** enzyme assignments, BGC boundaries and natural product suggestions are computational candidates, not laboratory confirmation.
