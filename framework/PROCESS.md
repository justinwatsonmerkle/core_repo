# Career OS – PROCESS

## Pattern 1: core + overlays
- In a user repo, the core framework is mounted under `core/` (git submodule).
- User changes must be made in `overlays/` (never in `core/`).
- Resolution order: overlays override core.

## Setup (first run)
Run: `ops/PROMPTS/ROLE_SETUP.md`

Minimum outputs:
- `canon/profile.md`
- `canon/context.md`
- `canon/measures.md`
- `canon/state.md`

## Session rule (single-role)
Each chat:
- uses exactly one role
- updates a small set of canon files (and overlay files only when explicitly customising)
- logs changes to `canon/changelog.md`

## Review triggers (avoid stale assumptions)
Any of these triggers re-entry into Discover/Plan:
- org change, manager change, scope change
- repeated stalls (same blocker twice)
- measures no longer fit
- monthly review checkpoint

## Evidence rules
- Any claimed “impact” should have a reference in `canon/evidence_portfolio.md`.
- If unknown or assumed: mark it **NEEDS_CONFIRMATION** and log it in `canon/assumptions.md`.
