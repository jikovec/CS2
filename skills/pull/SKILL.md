---
name: pull
description: Safely synchronize local repository state with upstream while preserving unrelated work and reconciling conflicts according to repository conventions.
---

# Pull

## Shared contracts

- [core](../../.agent/contracts/core.md)
- [authorization](../../.agent/contracts/authorization.md)
- [git-github](../../.agent/contracts/git-github.md)
- [handoff](../../.agent/contracts/handoff.md)

## Project context

Read `AGENTS.md` and [.agent/project.yaml](../../.agent/project.yaml).
Use [public-config maintenance](../../.agent/workflows/public-config.md) for
source checks and runtime boundaries. Read [integrations](../../.agent/integrations/README.md)
when external work state or delivery is involved.

## Workflow and decisions

1. Inspect status, local HEAD, current branch/upstream, remote and applicable guidance.
2. Fetch the intended remote and verify upstream/default identity.
3. Compare local/upstream history and inspect overlapping dirty or untracked work.
4. Fast-forward a clean checkout when possible. Reconcile divergence with a non-rewriting merge according to the Git contract.
5. If dirty overlap prevents integration, preserve it; use an isolated view for independent inspection and report the unsynchronized checkout.
6. Surface unresolved conflicts with exact paths and verify the resulting local status/ref and relevant checks after integration.

A fetch is not checkout synchronization. Never use destructive reset, stash or
clean as the default mechanism. Do not overwrite concurrent work. Use investigate
for an upstream status question that does not request local integration.

## Completion and handoff

Report prior/resulting refs, actual integration strategy, preserved local work and
any conflicts. Do not claim synchronization when only the remote-tracking ref moved.
