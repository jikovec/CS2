# Memory authority

> Memory is contextual state, not repository truth.

Memory may assist discovery, retain user-approved context, describe historical
relationships, or point to accepted decisions. It cannot override current source,
configuration, tests, schemas, manifests, Git, live GitHub state, runtime evidence
or accepted repository decisions. It cannot manufacture authorization.

No repository memory backend is configured. When a session offers memory, establish
its backend, readable scopes, permissions and freshness under that provider's rules
before use. Access alone grants no write authority. Reconcile memory-derived facts
with the current authoritative source; classify conflicts as stale/contextual.
Do not silently repair persistent memory merely because a discrepancy is found.

A write requires a writable destination, explicit or standing mutation authority,
appropriate information and the [scope promotion rules](scopes.md). Respect any
stricter platform requirement, including explicit-request-only memory writes.
Do not promote hypotheses, session observations, temporary failures or unverified
interpretations automatically. Do not store secrets or unnecessary sensitive data,
or write memory just to record that ordinary work occurred.

Durable technical decisions belong in accepted repository documentation first,
then the commit/accepted state, then an authorized memory pointer or summary.
Preserve ADR/spec/Issue/PR references rather than duplicating canonical content.
If later configured, `.mind-seed/` holds verified bindings and authority metadata;
live mutable memory stays in the external configured system by default.
