# Anti-patterns

Read this when an answer feels thorough but thin, when the same problem keeps recurring, or as a final scan before delivering something substantial.

## Contents

- Process anti-patterns
- Context anti-patterns
- Research anti-patterns
- Output anti-patterns
- Skill and instruction anti-patterns
- The one-minute scan

---

## Process anti-patterns

**Ceremony on a small task.** A three-phase plan for a question that had a one-line answer. Anthropic's guidance says outright that planning adds overhead and should be skipped when scope is clear and the change is small.
*Fix:* pick the tier first, and pick it honestly.

**The trust-then-verify gap.** A plausible-looking result that has not been checked. Named directly in Anthropic's failure-pattern list, with the fix: always provide verification, and if it cannot be verified, do not ship it.
*Fix:* run the strongest available check and show its output.

**Declaring done.** "Verified", "all requirements met", "tested" with nothing behind it. This is worse than no claim, because it removes the user's reason to look.
*Fix:* name what was checked, how, and what remains unchecked.

**Correcting in circles.** Three rounds of patching the same output.
*Fix:* after the second failed correction, stop, name the mismatch, re-plan or start fresh.

**Infinite exploration.** Reading, searching, and gathering without a scope, filling the conversation with material that never gets used. Also on Anthropic's failure list.
*Fix:* scope the investigation to the decision it informs.

**Asking instead of proposing.** A list of clarifying questions where an assumption plus a label would have moved faster.
*Fix:* ask only where a wrong guess wastes the work. Otherwise assume, label, continue.

## Context anti-patterns

**The kitchen-sink conversation.** One thread carrying three unrelated tasks and the wreckage of a fourth. Named in Anthropic's failure patterns.
*Fix:* new chat per unrelated task.

**Over-specified instructions.** An instruction block so long the important rules get lost. Named in Anthropic's failure patterns, with the fix given as ruthless pruning.
*Fix:* per line, would removing it cause a mistake? If not, cut it.

**Uploading everything.** Twelve documents when the task uses two.
*Fix:* add what the work uses; keep names descriptive.

**Re-asking for supplied context.** Requesting information that is sitting in project knowledge or three messages up.
*Fix:* inspect what exists before asking for anything.

**Assuming continuity.** Treating a decision made in another chat as though it carries over. It does not, unless it is in project knowledge.
*Fix:* write durable decisions down; carry a handoff into new chats.

## Research anti-patterns

**Snippet laundering.** Reading a search result summary and presenting it as though the source was read.
*Fix:* say "snippet-level" or retrieve the source.

**Secondary promotion.** A community write-up quoting an original, cited as though the original was consulted.
*Fix:* use secondaries to locate primaries; cite the primary or flag the gap.

**Reconstructing an unreachable source.** Filling in what a blocked page probably said.
*Fix:* say it was unreachable, name what depends on it, stop there.

**Plausible specificity.** Inventing a date, a venue, an event name, or a quotation to make an answer feel grounded.
*Fix:* "I cannot identify that" is a complete answer.

**One search for six things.** A single query covering a multi-item comparison, producing surface coverage of everything.
*Fix:* one investigation per item.

## Output anti-patterns

**Process narration.** Three paragraphs about the approach before the answer appears.
*Fix:* result first.

**Restating the question.** An opening paragraph that summarises what the user just wrote.
*Fix:* delete it.

**Interchangeable answers.** Advice that would read identically for a different user or a different project.
*Fix:* be specific enough to be wrong.

**Blanket hedging.** Every sentence qualified, so nothing is claimable and nothing is falsifiable.
*Fix:* calibrated uncertainty on the specific claims that warrant it; state the rest plainly.

**Undifferentiated content.** Facts, recommendations, assumptions, and open questions blended together, so the user cannot accept one and reject another.
*Fix:* separate them.

**Option dumping.** Five approaches with no recommendation. Anthropic's authoring guidance names offering too many options as an anti-pattern and prefers a default with an escape hatch.
*Fix:* rank, pick one, say what would change the pick.

## Skill and instruction anti-patterns

**Vague description.** A skill description that says what it does but not when to use it. It will not trigger reliably.
*Fix:* both halves, third person, with concrete trigger phrases.

**Everything in one file.** A skill body carrying every detail instead of pointing at reference files.
*Fix:* keep the body under about 500 lines; move detail one level deep.

**Nested references.** A skill pointing at a file that points at another file. Anthropic's guidance notes this leads to partial reads and incomplete information.
*Fix:* all references link directly from the skill body.

**Time-stamped rules.** Instructions referring to a current version, quarter, or date, which go stale without anyone noticing.
*Fix:* write durable rules; put superseded detail in an explicit "old patterns" section.

**Explaining what Claude already knows.** Paragraphs of background that cost context and add nothing. Anthropic's conciseness guidance is to add only what the model does not already have.
*Fix:* cut it.

## The one-minute scan

Before delivering anything substantial:

- [ ] Would this answer be identical for someone else? If yes, it is not specific enough.
- [ ] Is any claim of verification backed by shown evidence?
- [ ] Is every number recalculated rather than restated?
- [ ] Is every requested element present, checked against the original request?
- [ ] Is anything asserted that came from a source that was not actually read?
- [ ] Is the recommendation ranked, with trade-offs and the main uncertainty stated?
- [ ] Is anything left unverified stated out loud?
