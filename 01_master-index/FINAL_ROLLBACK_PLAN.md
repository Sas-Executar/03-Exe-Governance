# Final rollback plan

## Invariant

All migration work is additive in review branches. Source repository history and original paths remain intact.

## Restore procedure

1. Do not merge the relevant draft PR.
2. Close the draft PR if the change is rejected.
3. Keep the source path and SHA from the corresponding migration matrix as the active reference.
4. Reopen or recreate a review branch from the recorded base SHA if further work is needed.
5. Do not force-push shared branches and do not delete source repositories.

## Critical review branches

- Governance: `migration/cross-repo-cutover-validation`
- Maestro: `migration/maestro-operational-validation`
- Blueprints: `migration/blueprints-wave4-validation`, `integration/desyng-design-to-blueprints`, `migration/product-spec-to-blueprints`
- Ecosystem: `integration/ecosystem-boundaries`

## No destructive operations performed

- No source file deletion
- No repository rename
- No repository archive/read-only transition
- No automatic PR merge
