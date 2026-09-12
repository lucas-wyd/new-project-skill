# Collaboration and informed decisions

Read when establishing participation preferences or preparing a stage/milestone review. This is the canonical interaction guidance; export a concise project-specific agreement so later chats need not load this skill.

## Interactive questions

Use `request_user_input_async` when available. Use `request_user_input` only when its mode and purpose restrictions permit. Follow host/tool restrictions for approval questions. If no permitted interactive tool is available, disclose that limitation and ask one concise direct question with room for a custom answer; do not simulate buttons or claim to change modes.

Ask one decision or a small related batch at a time. Offer two or three concrete options when useful, put the recommendation first, and explain its fit and main tradeoff within or before the chooser. The question must remain understandable when displayed on its own. Use free text for names, paths, or facts that do not have sensible alternatives; do not add an “Other” choice where the UI supplies custom input.

Put explanations and review summaries before opening the question tool. After opening it, keep the question pending until the user submits an answer or explicitly cancels or redirects the request. An asynchronous tool response such as `accepted: true` acknowledges display of the question; it is not the user's answer. A preselected option and elapsed time are not answers either.

While the answer is pending, wait quietly using the host's interruptible wait mechanism (for example, `clock.sleep` in intervals of at most 60 seconds). After each wait, check for the user's reply and wait again if none arrived. Do not send a final response, an empty final message, repeated reminders, or another question, and do not advance the workflow. If the host cannot keep the turn pending, disclose that limitation before asking rather than claiming the tool blocks. Resume from the submitted answer; a new instruction that cancels or redirects the task takes precedence.

When the user is unsure, offer a concrete example, smaller scope, or reasoned recommendation. Explain unfamiliar concepts only when relevant. Stop interviewing once enough is known for the next decision. State reversible, low-impact assumptions before deciding whether a question is needed; once a question is presented, use the pending-answer protocol above rather than a timeout default.

## Choose the user's involvement

Early in definition, establish a preference unless one is already known. Normally recommend guided participation; tailor this to the user's expressed aim.

| Choice | User participates in | Agent handles |
| --- | --- | --- |
| Guided | Scope, major technical tradeoffs, UI direction, milestone acceptance | Detailed design, routine technical choices, implementation, verification, focused code review |
| Hands-on | Architecture, selected tools, UI iterations, agreed code walkthrough/review checkpoints | Alternatives and reviewable proposals, approved increments, checks and explanations |
| Agent-led | Outcomes, constraints, user-facing direction, exceptions, milestone acceptance | Architecture/stack/tools within delegated constraints, implementation, checks and review |

Allow mixed preferences. Record who decides architecture/stack, UI, tools, and code acceptance, plus explanation depth, review checkpoints, and any learning objective that affects how work should proceed. Technical familiarity and desired involvement are independent: a novice may want a deep walkthrough, while an expert may delegate. Ask about familiarity only when it helps calibrate explanations. Do not infer understanding or delegation from silence, or quiz the user before accepting a decision.

While ownership is unresolved, use guided explanations and retain consequential decisions for the user. For delegated choices, decide within constraints and explain the rationale; do not ask the user to choose every library. Carry forward settled choices. If new evidence materially changes an approved choice or exceeds delegated scope, explain the impact and seek a decision.

Agent-led work retains the stage and implementation milestone gates. Existing authorization for research or external operations remains valid; a participation preference alone does not authorize spending, publication, destructive operations, or new external access.

## Optional work log

Early in a new or continuing project, ask whether the user wants a concise work log for major milestones: “Would you like a short local work log for major project milestones?” Ask once unless no prior choice is recorded or the user asks to change it. When useful, ask this alongside the initial collaboration preference; do not turn a bootstrap-only request into a broader interview.

Recommend a work log for a multi-session project, a learning project, or work the user expects to review later. Recommend no work log for a short, one-off task. If a log already exists, report its path and ask whether to keep maintaining it rather than creating a second one. Without an explicit opt-in, do not create a new log.

When the user opts in, follow [continuity's work-log guidance](continuity.md#optional-work-log) for its local location, state record, active-instruction navigation, and updates. The work log is a human-readable milestone history; state remains authoritative for approvals, current status, and the next action.

For an unresolved visual direction, read [visual decisions](visual-decisions.md).

## Review summaries

Present the result in the conversation as well as linking the document. Before a stage or milestone approval, explain the applicable subset:

- What the user can do or what the plan proposes, with the important exclusions.
- How the main parts work together, using familiar language.
- The recommended or delegated choice, its reason, main alternative, and practical tradeoff.
- Material consequences: data storage/access, external accounts, recurring costs, maintenance owner, deployment responsibilities, and limits. Cite current external facts when checked; label unknowns.
- Evidence, untested assumptions, unfinished work, and exactly what continuing authorizes.

Do not invent architecture during definition or turn every approval into a lesson. A short paragraph may suffice for a utility; a hands-on architecture review may warrant a diagram and alternatives. Offer deeper explanation within the same decision when useful. Resolve misunderstandings that would change the decision before advancing.

## Export the working agreement

Keep detailed preferences in state and a compact agreement in the active project instructions. Repeat only terms that govern the implementation plan or a receiving task; include them in a starter prompt when the destination cannot read the instructions or state. Export behavior directly, not a dependency on this skill's installation path. When preferences change, update affected future checkpoints without rewriting historical approvals.

Meaningful behavior changes require relevant verification and focused agent review regardless of participation level. Use an installed review skill when appropriate; do not claim independent review unless it occurred or require a subagent merely because the user delegates. Hands-on checkpoints show a coherent increment and a small navigable diff/walkthrough after checks, before the next milestone. Guided/agent-led checkpoints report working behavior, important decisions, findings/fixes, and limits.

If deployment is in scope, plan the necessary configuration, accounts, secret handling without secret values, operating costs, and failure detection/recovery. Keep this proportional. Planning deployment does not authorize it.
