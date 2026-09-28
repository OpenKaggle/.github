# 👋 Join OpenKaggle

Welcome to the workbench. OpenKaggle is for competitors, students, engineers,
and curious builders who enjoy making useful things in public.

You do not need a polished paper, a finished repository, or a perfect idea.

## The one-minute path

1. Open the [Join OpenKaggle issue form](https://github.com/OpenKaggle/.github/issues/new?template=join.yml).
2. Choose what sounds interesting and write one sentence.
3. Tick the three small community promises and submit.
4. Watch GitHub notifications and click **Accept invitation**.

🎉 That is it. No code, repository, or data upload is required.

If email notifications are enabled, GitHub may also send an organization
invitation email. Notifications are the reliable place to check.

## You can participate without joining

Membership is optional. You can read repositories, open public issues, send
pull requests, reproduce an experiment, or share a correction without joining
the organization.

## Keep the welcome safe

Please do not paste passwords, API tokens, private competition rows, or other
people's restricted files into an issue. A link, short note, or question is
enough.

<details>
<summary>For maintainers: how the invitation workflow stays reliable</summary>

The automatic invitation step requires the organization owner to configure the
private Actions secret `OPENKAGGLE_ORG_MEMBERS_TOKEN` with the minimum
organization-membership-write permission. The secret is never printed or
placed in an issue. Until it is configured, the workflow only triages requests
and does not send invitations.

The workflow is idempotent and recoverable: it serializes runs for one issue,
checks whether the account is already active or pending before sending a new
invitation, retries transient API failures three times, records an
`invite-failed` label without exposing credentials, records a one-time
`invite-blocked` setup state without comment spam, and supports a member/owner
`/invite` retry. Workflow changes become active only after they are merged into
the repository's default branch; pull-request branches are not used to grant
membership.

The flow intentionally invites only the account that opened the issue. It does
not randomly invite arbitrary accounts or accept invitations on behalf of
people, which would make the organization a spam and account-takeover vector.

Membership is not a promise of repository write access. Repository permissions
and teams are granted separately and only when a project needs them.
</details>
