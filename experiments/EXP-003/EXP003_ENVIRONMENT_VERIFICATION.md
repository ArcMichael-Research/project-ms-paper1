# EXP-003 historical runner and environment verification

Status: RESOLVED. No reconstruction is required.

Verified on 2026-09-26 from the user's historical Windows workspace:

- Historical runner: `experiment-003-five-cases-refined.mjs` (27,416 bytes in the inspected workspace).
- Runner contains the five frozen EXP3 cases, predefined PATCH counterfactuals, permissions/approval/evidence fixtures, G0/G1/G2 definitions, deterministic replay logic, and assertions.
- `package-lock.json` records AI SDK `ai@7.0.114`, including resolved package and integrity metadata.
- The frozen evaluation plan records Node runtime `v24.21.0`; the runner preflight requires Node >= 22.
- Frozen EXP-003 evidence remains `MS-JEV-EXP-003-Paper1-Evidence.zip`.

Release handling:
- Preserve the runner and evidence as historical originals.
- Do not silently regenerate or modernize the runner for the Paper 1 release.
- The package-lock file remains in the user's historical local workspace; screenshots in this handoff document the exact dependency/version verification.
