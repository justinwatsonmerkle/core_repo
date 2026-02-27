# Persona packs index

LastUpdatedUTC: 2026-02-27T00:00:00Z

Persona packs are **composable defaults** used by prompts to adjust:
- question depth
- suggested cadence
- expected output tightness (how structured)
- typical milestone scale
- common risk patterns to watch for

Persona packs **do not change** the core framework rules.

## Composition model

A user's persona is composed of up to four components:
1) Band (seniority): `BAND_*`
2) Track (focus): `TRACK_*`
3) Time budget: `TIME_*`
4) Style preference: `STYLE_*`

Example composition string (store in `canon/state.md`):
- `BAND_MANAGER + TRACK_STABILITY + TIME_LOW + STYLE_CONVERSATIONAL`

## Resolution / precedence

- Prompts should apply **all** relevant components.
- If components conflict, resolve in this order (highest wins):
  1) Track
  2) Band
  3) Time
  4) Style
- If a component is missing, prompts should use sensible defaults and record **NEEDS_CONFIRMATION** in `canon/assumptions.md`.

## Available components

### Bands
- BAND_IC
- BAND_SENIOR_IC
- BAND_MANAGER
- BAND_LEADER

### Tracks
- TRACK_PROMOTION
- TRACK_STABILITY
- TRACK_EXTERNAL
- TRACK_EXPLORATION

### Time budgets
- TIME_LOW
- TIME_MEDIUM
- TIME_HIGH

### Styles
- STYLE_CONVERSATIONAL
- STYLE_BULLET
- STYLE_MIXED

## How prompts should use persona packs (minimum)
- Use the persona to choose **question count**, **depth**, and **output tightness**.
- Always produce structured artefact updates even if input is conversational.
- Prefer British English spelling regardless of persona.
