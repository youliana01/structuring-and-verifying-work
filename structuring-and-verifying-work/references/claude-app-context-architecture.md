# Claude app context architecture

Read this when structuring a Project, auditing instructions that have grown unwieldy, or deciding where a piece of knowledge belongs.

## Contents

- The five layers
- The placement decision
- Writing project instructions
- Curating project knowledge
- Uploads in a single chat
- Skills
- Styles
- Fresh chat versus continuing
- Auditing an existing Project

---

## The five layers

| Layer | Scope | Loading | Best for |
|---|---|---|---|
| Profile instructions | Every conversation on the account | Always | How you want Claude to communicate with you generally; your role and domain; recurring preferences |
| Project instructions | Every chat inside one project | Always, within that project | Project-specific role, workflow rules, standards, what to avoid |
| Project knowledge | One project | Available to chats in the project; retrieved as needed once large | Stable reference documents, source material, specifications, style guides |
| Skills | Anywhere the task matches | Only when relevant | Repeatable procedures and how-to knowledge |
| Chat uploads | One conversation | That conversation | Material for the task at hand |

Anthropic's documentation draws these lines explicitly: projects supply background knowledge that is loaded with the project, skills supply procedures that activate when needed, connectors supply tools, and account-wide custom instructions apply broadly to everything.

A consequence worth stating to users: **context is not shared across chats in a project unless it is written into project knowledge.** A decision made in chat 3 does not exist for chat 4.

## The placement decision

Ask two questions.

**How often is it needed?**

- Every single time in this project → project instructions
- Every time everywhere → profile instructions
- Sometimes, when a certain kind of task comes up → skill
- As reference material when relevant → project knowledge
- Once → paste or upload it in the chat

**Is it knowledge or procedure?**

- Facts, background, specifications, examples of finished work → knowledge
- Steps, standards to apply, a way of doing something → instructions or a skill

The failure mode is putting procedures into always-loaded instructions. They accumulate, and the always-loaded block becomes too long to be followed reliably.

## Writing project instructions

Target: short enough that every line is doing work. Anthropic's guidance for the equivalent always-loaded file is to ask, for each line, whether removing it would cause a mistake - and to cut it if not, because bloated instruction files cause real instructions to get lost.

Include:

- Role or perspective Claude should take in this project
- Standards that differ from sensible defaults
- Output conventions used repeatedly
- Things that must not be changed, included, or assumed
- Where authoritative information lives ("pricing figures come from the rate card in project knowledge, never from memory")

Exclude:

- Anything Claude does correctly without being told
- General advice ("be accurate", "write well")
- Long explanations or tutorials - link to a knowledge document instead
- Information that changes frequently
- Anything only relevant to one task - that belongs in the request

A useful diagnostic: if Claude keeps ignoring a rule that is written in the instructions, the instructions are probably too long and the rule is being lost. Prune rather than add emphasis. If Claude asks questions already answered in the instructions, the wording is probably ambiguous.

## Curating project knowledge

- Add the documents the work actually uses. Volume is not the goal.
- Name files so the name says what is inside. Retrieval and referencing both depend on it.
- Group related documents so connections can be drawn across them.
- Users can reference a document by name in a request to focus attention on it.
- Remove superseded documents. Two versions of a policy in the same project produce confident answers from the wrong one.
- Documents in project knowledge are reused across chats without re-uploading, which is the main reason to put stable material there rather than pasting it each time.

## Uploads in a single chat

Use for material that is specific to this task: a draft, one dataset, a document to be reviewed. If the same file gets uploaded three conversations running, it belongs in project knowledge.

Say which uploaded file a conclusion came from. When a file cannot be read or is incomplete, say that rather than working around it silently.

## Skills

A skill is the right home for a procedure that recurs across tasks. Structure follows Anthropic's authoring guidance:

- `SKILL.md` with valid YAML frontmatter: `name` (lowercase letters, numbers, hyphens; 64 characters maximum; must not contain the reserved words `anthropic` or `claude`) and `description` (non-empty, 1,024 characters maximum, no XML tags).
- The description carries the triggering signal. It must state both what the skill does and when to use it, written in the third person.
- Keep the body under about 500 lines; move detail into reference files linked directly from `SKILL.md`, one level deep.
- Reference files longer than about 100 lines get a table of contents.
- Skills in the Claude app require code execution and file creation to be enabled, and are uploaded as a ZIP under Customize → Skills.

Only install skills from sources that can be trusted. A skill is instructions Claude will follow, so an untrusted one is an untrusted instruction set.

## Styles

Anthropic's personalization documentation currently presents three ways to shape Claude's behaviour - profile instructions, project instructions, and skills - and describes skills as the mechanism for adjusting tone and format as well as adding capability. Styles are still referenced in the same article's summary.

Practical guidance: treat presentation preferences as belonging in whichever of these the user actually has available in their app version. If a user asks specifically about styles, check the current Help Center rather than asserting the feature's status from memory - this area has changed.

## Fresh chat versus continuing

Start a fresh chat when:

- The task is genuinely new
- The conversation is full of a failed approach
- The same correction has been needed twice
- A review is wanted that will not inherit the reasoning being reviewed

Continue when the accumulated context is doing useful work and the next step builds directly on it.

When starting fresh on related work, carry a written handoff: objective, decisions already made, constraints, what was ruled out and why, where the material lives, and the next step. The handoff template is in `request-templates.md`.

## Auditing an existing Project

1. Read the instructions and mark each line: load-bearing, redundant, obsolete, or misplaced.
2. Move procedures into a skill; move background into project knowledge; delete the rest.
3. List knowledge documents and flag duplicates, superseded versions, and anything never referenced.
4. Check that file names describe contents.
5. Test one real task before and after. If behaviour does not change, the edit was cosmetic - say so rather than claiming improvement.
