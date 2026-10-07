# Hooks

No executable or provider hook is installed. Manual source checks are documented
in [public-config.md](../workflows/public-config.md). Recurring synchronization and
hook activation require an explicitly scoped policy under `AGENTS.md`.

If a real deterministic invariant later warrants a hook, document its trigger,
purpose, inputs, side effects, expected runtime, dependencies, manual invocation,
exit codes and failure behavior. Keep it fast, idempotent where practical and
independently testable. Shared implementations belong here or in an established
native script location; provider configuration should reference them.

Architecture review, root-cause reasoning, severity and completion decisions remain
agent work. Do not silently install Git hooks or automatic external integrations.
