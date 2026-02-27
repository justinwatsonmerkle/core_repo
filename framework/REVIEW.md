# Monthly framework review

Cadence: monthly (or when there is enough evidence to justify changes).

Goal: improve the framework without bloating it. Ship small, useful changes.

## Inputs
- `framework/ISSUES.md` (problems and ideas logged during use)
- `framework/PLAYTESTS.md` (what happened with real users)
- prompt failures (where output quality was poor or confusing)
- maintenance friction (where people struggled to update core, bundle, etc.)

## Rules (keep it lightweight)
- Ship **max 3–5 changes** per review cycle.
- Prefer changes that:
  - reduce confusion
  - increase consistency
  - reduce manual effort
- Avoid adding new artefacts unless there is clear repeated pain.

## Review process (30–60 minutes)
1) Triage inputs
   - Group issues into: Prompt / Process / Artefact / Persona / Tooling
2) Choose the top changes (3–5)
   - Define acceptance criteria for each change
3) Implement in core repo
   - Update the relevant files
   - Update `framework/CHANGELOG.md`
4) Regression check (quick)
   - Setup still works (ROLE_SETUP)
   - Overlay precedence guidance still correct
   - No accidental instructions to edit `core/`
5) Publish
   - Merge to `main`
   - Announce "core updated" to users (with a one-line summary)

## Output format for changelog entries
Use short bullets:
- What changed
- Why it changed
- Any user action required (usually: "Update core")
