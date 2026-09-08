# Continuity and local documents

Read before creating documents, recovering progress, or handing off. Use maintained Markdown as a small recovery record, not a second project-management system.

## Local-only working documents

Default to `.project/` at the intended project root. Reuse an intentional local-only planning location when one exists and record the actual paths. Create only what the current stage needs.

| Suggested path | Purpose |
| --- | --- |
| `.project/state.md` | Current focus, authoritative document map, approvals, blockers, and next action |
| `.project/brief.md` | Purpose, audience, scope, constraints, success criteria |
| `.project/research.md` | Dated evidence, comparison, chosen direction |
| `.project/design.md` | Product behavior and proposed/approved technical decisions |
| `.project/implementation-plan.md` | Working increments, checks, milestone boundaries |
| `.project/handoff.md` | Latest implementation or continuation starter prompt |
| `.project/work-log.md` | Optional plain-language history of important milestones |

These are roles, not six required files. A small project may keep brief, design, and plan in one document with clearly labeled sections and separate approval statuses. Combining documents never combines stage approvals automatically. Keep state as the concise index; record section anchors when several roles share a document.

Add `/.project/` to the intended repository-root `.gitignore` before creating local artifacts. In a larger repository, use the exact root-relative project path or an appropriate nested ignore file without hiding siblings. Without Git, write the intended project's ignore file; do not initialize Git just to check exclusion. Verify after later initialization.

Keep generated research, plans, designs, previews, exports, and experiment artifacts under an ignored location. If the user chooses another location, add narrowly scoped ignore entries before staging. Avoid broad patterns such as `*.md` or `docs/` that hide maintained product documentation. Project instruction files, `.gitignore`, and a requested README may be tracked; do not copy private research/plans into them. An artifact intended to ship follows the user's explicit publication choice.

An existing tracked document remains tracked after adding an ignore rule. Preserve local content and unrelated changes; inspect staging and references before proposing exact index-only removal and navigation changes. Remove from the index only within authorization, without discarding staged edits or rewriting history. If previously published, history remains. Do not claim exclusion while a document is tracked or staged.

Before commits/pushes, inspect status and the intended staged diff. When local-only planning artifacts exist, changed, or might be staged, also inspect relevant `git ls-files`, verify actual document paths with `git check-ignore -v -- <paths>`, and confirm they are untracked. Avoid force-adding local notes or sweeping unrelated files into staging. Ignoring is neither encryption nor synchronization.

## Optional work log

Create a work log only after the user opts in, or reuse an existing log they choose to maintain. Default to `.project/work-log.md`; treat it as local-only unless the user explicitly chooses to publish it. Record its actual path and active status in `state.md`, and add that repository-relative path to the active project instruction file. Do not create a parallel log if the project already has an intentional one.

The work log is a short, human-readable history. It does not replace state, approval evidence, detailed plans, research, or technical verification. Update state first, then summarize an important outcome in the log: an approved stage result, a major direction change, a completed and verified implementation milestone, or a blocker that materially pauses or redirects the project. Do not log routine edits, individual commands, draft revisions, repeated attempts, ordinary questions, or every conversation.

Use this simple hierarchy: a year bullet, a date sub-bullet, then outcome bullets. Add new dates in chronological order. Each outcome bullet has one or two clear sentences. Split independent outcomes into separate bullets.

```markdown
# Work Log

- 2026
  - 7.15
    - Finished the first playable tutorial and created the project repository.
    - Approved the game design. The next step is the implementation plan.
```

Keep the entry factual: what changed, what was decided, or what became ready. Link a relevant project document only when it materially helps the reader. Do not copy state fields, approval transcripts, raw tool output, or every implementation detail into the log.

## State and approval evidence

Keep state dated and concise, with:

- Project/subproject identity, purpose, current stage or milestone, and last meaningful activity/stopping point.
- Actual authoritative paths/sections and status: draft, approved, skipped, stale, superseded. Separate proposed architecture from what exists.
- The collaboration agreement: decision ownership, explanation depth, relevant learning goals, preview preference, and review checkpoints. Unanswered preferences are not delegation.
- Whether the optional work log is active or declined and, when active, its actual path. State remains authoritative when the log and state differ.
- Approval evidence: reviewed document revision or section revision, date, explicit response summary/reference, conditions, and the permitted next action. Record plan approval separately from execution authorization; use “awaiting user request” when execution is not authorized.
- Material decisions/reasons, open questions, assumptions, blockers, and the next concrete action. Link detailed rationale instead of duplicating it.
- Completed work and verification evidence, including what ran versus what did not. For significant implementation evidence, identify the checkout/revision and relevant uncommitted changes tested; use paths/artifact revisions when Git is absent.

Use a revision label or precise timestamp that identifies the reviewed result. Material edits make affected approvals stale; unrelated approvals remain valid, including unaffected sections of a combined document. Do not infer approval from file presence or completion from a checklist. Never rewrite historical authorization to match a new preference.

Read the current state again before materially updating it and reconcile intervening changes. Update at decisions, milestones, interruptions, and handoffs rather than every edit. Keep the active record a digest; move substantial superseded detail into linked local history only when needed. Avoid competing status trackers. If concurrent chats are actually working on the project, establish one owner of canonical state updates and collect other results for reconciliation; do not introduce a locking system for sequential use.

## Recovery and navigation

Resolve active instructions using [the instruction standard](agents-standard.md), then read local state and only the documents relevant to the request. Compare their claims with current source, Git state, and validation evidence. A branch change or unfinished code can invalidate implementation status without invalidating the brief. Do not reset the lifecycle merely because filenames differ.

When state is absent, infer progress from existing documents/code and the user's current request. Preserve useful documents and write a concise map. Ask only for consequential missing approvals or conflicts; the user may approve adoption of existing work without repeating discovery. Do not reconstruct private plans or authorization as facts. For completed implementation, record completion and remaining requested work instead of inventing a roadmap.

When creating or updating navigation, follow [the instruction standard](agents-standard.md). Point later agents to state and authoritative documents; when a work log is active, include its local-only path and update threshold. Keep changing stage information in state.

Label ignored documents local-only and absent from fresh clones. If absent, use tracked instructions/docs/source for ordinary work and request missing context only when the task depends on it. A new chat in the same directory can use the notes without invoking this lifecycle skill. Another checkout or host needs the verified transfer described in [handoff](stages.md#handoff). A tracked summary offers orientation but cannot substitute for an unavailable detailed execution plan.
