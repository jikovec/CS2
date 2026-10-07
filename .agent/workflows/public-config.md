# Public-config maintenance

## Source and disclosure

Root `autoexec*.cfg` files target CS2. `legacy/csgo/` is an archive of historical
CS:GO settings. `README.md` describes public use; `.gitignore` names permitted
public paths. Work from exact requested files, never the enclosing gaming folder.
Review both the source material and destination before importing anything.

`autoexec.cfg` starts by clearing binds and ends with `host_writeconfig`.
The practice helpers use cheat-gated commands. Installing/executing them can change
and persist settings. Source inspection does not establish CVar availability on
the current game build. Historical settings are not CS2 acceptance evidence.

Preserve recorded bytes/EOLs of unchanged configs. Review changed commands, aliases,
binds, `exec` dependencies, server context and effects against actual source.
Do not normalize the four CRLF root helpers as incidental toolkit maintenance.

## Relevant manual source checks

There is no application build/package manager, automatic game test or project CI
command. From the repository root use these proportionately:

```sh
git status --porcelain=v2 --branch
git remote -v
git ls-remote --symref origin HEAD refs/heads/main
git diff --check
git diff --cached --check
git diff --cached --name-only
git diff --cached
git ls-files --eol
git fsck --no-reflogs --full
git check-ignore -v --no-index private-candidate.demo
```

The final command should show the rejecting rule; its matched/ignored result is
the intended outcome. For allowlist changes, test private candidates at the root
and inside every newly opened directory, and ensure named public files remain
addable without force. Never permit arbitrary content by unignoring a whole tree.
Compare config blob identities when a change promises to leave settings untouched.

Toolkit changes additionally need parsed metadata/frontmatter, reference resolution,
provider discovery checks where possible and [routing cases](../evals/skill-routing.md).
Run such ad hoc validation with available tools; do not add a package runtime just
for documentation. Keep temporary validation artifacts outside the public tree.

## Runtime and delivery evidence

Use the selected root config and a permitted local/practice context. Before any
authorized game installation, confirm the actual target and backup/rollback; the
Windows path in README is documentation, not proof of the user's current install.
Record the game build, executed config, relevant console output and observed
behavior when an in-game test actually occurs. Never infer acceptance from Git.

Source delivery follows [git-github.md](../contracts/git-github.md). Read the
[deployment contract](../contracts/deployment.md) for release/install/force intent.
A tagged source release is still distinct from installation and live behavior.
