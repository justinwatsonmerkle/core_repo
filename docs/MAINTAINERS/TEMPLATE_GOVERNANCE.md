# User template governance

LastUpdatedUTC: 2026-02-27T00:00:00Z

Goal: keep the user template safe, simple, and free of personal data.

## Hard rules
- Never commit real user content into the template.
- Treat `canon/` in the template as blank templates only.
- Do not include client names, company identifiers, or sensitive details.
- Keep scripts ASCII-safe (no smart punctuation).
- Keep the template stable; avoid renames.

## What belongs in the template
- Blank canon files (all required artefacts)
- Helper scripts:
  - lint.ps1
  - bundle.ps1
  - update-core.ps1
- User-facing docs (USER_GUIDE, update core instructions)
- Overlay scaffolding (empty)

## What does not belong
- Populated canon from any real person
- Organisation-specific overlays (unless you are distributing internally and it is intentional)
- Large binary files (unless essential)

## Versioning approach
- Template changes should be less frequent than core changes.
- When template changes:
  - update template README with "what changed"
  - consider tagging releases (optional)
