# Reproducibility Notes

## Scope
Paper 1 reports three synthetic component experiments. The public package preserves the evidence used for the reported descriptive results and the recovered historical runners where available.

## EXP-001
The archive contains three run records: one successful response and two API errors. It demonstrates the typed-decision recording path and is not an accuracy or governance-effectiveness experiment.

## EXP-002
The archive contains 25 run records: 12 successful responses and 13 API-error records. The binary confusion matrix excludes the single UNCONFIRMED case.

### Source-provenance limitation
The preserved historical runner is the final CASE-012-only retry state. Evidence timestamps and sanitized execution chronology support the earlier all-case rerun and isolated CASE-012 retry, but the untouched all-case source state was not separately preserved. Any reconstructed all-case runner must be labeled as reconstructed and compared against the frozen evidence.

## EXP-003
The formal batch contains five model requests. The observed proposal from each case and a predefined PATCH counterfactual are replayed across G0, G1, and G2 without additional model calls. The exact historical runner `experiment-003-five-cases-refined.mjs` is included.

The preserved evaluation plan records Node.js v24.21.0. Release verification identified AI SDK `ai@7.0.114`; the recovered runner requires Node.js 22 or later.

## Timing caveat
Local experiment intervals are not end-to-end SOC latency or pure inference time. EXP-003 CASE-001 contains timestamps originating from different clock sources; those clocks must not be subtracted from one another. Paper 1 therefore reports the locally recorded elapsed interval only.

## Hashes
`integrity/SHA256SUMS.txt` contains hashes for the public release files. Historical per-record sidecars remain inside the experiment archives.

## New live calls
A new API run is a new experiment. It should not overwrite or be presented as a reproduction of historical model responses.
