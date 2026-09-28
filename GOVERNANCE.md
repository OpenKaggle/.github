# OpenKaggle Governance

OpenKaggle is maintainer-led and contribution-friendly. Its purpose is to keep
Kaggle research inspectable, reusable, and honest about its limits without
turning participation into a ranking system.

## How decisions are made

- Maintainers decide repository admission, naming, archival status, and merges.
- Decisions are based on scope, evidence, provenance, licensing, maintenance
  cost, and the safety of publishing the material.
- Substantial or irreversible changes should begin with an issue so assumptions
  can be reviewed before implementation grows.
- When reasonable contributors disagree, maintainers summarize the trade-off,
  choose a direction, and record the decision where future readers can find it.

## Repository stewardship

Each repository should identify whether it is active, frozen, or archived. An
archive may still accept corrections to documentation, provenance, security,
or reproducibility material, but it does not promise active feature work.

Maintainers may split a workspace when one competition, method, or artifact
boundary has become independently useful. Repositories are not split merely to
work around hosting limits.

## Becoming a maintainer

There is no medal, rank, employer, or minimum contribution count required.
Maintainers are invited after a sustained record of careful review, reliable
follow-through, respectful collaboration, and attention to evidence and
licensing boundaries. Responsibility may be scoped to one repository or
research area.

## Review, permissions, and transparency

The default route for a normal change is a public pull request. The current
owner and any repository-specific reviewers are listed in `CODEOWNERS`; that
file identifies responsibility, but it does not by itself mean that a change
has been reviewed or that a release is reproducible. Where GitHub settings
permit, protected branches should require an appropriate review before a
merge, especially for publication-sensitive paths.

Maintainers use the least privilege needed for their work. Credentials are
personal, are never shared in issues or workflows, and are not a substitute
for a provenance record. A maintainer may pause a merge, hide a release asset,
or temporarily restrict a repository when a credential, private identifier,
restricted data, or material safety risk is reported. The public record should
then state what was paused or corrected without repeating the sensitive
material.

At least once a year, and before a major archive release, maintainers should
review each mapped repository's status, citation metadata, source and license
links, release manifests, security contact, and known reproduction limits.
The outcome can be a short issue, pull request, or release note. Routine
decisions belong in public issues or pull requests; privacy, security, legal,
and account-recovery details belong in the private channel described in
`SECURITY.md`.

Contributors may ask for a decision to be reconsidered by replying on the
public issue or contacting the organization owner when the issue is private.
The owner may ask for a second review, record the trade-off, and either keep,
narrow, or reverse the decision. There is no promise that every contribution
or artifact will be accepted, but the reason should be proportionate and
understandable.

## Changes to this governance

Governance changes are discussed publicly when possible. Security, privacy,
legal, or account-recovery details may be handled privately. The organization
owner retains final responsibility for GitHub account and publication safety.
