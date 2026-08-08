# Request templates

Ten fill-in templates. Read this when a user wants a reusable prompt, brief, or handoff.

Use only the fields that would change the result. Delete the rest. An over-filled template is worse than three specific sentences.

## Contents

1. Strong initial request
2. Complex-task planning request
3. Context and file review request
4. Research request requiring primary sources
5. Deliverable or artifact request
6. Verification request
7. Correction after a poor answer
8. Project instruction review
9. Convert a workflow into a skill
10. Fresh-chat handoff summary

---

## 1. Strong initial request

```
Objective: [the outcome I want, not the steps]
Context: [what you need to know to make good decisions here]
Audience: [who reads this and what they already know]
Constraints: [length, format, tone, deadline, anything fixed]
Out of scope: [what not to change, include, or assume]
Desired output: [format and rough size]
Success criteria: [how I will judge whether this is good]
```

## 2. Complex-task planning request

```
I want to [objective]. Before producing anything, give me a plan.

What I have: [files, project knowledge, data already available]
What I know: [constraints, decisions already made]
What I am unsure about: [open questions]

In the plan, include:
- your reading of the objective and what "done" means
- scope in and out
- the steps, in order
- what only I can supply
- how each step will be verified
- the main risk and its early warning sign

Ask me only the questions where a wrong guess would waste the work.
Wait for my go-ahead before executing.
```

## 3. Context and file review request

```
Before answering, review what is already available: [project knowledge / uploaded files / earlier in this chat].

Tell me:
- what you found that is relevant, and where
- what is missing that you need
- anything contradictory or out of date between sources
- which sources you will treat as authoritative, and why

Do not ask me for anything already in the material.
```

## 4. Research request requiring primary sources

```
Research question: [the specific question]
Decision it informs: [what I will do with the answer]
Source standard: primary sources only - original publisher, official
documentation, the actual paper, filing, or dataset. Secondary write-ups
may be used to locate primaries but not cited as evidence.
Recency: [how current it must be]
Out of scope: [what not to spend time on]

Deliver:
- a source table: source, author, publisher, date, URL, primary yes/no,
  whether you actually retrieved it or only saw it described
- findings, each tied to a source
- where sources disagree, and how
- what you could not confirm

Do not present anything as verified that you did not retrieve.
```

## 5. Deliverable or artifact request

```
Deliverable: [document / spreadsheet / dashboard / page / deck / other]
Format: [file type, or in-chat]
Purpose: [what it is used for and by whom]
Must contain: [required sections, fields, or elements]
Must not contain: [exclusions]
Style reference: [an example of the standard, if quality is subjective]
Length: [approximate]
Success criteria: [what makes this usable rather than merely complete]

Build it, then check it against this list and tell me what you checked.
```

## 6. Verification request

```
Check this before I use it: [what to check]

Verify:
- every requested element is present, against my original request
- factual claims trace to a source you actually retrieved
- all figures recalculated, with the method stated
- internal consistency - no contradictions between sections
- unsupported assumptions, flagged individually

Report as: what passed, what failed, what you could not check and why.
Only flag issues affecting correctness or my stated requirements -
not style preferences.
```

## 7. Correction after a poor answer

```
That did not work. Specifically: [what was wrong - be concrete]
What I actually need: [restated objective]
What was right in it: [keep this]

Do not patch the previous answer. Tell me where the approach went wrong,
then redo it with a corrected approach.
```

If the same thing has now been corrected twice, start a fresh chat and open with template 10 instead.

## 8. Project instruction review

```
Here are my current project instructions:
[paste]

Review them for:
- lines that would not change your behaviour if deleted
- anything that belongs in project knowledge instead (background, reference)
- anything that belongs in a skill instead (a procedure used only sometimes)
- rules that contradict each other
- anything time-sensitive that will go stale
- ambiguous wording that would make you ask questions already answered here

Give me a shorter rewrite, and list what you moved or removed and why.
```

## 9. Convert a workflow into a skill

```
I do this repeatedly: [describe the workflow]

Turn it into a skill.
Trigger: [when it should activate]
Should not trigger for: [near misses]
Inputs: [what I typically provide]
Output: [what it should produce, and in what format]
Standards: [rules that must hold every time]
Verification: [how the output should be checked before I see it]

Give me SKILL.md with valid frontmatter - lowercase-hyphenated name with no
reserved words, and a description stating both what it does and when to use
it - plus any reference files, and three test prompts that should trigger it
and three that should not.
```

## 10. Fresh-chat handoff summary

```
Continuing work from another conversation.

Objective: [what we are producing]
Decisions already made: [with the reason for each]
Constraints: [fixed things]
Ruled out: [approach, and why - so we do not revisit it]
Where the material is: [project knowledge files, uploads, links]
State: [what is finished, what is in progress]
Next step: [the immediate task]
Verification: [how the result will be checked]
```

Write the handoff before closing the old chat, while the reasoning is still fresh.
