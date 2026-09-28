# MS-JEV-EXP-003 Session Preflight Checklist

## Objective
Run one frozen five-case formal evaluation set, preserve the raw evidence, then import the evidence into the existing M/S dashboard. No live scanning, exploitation, patching, containment, or production changes are performed.

## Prepare before the session
1. Keep the existing working Node project folder used for EXP-002 intact. It should contain `package.json`, `package-lock.json`, `node_modules`, and the installed `ai` SDK.
2. Save `experiment-003-five-cases-refined.mjs` into that same working Node project folder. Do not edit the frozen cases after the formal run starts.
3. Have the AI Gateway API key available, but do not paste it into the script or chat.
4. Confirm the final M/S Streamlit dashboard folder still exists and can be launched locally. No dashboard modification is needed before collecting EXP-003 evidence.
5. Close or pause unrelated terminals so it is obvious which PowerShell window contains the EXP-003 API key.
6. Have enough local disk space for a small evidence folder and ZIP archive; the experiment itself is tiny.

## Session start — no API calls
From the EXP-002 Node project folder:

```powershell
node experiment-003-five-cases-refined.mjs --dry-run
```

Review the five frozen case IDs, reference actions, and deterministic counterfactual G0/G1/G2 wiring.

Then configure the key in the SAME PowerShell session if needed:

```powershell
$env:AI_GATEWAY_API_KEY = (Read-Host "Enter your AI Gateway API key").Trim()
```

Run the environment preflight:

```powershell
node experiment-003-five-cases-refined.mjs --preflight
```

Proceed only if every preflight row is `true`. Preflight makes no API calls.

## Formal run — five JEV calls maximum

```powershell
node experiment-003-five-cases-refined.mjs --live
```

Rules:
- Do not edit the script after the run starts.
- Do not manually rerun a failed case until the saved error evidence is reviewed.
- Do not delete error records; collection failures are part of the execution history.
- Do not run a second full batch simply to obtain “cleaner” results.

## Immediately after the run
1. Locate the printed evidence path under `MS-JEV-EXP-003\<batch-id>`.
2. Preserve the entire batch folder unchanged.
3. Create a ZIP of that exact batch folder. Example:

```powershell
Compress-Archive -Path ".\MS-JEV-EXP-003\<batch-id>\*" -DestinationPath ".\MS-JEV-EXP-003-<batch-id>-Evidence.zip"
```

4. Upload/send the ZIP for interpretation and dashboard integration.
5. Keep the original folder and ZIP as immutable evidence copies.

## What the script already records
- Frozen evaluation plan and literature anchors before the first model call
- Frozen case/reference labels outside the model prompt
- One JEV response per case, no automatic retries
- Input/output/error JSON records with SHA-256 sidecars
- Observed-proposal G0/G1/G2 governance replay
- Predefined adversarial-counterfactual G0/G1/G2 replay
- Checkpoints after each attempted case
- Final summary and dashboard-ready summary JSON
- Timing, token usage, provider confidence/probability, and provider market-cost field when available

## Dashboard phase
Do not change the existing dashboard before the experiment. After the evidence ZIP is complete, import/extend the dashboard once, using the saved `dashboard-summary.json` and raw evidence. This keeps evidence collection separate from presentation code and avoids wasting time during the live run.
