---
name: new-project
description: Guide project definition, approved online comparison research, design, implementation planning, repository bootstrap, and handoff when the user explicitly invokes $new-project. Recover the current stage when resuming an existing project. Do not activate from general project-starting intent or ordinary feature work.
---

# New Project

Use only when the user explicitly requests this skill in their prompt. Turn an idea into a reviewed, actionable implementation plan, or recover an existing project's actual stage. Explicit invocation does not mean restarting discovery.

Default to planning and a new-chat handoff. Explain that this produces project context and an implementation plan; a runnable application comes during implementation. Do not scaffold or implement the application unless explicitly requested. A separately authorized feasibility experiment may inform a planning decision. The user's explicit workflow choices take precedence.

## Start at the actual stage

Resolve the intended project directory and immediate request from conversation and local evidence. Distinguish the project directory from an enclosing Git repository. Inspect applicable instructions, relevant top-level docs, Git root/worktree, uncommitted changes, remotes, and existing plans. Inspect a missing directory's parent; if the path is a file or the intended target is consequentially ambiguous, resolve that before writing. Inspect secret-bearing files by name only.

Read [continuity](references/continuity.md) before creating documents or recovering state. Use [the instruction standard](references/agents-standard.md) to make navigation reachable through the active project instruction file, then maintain it as facts become established. Preserve unrelated files and instructions.

Report the inferred stage and next unresolved decision. Reuse valid work: a document is not proof of approval, and a checklist is not implementation evidence.

- **New idea:** begin definition and tailor depth using the project cues in [stage deliverables](references/stages.md).
- **Existing brief, research, design, or plan:** resume at the first incomplete or unapproved relevant decision. Revisit only work invalidated by changed premises.
- **Implementation underway or complete:** compare the plan with source and verification evidence; prepare continuation or completion context without forcing discovery or inventing a new roadmap.
- **Bootstrap only:** follow [repository setup](references/repository-setup.md); do not impose product discovery, participation interviews, or market research.

For lifecycle work, read [collaboration](references/collaboration.md) when participation preferences, the work-log choice, or a review is unknown or needs revision; otherwise reuse the recorded agreement. For bootstrap-only work, ask about a work log only when creating durable instructions and no earlier choice is known; then read [the work-log guidance](references/collaboration.md#optional-work-log).

## Finish, show, ask, and wait

Read [stage deliverables](references/stages.md) for the active stage. Finish, verify, and show each result. Pause only for a material decision, unapproved external operation, or recorded checkpoint.

| Decision point | Default stop |
| --- | --- |
| Definition/research | Resolve the remaining brief, research-scope, or direction decision. |
| Design | Review the design and ask whether to continue to the implementation plan. |
| Implementation plan | Review the plan and ask whether to prepare the handoff. |
| Handoff | Implementation needs an explicit start request. |

At a checkpoint, save and link the reviewed result, summarize it using the collaboration guidance, and ask for the next action. Do not draft a later stage while required approval is pending. Record the explicit response against the reviewed revision; silence or a timeout is not approval. Reuse prior approval and authorization for the same result and action. A scoped request can authorize later work or research, but cannot bypass a checkpoint chosen by the user or recorded in the agreement; only the user may remove or combine one.

Design approval permits implementation planning, and plan approval permits handoff. Record either separately from execution authorization. Without an explicit start request, record “awaiting user request.” Comparison research needs permission covering that comparison; reuse an existing request for the same scope and record a skip or stop outcome.

## Supporting skills and completion

Use an available supporting skill only when its scope helps the current stage; an optional unavailable skill never blocks this lifecycle.

When creating or revising project instructions or another document written primarily for agents, use `writing-for-agents` as an authoring discipline when it is available. Keep lifecycle decisions, document roles, filenames, and authorization boundaries in this skill; do not make the project depend on the supporting skill.

For authorized internet research, use `agent-reach` as the research-retrieval skill when it is available. Follow its platform routing, backend checks, and retry guidance. Keep research authorization, query boundaries, evidence assessment, synthesis, recommendations, and lifecycle records in this skill; `agent-reach` retrieves source material and does not replace those responsibilities. Do not silently substitute another internet-research workflow when `agent-reach` or a required channel is unavailable; report the coverage gap and let the user decide whether to continue with narrower evidence.

At material decisions, completed deliverables, or handoffs, update state and affected navigation. If the user enabled a work log, update it only for an important completed or materially changed milestone, following [continuity](references/continuity.md). Verify document links, consistency, approval status, and that paths/commands are evidenced or labeled proposed. Before handoff, check requirement-to-plan coverage as described in the stage reference. Before commits/pushes, verify local-only documents remain ignored and untracked only when they exist, changed, or might be staged. Run diff whitespace checks when applicable; do not run application builds for planning-only edits.

End with the project path, stage reached, deliverable links, verification, and the exact pending decision or next action. Never label a draft approved, an approved plan authorized for execution without evidence, or planned work implemented.
