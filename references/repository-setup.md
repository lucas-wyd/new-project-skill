# Repository setup

Use when the user requests local bootstrap or Git/GitHub operations. Product definition does not imply publication. Repository setup can happen when needed; it is not a reason to delay an otherwise useful brief or to create an unused remote before the research decision.

Resolve the absolute project path, name, and new/existing status. Inspect applicable instructions, relevant files, Git root/worktree, changes, and remotes. Initialize Git only when requested at the intended root and when it is not already in a repository/worktree. Preserve unrelated changes and inspect secret-bearing files by name only.

Resolve and update the active project instruction file using [the instruction standard](agents-standard.md); default to `AGENTS.md` when no override applies. Verify navigation from the intended project directory. Add a minimal README only when requested or needed for the authorized setup. When local working documents will be created, apply the working-document ignore rules in [continuity](continuity.md) before staging.

For unresolved repository choices, read [interactive questions](collaboration.md#interactive-questions) without running the lifecycle participation interview. For GitHub creation, settle owner, repository name, visibility, and whether an initial commit/push is wanted. Explain consequential choices when the user is unsure. Never infer public visibility or publishing permission from a local-file request. Use available connected tooling or `gh`, checking access without exposing credentials.

Stage only intentionally included files; commit, create a remote repository, add/change remotes, and push only within the settled authorization. Prepare exact contents and identify the external effect before asking for any still-required approval. Existing authorization remains valid; do not repeat a completed approval step.

Do not reset/clean the working tree, discard files, overwrite unrelated configuration, rewrite history, or force-push. Replacing a remote requires authorization for that target. If access fails or a creation result is ambiguous, inspect the outcome before retrying; finish independent local work and report the blocker accurately.

Verify affected files, active instruction discovery/navigation, Git status, remotes, and diff whitespace when applicable after operations. When local-only planning artifacts exist, changed, or might be staged, also verify that they are ignored and untracked. Report the local path and actual Git/GitHub outcome. Do not choose a framework, scaffold application source, install dependencies, or add CI just to bootstrap a repository.
