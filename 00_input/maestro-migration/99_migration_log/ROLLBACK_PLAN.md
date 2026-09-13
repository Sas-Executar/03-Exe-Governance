# Rollback

All migration changes are additive in temporary branches. Original trees and refs remain untouched. Before a merge, rollback means declining the PR. After a merge, revert the corresponding merge commit through a reviewed PR; do not reset or force-push.

The baseline records original refs and blobs; it is not a complete Git history backup. Sources must remain available. Renames and archives are blocked until reconciliation and complete recovery checks.
