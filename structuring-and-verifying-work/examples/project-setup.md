# Example: setting up and auditing a Project

Shows the placement decision and instruction pruning.

## Request

> Help me set up a Project for my client proposals. I keep re-explaining the same stuff every time.

## Tier

Medium, moving to complex only if the user has a lot of existing material to audit.

## What the skill does

Asks one bundled question, then proposes a structure rather than interviewing at length:

> Before I lay this out - what do you already have written down anywhere: a rate card, past proposals you'd call good, a scope-of-work template? Anything existing is better raw material than anything I'd draft blind.

Then the placement, layer by layer:

| Content | Layer | Why |
|---|---|---|
| "I write proposals for [sector] clients; direct tone, no filler" | Project instructions | Needed in every chat in this project |
| "Every proposal has: problem, approach, scope, timeline, price, what's excluded" | Project instructions | A standard, applied every time, short |
| "Never quote a price not on the rate card" | Project instructions | A constraint that prevents a real error |
| Rate card | Project knowledge | Reference material, changes occasionally |
| Two past proposals the user rates highly | Project knowledge | Quality examples where the standard is subjective |
| Scope-of-work boilerplate | Project knowledge | Long, reused, does not belong in instructions |
| The step-by-step drafting procedure | A skill | Only relevant when actually drafting, not in every chat |
| This week's client brief | Chat upload | One task |

## The instruction draft

Short on purpose:

```
Role: draft client proposals for [sector].

Structure every proposal: problem, approach, scope, timeline, price, exclusions.

Rules:
- Prices come only from the rate card in project knowledge. Never estimate one.
- Anything not in the scope section goes in exclusions explicitly.
- Direct tone. No filler openings, no "in today's fast-paced".
- Match the structure and register of the example proposals in project knowledge.
```

Anything longer than this starts to compete with itself.

## Auditing an existing set of instructions

When the user pastes something already sprawling:

1. Mark each line **load-bearing**, **redundant**, **obsolete**, or **misplaced**.
2. Redundant means Claude does it correctly without being told - "write clearly" is the archetype.
3. Misplaced means it is background (→ knowledge) or a procedure (→ skill).
4. Obsolete means time-stamped or superseded.
5. Return a shorter rewrite plus a table of what moved and why.
6. Test one real proposal before and after. If the output does not change, say so - do not claim an improvement that did not happen.

## What the skill tells the user plainly

- Context does not carry between chats in a project unless it is in project knowledge. A decision made in one conversation is invisible to the next one.
- The instructions are always loaded, so length there is a permanent cost. Anthropic's own guidance is that over-long instruction files cause real instructions to be ignored.
- The rate card belongs in knowledge rather than instructions because it will change, and changing one document is easier than editing an instruction block.
