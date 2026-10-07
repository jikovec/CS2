---
name: build
description: Implement substantial repository changes and carry them through relevant verification and normal repository completion workflow.
---

# Build

## Shared contracts

- [core](../../.agent/contracts/core.md)
- [authorization](../../.agent/contracts/authorization.md)
- [verification](../../.agent/contracts/verification.md)
- [git-github](../../.agent/contracts/git-github.md)
- [handoff](../../.agent/contracts/handoff.md)

## Project context

Read `AGENTS.md` and [.agent/project.yaml](../../.agent/project.yaml).
Use [public-config maintenance](../../.agent/workflows/public-config.md) for
source checks and runtime boundaries. Read [integrations](../../.agent/integrations/README.md)
when external work state or delivery is involved.

## Workflow and decisions

1. Establish the requested end state, current source, affected paths and relevant Git baseline.
2. Inspect existing patterns and preserve architecture; make ordinary implementation decisions within the task.
3. Implement the coherent change, updating stale canonical documentation and preserving unrelated work.
4. Run relevant source/toolkit or runtime checks. Repair task-caused failures and rerun affected checks.
5. Complete the authorized Git/GitHub workflow through its valid endpoint; report any external block.

Use fix for an identified defect or incomplete prior change. Build is substantial
implementation, not a request to invent a build system for this repository.
`develop` is an alias for this workflow. Load memory/scope contracts only when
persistent context, identity or promotion is actually involved.

Do not automatically release, install, deploy or force-publish merely because
implementation and PR delivery are complete.

## Completion and handoff

Report changed behavior, source verification and the actual commit/PR/merge state.
Completion requires the requested implementation and authorized delivery, not a plan.
