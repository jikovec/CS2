---
name: fix
description: Diagnose and repair a known defect, failed check, incomplete prior change, review finding, or inconsistency between authoritative project states.
---

# Fix

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

1. Identify the defect, failed check, review finding or inconsistent state and the intended behavior.
2. Reproduce or collect direct evidence; diagnose the causal defect rather than hide symptoms.
3. Apply the smallest coherent repair and update stale canonical documentation in scope.
4. Run meaningful affected checks; add regression coverage only where a real test surface and defect justify it.
5. Complete authorized Git/GitHub delivery and inspect current checks/review after changes.

`reconcile` means fix with state-reconciliation intent. Separate repository truth,
documentation, Git, GitHub, runtime/deployment, registry, memory and old handoffs.
Read memory/scopes only if reconciliation crosses persistent state. Reuse existing
work objects; do not manufacture memory/registry authority. Use build for a new
substantial capability and investigate when only diagnosis was requested.

## Completion and handoff

Report the cause, repair, evidence that the original failure is resolved and actual
delivery state. Name unreproduced behavior or required runtime validation candidly.
