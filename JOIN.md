# Joining OpenKaggle

OpenKaggle is open to competitors, students, engineers, and curious builders
who want to share useful work in public. Organization membership is optional;
you can read and contribute through public issues and pull requests without
joining the organization.

## The request flow

1. Open the **Join OpenKaggle** issue form in this repository.
2. Use your own GitHub account and describe what you would like to share or
   learn. Do not include credentials, private competition rows, or third-party
   files.
3. An owner reviews the request. The bot adds `needs-review` and explains the
   next step; it does not grant access merely because an issue was opened.
4. After an owner has reviewed the request, the owner may comment `/invite`.
   The workflow sends a least-privilege member invitation and records the
   action on the issue.
5. The applicant must accept the invitation in GitHub. The workflow cannot and
   should not accept it on another person's behalf.

The invitation step requires the organization owner to configure the private
Actions secret `OPENKAGGLE_ORG_MEMBERS_TOKEN` with the minimum organization
membership-write permission. The secret is never printed or placed in an
issue. If it is not configured, the workflow only triages requests and an
owner can send the invitation through GitHub's normal UI.

Membership is not a promise of repository write access. Repository permissions
and teams are granted separately and only when a project needs them.
