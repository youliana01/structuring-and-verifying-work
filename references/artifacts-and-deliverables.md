# Artifacts and deliverables

Read this before producing anything the user will keep, edit, share, or hand to someone else.

## Contents

- Chat, artifact, or file
- What counts as an artifact
- Working with artifacts
- File generation
- Deliverable verification
- Handing over

---

## Chat, artifact, or file

| Form | Use when |
|---|---|
| In the conversation | The user reads it once - an answer, an explanation, a recommendation, a short list, a summary, a plan for discussion |
| Artifact | Substantial, self-contained content the user will edit, reuse, iterate on, or return to |
| File | The user needs something to download, send, open in another application, or store |

Anthropic's documentation describes the artifact bar as content that is significant and self-contained (typically over roughly fifteen lines), that the user is likely to edit or reuse outside the conversation, that stands on its own without the surrounding conversation, and that they will want to refer back to. Documents, code, single-page sites, diagrams, and interactive components are the common cases.

Two errors to avoid in both directions:

- Wrapping a three-paragraph answer in a document, which forces the user to open something to read a reply.
- Delivering a 900-word specification as chat text the user then has to copy out by hand.

## What counts as an artifact

Yes: a report, a full document draft, a spreadsheet model, a dashboard, a landing page, a diagram, a reusable template, a piece of code of any real size, a specification.

No: a recommendation, a comparison of three options, a summary of search findings, a plan under discussion, an explanation, a short list.

If it is unclear, ask which the user prefers - once, in a clause, not a paragraph.

## Working with artifacts

- Iterate on the existing artifact rather than producing a near-duplicate. Version history is part of what makes artifacts useful.
- When several artifacts are open, say which one you are changing.
- On a substantial revision, state what changed rather than making the user diff it.
- For markdown documents, users can highlight a passage and request an edit in place. Structure documents with clear headings so a section can be pointed at.
- An artifact that connects to external services asks the user for approval on first use. Never present that approval as automatic.

## File generation

Create a file when the user needs a file. Signals: "send me", "download", "so I can open it in", "attach", a named extension, or a deliverable destined for someone else.

- Choose the format the destination needs, not the one that is easiest.
- Say what was generated and what is in it, in one or two lines. Do not narrate the build.
- If the file is derived from user data, state which inputs were used.
- Never write credentials, secrets, or personal identifiers into a generated file.

## Deliverable verification

Before handing anything over:

- [ ] Every required element from the request is present - checked against the request, not against the outline
- [ ] Figures recomputed, and any total, percentage, or derived value actually recalculated rather than restated
- [ ] Facts traceable to a source or explicitly labelled as assumption
- [ ] No internal contradictions between sections
- [ ] Format, length, and tone match what was asked for
- [ ] Nothing included that was declared out of scope
- [ ] Placeholders, lorem text, and unresolved "TBD" markers removed or flagged
- [ ] The file opens or the artifact renders as intended - and where that could not be confirmed, say so

Anthropic's skill authoring guidance describes exactly this loop for work with no code in it: draft against the standard, review against a checklist, revise, and only proceed when the requirements are met.

Show the check. "Verified" without evidence is the failure this list exists to prevent.

## Handing over

Lead with the result and where to find it. Then, briefly:

- What was assumed
- What was checked, and how
- What remains unverified
- The single most useful next step

Do not close with a summary of the process. The deliverable is the point.
