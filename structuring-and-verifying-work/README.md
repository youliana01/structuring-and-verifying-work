# structuring-and-verifying-work

> **Not an official Anthropic product.** Independent, unaffiliated, and not endorsed by Anthropic or by any Anthropic employee. Built from public Anthropic and Claude documentation. See [Source policy](#source-policy).

A Claude app skill that improves how Claude handles work: clarifying the real objective, putting context in the right layer, planning proportionally, researching with real sources, choosing the right output form, and verifying results before calling anything done.

## What it does

When it activates, Claude:

- Picks a tier - simple, medium, or complex - and scales process to it instead of applying ceremony everywhere
- Inspects available Project knowledge and files before asking for context it already has
- Plans before executing on complex work, and skips planning on small work
- Uses web search and source research when currency or authority matters, and distinguishes primary from secondary sources
- Chooses between a chat answer, an artifact, and a file deliberately
- Verifies before presenting: requirements checked against the original request, figures recalculated, claims traced to sources, unverified items named
- Treats corrections as task feedback first, and promotes a lesson to permanent instructions only when it is durable, general, and recurrent
- Keeps the user in control of anything external or irreversible

## Claude app, not Claude Code

This is built for the Claude app - claude.ai, desktop, and mobile. It deliberately excludes Claude Code features that have no app equivalent: hooks, permission modes, auto-accept editing, `--dangerously-skip-permissions`, git worktrees, non-interactive mode, repository CLAUDE.md files, custom slash commands, subagent orchestration, and pull-request review automation.

Where a Claude Code practice has a genuine app equivalent, the skill uses the equivalent and says so. The full mapping table - including what was excluded and why - is in `references/source-ledger-and-scope.md`.

## Who it is for

People doing substantive work in the Claude app who want consistent results rather than occasional good ones: consultants, analysts, researchers, operators, and anyone maintaining Projects that several conversations depend on.

It is not for people who mainly ask quick questions. It is designed not to fire on those.

## Source policy

Every operating rule traces to official Anthropic or Claude documentation that was retrieved and read: the Claude Code best-practices documentation, the skill authoring best-practices documentation, and Claude Help Center articles on projects, skills, personalization, artifacts, files, and search. The source ledger lists each one with its URL and how completely it was retrieved.

**On personal attributions.** A number of these working practices circulate online attributed to individual Anthropic engineers, usually via posts on X, conference talks, and podcast appearances. None of those primary sources could be retrieved - X blocks automated access, and no transcripts were available for the video and stage appearances. **This skill therefore makes no direct quotation of, or attribution to, any named individual.** The underlying principles - verification loops, planning before execution, keeping always-loaded instructions lean, writing lessons down rather than re-prompting - appear in Anthropic's own documentation, and that documentation is what is cited. Ask the skill who said what and it will tell you what is verified and what is not, rather than filling the gap. The full ledger, including what was excluded and why, is in `references/source-ledger-and-scope.md`.

## Installing

1. Enable code execution. On Free, Pro, or Max: **Settings → Capabilities**, turn on *Code execution and file creation*. On Team or Enterprise, an Owner enables both *Code execution and file creation* and *Skills* in **Organization settings → Skills**.
2. Go to **Customize → Skills**.
3. Click **+**, then **Create skill**.
4. Upload `structuring-and-verifying-work.zip`.
5. Toggle the skill on — uploaded is not the same as enabled.

The ZIP contains the skill folder as its root, which is the structure the uploader expects.

Uploaded skills are private to your own account. Menu paths move; if these do not match what you see, check the current Claude Help Center article on using skills.

## Using it

**Automatic triggering.** Claude reads the skill's name and description at the start of a conversation and loads the body when the description matches the task. Requests that reliably trigger it:

- "Help me get a better result from Claude"
- "Plan this complex task before doing it"
- "What context should I give Claude for this?"
- "Help me structure this Project"
- "Improve my project instructions"
- "Turn this workflow into a reusable skill"
- "Research this properly and verify the sources"
- "Review your answer before finalising"
- "Break this task into a reliable workflow"
- "My last few answers have been generic - what am I doing wrong?"

**Manual invocation.** Name it: "Use the app workflow skill for this," or "apply the workflow skill and plan this before you start."

**What should not trigger it.** Ordinary factual questions, everyday writing, debugging, and creative requests. If it starts announcing tiers on small questions, that is a bug - see Limitations.

## Skill name

The folder and frontmatter name is `structuring-and-verifying-work` - gerund form, naming the two things the skill actually does. It does not contain the word "claude" because Anthropic's skill authoring documentation states that skill names cannot contain the reserved words `anthropic` or `claude`; "Claude app" appears in the description instead, where there is no such restriction.

If you rename it: lowercase letters, numbers, and hyphens only, under 64 characters, neither reserved word, and avoid vague names like `helper` or `workflow`. Change the folder name, the `name:` field in `SKILL.md`, and the `skill_name` field in `evals/evals.json` together - they must match.

## What it can and cannot do

**Can:** improve consistency on substantive work; help you place context correctly; produce plans, briefs, templates, and reusable skills; enforce source discipline; catch arithmetic errors, missing requirements, and internal contradictions before you send something.

**Cannot:** make Claude omniscient or infallible; access sources that block retrieval; verify a claim with no available source; check anything about your business only you can judge; change Claude app features or availability; replace your own review of anything consequential.

## Known limitations

- **Verification has limits.** Claude can recalculate, cross-check, and compare against your stated criteria. It cannot confirm that an input file is complete, that an assumption fits your market, or that a rendered artifact looks right on your screen. The skill is written to say so rather than paper over it.
- **Self-review inherits blind spots.** For anything expensive to redo, use a fresh chat given the deliverable and criteria but not the reasoning.
- **Overlap with other working-method skills.** If you already run a general method or planning skill, expect overlap on tiering, planning, and verification. What this one adds is the Claude-app-specific layer: Projects, the instruction hierarchy, artifacts versus files, search modes, and the source policy. Running both is fine; if responses start getting procedural, disable one.
- **Triggering is probabilistic.** No description guarantees activation. Invoke it by name when it matters.
- **Feature drift.** Claude app features change. The skill deliberately avoids version numbers and dated claims, but any specific menu path may move.
- **Styles.** Anthropic's personalization documentation currently foregrounds profile instructions, project instructions, and skills, with styles referenced in passing. The skill points at checking current documentation rather than asserting the feature's status.

## Contents

```
structuring-and-verifying-work/
├── SKILL.md
├── README.md
├── references/
│   ├── source-ledger-and-scope.md               source and recommendation ledgers, mapping table
│   ├── claude-app-context-architecture.md       projects, instructions, knowledge, skills, uploads
│   ├── planning-and-briefing.md                 planning depth, plan format, asking vs assuming
│   ├── request-templates.md                     ten fill-in templates
│   ├── research-and-source-verification.md      primary vs secondary, ledger, honesty rules
│   ├── artifacts-and-deliverables.md            chat vs artifact vs file, deliverable checks
│   ├── correction-and-learning.md               what becomes permanent, what does not
│   └── anti-patterns.md                         recurring failure modes and fixes
├── examples/
│   ├── simple-request.md
│   ├── complex-research.md
│   ├── project-setup.md
│   ├── deliverable-creation.md
│   └── self-review.md
├── evals/
│   └── evals.json                               12 triggering and 6 non-triggering cases
└── LICENSE
```

## Updating it

Anthropic's guidance on skill authoring is that skills should be revised from observed behaviour rather than assumptions. In practice:

1. Use it on real work and note where Claude misses - not where it merely differs from what you imagined.
2. Fix the smallest thing that would have prevented the miss. Adding a rule because it sounds rigorous is how skills bloat.
3. Re-run the relevant cases in `evals/evals.json`, including the non-triggering ones. Over-triggering is the more common regression.
4. When a Claude app feature changes, update `references/claude-app-context-architecture.md` and the mapping table. The `SKILL.md` body is written to avoid feature specifics so it should need fewer edits.
5. When new primary sources become available - a published transcript, an official post - add them to the source ledger and move the corresponding recommendations from unverified to verified. Do not move a claim without the source.

Bump the `version` in the frontmatter when you change behaviour, not when you fix a typo.
