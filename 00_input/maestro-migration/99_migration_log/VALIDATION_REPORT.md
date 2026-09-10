# Copy validation

WF-01 main snapshot: PASS_WITH_GAPS.

67/67 non-operational nonempty source artifacts copied with identical Git blob SHA and mode in tree `6f30ffea7ecfaff247d8b86ed82d5762c234dbf1`. Includes the original XLSX, SHA `7a974a5308edc3ef82495927524e40481872fd21`. All original IDs/statuses inside copied bytes are preserved by exact byte identity. 86 text blobs read locally matched their Git hashes. Maestro mirror passed git fsck --full and a bundle --all was created.

No source was removed. Empty placeholders, operational assets and submodule remain in source. Inventory contains all 277 main entries. Semantic ID collisions across other sources are not yet resolved. External links not asserted valid. Relative links preserve source context; final distribution needs link reconciliation. No runtime code was changed.

Maestro branch ancestry against pinned main (left/right commits): export 18/0; ambiente 18/2; plugin-engineer 1/2; rc-knw 1/0. Divergent branches require a documented disposition; do not declare all-branch migration complete.
