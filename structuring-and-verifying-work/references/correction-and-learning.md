# Correction and learning

Read this when an answer missed, when a user is frustrated, or when deciding whether a lesson should become permanent.

## Contents

- Read the correction correctly
- The promotion test
- Where a lesson goes
- Writing the rule
- Keeping instructions from bloating
- When to stop and re-plan
- When to start fresh

---

## Read the correction correctly

A correction is information about **this task** until there is evidence it is broader. Three different things get expressed the same way:

| The user said | It probably means | Response |
|---|---|---|
| "Too long" | This particular answer overshot | Shorten this one |
| "You always do this - too long again" | A standing preference | Consider profile or project instructions |
| "That is wrong" | A factual error | Fix the fact, check what else rests on it |
| "That is not what I asked for" | Objective misread | Stop, restate the objective, re-plan |

Turning a one-off into a permanent rule is how instruction sets rot. Anthropic's guidance warns that over-long always-loaded instruction files cause real instructions to be ignored - so every added line has a cost paid by every future conversation.

## The promotion test

A lesson becomes a permanent instruction only when all three hold:

1. **Durable** - it will still be true in three months.
2. **General** - it applies to a class of tasks, not one output.
3. **Recurrent** - it has come up more than once, or the user has said it is a standing preference.

If any fails, apply it now and let it go.

## Where a lesson goes

| Kind of lesson | Home |
|---|---|
| How the user wants Claude to communicate, everywhere | Profile instructions |
| A standard for one project | Project instructions |
| A fact, figure, or reference the work keeps needing | Project knowledge document |
| A repeatable procedure | A skill |
| Something true only for this task | Nowhere - just do it |

## Writing the rule

- One line where possible.
- Specific enough to act on. "Be more careful with numbers" changes nothing; "recalculate every total and show the method" does.
- Replace, do not stack. If a new line supersedes an old one, delete the old one.
- Nothing time-sensitive. A rule referring to a current quarter or a version number goes stale silently.
- No rules for behaviour that is already correct.

After adding, test one real task. If behaviour does not change, the rule was not the fix - remove it and look again.

## Keeping instructions from bloating

Symptoms:

- A rule is written down and still gets ignored - the block is probably too long and the rule is being lost in it
- Questions get asked that the instructions already answer - the wording is ambiguous
- Nobody can say what half the lines are for

Fix by pruning, not by adding emphasis. For each line: would removing it cause a mistake? If not, cut it. Move background into project knowledge and procedures into skills so the always-loaded block stays small.

## When to stop and re-plan

If the output is heading the wrong way, do not keep patching sentences:

1. Stop.
2. Say in one or two sentences where the result diverged from the objective.
3. Say what you now believe the objective actually is.
4. Propose a corrected approach.
5. Execute only after the user confirms, if the correction changes direction materially.

Correcting the wording of a wrong approach produces a well-worded wrong answer.

## When to start fresh

Anthropic's guidance recommends resetting after repeated failed corrections rather than accumulating failed approaches in the context, because a clean start with a better prompt outperforms a long thread carrying every dead end.

Start a fresh chat when:

- The same issue has been corrected twice
- The conversation is mostly a record of what did not work
- The task has changed into a different task
- An independent review is wanted that will not inherit the current reasoning

Carry a written handoff into the new chat: objective, decisions made, constraints, what was ruled out and why, where the material is, and the next step. Template 10 in `request-templates.md`.
