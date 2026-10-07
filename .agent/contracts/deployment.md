# Release, deploy and publish

**Release** manages a named version, tag, notes, assets or release record. It does
not inherently install configs or make them live. Discover actual conventions
from current tags/releases; this repository has a historical GitHub `v1.0.0`
release, but no release automation or version manifest. Do not invent a next
version, move an existing tag or copy historical claims as fresh verification.

**Deploy** follows the normal governed path to a specified runtime. Honor repository
checks, migrations/health requirements when real, and external controls. No hosted
deployment configuration is defined here. A Git push is a source update. Copying
configs into a game installation and executing them are separate runtime effects;
require the intended installation, selected files, backup/rollback and authority.
If the target/process is unspecified, complete source preparation and request the
missing target or authority instead of inventing infrastructure.

**Publish** means explicit force publication in this toolkit. Ordinary requests
to publish reviewed source on GitHub use the normal Git workflow unless force
intent is established. Do not silently escalate a blocked deploy into publish.

For an authorized force publication:

1. Identify the exact normal deployment blocker and intended state/target.
2. Classify the gate and who controls it. Only repository-controlled or
   deployment-process-controlled gates can be eligible; this is not blanket
   permission to bypass any repository safety, privacy or data boundary.
3. Confirm force-publication authority covers that effect and use the minimum
   eligible bypass. Record every failed, skipped or intentionally bypassed check.
4. Preserve external GitHub branch protection, Rulesets, required checks/reviews,
   environment approvals, organization governance, hosting policy, IAM and cloud
   protections. Administrator credentials never make these eligible bypasses.
5. Verify the resulting deployed identity and live state, and report rollback
   readiness and remaining limitations. If externally blocked, report the block.

Missing deployment configuration is not a gate to bypass. Release, deploy and
publish skills remain available as entry points, but must discover a real target
and procedure before action. Consult [public-config.md](../workflows/public-config.md)
for in-game evidence boundaries.
