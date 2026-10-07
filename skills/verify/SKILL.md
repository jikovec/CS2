---
name: verify
description: Independently verify claimed repository, branch, PR, release, deployment, or live state using current evidence.
---

# Verify

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

1. Turn the claim into observable acceptance criteria and identify the exact target/ref.
2. Retrieve current evidence independently of earlier agent claims.
3. Run the strongest proportional checks supported by the repository and target environment.
4. Classify each relevant result using the verification contract; preserve failures and unavailable evidence.
5. Explain whether the evidence establishes the claim and which later evidence lanes remain unobserved.

Read Git/deployment contracts when verifying those states; read memory/scopes only
when those bindings or state promotions are under verification. Do not weaken
criteria to produce a pass. Default to verification without repair; use review
for discovering defects in a change and fix for an authorized repair.

## Completion and handoff

Report target, checks, outcomes and practical limits. A clean source diff does not
prove a config works in CS2, and an absent hosted check is not a passing check.
