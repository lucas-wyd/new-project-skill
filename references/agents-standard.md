# Project instruction standard

Use when creating or updating project instructions. Include knowledge that changes an agent's decisions; leave routine implementation judgment to it.

## Resolve the active instruction file

Inspect instruction discovery for the intended working directory before writing navigation. Codex includes at most one instruction file per directory: `AGENTS.override.md` takes precedence over `AGENTS.md`, then configured fallback names. Project guidance follows the path from the project root to the working directory; a sibling or deeper file is not automatically loaded from the parent.

Use `AGENTS.md` when no override applies. If an existing override is active, preserve it and make the project summary/navigation reachable through it, directly or through an explicit reference. Do not put the only navigation in a shadowed file, delete an override, or change global discovery settings to make a new file load. Honor an explicitly requested filename, but disclose if it is not automatically discovered and arrange navigation through the active file when authorized.

For a nested project, place its context within the intended scope; add a short root pointer when tasks started at the enclosing repository need to find it. Verify navigation from the intended task directory. Preserve unrelated instructions and distinguish shared guidance from local overrides.

## What belongs in the file

- Stable product purpose, verified stack, and constraints that prevent concrete mistakes: behavior, architecture boundaries, data protection, licensing, or generated-file ownership.
- Relevant commands and conditional documentation pointers. Verify commands against manifests/scripts or maintained docs; distinguish existence from successful execution.
- A concise project-specific [collaboration agreement](collaboration.md): decision ownership, explanation depth, permitted interactive choices, preview preference, and review checkpoints. Export enough for an agent without this skill to act correctly.
- Navigation to the local state and relevant authoritative documents using [continuity](continuity.md). If the user opted in, include the exact local-only work-log path, identify it as milestone chronology, and say to update it only after important milestones; state remains authoritative for approvals and current status. For example: `Work log: .project/work-log.md — local-only milestone chronology; update only after important milestones. Current status and approvals are in .project/state.md.` Provide basic orientation without publishing private plans.
- The completion and authorization boundaries actually needed by this project: finish and verify a coherent milestone, show the result, ask before advancing, and preserve existing authorization. Plan approval alone is not a start request.

For a blank project omit unknown tools, commands, architecture, and future milestones. Use a few short sections, not a fixed quota or a copy of this reference.

## Domain glossary

A domain glossary is separate from project instructions. Create one only when multiple ambiguous or specialized domain terms materially affect product, design, or implementation decisions. Do not derive it from `AGENTS.md` or create it as a generic project summary.

When a relevant `CONTEXT.md` already exists, treat it as the domain glossary unless the repository establishes another meaning. If a root `CONTEXT-MAP.md` maps several domains, follow it to the glossary for the affected area. Keep each glossary limited to stable terms, meanings, relationships, and resolved ambiguities; keep implementation decisions, plans, approvals, and current status in their authoritative documents.

When creating a glossary, prefer a maintained, tracked project document because its vocabulary should travel with the code. Keep private planning details out of it. Add a concise pointer from the active instruction file that states when to read it, such as before naming domain concepts or changing domain behavior. Ordinary projects with clear terminology need no glossary.

## Keep instructions proportional and durable

Link detail where it matters, such as “For permission-callback changes, read …”. Do not require every document or old plan before a small edit. Keep broadly applicable constraints at the root and substantial contracts/manual procedures in relevant maintained documents or scoped instructions.

Write each documentation pointer as a condition plus a destination: state what the document contains and which work requires it. Keep each fact or rule in one authoritative place instead of copying its meaning into the pointer.

Avoid repeating global rules and existing documentation. If contributors lack the global agreement, include only what the project needs to be self-contained. Preserve important product, safety, and licensing constraints when shortening an existing file. Prefer repository-relative paths and do not require unavailable local notes for routine work supported by tracked context.

Keep project-specific constraints and relevant verification. If the instructions do not inherit a shared engineering agreement, add only the principles this project needs. Do not add blanket checks or approval gates; project instructions never override user intent or runtime permissions.

## Authoring check

Before saving, verify active navigation and that ordinary work and handoff have a proportional path to completion. Remove duplicated rules and unsupported dependencies while preserving actual choices and boundaries.
