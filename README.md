# New Project

`new-project` is an explicit-invocation Codex skill for turning a new idea—or the real state of an existing project—into reviewed project context, comparison research, a design, an actionable implementation plan, and a clean implementation handoff.

It is deliberately planning-first. Invoking the skill does not authorize application scaffolding or implementation, and resuming an existing project does not restart discovery from scratch.

## What it does

- Recovers the actual stage of an existing project from its instructions, documentation, source, Git state, and verification evidence.
- Defines the smallest useful outcome, constraints, exclusions, and observable success criteria.
- Performs explicitly authorized comparison research and separates verified facts, vendor claims, inference, and unknowns.
- Produces a proportionate product and technical design.
- Writes an implementation plan in working increments, with verification and review boundaries.
- Prepares a self-contained handoff without treating plan approval as permission to implement.
- Keeps private working documents local and ignored by default.

The workflow can also handle a narrowly requested repository bootstrap without forcing product discovery or market research.

## Installation

Clone the repository into your Codex skills directory:

```bash
git clone https://github.com/lucas-wyd/new-project-skill.git ~/.codex/skills/new-project
```

If `CODEX_HOME` points elsewhere, clone it into that installation's `skills/new-project` directory instead. Restart Codex or begin a new session so the skill is rediscovered.

## Usage

The skill only runs when explicitly invoked:

```text
Use $new-project to help me define and plan a personal finance dashboard.
```

For an existing project:

```text
Use $new-project to inspect this repository, recover its current stage, and continue from the first unresolved decision.
```

For repository setup only:

```text
Use $new-project to initialize and publish this project repository. Skip product discovery.
```

The skill shows each material deliverable for review and stops at the relevant decision boundary. By default, implementation begins only after a separate, explicit start request.

## Local project records

When durable project context is useful, the skill stores it under `.project/` in the target project and adds that directory to `.gitignore`. Typical records include:

- `state.md` — current focus, approvals, blockers, and next action
- `brief.md` — purpose, audience, scope, constraints, and success criteria
- `research.md` — dated evidence, comparisons, and the selected direction
- `design.md` — product behavior and technical decisions
- `implementation-plan.md` — working increments and verification
- `handoff.md` — context for the implementation task
- `work-log.md` — optional milestone history

These records are local-only by default because they may contain private context and do not automatically travel with clones or worktrees.

For a domain-heavy project, the skill may also create a tracked `CONTEXT.md` containing only stable domain terminology and relationships. It is not generated from `AGENTS.md`, does not replace project state or design, and is omitted when the project's language is already clear.

## Supporting skills

- [Agent Reach](https://github.com/Panniantong/Agent-Reach) is the preferred internet-retrieval layer for authorized comparison research. `new-project` retains responsibility for research scope, source assessment, synthesis, recommendations, and lifecycle records.
- `$writing-plans`, when installed, supplies the detailed implementation-plan workflow. `new-project` provides its approved brief, design, constraints, output location, and lifecycle checkpoints.
- `$deep-research` is not invoked automatically. It is reserved for requests that explicitly ask for Deep research.
- An installed review skill may be used for focused review when a material behavior change requires it; no particular review implementation is required.

Unavailable optional skills do not stop the overall lifecycle. For research, however, an unavailable Agent Reach backend is disclosed as a coverage gap instead of being silently replaced.

## Repository layout

```text
.
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── agents-standard.md
    ├── collaboration.md
    ├── continuity.md
    ├── domain-language.md
    ├── repository-setup.md
    ├── stages.md
    └── visual-decisions.md
```

`SKILL.md` contains the shared lifecycle rules. The reference files hold stage-specific guidance so Codex only loads the detail needed for the current decision.
