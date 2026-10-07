# Repository agent toolkit

The portable identity is [project.yaml](project.yaml); [../AGENTS.md](../AGENTS.md)
is the always-on policy. Canonical reasoning workflows live in [../skills/](../skills/).
Choose one workflow and load only its required contracts. All backticked repository
paths in this toolkit resolve from the repository root unless stated otherwise.

| Intent | Canonical skill |
| --- | --- |
| Substantial implementation; develop | [build](../skills/build/SKILL.md) |
| Establish local behavior or root cause, read-only | [investigate](../skills/investigate/SKILL.md) |
| External evidence and alternatives | [research](../skills/research/SKILL.md) |
| Check a claim against fresh evidence | [verify](../skills/verify/SKILL.md) |
| Find material defects in a change | [review](../skills/review/SKILL.md) |
| Repair a known defect; reconcile states | [fix](../skills/fix/SKILL.md) |
| Version/tag/release record | [release](../skills/release/SKILL.md) |
| Normal governed delivery to a runtime | [deploy](../skills/deploy/SKILL.md) |
| Explicit force publication through eligible process gates | [publish](../skills/publish/SKILL.md) |
| Deliver completed source through PR and merge | [push](../skills/push/SKILL.md) |
| Synchronize a local checkout | [pull](../skills/pull/SKILL.md) |

`develop` and `reconcile` are semantic aliases, not duplicate skills. In Codex,
select the repository skill (for example `$build`); in Claude Code use `/build`.
If a personal or built-in command shadows a short name, explicitly reference the
canonical repository file. Provider selection is discovery, never authorization.

## Shared and conditional context

[Contracts](contracts/) hold core execution, authorization, verification, Git,
deployment, handoff, memory and scope semantics. [Workflows](workflows/README.md)
hold the public-config process. [Integrations](integrations/README.md) identify
GitHub configuration and access. [Hooks](hooks/README.md) records the no-hook setup.
[Routing evaluations](evals/skill-routing.md) cover each workflow's boundaries.

This repository has no configured registry or persistent-memory binding and is
not enrolled into Mind-Seed. Its repository-qualified ID makes no claim about an
external registry. The registry could not be reconciled because no canonical
registry endpoint or binding is configured. A containing filesystem path does not
establish enrollment. Only add `.mind-seed/` after verified enrollment/bindings.
Do not commit mutable memory or manufacture registry, organization or scope IDs.

There is no project-specific skill yet: the shared public-config workflow covers
the existing maintenance process without another reasoning layer. Add a skill
under `skills/project/` only for a real recurring complex task; give it a unique
name, provider adapters and routing examples. No empty extension tree is needed.

## Provider discovery

Codex's documented repository location is `.agents/skills/`. Each skill folder
there is a relative symlink to the thin adapter in `.codex/skills/`; this preserves
the requested compatibility surface without another policy copy. Checkouts must
preserve Git symlinks for this route. If the platform cannot, use the canonical
file explicitly; do not claim automatic discovery works there.

Claude's thin adapters live in `.claude/skills/`; `CLAUDE.md` imports `AGENTS.md`.
Both adapter sets point to `skills/`. No provider hook, MCP connection, permission
bypass or automatic synchronization is installed by this toolkit.

Discovery references: [OpenAI local skills](https://learn.chatgpt.com/docs/build-skills),
[Claude skills](https://code.claude.com/docs/en/skills), and
[Claude imports](https://code.claude.com/docs/en/memory). Recheck provider discovery
when upgrading; successful parsing is not proof of actual runtime discovery.
