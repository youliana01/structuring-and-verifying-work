# Planning and briefing

Read this when work is complex enough that jumping straight to output risks solving the wrong problem, or when helping a user write a stronger request.

## Contents

- What a brief carries
- Planning depth by tier
- The plan format
- Asking versus assuming
- Interviewing on large work
- Re-planning
- Phasing execution

---

## What a brief carries

Anthropic's prompting guidance names contextual information that improves results: what the results will be used for, who the output is for, where the task sits in a workflow, and what successful completion looks like. Its Claude Code guidance adds the same idea from the other direction - be specific about scope, point at the sources that can answer the question, reference examples of the pattern wanted, and describe what "fixed" looks like.

The working set:

| Field | Why it changes the answer |
|---|---|
| Objective | The outcome, not the steps to reach it |
| Context | Background that changes decisions - not everything known |
| Audience | Who reads it, and what they already know |
| Constraints | Length, format, tone, budget, deadline, things fixed |
| Examples | Only when quality is subjective and hard to specify |
| Out of scope | What should not be changed, included, or touched |
| Desired output | Format and rough size |
| Success criteria | How the result will be judged |
| Verification | How correctness will be checked, and by whom |
| Permission boundaries | What may be done autonomously and what needs approval |

Include a field only when it would change the result. A brief with ten empty headings is worse than three specific sentences.

## Planning depth by tier

| Tier | Planning |
|---|---|
| Simple | None. Answer. |
| Medium | One line naming the outcome, plus assumptions surfaced inline as they arise |
| Complex | An explicit plan before execution |
| Anything irreversible, externally visible, or expensive to redo | Explicit plan **and** approval before acting |

Anthropic's guidance is direct that planning carries overhead and should be skipped when scope is clear and the fix is small; it is most valuable when the approach is uncertain, the work touches several parts, or the material is unfamiliar. If the change could be described in one sentence, skip the plan.

## The plan format

```
PLAN
Objective:     one outcome, stated so it can be checked
Constraint:    the thing that actually limits this
Scope:         in / out
Inputs needed: what only the user can supply
Steps:         numbered; smallest first where order allows
Verification:  how each step and the whole will be checked
Risks:         what would invalidate this, and the early signal
```

Keep it short enough to argue with. A plan nobody reads is a formality, not a control.

For multi-step work, a visible checklist that gets ticked as phases complete is a documented pattern in Anthropic's skill authoring guidance, including for pure analysis work with no code involved.

## Asking versus assuming

Ask only when the answer would change the work and cannot be inferred:

- The objective, when genuinely ambiguous
- Hard constraints that are not guessable
- Which source is authoritative when two conflict
- Anything with a permission, privacy, or safety dimension

Otherwise assume, label the assumption inline, and continue. Re-asking something the user already provided is friction, not diligence. Bundle questions into one message rather than trickling them.

Prefer a concrete proposal to an open question. "I will assume the audience is prospective clients rather than existing ones - say if not" moves faster than "who is the audience?"

## Interviewing on large work

For big, underspecified work, interviewing first is documented as effective: ask about the hard parts - edge cases, trade-offs, things not yet considered - rather than the obvious ones, keep going until the space is covered, then write a self-contained specification.

What makes a specification useful, per the same guidance: it names the things involved, states what is out of scope, and ends with an end-to-end check that proves the result works. Time spent making the spec precise pays off more than time spent supervising execution.

In the Claude app, the natural sequence is: interview in one chat, produce the spec as an artifact, then start a fresh chat with the spec to execute.

## Re-planning

Correcting the same thing repeatedly means the approach is wrong, not the wording. Anthropic's guidance recommends resetting rather than accumulating failed attempts, because the failed approaches stay in the conversation and compete with the instructions.

When work is going wrong:

1. Stop.
2. Say in one or two sentences where the output diverged from the objective.
3. Propose the corrected approach.
4. If the conversation is already cluttered with failed attempts, suggest a fresh chat with a written brief incorporating what was learned.

Do not patch around a broken premise. Everything built after inherits it.

## Phasing execution

- Name the phase you are on.
- A phase ends when its check passes, not when it looks finished.
- Hand back control between phases on long work so the user can redirect before the next phase compounds the last.
- Change one thing at a time when diagnosing. Two simultaneous changes make the outcome uninterpretable.
