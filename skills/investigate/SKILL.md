---
name: investigate
description: Inspect repository, runtime, or work state to establish current behaviour, root cause, or required work without changing implementation by default.
---

# Investigate

## Shared contracts

- [core](../../.agent/contracts/core.md)
- [handoff](../../.agent/contracts/handoff.md)

## Project context

Read `AGENTS.md` and [.agent/project.yaml](../../.agent/project.yaml).
Use [public-config maintenance](../../.agent/workflows/public-config.md) for
source checks and runtime boundaries. Read [integrations](../../.agent/integrations/README.md)
when external work state or delivery is involved.

## Workflow and decisions

1. Identify the local behavior, root-cause question or work-state uncertainty.
2. Inspect the smallest relevant source/configuration and fresh evidence. Reproduce read-only observations when safe.
3. Trace causes and alternatives; separate observed, supported, inferred and unknown conclusions.
4. State the required work or missing evidence without silently implementing a remedy.

Read the Git contract when inspecting branch/PR state. Read memory and scopes only
for registry/persistent/cross-project context. Use research for external technical
evidence, verify for testing a specific claim, and fix when repair is requested.

Default to read-only investigation. Do not execute a game config, persist memory,
edit implementation or create a work item just to investigate.

## Completion and handoff

Return the finding, evidence locations, confidence and the next concrete diagnostic
or repair needed. An unexplained symptom remains an uncertainty, not a proven cause.
