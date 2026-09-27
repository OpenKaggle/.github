# Publishing research from a competition workspace

OpenKaggle exists to preserve useful research context without redistributing
material that a competition, dataset owner, or upstream project has not
licensed for sharing. This guide is the release gate used when a local
competition folder is turned into a public repository.

## The four release lanes

Every file belongs in one of these lanes before it is copied anywhere public.

| Lane | What belongs there | Public destination | What must accompany it |
| --- | --- | --- | --- |
| Source and evidence | User-authored code, notebooks with inputs removed, papers, experiment plans, evaluation logic, logs, receipts, figures whose inputs may be shared | The competition repository | README, status, license, and reproduction steps |
| Acquisition record | Organizer data, external datasets, base models, third-party notebooks, packages, and other files we may use but may not redistribute | A source-and-version record, not a copy | `DATA_SOURCES.md` with official URL, license/rules, version, checksum when practical, expected path, and retrieval command |
| Reviewed derivative | User-authored features, aggregate statistics, redacted traces, model adapters, or small data products whose redistribution is allowed | The repository or a documented artifact host | License review, provenance, transform, manifest, and checksums |
| Private preservation | Original competition downloads, full checkpoints, large submission bundles, raw traces, and any item with uncertain rights | A separately verified private archive | Immutable manifest, checksums, retention location, and a clean restore check |

Do not treat an item as public merely because it is present in a local folder or
because the surrounding code has an open-source license.

## Before making a public repository

1. **Split at the research boundary.** Use one repository for one competition
   or a genuinely shared tool. Do not make a single 100+ GiB workspace the
   release unit.
2. **Inventory first.** Record each included top-level path and every excluded
   large path. Classify its author, source, license/rules, size, and release
   lane.
3. **Remove non-public inputs.** Exclude competition downloads, caches, virtual
   environments, model weights, `.git` copies, generated submissions, and
   local credentials by default. Never commit a Kaggle credential, token,
   cookie, SSH key, or private identifier.
4. **Make reproduction concrete.** Add `README.md`, `DATA_SOURCES.md`, and
   `RELEASE_MANIFEST.md`. The last should say exactly what was scanned, what
   was excluded, the source revision, and what verification passed.
5. **Run the release checks.** Scan for secrets and private paths; reject
   prohibited data and unexpected large files; compile or test the source-only
   package; and review the diff as a stranger would.
6. **Publish and read back.** Push, read the remote commit by hash, clone into
   a clean temporary location, and confirm that documented setup is possible
   without the original workspace.

## Sanitization means making a safe public derivative

Sanitization is not a label for deleting a few obvious fields. Keep the method
reviewable:

- preserve the public transform or clear pseudocode for it;
- document which fields or files were removed, generalized, or regenerated;
- scan text, notebook outputs, filenames, metadata, and archives for secrets,
  local absolute paths, identifiers, and raw rows;
- ensure that reported metrics and figures do not disclose restricted rows;
- keep any re-identification mapping out of the public release. If the owner
  needs reversibility, store that mapping only with the private archive and
  protect it independently.

Where a derivative is itself allowed to be shared, publish the transform and a
manifest alongside it. This lets someone understand its boundary without
pretending they have the original dataset.

## Models and training outputs

Configuration, training code, evaluation recipes, metric outputs, and
experiment receipts are usually the first things to publish. Checkpoints,
adapters, embeddings, and generated outputs require a second decision:

- the base model's license and the competition rules must permit distribution;
- user-authored deltas must be distinguishable from upstream weights;
- the artifact must pass the same secret and data-boundary review;
- large allowed artifacts need a documented host and SHA-256, not a giant Git
  history.

When the artifact itself cannot be shared, release the recipe, source link,
version, checksum, and expected output layout instead.

## Deleting a local copy

Public source is not a backup for a 75–120 GiB workspace. Delete a local item
only after its designated remote copy has passed all of these checks:

1. the remote manifest and byte-level checksum match the local archive;
2. a clean download or restore succeeds;
3. the archive location, ownership, and access method are recorded;
4. the item has no active process or unfinished experiment depending on it.

For mixed workspaces, delete only the verified subdirectory or archive after
its own gate passes. Keep a compact local manifest and the source-only
repository even after bulk artifacts move elsewhere.

## Suggested repository shape

```text
competition-research/
  README.md                 # purpose, current status, limits
  DATA_SOURCES.md           # official source links; no copied organizer data
  RELEASE_MANIFEST.md       # inclusion/exclusion and verification receipt
  LICENSE                   # applies only to owned material
  src/  notebooks/  reports/  tests/
  scripts/fetch_data.sh     # obtains permitted inputs after the user has access
```

An honest archive is more valuable than a large opaque upload. Preserve failed
experiments and limitations when they help a future researcher understand what
was actually tried.
