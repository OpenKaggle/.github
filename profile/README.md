<p align="center">
  <img src="assets/openkaggle-primary-white.png" alt="OpenKaggle graduate-duck wordmark" width="640">
</p>

# OpenKaggle

**An open workbench for sharing how Kaggle research actually gets made.**

OpenKaggle is a community workbench for transparent competition research: code people can inspect, experiments people can reproduce, and notes that make the work more useful than a leaderboard score alone.

It is maintained in public by competitors, students, engineers, and researchers who like learning by building. A baseline, a notebook, a technical tool, a careful correction, a useful failure, or a complete system can all start a good conversation here when the provenance and evidence are clear.

Bring the work you have. Curiosity, evidence, and generosity are enough; polish can come later.

## An open workbench

OpenKaggle is a place to share:

- current and archived Kaggle competition projects;
- exploratory notebooks and reusable analysis systems;
- data preparation, training, inference, evaluation, and submission processes;
- technical production workflows that make research more reliable;
- experiment logs, including negative and inconclusive results;
- research plans, hypotheses, decision records, and open questions;
- provenance records, checksums, environment details, and reproduction receipts;
- open datasets and models when their licenses permit redistribution.

Each repository should plainly say what it is for, what someone can reuse,
what evidence supports its claims, and what remains outside its scope.

## Share your work

There are several good ways to participate:

- propose a repository for the OpenKaggle organization;
- keep a repository under your own account and ask us to list it in the portfolio;
- contribute a focused improvement to an existing project;
- reproduce an experiment and report what matched or differed;
- publish an experiment log, research plan, analysis system, or technical workflow;
- help clarify documentation, provenance, licensing, or known limitations.

A small, well-explained contribution is often more useful than a large unexplained upload.

## Repository map

This is a growing map of shared tools, careful archives, and competition work.

### Portfolio

| Repository | Purpose |
| --- | --- |
| [`kaggle-research-portfolio`](https://github.com/OpenKaggle/kaggle-research-portfolio) | Project index, external contributions, archive status, migration notes, and related work |

### Community infrastructure

| Repository | Purpose |
| --- | --- |
| [`brand-assets`](https://github.com/OpenKaggle/brand-assets) | Versioned wordmarks, square lockups, provenance, hashes, and contribution guidance |

### Competition research

| Repository | Scope |
| --- | --- |
| [`nemotron-reasoning-research`](https://github.com/OpenKaggle/nemotron-reasoning-research) | Reasoning competition research, experiments, reports, and submission methods |
| [`neurogolf-2026-onnx-research`](https://github.com/OpenKaggle/neurogolf-2026-onnx-research) | ONNX construction, optimization, validation, and competition artifacts |
| [`maze-crawler-research`](https://github.com/OpenKaggle/maze-crawler-research) | Agent development, evaluation work, experiment history, and reproducibility material |
| [`arc2-paper-research`](https://github.com/OpenKaggle/arc2-paper-research) | ARC2 methods, paper materials, evaluation records, and public notebooks |
| [`arc3-2026-research`](https://github.com/OpenKaggle/arc3-2026-research) | ARC-AGI-3 feasibility, policy, and baseline research |
| [`biohub-cell-tracking-research`](https://github.com/OpenKaggle/biohub-cell-tracking-research) | Cell-tracking methods, tests, campaign records, and provenance |
| [`cuhk-x-research`](https://github.com/OpenKaggle/cuhk-x-research) | CUHK-X large- and small-track research in one reviewable archive |
| [`kaggriculture-research`](https://github.com/OpenKaggle/kaggriculture-research) | Agents, evaluators, research notes, and experiment receipts |
| [`playground-s6e9-research`](https://github.com/OpenKaggle/playground-s6e9-research) | Playground-series modelling, validation, and reproducibility materials |
| [`poker-transfer-research`](https://github.com/OpenKaggle/poker-transfer-research) | Transfer-detection methods, evaluation protocols, and evidence records |
| [`rogii-wellbore-geology-research`](https://github.com/OpenKaggle/rogii-wellbore-geology-research) | Wellbore-geology training, selection, validation, and operational research notes |
| [`tartan-imu-research`](https://github.com/OpenKaggle/tartan-imu-research) | IMU methods, protocols, notebooks, and evidence records |
| [`traffic-forecasting-research`](https://github.com/OpenKaggle/traffic-forecasting-research) | Traffic-flow methods, notebooks, campaign records, and provenance |
| [`hyperspectral-od-2026-research`](https://github.com/OpenKaggle/hyperspectral-od-2026-research) | Hyperspectral object-detection source, protocols, tests, and lightweight evidence |

## Evidence, without ceremony

OpenKaggle does not ask a project to fit a fixed maturity ladder. A README
should simply state the question, inputs, method, evidence obtained,
reproduction path, and known limits. If a repository is an archive or is
actively maintained, say so in plain language.

Local validation, public leaderboard scores, private leaderboard scores, and
estimates are different kinds of evidence. Repositories should not blur them
together. Failed experiments belong here too: when the setup and outcome are
recorded, failure becomes reusable knowledge.

## Data and license boundaries

We preserve as much research context as possible without pretending that every public file may be redistributed.

- Each repository states its own license and status.
- A code license does not automatically cover datasets, model weights, competition files, or third-party outputs.
- Original licenses and competition rules take precedence.
- Large permitted artifacts may live in releases, Git LFS, Kaggle datasets, or another documented store.
- When bytes cannot be mirrored, we prefer a source URL, version, checksum, expected path, approximate size, and retrieval instructions.
- Credentials, private identifiers, restricted data, and unrelated personal files do not belong in public commits.

The practical release gate is documented in [Publishing research from a competition workspace](../PUBLISHING.md).

For a consistent way to cite a repository, model, report, or artifact release,
see the [OpenKaggle citation and archival standard](../CITATION_POLICY.md).
It uses `CITATION.cff`, a synchronized BibTeX entry, a README citation block,
and a versioned release or DOI when one exists.

Unclear cases are discussed patiently. It is always acceptable to publish the method and provenance record before publishing the artifact itself.

## The atmosphere we want

OpenKaggle is a friendly, independent workshop: serious about evidence and
light on ceremony. We value patient explanations, honest uncertainty, compact
experiments, useful archives, and review that leaves both the work and the
person sharing it in a better place.

Come with a complete system or a single interesting trace. There is room at
the bench.

## Independence

OpenKaggle is an independent project and is not affiliated with, endorsed by, or operated by Kaggle or Google. Kaggle and related names and marks belong to their respective owners.
