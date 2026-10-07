---
name: publish
description: Force-publish the intended state by bypassing only eligible repository or deployment-process gates while preserving external platform protections.
---

# Publish

## Shared contracts

- [core](../../.agent/contracts/core.md)
- [authorization](../../.agent/contracts/authorization.md)
- [verification](../../.agent/contracts/verification.md)
- [deployment](../../.agent/contracts/deployment.md)
- [handoff](../../.agent/contracts/handoff.md)

## Project context

Read `AGENTS.md` and [.agent/project.yaml](../../.agent/project.yaml).
Use [public-config maintenance](../../.agent/workflows/public-config.md) for
source checks and runtime boundaries. Read [integrations](../../.agent/integrations/README.md)
when external work state or delivery is involved.

## Workflow and decisions

1. Establish explicit force-publication intent, target/state and authority for the effect.
2. Identify the exact normal deployment blocker; classify whether it is repository/process controlled or externally enforced.
3. Apply the deployment contract's eligibility rules. Stop at external protections, including required reviews/checks and protected environments.
4. For an eligible authorized process bypass, use the minimum force path and record failed/skipped/bypassed status truthfully.
5. Verify resulting live identity/behavior and report the bypass, evidence and remaining limitations.

An administrator credential never permits external-control bypass. Missing target
configuration is not an eligible gate. There is no preconfigured force-publication
path in this repository. Do not force-push, rewrite history, broaden private-file
access or invent a hosting system. Ordinary public Git source delivery uses push;
normal deployment uses deploy. Clarify ambiguous force intent before bypassing anything.

## Completion and handoff

Report the blocker classification, authority, exact eligible bypass (if any),
resulting state and live verification. An external block remains blocked.
