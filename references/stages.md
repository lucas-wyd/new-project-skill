# Stage deliverables

Use the relevant section for the active decision. Store artifacts according to [continuity](continuity.md); stage approvals are defined in `SKILL.md` and interactions in [collaboration](collaboration.md).

## Definition and project cues

Build a concise brief through interactive questions: the problem and current workaround, purpose, specific audience and setting, smallest useful outcome, exclusions, material constraints, and observable success criteria. Distinguish learning, personal utility, internal workflow, and commercial aims when they change the recommendation. Propose an initial scope when the user is unsure and invite correction. Do not invent numerical targets or settle the stack before understanding the need.

Use only the project cues that change a decision; these are not a mandatory questionnaire:

| Situation | What to establish early |
| --- | --- |
| Learning/portfolio | Learning objective, demonstrable result, and which work the user wants to understand or perform |
| Utility/script/automation | Example inputs/outputs, execution environment, and failure behavior; avoid unnecessary UI or hosting |
| Commercial/internal application | Users versus buyers/approvers, actual workflow, evidence of need/adoption, integration constraints, operating owner, and budget |
| Game/creative interaction | Core experience, smallest playable loop, relevant assets/licensing, and target export; use playable evidence for questions of feel |
| Data/ML/research | Data access/provenance, baseline, evaluation data, reproducibility, compute limits, and uncertain performance to measure |
| Library/SDK/developer tool | Consumer example, public interface, supported runtime, packaging/distribution, and integration check |
| Native mobile/desktop | Target devices/OS, necessary permissions, offline behavior, signing and distribution constraints when material |
| Existing repository/monorepo | Intended subproject, actual implementation, active instructions, established contracts/dependencies, and relevant checks |

Include relevant time, budget, platform, skills, privacy/data, accessibility, and integration constraints. Decompose an oversized idea before refining every subsystem; define the first useful increment and defer unrelated capabilities. A brief is ready when the audience, problem, bounded outcome, and completion criteria support comparison of alternatives.

When comparison research could inform a decision and its scope is not already explicitly authorized, finish with a short research proposal: the decision it informs, search topics/source types, and proportionate scope. Keep private names, code, internal documents, and customer data out of queries. If the scope is already authorized, record the decision it informs and its agreed bounds. If research would not inform a decision, record it as unnecessary. Present the brief for any remaining scope or approval decision.

## Online comparison research

Start after explicit permission for this comparison; reuse an existing request for the same research. Search close products, relevant open-source projects, substitutes, and the user's current workaround. Prefer primary pages, docs, pricing, repositories, and license files; read the actual supporting pages. Do not invoke Deep research unless explicitly requested.

Use `agent-reach` for internet retrieval when it is available. Read its instructions before searching, run its required backend diagnosis, and use its routing and retry chain for each source type. Keep private project material out of queries. Treat retrieved results as inputs to this stage: evaluate source quality, distinguish claims from inference, synthesize the comparison, and record citations here. If `agent-reach` or a required channel is unavailable, state the resulting coverage gap instead of silently switching research workflows; ask whether to proceed with the narrower evidence when that gap could change the decision.

Choose enough close alternatives to support the decision, often three to five when available, without padding. Record date, links, coverage limits, and facts that may change. If access fails, report the gap and seek a decision to retry or continue with uncertainty.

Use a compact comparison with dimensions relevant to the brief: users, core-use-case overlap, differences, cost, licensing, hosting/privacy, and integration fit. Distinguish verified facts, vendor claims, inference, and unknowns. Absence from documentation does not prove absence of a capability.

Recommend a direction based on the user's purpose:

- **Use an existing product:** it meets the important need with a lower total burden.
- **Adapt/contribute:** extensibility and verified licensing permit the needed difference.
- **Build:** unmet constraints, learning, control, or a differentiated workflow justify development and maintenance.
- **Validate further or stop:** evidence is insufficient or benefit does not justify effort.

Explain the strongest reason for and against continuing. Similarity alone does not invalidate a learning/personal project; no close match does not prove novelty or demand. The user chooses. A pivot revisits only affected decisions; choosing an existing product or stopping ends this lifecycle without an unnecessary implementation plan.

## Optional feasibility investigation

When an important design choice cannot be resolved from available evidence, propose the cheapest useful investigation before committing to it. Examples include a playable game loop, a model baseline on representative data, or an OS capability probe. This is an optional branch from the current stage, not a mandatory extra stage.

Present the uncertainty, experiment and disposable output, required time/cost/resources, success condition, and stop condition. Ask for authorization of that bounded experiment unless already explicitly requested. Research permission or a request for a visual preview alone does not authorize experimental code, installations, paid resources, or production changes.

Use an isolated, appropriate local workspace and existing tools where suitable. Describe any needed installations, accounts, or data access in the proposal. Keep experimental artifacts ignored, preserve source data, and do not deploy or alter the application without authorization. Respect a user's planning-only restriction; propose the experiment for later execution if it cannot run within the permitted scope.

Stop when the question is answered, the agreed bound is reached, or a consequential blocker appears. Record conditions, results, uncertainty, and recommendation in the relevant local document/state. Present the result and ask whether to continue the affected design, revise scope, or stop. Label disposable code clearly; adopting it into the product requires an explicit implementation decision and relevant verification.

## Design

After a direction is selected, or an existing authorized scope establishes one without a material conflict in the evidence, create a design sized to the first useful release:

- Primary user flow, meaningful states/edge cases, and acceptance criteria.
- Components and responsibilities, core entities, interfaces, and storage where applicable.
- Recommended platform/stack, meaningful alternatives, and reasons grounded in constraints and existing dependencies. Label proposed paths/tools; verify current external capabilities with primary docs within the authorized research scope. Resolve additional research permission when needed.
- Material privacy/access, accessibility, deployment, cost, maintenance, risks, and unresolved assumptions.

Prefer a simple end-to-end design that grows in working increments. Do not invent screens, databases, services, or architecture layers. Use the collaboration agreement for technical decisions; for an unresolved visual direction, read [visual decisions](visual-decisions.md). Designing does not authorize application scaffolding, dependency installation, or deployment; use the separately authorized investigation route when evidence requires an experiment.

Finish and verify the design, show its overview and relevant artifacts, and ask whether to continue with implementation planning. This is the default review checkpoint; do not write the detailed implementation plan before that decision unless the user has explicitly removed or changed the checkpoint. If scope changes materially, revisit the affected approval and keep unrelated approvals valid.

## Implementation plan

Use installed `writing-plans` when available, specifying the ignored local location. Inspect relevant existing code and distinguish proposed files from existing ones. Make the plan usable by a fresh chat:

- Link the approved brief/design and relevant evidence; state goal, scope, constraints, and observable completion criteria.
- Separate actual implementation/verification from planned work.
- Order meaningful working increments. The first includes necessary environment prerequisites and the smallest functioning end-to-end result; later increments preserve it. Identify affected files/modules, dependencies, and checks for each.
- Identify major milestones, the working demo or evidence for acceptance, and the stop before the next milestone. Routine edits, fixes, and checks within an authorized milestone proceed without another gate.
- Link the recorded collaboration agreement; restate only user-owned decisions, review checkpoints, and focused-review expectations that affect execution.
- Identify consequential external operations, required accounts/configuration, and unresolved choices. Do not invent installed tools, runnable commands, test results, or publication permission.

Before presenting the plan, perform a short coverage check: each required outcome has corresponding implementation work and observable verification; each planned task serves approved scope or is identified as a proposal; terminology and dependencies agree with the design. Small plans need no separate matrix. Resolve choices blocking the first milestone before declaring readiness; later unknowns can remain explicit. Scale tests and plan detail to risk.

Present the completed plan and ask whether to approve it and prepare the handoff, revise, or pause. This is the default execution-review checkpoint. Record plan approval separately from permission to execute. An approved handoff can legitimately await a start request.

## Handoff

After plan approval, update state and save a short starter prompt. Include project purpose/current stage, authoritative document paths, the active instruction file, plan revision, first planned milestone and its verification, and execution status. Include the work-log path when it is active. If implementation was explicitly authorized, identify the authorized scope and evidence. Otherwise state “Plan approved; implementation awaits the user's start request.” Include only agreement terms and future stops that the receiving task cannot recover from active instructions or transferred state.

Invite the user to open a new chat in the project when ready to implement. Pasting a prompt that explicitly asks to implement the first milestone is a new start request; do not describe that future request as approval already received. Honor explicit same-chat implementation requests within their scope.

Before a receiving task starts execution, verify its project/subproject, source revision and relevant uncommitted work, active navigation, and access to the required local-only documents. Ignored files do not follow clones, worktrees, remote hosts, or cloud tasks. Arrange an authorized transfer or supply sufficient context directly in the starter prompt; preserve ignore rules and verify received contents. Do not dispatch a prompt to execute while its needed context is still awaiting transfer. If the destination is not available yet, provide a self-contained prompt or mark transfer pending rather than claim readiness there.

Do not commit private planning documents to solve handoff or assume shared conversation history. Create or send to another task only when explicitly requested, following host destination rules. Task creation or handoff-only review does not by itself authorize application implementation; follow the requested action.
