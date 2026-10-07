# Integrations

Only GitHub is configured by repository identity. Canonical binding is the Git
`origin` remote for `jikovec/CS2`; [.agent/project.yaml](../project.yaml) records
stable discovery metadata. Live GitHub APIs are authoritative for Issues, PRs,
Projects, branch rules, checks, releases and deployment records.

Git performs fetch/push; an authenticated `gh` CLI or available GitHub connector
can inspect and mutate work state under [authorization](../contracts/authorization.md).
Read access and write capability must be checked independently. Credentials come
from the user's existing credential helper/CLI login or authorized connector,
never repository files or logs. Do not print tokens or install a recommended plugin
merely because it is listed. Tool availability does not grant authority.

Refresh remote controls and delivery triggers before mutations. Configuration does
not imply this session is authenticated. There is no declared hosting integration,
registry or memory backend, and no organization binding. Add integration documents
only for actually configured services, naming canonical config, external service,
read/mutation behavior, required tooling, project binding and credential source.
Do not commit secrets, credentials or duplicate live service state.
