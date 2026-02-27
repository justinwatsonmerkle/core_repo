# Release process (Core)

LastUpdatedUTC: 2026-02-27T00:00:00Z

This describes a lightweight release approach. Use it when you want stability and predictable rollouts.

## Recommended release types
- Patch: small fixes, no structure changes (vX.Y.Z -> vX.Y.(Z+1))
- Minor: new features / new prompts / new artefacts (vX.Y.Z -> vX.(Y+1).0)
- Major: breaking changes (avoid if possible)

## Release steps
1) Prepare
- ensure playtests are logged
- ensure lint passes (including core + docs)

2) Update docs
- update `core/framework/CHANGELOG.md`
- if needed, update SOP and user guide

3) Tag and publish
- create a git tag (e.g., v0.3.0)
- push tag

4) Communicate
- summary of changes
- what users must do (update core submodule + regenerate bundle)
- any migration steps

## Rollback
If a release causes issues:
- revert the PR or tag a hotfix patch
- communicate clearly
