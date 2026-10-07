# Verification

Classify every relevant result as exactly one of: **passed**, **failed**,
**blocked/unavailable**, **intentionally bypassed**, or **not required**.
An unexecuted check is never passed. Preserve command, target/ref, outcome and
material limitations in the handoff or PR, not in stable project identity metadata.

Choose checks proportional to the change and supported by repository truth.
Use [public-config checks](../workflows/public-config.md). For toolkit changes,
parse YAML/frontmatter, check skill names, canonical references, thin adapters,
symlink resolution, exact ignore allowances and routing counterexamples. A parser
check is structural evidence, not a behavioral evaluation. Try native discovery
without running a mutating agent task where the provider exposes that capability.

There is no game test suite, build or configured CI. Do not invent successful CI
from an empty check list. Refresh GitHub requirements before delivery. Source
checks, provider discovery, remote delivery and actual in-game acceptance are
separate evidence. Game-command compatibility needs the intended CS2 build and
permitted server context. Do not claim it from syntax inspection.

Fix the cause of a failing check and rerun affected checks. Do not relax criteria
or change runtime behavior solely to make checks pass. Stop expanding validation
once relevant concerns are resolved. Explicit bypasses remain visible as bypasses.
