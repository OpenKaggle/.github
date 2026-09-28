# Publishing research from a competition workspace

OpenKaggle exists to preserve useful research context without redistributing
material that a competition, dataset owner, or upstream project has not
licensed for sharing. This guide is the release gate used when a local
competition folder is turned into a public repository.

## The four release lanes

Every file belongs in one of these lanes before it is copied anywhere public.

| Lane | What belongs there | Public destination | What must accompany it |
| --- | --- | --- | --- |
| Source and evidence | User-authored code, notebooks with inputs removed, papers, experiment plans, evaluation logic, validation records, derived replay/trace evidence, receipts, and figures | The competition repository | README, status, license/rules check, and reproduction steps |
| Acquisition record | Organizer data, external datasets, base models, third-party notebooks, packages, and other files we may use but may not redistribute | A source-and-version record, not a copy | `DATA_SOURCES.md` with official URL, license/rules, version, checksum when practical, expected path, and retrieval command |
| Reviewed derivative | User-authored features, validation tables, derived replays/traces, checkpoints or adapters, compiled model files, and generated submission bundles whose redistribution is allowed | The repository for small source-adjacent files, otherwise a documented artifact host | License review, provenance, transform where relevant, manifest, and checksums |
| Private preservation | Original competition downloads, copied upstream weights, unreviewed external artifacts, raw traces, and any item with uncertain rights | A separately verified private archive | Immutable manifest, checksums, retention location, and a clean restore check |

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
   environments, copied upstream weights, `.git` copies, unreviewed generated
   submissions, and local credentials by default. A reviewed user-authored
   checkpoint, compiled model artifact, or submission bundle belongs in the
   reviewed-derivative lane instead of being silently discarded. Never commit a
   Kaggle credential, token, cookie, SSH key, or private identifier.
4. **Make reproduction concrete.** Add `README.md`, `DATA_SOURCES.md`, and
   `RELEASE_MANIFEST.md`. The last should say exactly what was scanned, what
   was excluded, the source revision, and what verification passed.
5. **Run the release checks.** Scan for secrets and private paths; reject
   prohibited data and unexpected large files; compile or test the source-only
   package; and review the diff as a stranger would.
6. **Publish and read back.** Push, read the remote commit by hash, clone into
   a clean temporary location, and confirm that documented setup is possible
   without the original workspace.

## Derived evidence can be public when it has a real research boundary

We do not reduce every useful record to a single aggregate number. A
user-produced validation table, replay, trace, failure case, or experiment
receipt may be published when all of the following are true:

- it is a genuine product of the research process rather than a copied
  organizer file, downloaded submission, or third-party export;
- it does not carry credentials, private account material, or an original file
  that the competition or upstream source expressly withholds from
  redistribution;
- the applicable competition rules, dataset terms, and upstream licences do
  not expressly prohibit sharing that derivative; and
- its README says how it was derived, what it proves, and what was deliberately
  left out.

The fact that a reader might infer something from a well-described experiment,
or might reproduce the same derived output after obtaining the official inputs,
does not by itself make the evidence non-public. The boundary is the material
being distributed: do not mirror the original download or an explicitly
restricted export, but do preserve the work we made with it. When a rule is
unclear, retain a receipt and resolve that specific rule question before
publishing the disputed artifact.

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
experiment receipts are usually the first things to publish. User-authored
checkpoints, adapters, compiled model files, embeddings, generated outputs,
and submission bundles are also publishable research artifacts when they pass
the following review:

- the base model's license and the competition rules must permit distribution;
- user-authored deltas must be distinguishable from upstream weights, and a
  submission must be distinguishable from any organizer input it consumed;
- the artifact must pass the same secret and data-boundary review;
- large allowed artifacts need a documented host and SHA-256, not a giant Git
  history; and
- its release manifest must name the producing source revision, command or
  recipe, base-model source and licence where applicable, exact files, sizes,
  and hashes.

Use the competition repository for source and the artifact host for bytes. A
small public artifact may live alongside its source; a large collection belongs
in a public Kaggle Dataset or a GitHub Release. If a transport limit requires
splitting an allowed artifact, publish a deterministic `REASSEMBLE.md` and
checksums for both the parts and the reconstructed file. Splitting is for
reliable delivery, not a way to hide an opaque archive.

When an artifact itself cannot be shared because of its actual licence or
competition rule, release the recipe, source link, version, checksum, and
expected output layout instead. Do not withhold an otherwise permitted
user-produced model or submission simply because it is large or could be
reproduced from the official inputs.

## Corrections, withdrawal, and post-publication audit

Publication is revisable. A correction is appropriate when the bytes may stay
public but the description, provenance, citation, checksum, or reproduction
claim is wrong. A withdrawal or restriction is appropriate when an asset is
not safe or permitted to remain public, including an accidental credential,
private identifier, restricted row, or incorrectly redistributed upstream
file.

Use this sequence:

1. Open a public correction issue or pull request when the description can be
   safely discussed. For sensitive cases, email the private contact in
   `SECURITY.md` with the URL/path and a minimal explanation; do not paste the
   affected material.
2. Freeze the affected release or link while the maintainer confirms the
   scope. Treat Git history, release assets, Kaggle versions, caches, and DOI
   deposits as separate surfaces to audit.
3. For a correction, publish the replacement text or asset with a new commit
   or release, preserve the old hash in the audit note when it is safe, and
   state exactly what changed. For a withdrawal, remove or restrict the
   affected surface, rotate exposed credentials if applicable, and leave a
   minimal tombstone explaining that the item was withdrawn without repeating
   the sensitive content.
4. Re-run the relevant secret, boundary, manifest, hash, and reproduction
   checks. Record the surviving public source revision, replacement URL, and
   known limits in the issue, pull request, or release note.
5. If old Git objects, release caches, or an external host still retain the
   material, follow that host's removal process; deleting the current file is
   not presented as complete erasure. Do not rewrite history casually: obtain
   owner approval, preserve a private incident record, and verify the new
   clone and release surfaces if history repair is required.

The organization keeps the public record focused on what a reader needs to
trust the current release. Private incident details and re-identification
maps remain private and are not used as a substitute for a public status note.

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
