---
name: deploy
description: Deploy the intended repository state through its normal governed deployment process and verify the resulting live state.
---

# Deploy

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

1. Identify the intended state, runtime target, deployment authority and real normal procedure.
2. Inspect required source checks, external controls, prerequisites, backup/rollback and health criteria.
3. This repository defines no hosted deployment. For requested game installation, confirm exact selected root configs and actual installation path first.
4. Follow the authorized normal procedure, preserving protections and recording resulting identity.
5. Verify the target and live behavior against the requested acceptance criteria, or report the unavailable evidence.

Do not invent a deployment provider or infer a game installation from a README
example. Do not turn a blocked deploy into force publication. Missing configuration
or target is not a gate to bypass. Use release for tags/records and publish only
when explicit force intent and eligible gate bypass authority are established.

## Completion and handoff

Report target, deployed identity, performed checks, observed live state and rollback
status. If blocked, deliver completed preparation and the exact missing prerequisite.
