# OpenKaggle

**An open workbench for sharing how Kaggle research actually gets made.**

<img width="1492" height="1054" alt="image" src="https://github.com/user-attachments/assets/cffefb1c-ef70-42c1-8834-5fa64fa78571" />

OpenKaggle grows from years of competition folders, experiment traces, unfinished ideas, and hard-won lessons. We turn that material into careful public projects and invite others to work in the open with us.

People participate at different levels. Some bring a complete competition pipeline; others share one careful notebook, an analysis system, a production technique, a failed experiment, or a research plan that has not been tested yet. All of these can be useful when their status and limits are explained honestly.

You do not need a medal, a polished result, or a grand theory to contribute. Curiosity, evidence, and kindness are enough.

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

A repository may be complete, actively evolving, or preserved as a historical snapshot. We simply ask that it says which one it is.

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

The map changes as older workspaces are separated, documented, and migrated.

### Portfolio

| Repository | Purpose |
| --- | --- |
| [`kaggle-research-portfolio`](https://github.com/openkaggle/kaggle-research-portfolio) | Project index, external contributions, archive status, migration notes, and related work |

### Competition research

| Repository | Scope |
| --- | --- |
| [`nemotron-reasoning-research`](https://github.com/openkaggle/nemotron-reasoning-research) | Reasoning competition research, experiments, reports, and submission methods |
| [`neurogolf-2026-onnx-research`](https://github.com/openkaggle/neurogolf-2026-onnx-research) | ONNX construction, optimization, validation, and competition artifacts |
| [`maze-crawler-research`](https://github.com/openkaggle/maze-crawler-research) | Agent development, evaluation work, experiment history, and reproducibility material |
| [`arc2-paper-research`](https://github.com/openkaggle/arc2-paper-research) | ARC2 methods, paper materials, evaluation records, and public notebooks |
| [`arc3-2026-research`](https://github.com/openkaggle/arc3-2026-research) | ARC-AGI-3 feasibility, policy, and baseline research |
| [`biohub-cell-tracking-research`](https://github.com/openkaggle/biohub-cell-tracking-research) | Cell-tracking methods, tests, campaign records, and provenance |
| [`cuhk-x-research`](https://github.com/openkaggle/cuhk-x-research) | CUHK-X large- and small-track research in one reviewable archive |
| [`kaggriculture-research`](https://github.com/openkaggle/kaggriculture-research) | Agents, evaluators, research notes, and experiment receipts |
| [`tartan-imu-research`](https://github.com/openkaggle/tartan-imu-research) | IMU methods, protocols, notebooks, and evidence records |
| [`traffic-forecasting-research`](https://github.com/openkaggle/traffic-forecasting-research) | Traffic-flow methods, notebooks, campaign records, and provenance |
| [`tree-species-hsi-research`](https://github.com/openkaggle/tree-species-hsi-research) | Phase 1 and Phase 2 hyperspectral tree-species source, protocols, tests, and lightweight evidence |

## How we describe evidence

We welcome work at every stage, but label it clearly:

- **Plan** — a question, hypothesis, or intended experiment;
- **Exploration** — useful observations not yet controlled or reproduced;
- **Candidate result** — measured work with enough context to inspect;
- **Reproduced result** — rerun successfully under documented conditions;
- **Archive** — preserved for history and no longer actively maintained.

Local validation, public leaderboard scores, private leaderboard scores, and estimates are different kinds of evidence. Repositories should not blur them together. Failed experiments belong here too: when the setup and outcome are recorded, failure becomes reusable knowledge.

## Data and license boundaries

We preserve as much research context as possible without pretending that every public file may be redistributed.

- Each repository states its own license and status.
- A code license does not automatically cover datasets, model weights, competition files, or third-party outputs.
- Original licenses and competition rules take precedence.
- Large permitted artifacts may live in releases, Git LFS, Kaggle datasets, or another documented store.
- When bytes cannot be mirrored, we prefer a source URL, version, checksum, expected path, approximate size, and retrieval instructions.
- Credentials, private identifiers, restricted data, and unrelated personal files do not belong in public commits.

Unclear cases are discussed patiently. It is always acceptable to publish the method and provenance record before publishing the artifact itself.

## The atmosphere we want

OpenKaggle is not a leaderboard club, a fund, or a grand institution. It is a long-running workbench maintained by people who enjoy careful competition research and want more of its real process to remain visible.

We value patient explanations, honest uncertainty, compact experiments, useful archives, and review that leaves both the work and the person sharing it in a better place.

Come with a complete system or a single interesting trace. There is room at the bench.

## Independence

OpenKaggle is an independent project and is not affiliated with, endorsed by, or operated by Kaggle or Google. Kaggle and related names and marks belong to their respective owners.
