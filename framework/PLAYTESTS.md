# Playtests (anonymised)

Purpose: capture what happened when the framework was used, without sharing personal content.

Do not include:
- names
- company/client identifiers
- sensitive metrics or incident details

Do include:
- persona band (IC / Senior IC / Manager / Leader)
- track focus (promotion / stability / external / exploration)
- time budget (low / medium / high)
- what worked / what failed
- where prompts were confusing
- which artefacts were useful (and which were ignored)

---

## Playtest template (copy/paste)

### PT-YYYYMMDD-01
- Date:
- Persona:
  - Band:
  - Track:
  - Time budget:
  - Style:
- Session type (role):
- Objective:
- What worked:
- What failed / confused:
- Artefacts used:
- Artefacts ignored:
- Prompt issues (quote short snippets if needed):
- Proposed changes (max 3):
- Outcome signal (what improved, even qualitatively):

---

## Log

### PT-20260227-01
- Date: 2026-02-27
- Persona:
  - Band: Manager
  - Track: Stability
  - Time budget: Low
  - Style: Conversational
- Session type (role): Setup + system hardening
- Objective: Make Pattern 1 operational (core in bundle), enforce WRAP_UP/CHECKPOINT output control, and remove smart punctuation risk.
- What worked:
  - Bundling `core/` made core-referenced prompts usable in fresh chats.
  - One-click update helper can run from cmd via Windows PowerShell.
- What failed / confused:
  - Lint originally missed `core/` and `docs/`, allowing smart punctuation to persist.
  - A naive replace introduced encoding risk; required safer approach and lint enhancements.
- Artefacts used:
  - core/framework/SOP.md
  - core/ops/PROMPTS/START.md
  - docs/USER_GUIDE.md
- Proposed changes:
  - Expand lint to scan `core/` + `docs/` and flag mojibake patterns.
  - Require strict output control: no COMMIT PACK unless standalone WRAP_UP/CHECKPOINT.
  - Provide sharing guidance to avoid leaking personal canon.
- Outcome signal:
  - Bundles contain the necessary core assets; repo-wide punctuation can be prevented with lint.
