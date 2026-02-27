# Career OS – SOP

LastUpdatedUTC: 2026-02-27T00:00:00Z

This SOP is the governing operating procedure for Career OS sessions.

## Non-negotiables
- Use **British English spelling**.
- The attached bundle is the source of truth.
- Core is read-only (`core/`). Never modify core during a user session.
- Overlay precedence: `overlays/` overrides `core/`.
- Do not invent facts. If uncertain, tag **NEEDS_CONFIRMATION** and log it in `canon/assumptions.md`.
- Use ASCII punctuation only: " and '. Do not use smart quotes.

## Session modes
Career OS supports three user-invoked commands:

### 1) Normal mode (default)
- Hold a conversational session.
- Ask questions appropriate to the selected role.
- Do **not** output repo files unless asked.
- Keep a running internal note of intended updates.

### 2) CHECKPOINT (optional save-point)
User message includes: `CHECKPOINT`
- Produce a **minimal** HARVEST + COMMIT PACK.
- Only include files that are clearly updated based on the conversation so far.
- Output as a **single zip file** (see "Output format").

### 3) WRAP_UP (end the session)
User message includes: `WRAP_UP`
- Produce the full HARVEST + COMMIT PACK.
- Include all relevant canon updates.
- Output as a **single zip file** (see "Output format").

## Role discipline
- Questioning and decisions must stay within **one role** per session.
- Respect role write boundaries defined in `core/framework/ROLES.md`.
- Cross-role implications belong in HARVEST as follow-ups.

## HARVEST (required on CHECKPOINT or WRAP_UP)
Provide these sections:
1) FACTS to commit
2) ASSUMPTIONS / unknowns (NEEDS_CONFIRMATION)
3) IMPLICATIONS (what this means)
4) FOLLOW-UPS (items for other roles)

Follow-ups should go into `canon/followups_backlog.md` if they are not ready for the main backlog.

## COMMIT PACK (required on CHECKPOINT or WRAP_UP)
A commit pack must:
- list files that changed
- include **full updated contents** for each changed file
- append an entry to `canon/changelog.md`
- append a session entry to `canon/session_harvest.md`
- On CHECKPOINT/WRAP_UP, output Git publish metadata in chat as a single code block named GIT_PUBLISH_METADATA. Do not write it to any repo file and do not include it in the zip. Git publish metadata is described in this document.


## Output format (required on CHECKPOINT or WRAP_UP)
- Output a **single zip file** containing **only the updated files** (full files), preserving filenames and paths exactly.
- Do **not** paste file contents in chat.
- Do not include unrelated files in the zip.


## GIT_PUBLISH_METADATA format (in chat, code block)

- BaseCanonBundle: <filename>
- UTC_GeneratedAt: <timestamp>
- SuggestedBranch: <branch>
- SuggestedCommitMessage: <message>
- SuggestedPRTitle: <title>
- SuggestedPRDescription:
  - <bullet>
  - <bullet>
- ChangedFiles:
  - <path>
  - <path>
- PublishDecision: PUBLISH|HOLD