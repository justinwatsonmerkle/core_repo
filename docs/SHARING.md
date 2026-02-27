# Sharing Career OS without leaking personal detail

Rule: treat `canon/` as private by default.

## Recommended model (Pattern 1)
Share:
- the core repo (framework, prompts, SOP, docs)
- a blank user template repo (empty/templated canon)

Do not share:
- any real user repo that contains populated `canon/` content

## How to onboard a new user
1) Create a new private user repo from the user template.
2) Add the core repo as a submodule under `core/`.
3) Generate a bundle and start chats using `core/ops/PROMPTS/START.md`.

## If you need to demonstrate the system
Use a sanitised demo repo:
- start from the user template
- fill canon with fake/sample data only
- do not include any client/company identifiers
