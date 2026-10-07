---
name: push
description: Finalize completed local work through the repository's normal commit, push, pull-request, check, and merge workflow.
---

# Push

## Shared contracts

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

1. Inspect the current worktree, source changes, branch/upstream and remote target.
2. Refresh existing PRs, relevant work items, checks/protections and delivery triggers.
3. Preserve unrelated work; verify and stage only exact reviewed task paths.
4. Create coherent commits, push the topic branch and create/update the target PR.
5. Inspect current checks/reviews and remediate task-caused failures.
6. When permitted and requirements pass, mark ready, merge and verify remote/default-branch state.

Follow the shared Git contract for isolation and the detailed PR lifecycle. This
workflow finalizes completed work; use build/fix for substantial remaining edits.
A task may explicitly stop at local commit, push or PR. Do not extend that limit.
Source publication is not a tag/release, deployment or in-game acceptance.
Read deployment rules if a discovered trigger causes runtime effects.

## Completion and handoff

Report delivered commit and PR, check/review status, merge/default ref and any
preserved dirty checkout. If externally blocked, identify the exact remaining gate.
