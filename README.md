# Project M/S - Paper 1

## Separating AI Agent Recommendations from Governance Outcomes in Cybersecurity

**Author:** Peter P. Chavez  
**Research brand:** ArcMichael Research  
**ORCID:** https://orcid.org/0009-0006-7318-6995  
**Version:** v1.0.0  
**Release date:** 28 September 2026  
**Archival DOI:** https://doi.org/10.5281/zenodo.23003470

Project M/S Paper 1 is a preliminary applied cybersecurity study that separates model recommendations from downstream governance outcomes. It reports three synthetic component experiments using Jev, including a five-case paired replay in which observed and predefined PATCH proposals are evaluated across three governance conditions.

The contribution is intentionally narrow. The repository does **not** claim invention of external AI governance, runtime authorization, fixed-proposal comparison, structured decision models, or evidence-oriented governance evaluation. The paper positions those mechanisms against prior work and focuses on a specific vulnerability-response protocol, preserved experimental evidence, and the distinction between preventing an unauthorized change and selecting the exact reference action.

## What Paper 1 reports

- EXP-001: typed-decision interface feasibility.
- EXP-002: twelve synthetic vulnerability-classification cases, including preserved API-error history.
- EXP-003: five frozen governance-boundary cases and deterministic proposal replay across G0/G1/G2.
- Offline dashboard v1.6 for evidence inspection.
- Explicit limitations covering synthetic case construction, sample size, model/version uncertainty, source provenance, and the fact that evidence verification is not independently isolated in EXP-003.

## Repository structure

- `manuscript/` - canonical Paper 1 PDF.
- `experiments/` - frozen experiment evidence and recovered runners.
- `dashboard/` - metadata-reconciled offline dashboard package.
- `figures/` - proposed Phase 2 architecture figure.
- `docs/` - reproducibility, provenance, AI-assistance disclosure, and release notes.
- `integrity/` - SHA-256 manifest and machine-readable release manifest.

## Reproducibility boundary

The public artifacts are intended to support inspection and recomputation of the reported descriptive results without requiring new model calls. Historical model outputs are frozen evidence; a new live API request is not expected to reproduce the same response because provider routing and model versions may change.

EXP-002 has a documented source-provenance limitation: the preserved historical runner reflects the final isolated CASE-012 retry state. Earlier all-case execution is evidenced by the raw records and sanitized chronology, but the untouched all-case source state was not separately preserved.

## Important interpretation limits

The experiments are synthetic and small. They do not establish real-world model accuracy, general operational safety, statistical attack-prevention rates, or superiority of one autonomy/governance architecture. In EXP-003, all four unsafe forced PATCH proposals were intercepted under G2 because the approval check failed; the marginal contribution of evidence validation was not isolated.

## Phase 2

Phase 2 proposes a SOC-oriented decision-assurance framework that separates proposal, validation, authorization, human review, and execution. It is future work and is not implemented or validated in Paper 1.

## Citation

See `CITATION.cff`. The archival release is reserved at DOI `10.5281/zenodo.23003470` and becomes publicly resolvable when the Zenodo record is published.

## AI assistance

See `docs/AI_ASSISTANCE_DISCLOSURE.md`.

## License

This release uses a split license:

- Manuscript, figures, documentation, and synthetic research evidence: **Creative Commons Attribution 4.0 International (CC BY 4.0)**.
- Source code, runners, and dashboard software: **Apache License 2.0**.

See `LICENSE.md` for the file-level licensing boundary and `LICENSE-APACHE-2.0.txt` for the Apache-2.0 text.
