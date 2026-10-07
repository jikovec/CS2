---
name: release
description: Prepare and complete the repository's normal release workflow, including versioning, notes, tags, artifacts, or release records where applicable.
---

# Release

## Shared contracts

- [core](../../.agent/contracts/core.md)
- [authorization](../../.agent/contracts/authorization.md)
- [verification](../../.agent/contracts/verification.md)
- [git-github](../../.agent/contracts/git-github.md)
- [deployment](../../.agent/contracts/deployment.md)
- [handoff](../../.agent/contracts/handoff.md)

## Project context

Read `AGENTS.md` and [.agent/project.yaml](../../.agent/project.yaml).
Use [public-config maintenance](../../.agent/workflows/public-config.md) for
source checks and runtime boundaries. Read [integrations](../../.agent/integrations/README.md)
when external work state or delivery is involved.

## Workflow and decisions

1. Confirm release intent, target commit and authority; inspect live releases/tags for duplicates.
2. Discover actual versioning, notes, tags, assets and release procedures. Do not invent absent machinery.
3. For this repository, inspect the historical GitHub release and current public config set; do not copy stale claims.
4. Verify the intended source and review precisely what the release would disclose.
5. If the version or intended assets are unspecified and cannot be established, prepare the release and request the missing decision.
6. Under valid authority and applicable gates, create the intended tag/release and verify its target, notes and assets remotely.

Use push for source/PR delivery without a release record. A release does not install
configs or authorize deployment. Never move existing tags or imply that source
verification is in-game acceptance. Do not create a new release for routine toolkit work.

## Completion and handoff

Report version/tag, resolved commit, release URL, verified artifacts and source
checks. State independently whether any deployment or game test occurred.
