# Management workflow (Core + User Template)

LastUpdatedUTC: 2026-02-27T00:00:00Z

This document defines how Career OS is managed and improved for all users.

## Repos and responsibilities

### career-os-core (shared)
Contains:
- framework rules (SOP, PROCESS, ROLES)
- prompts (START, HANDOVER, ROLE_*)
- personas
- maintainer docs and testing regime

Principle:
- core is centrally maintained and shared.
- users should not modify core in their personal repos.

### career-os-user-template (blank)
Contains:
- blank canon files (templates only)
- scripts (lint, bundle, update-core)
- user-facing docs
- overlays (empty)
- placeholder `core/` directory (core is added as a submodule by users)

Principle:
- template contains no personal data, ever.

### user repos (private)
Contains:
- canon (personal truth)
- overlays (optional personal changes)
- core as submodule

Principle:
- personal canon should not be shared.

## Change classification (where changes go)

### Change belongs in core when it is:
- a rule or behaviour that should apply to all users
- a prompt improvement
- a new role or persona component
- a quality/safety guardrail (e.g., WRAP_UP/CHECKPOINT enforcement)
- a shared documentation standard

### Change belongs in the user template when it is:
- a new default canon artefact (blank file) needed for normal operation
- a script improvement (bundle/lint/update-core)
- user guide updates (how to use the system)
- template folder structure changes

### Change belongs in overlays when it is:
- organisation-specific or user-specific preference
- a temporary experiment before upstreaming to core

## Standard workflow for changes (core)

1) Create a branch
- Naming: `core/YYYYMMDD-topic` (or `core/vX.Y.Z-topic` if using versioning)

2) Make a small change set
- keep PRs small and specific
- update SOP/PROCESS/ROLES if behaviour changes

3) Run checks
- run lint (must pass)
- run the minimum playtest suite in TESTING.md for any prompt/SOP changes

4) Raise a PR and merge
- include a short "what changed / why / user impact" summary

5) Announce
- what changed
- who is impacted
- what users must do (usually: update core submodule + regenerate bundle)

## Standard workflow for changes (user template)

1) Create a branch
- Naming: `template/YYYYMMDD-topic`

2) Update blank canon/scripts/docs only
- never include real user data in template

3) Validate
- clone template fresh
- add core submodule
- generate bundle
- run a short chat playtest (START -> role -> WRAP_UP)

4) PR and merge

5) Communicate to users
- new template versions typically affect new users only
- existing users can cherry-pick template changes if needed (scripts/docs)

## Backwards compatibility rules
- Avoid renaming canon files once users exist.
- If a rename is unavoidable:
  - keep the old file for one version and add a migration note
  - update user guide and SOP
- Avoid moving prompt entrypoints:
  - `core/ops/PROMPTS/START.md` should remain stable

## Ownership model
- Core maintainers: limited set of trusted people.
- Template maintainers: same set (or subset).
- Users: can only change canon and overlays in their own repos.

## Operating rhythms
- Monthly: framework review (use AUDITOR monthly review prompt)
- Quarterly: review personas, docs usability, and any repeated confusion patterns

## Evidence and feedback loop
- Log real-world usage issues in `core/framework/ISSUES.md`.
- Log outcomes in `core/framework/PLAYTESTS.md`.
- Use these as primary inputs for monthly review and releases.
