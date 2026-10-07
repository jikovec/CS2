# Scope semantics

Scope determines visibility and persistence, not a universal override hierarchy.
Identity and authority are defined by data type. No scope is automatically readable
or writable merely because its name appears below. Apply backend/platform controls.

| Scope | Identity and lifetime | Read visibility | Write authority | Inheritance and promotion |
| --- | --- | --- | --- | --- |
| global | Established user/platform identity; durable across projects | Only configured global context | Explicit or valid standing grant for global data | Context may inform lower scopes; promotion into global requires global authority |
| organization | Verified organization ID; organization lifetime | Authorized members/tools only | Organization-governed writers | Lower scopes may narrow policy, never widen prohibited permissions; project-to-organization promotion needs organization authority |
| project | Stable project ID; project lifetime, possibly several repositories | Configured project context | Project owner or valid delegate for that data | Repository binding inherits identity, not every permission; task-to-project promotion requires project authority |
| repository | Verified remote identity; repository lifetime | Public tracked source here; private data excluded | Governing repository/task grants | Source/configuration/accepted decisions are technical truth; do not copy a cross-project graph here |
| agent | Runtime/provider agent identity; assigned agent lifetime | Only explicitly available scopes | Delegated writes within held rights | Agent identity grants no project identity or policy override; agent findings remain contextual |
| task | Assigned objective ID if one exists; task lifetime | Context necessary for that objective | Task-authorized effects in permitted destinations | Narrows work; may grant actions allowed by governing authorization; findings do not auto-promote |
| session | Actual provider session identity; session lifetime | Available session context only | Ephemeral session state, plus separately granted effects | Observations are contextual; session-to-task persistence needs destination authority |

Organization binding is null for this user-owned repository. Dynamic agent/task/
session IDs are not fabricated or committed as stable identity. One project may
span repositories, or one repository may contain several components; a local
binding cannot silently rewrite the canonical registry's broader graph.

A session cannot change project identity; a task cannot redefine organization
identity; an agent cannot invent a canonical project ID. Current repository truth
wins over project/agent/task/session memory. Repository instructions refine generic
execution; task/session intent can narrow work but cannot silently remove safety
or governance. Authorization comes from the governing model, never mere scope depth.

## Promotion

Session-to-task, task-to-project, project-to-organization and organization-to-global
promotion are explicit persistence operations, not automatic inheritance. For each:

1. Identify destination scope, data type and authoritative owner.
2. Verify destination write permission and mutation authority.
3. Check relevance, privacy and appropriate lifetime.
4. Update canonical repository/registry truth first or atomically when applicable.
5. Use a supported persistence mechanism and verify the resulting write.

Durable technical decisions normally enter accepted repository documentation before
or together with memory promotion. If a mechanism or authority is absent, keep the
finding ephemeral. Read [memory.md](memory.md) when persistent memory is involved.
