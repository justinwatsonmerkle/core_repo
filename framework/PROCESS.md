# Career OS – PROCESS

LastUpdatedUTC: 2026-02-27T00:00:00Z

## Pattern 1: core + overlays
- In a user repo, the core framework is mounted under `core/` (git submodule).
- User changes must be made in `overlays/` (never in `core/`).
- Resolution order: overlays override core.

## How to start (standard)
Use: `core/ops/PROMPTS/START.md`
- Attach the canon bundle zip.
- Choose role + task.

Use: `core/ops/PROMPTS/HANDOVER.md` only when you need to seed a new chat mid-session.

## Session rule
- Keep questioning in **one role**.
- End every chat with a **COMMIT PACK**:
  - list files to update
  - provide full updated contents for each changed file
  - append to `canon/changelog.md`
  - append to `canon/session_harvest.md`

## Review triggers (avoid stale assumptions)
Any of these triggers re-entry into Discover/Plan:
- org change, manager change, scope change
- repeated stalls (same blocker twice)
- measures no longer fit
- monthly review checkpoint

## Evidence rule
- Any claimed “impact” should have a reference in `canon/evidence_portfolio.md`.
- If unknown or assumed: mark it NEEDS_CONFIRMATION and log it in `canon/assumptions.md`.
