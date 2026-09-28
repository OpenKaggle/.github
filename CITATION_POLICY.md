# OpenKaggle citation and archival standard

This document is the shared citation contract for OpenKaggle repositories.
It is deliberately compatible with the way software papers, benchmark
archives, and reproducibility packages are usually cited: a human-readable
README section, a machine-readable `CITATION.cff`, a BibTeX entry, and a
versioned release with an immutable commit. A DOI is preferred when a release
has been deposited in a DOI service such as Zenodo; a DOI is not required for
an early or actively changing project.

The goal is to make a repository easy to cite without making it look like a
peer-reviewed paper when it is a competition archive, an experiment log, or a
workbench contribution. Use the repository's actual status and scope.

## The four citation surfaces

Each maintained or archived research repository should provide these surfaces
at its repository root:

| Surface | File or location | Purpose |
| --- | --- | --- |
| Human guidance | `README.md` → `## Citation` | Tells a reader what to cite and which version was used |
| Machine metadata | `CITATION.cff` | Lets GitHub and citation tools generate a citation |
| LaTeX/BibTeX | `CITATION.bib` | Gives papers and reports a copyable BibTeX entry |
| Immutable record | Git tag + GitHub Release, optionally DOI | Pins the exact source and artifact version |

The templates in [`templates/`](templates/) are starting points. Replace all
`REPLACE_*` values before publishing. A template is not itself a citation for
the repository.

## What a reader should cite

Use the narrowest citation that supports the claim:

1. **Code or method reuse:** cite the versioned software release and its DOI
   when available. Otherwise cite the GitHub Release URL and commit.
2. **A result, report, or experiment record:** cite the release containing the
   report, and identify the report path in the README or BibTeX `note`.
3. **A model, ONNX file, adapter, or submission bundle:** cite the artifact
   release or public dataset separately from the source repository. Include
   the artifact version, SHA-256 manifest, and producing source revision.
4. **A dataset or official competition input:** cite the organizer's dataset
   and competition page under the original terms. OpenKaggle is not the owner
   of those inputs and its repository citation must not replace the official
   citation.
5. **A third-party model, notebook, package, or baseline:** cite its original
   author and license in addition to any OpenKaggle analysis that used it.

The repository citation and the academic-source citation are separate layers:

- `CITATION.cff` and an `@software{...}` entry identify the executable
  repository or release that was used;
- the README may add a `References` section, and `CITATION.bib` may include
  related `@article{...}`, `@inproceedings{...}`, `@phdthesis{...}`, or other
  scholarly entries when they genuinely describe the method, benchmark, or
  upstream work; and
- an academic entry must not be invented to make a competition archive look
  like a paper. If no paper, proceedings article, or thesis exists, cite the
  software/archive release and label it honestly.

If a paper later describes the work, add it as `preferred-citation` in
`CITATION.cff`, but keep the software/archive citation available: the paper
and the executable research object are related, not interchangeable.

## CITATION.cff requirements

Every repository-level `CITATION.cff` should contain, at minimum:

- `cff-version: 1.2.0`;
- `message` explaining that users should cite the version they used;
- `type: software` for code and research archives, or the appropriate CFF
  type for a standalone dataset/model release;
- the repository title, real authors/contributors, and `date-released` for a
  tagged release;
- `repository-code`, `url`, and the repository license when applicable;
- `version`, or an explicit archive snapshot identifier; and
- a short abstract and keywords when the scope is not obvious from the title.

Do not put secrets, local paths, private account identifiers, or raw
competition rows into citation metadata. Author order should reflect the
project's documented contribution order, not a leaderboard position. Use
`OpenKaggle` as the publisher or community only when it is actually the
repository host; do not imply endorsement by Kaggle or Google.

For a release with a DOI, add `doi` and make the DOI landing page the primary
versioned citation target. For an evolving repository without a DOI, cite the
tagged GitHub release URL and the commit SHA. A branch URL such as `main` is a
discovery link, not a reproducible citation.

## Release and DOI convention

Use a tag that clearly identifies the cited state:

- `vMAJOR.MINOR.PATCH` for software releases with compatibility meaning;
- `snapshot-YYYY-MM-DD` for a dated research archive; or
- `artifact-YYYY-MM-DD` for a large model, ONNX, replay, or submission
  collection released outside Git history.

Every release should include a short release note stating the source commit,
included and excluded paths, verification performed, and known limits. Large
permitted bytes belong in a GitHub Release, public Kaggle Dataset, or another
documented artifact host, not in ordinary Git history. Split files only with a
deterministic reassembly recipe and checksums for both parts and the restored
file.

When using Zenodo or another DOI service:

1. preserve the GitHub repository and tag as the source of truth for code;
2. archive the exact tagged release, not an unreviewed working tree;
3. record the DOI and landing URL in `CITATION.cff`, `README.md`, and the
   release notes; and
4. cite the specific version DOI, not only a concept DOI, when reproducing a
   result.

Do not mint a DOI for a draft merely to make it look like a paper. A clear
GitHub release with a commit and manifest is an adequate citation surface
until the archive is stable.

## README citation block

Copy [`templates/README-CITATION.md`](templates/README-CITATION.md) into each
repository's README and fill in the version-specific values. The block should
show:

- the preferred citation (DOI when available, otherwise the release URL);
- the exact version/tag and commit used;
- a link to `CITATION.cff` and `CITATION.bib`; and
- separate links to official competition/data sources and third-party inputs.

Keep the citation block near the end of the README, after scope and
reproduction instructions. Readers should understand what the project is
before they are asked to cite it.

## Data, model, and evidence boundaries

Citation metadata does not change redistribution rights. Apply the OpenKaggle
publication gate before adding a citation file or release asset:

- official competition downloads, restricted event streams, and organizer
  files remain source-linked unless their terms explicitly allow mirroring;
- third-party weights, notebooks, and packages remain attributed and
  license-bound; cite their original source rather than relabeling them as
  OpenKaggle work;
- user-authored code, evaluation logic, reports, derived tables, replays,
  adapters, compiled models, and submission bundles may be cited and released
  when their license/rules review permits it;
- derived artifacts need provenance, a transform or build recipe, an explicit
  boundary statement, and checksums; and
- private mappings, credentials, raw restricted rows, and unrelated local
  files never belong in `CITATION.cff`, `CITATION.bib`, a release, or a DOI
  deposit.

When the bytes cannot be redistributed, cite the original source and publish
the acquisition record (`DATA_SOURCES.md`) with version, expected path,
checksum when practical, and retrieval instructions. Do not cite a private
local path as if it were a public artifact.

## Minimal adoption checklist

Before merging a new or updated repository into the OpenKaggle map:

- [ ] `CITATION.cff` is filled with real authors, scope, license, version, and
      repository URL;
- [ ] `CITATION.bib` agrees with the CFF title, authors, year, version, and URL;
- [ ] the README has the citation block and identifies the exact release;
- [ ] the release note links the source commit and manifests any large bytes;
- [ ] a DOI is recorded if one exists, but no DOI is implied when it does not;
- [ ] official data, third-party material, and user-authored derivatives are
      separately attributed; and
- [ ] a stranger can tell what is reproducible from the public repository and
      what must be fetched from an official source.

For a repository that is still exploratory, it is acceptable to add the CFF
and README block before a release exists. In that case label the citation as
an evolving snapshot and do not claim that it is a peer-reviewed publication.
