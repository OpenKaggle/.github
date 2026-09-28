# Contributing to OpenKaggle

Thank you for sharing your work. OpenKaggle welcomes experienced competitors, first-time researchers, engineers, students, and careful observers. Contributions do not need to be large or polished; they need to be understandable about what they are, where they came from, and how confident we should be in them.

## Proposing a repository

A repository may be hosted by OpenKaggle or remain under your own account and be linked from the portfolio. Please include:

- the competition, task, or research area;
- the repository purpose and current status: plan, active research, maintained project, or archive;
- what it contains: code, notebooks, reports, logs, data, models, or other artifacts;
- what can and cannot be redistributed;
- known missing context or reproduction limits;
- whether you want an organization repository, a transfer, or an external listing;
- who expects to maintain it, if anyone.

We may suggest splitting a very large workspace by competition or artifact boundary. This is organizational help, not a requirement that every project become elaborate.

## Choose a contribution route

Use the issue form that best describes the work before opening a pull request:

- **Bug:** a focused, reproducible problem in code, documentation, or a
  published workflow;
- **Reproduction:** a rerun that matched, differed, or failed, with its
  revision and evidence;
- **Provenance or license:** a source, attribution, or redistribution question;
- **Research proposal:** a new competition archive, method, experiment, or
  external repository; and
- **Archive correction or withdrawal:** a public request to revise, restrict,
  or replace a published record.

Use the private contact in `SECURITY.md` for credentials, personal data,
restricted competition material, security findings, or legal concerns. Do not
make a public pull request merely to report sensitive content. If the work is
large, describe the artifact host, manifest, source revision, and checksums;
size alone is not a reason to hide an otherwise permitted user-produced
artifact, and a public repository is not automatically allowed to mirror an
official or third-party file.

## Ordinary contribution and submission flow

Small, focused changes may go directly to a pull request. For a larger or
irreversible change, opening a proposal issue first is recommended so that
scope and assumptions can be discussed, but it is not a mandatory ceremony.
The same route is open to first-time contributors and established projects.

OpenKaggle does not require a uniform directory tree or a paper-shaped
manuscript. Each project should instead keep a short README entry explaining
what the contribution is, where it came from, how to run or inspect it, and
what cannot be reproduced. Use the project’s actual structure and omit empty
sections rather than copying boilerplate.

| Contribution type | Recommended public material |
| --- | --- |
| Source or code | Source files, tests, environment notes, and a focused README entry |
| Methods or research notes | Hypothesis, method, assumptions, decision record, and known limits |
| Experiments or models | Configurations, evaluation recipe, model/adapter/ONNX provenance, and metrics |
| Failure or negative result | Setup, attempted method, observed failure, and evidence that supports the conclusion |
| Reproduction | Source revision, inputs or official retrieval path, command, environment, and receipt |
| Derived evidence | Transform or aggregation logic, manifest, checksums, and a clear boundary statement |
| Data-source record | Official URL, version, license/rules, expected path, checksum when practical, and retrieval instructions |
| Documentation or design | User-facing explanation, diagrams, review context, and maintenance status |

Do not publish credentials, personal sensitive data, unauthorized official or
holdout data, third-party files without redistribution rights, malicious code,
hidden telemetry, or inflated claims. A model or derived artifact is welcome
when its license/rules and provenance permit release. Put large permitted
bytes in a documented GitHub Release, Kaggle Dataset, or equivalent artifact
host; do not place them in ordinary Git history.

## Contributing to an existing project

1. Read the project README and current status.
2. Check whether the project is active or preserved as an archive.
3. Keep the change focused enough to review.
4. Explain what changed, why it helps, and how you checked it.
5. Avoid unrelated formatting or bulk-generated changes.
6. Preserve useful historical evidence unless the project documents a reason to replace it.

Good contributions include reproductions, bug fixes, clearer instructions, provenance corrections, experiment receipts, failure reports, and small method improvements. For a substantial new direction, begin with a short issue or research plan.

## Evidence expectations

Match the evidence to the strength of the claim. For an experiment, record as much of the following as practical:

- command, notebook entry point, or execution steps;
- code revision and dependency information;
- dataset and model versions;
- random seed and hardware assumptions;
- evaluation method and metric;
- output location, log, checksum, or other receipt;
- known variance, failures, exclusions, and unresolved questions.

Label results accurately. Local evaluation is not a leaderboard result; a public score is not a private score; a single run is not automatically a stable benchmark. Early ideas are welcome when marked as plans or explorations.

## Licensing and data boundaries

Before adding data, weights, competition assets, or third-party outputs:

- confirm that redistribution is permitted;
- retain original source and license information;
- note competition-specific restrictions;
- avoid assuming that a repository code license covers the artifact;
- exclude credentials, personal information, and private or restricted material.

If an artifact cannot be committed, add a manifest with its source, version, checksum, expected path, approximate size, and retrieval instructions. If the boundary is uncertain, contribute the method and provenance information first and ask.

For the full release gate and the distinction between public research,
official-data acquisition records, reviewed derivatives, and private
preservation, read [Publishing research from a competition workspace](PUBLISHING.md).

For organization membership, read [JOIN.md](JOIN.md). Membership is optional,
and repository access is granted separately from a successful invitation.

For the shared academic-style citation shape, use the
[citation and archival standard](CITATION_POLICY.md) and copy the templates
from [`templates/`](templates/). Each repository should expose a
`CITATION.cff`, a synchronized `CITATION.bib`, and a README `## Citation`
block once it has a citable release.

## A friendly review process

Review is a conversation about making work easier to trust and reuse. Feedback should be specific, kind, and proportionate to the contribution. Experience level, competition rank, and writing fluency are neither substitutes for evidence nor prerequisites for respect.

Some proposals may be redirected, narrowed, linked externally, or declined because of scope, maintenance, licensing, or reproducibility constraints. We will explain why and, where possible, suggest a smaller path forward.
