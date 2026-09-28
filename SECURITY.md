# Security Policy

Do not open a public issue for credentials, private identifiers, restricted
competition material, or a vulnerability that could expose another person or
system. Do not test a live system beyond data and access you are authorized to
use; stop and report if a test begins to reveal someone else's information.

Report sensitive findings privately to `jydu_seven@outlook.com` with the
subject `OpenKaggle security` or `OpenKaggle publication concern`. Include the
affected repository or release URL, a concise impact description, minimal
reproduction details, and any suggested mitigation. Redact secrets rather
than attaching them, and avoid accessing or copying more data than is
necessary to demonstrate the issue. If GitHub private vulnerability reporting
is enabled for the affected repository, that channel is also appropriate.

The maintainer will aim to acknowledge a report within seven days and will
share a follow-up when the assessment or remediation path is clear. These are
targets, not an enterprise support SLA. Depending on the finding, the first
safe action may be to hide a release asset, remove a public link, rotate a
credential, or pause publication while the repository history and manifests
are checked. A deleted file in the current branch is not assumed to erase old
Git objects or cached release assets.

For a suspected restricted-data or privacy exposure, include the public URL or
path and why it is a concern, but do not quote or resend the affected rows.
The maintainer will record a minimal public correction or withdrawal notice
after the private assessment when doing so is safe.

Historical research repositories may be archived and unsupported. Their README should state maintenance status and known runtime limits.
