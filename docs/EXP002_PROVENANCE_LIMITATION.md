# EXP-002 Provenance Limitation

The preserved EXP-002 runner reflects the final isolated CASE-012 retry state. Earlier all-case execution is supported by the raw input/error/output records and sanitized execution chronology. The untouched pre-retry all-case source state was not separately preserved.

This limitation affects source-level historical reconstruction, not the count of preserved successful responses and error records reported in Paper 1.

Do not describe a future reconstructed all-case runner as the original historical runner. If one is provided, label it clearly as `RECONSTRUCTED_EXP002_ALL_CASES_RUNNER` and compare it against the frozen evidence.
