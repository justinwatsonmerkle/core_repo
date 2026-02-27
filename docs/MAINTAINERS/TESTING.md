# Testing regime (Framework)

LastUpdatedUTC: 2026-02-27T00:00:00Z

Purpose: prevent regressions and ensure the system behaves as intended.

## Layer 1 - Static checks (every change)
Run lint from repo root:
- `powershell -NoProfile -ExecutionPolicy Bypass -File .\ops\scripts\lint.ps1`

Lint should scan:
- canon/
- overlays/
- ops/PROMPTS/
- core/
- docs/

It must flag:
- smart quotes (U+2018/2019/201C/201D)
- tabs
- mojibake sequences (e.g., \u00E2\u20AC and \u00C2)

## Layer 2 - Bundle integrity (when bundling or prompts change)
1) Generate a bundle (`bundle.ps1`)
2) Open the zip and confirm it contains:
- canon/
- ops/PROMPTS/
- docs/
- core/ (required because prompts reference it)

## Layer 3 - Behaviour playtests (minimum suite)
Perform these as real ChatGPT sessions using the latest bundle.

### Test A - START prompt
- Paste `core/ops/PROMPTS/START.md`
- Confirm it asks: role + task

### Test B - Output control
- Choose role: SETUP
- Provide a normal task (do not include WRAP_UP)
- Confirm: it asks onboarding questions and does not output updates
- Send `WRAP_UP` as a standalone message
- Confirm:
  - zip output of updated files
  - GIT_PUBLISH_METADATA printed in chat in a single code block

### Test C - CHECKPOINT
- In the middle of a session, send `CHECKPOINT`
- Confirm minimal zip + metadata output

### Test D - HANDOVER
- Start a session, answer 2-3 questions
- Start a new chat using HANDOVER
- Confirm it continues from next unanswered question

### Test E - Persona sanity
- Run SETUP twice with different persona combos
- Confirm question depth and output tightness change appropriately

## Logging results
- Log outcomes in `core/framework/PLAYTESTS.md`.
- Log issues in `core/framework/ISSUES.md`.
