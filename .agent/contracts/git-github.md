# Git and GitHub

1. Record machine-readable status, HEAD, branch/upstream, remote URL and relevant
   file hashes/EOLs. Read scoped guidance. Fetch `origin --prune`; verify
   `https://github.com/jikovec/CS2.git`, live default branch and intended target.
2. Inspect relevant live Issues, PRs, Projects, checks, branches, tags/releases,
   protection/Rulesets and deployment triggers. Reuse existing work items. GitHub
   work tracking does not substitute for technical evidence or grant authority.
3. Use a `codex/` topic branch. If original paths are dirty or another worker owns
   them, use a worktree from the verified base. Do not reset, stash, clean or
   broadly stage. Preserve the original checkout and source copies.
4. Synchronize clean branches by fast-forward when possible. Merge upstream into
   a diverged topic branch without rewriting history. Resolve only understood
   conflicts in scope; otherwise report the exact conflict. Never force-push or
   rebase published history. Do not integrate into an overlapping dirty checkout.
5. Run relevant verification. Stage exact reviewed paths with ordinary `git add`.
   Inspect the complete staged diff, names, EOLs and `git diff --cached --check`.
   The deny-by-default ignore policy must remain effective at every new depth.
   Commit cohesive changes with concise imperative subjects following local history.
6. Push the topic branch and create/update a PR against the verified base. Use a
   draft initially unless requested otherwise. Describe final behavior and actual
   validation; no private conversation excerpts or fabricated readiness claims.
7. Inspect current head checks, reviews, conflicts and requirements. Fix task-caused
   failures, rerun affected checks and update the PR. Mark ready when the requested
   workflow and actual state warrant it. Merge only after applicable requirements
   pass, using an allowed merge method and matching the reviewed head commit.
   Never use administrator bypass. An absent CI workflow is not a passing CI run.
8. Verify PR merge state and resulting remote default-branch commit/tree. Fetch and
   verify locally; fast-forward a clean delivery worktree when safe. A dirty original
   checkout may remain behind deliberately: report it without overwriting work.
   Clean up only completed task branches/worktrees that contain no unique work.

Revalidate policy and indirect deployment effects before push/merge. The ordinary
source delivery grant is defined in [authorization.md](authorization.md); release,
deployment and force publication semantics are in [deployment.md](deployment.md).
