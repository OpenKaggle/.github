# Joining OpenKaggle

OpenKaggle is open to competitors, students, engineers, and curious builders
who want to share useful work in public. Organization membership is optional;
you can read and contribute through public issues and pull requests without
joining the organization.

## The request flow

1. Open the [Join OpenKaggle issue form](https://github.com/OpenKaggle/.github/issues/new?template=join.yml).
2. Use your own GitHub account. GitHub records the account automatically, so
   there is no username to copy or type. Describe what you would like to share or
   learn. Do not include credentials, private competition rows, or third-party
   files.
3. When the username matches the account that opened the issue and all required
   checkboxes are selected, the workflow sends a least-privilege member
   invitation automatically. No OpenKaggle owner comment is required.
4. The applicant must accept the invitation in GitHub. This is a GitHub account
   security boundary: the workflow cannot and should not accept it on another
   person's behalf. A member or owner can still use `/invite` as a manual
   fallback if an edited issue needs a retry.

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
