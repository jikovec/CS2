---
name: review
description: Review a change, branch, pull request, or implementation for material correctness, regression, architecture, security, and maintainability issues.
---

# Review

## Shared contracts

- [core](../../.agent/contracts/core.md)
- [verification](../../.agent/contracts/verification.md)
- [handoff](../../.agent/contracts/handoff.md)

## Project context

Read `AGENTS.md` and [.agent/project.yaml](../../.agent/project.yaml).
Use [public-config maintenance](../../.agent/workflows/public-config.md) for
source checks and runtime boundaries. Read [integrations](../../.agent/integrations/README.md)
when external work state or delivery is involved.

## Workflow and decisions

1. Identify the change, base/head and requested behavior. Read the Git contract for branch/PR review.
2. Inspect the relevant diff and context, preserving independent judgment from prior summaries.
3. Prioritize correctness, requested behavior, regressions, contracts, architecture, security, tests and maintainability.
4. Consider performance/accessibility only where relevant; avoid burying defects under style noise.
5. Substantiate actionable findings with location, trigger, consequence and severity. Run focused checks when useful.

Review discovers material defects; verify checks specific claims. Do not turn a
review request into implementation, PR approval or merge authority. Existing
source-only evidence cannot establish game compatibility. If no actionable issue
is found, say so and state material coverage limits without inventing findings.

## Completion and handoff

Return actionable findings first, with precise paths/lines and evidence. Distinguish
review conclusions from test results and any unreviewed runtime behavior.
