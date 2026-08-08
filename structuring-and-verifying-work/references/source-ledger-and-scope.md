# Verified principles, sources, and what was excluded

## Contents

- Access note (read this first)
- Source ledger
- Recommendation ledger
- Claude Code to Claude app mapping table
- Excluded and unverified claims

---

## Access note

Every recommendation used in this skill comes from official Anthropic or Claude documentation that was **retrieved and read in full**, except where the ledger marks it otherwise.

Boris Cherny's own posts, threads, talks, and podcast appearances **could not be retrieved**:

- Posts on X (`x.com/bcherny`) return a robots restriction to automated retrieval. The URLs of specific threads are known, but their contents were not read.
- Video appearances (conference fireside chats, launch retrospectives) have no accessible transcript.
- Third-party compilations of his tips exist and were used **only to locate original URLs**, never as evidence.

Consequence: **no statement in this skill is presented as a direct Boris Cherny quote or recommendation.** Several ideas widely attributed to him - verification loops, planning before execution, lean always-loaded instruction files, writing lessons down rather than re-prompting - appear in Anthropic's own official documentation, and that documentation is what this skill cites. Whether Boris Cherny authored or originated them is not something this skill asserts.

If a user refers to a specific stage presentation, keynote, or talk: **the specific event cannot be identified from the material available here.** Several Boris Cherny stage and fireside appearances are publicly listed, but without access to a recording or transcript, nothing about the content of any of them can be confirmed. Do not guess which event was meant, and do not attribute content to it.

---

## Source ledger

| ID | Source | Speaker/author | Publisher | Date | URL or location | Primary source? | Access | Relevant topic |
|---|---|---|---|---|---|---|---|---|
| S1 | Best practices for Claude Code | No named author on current version | Anthropic | Retrieved 2026-08-08; lineage from the Apr 18 2025 engineering post | code.claude.com/docs/en/best-practices (redirect target of anthropic.com/engineering/claude-code-best-practices) | Yes - official Anthropic doc | Full text | Verification loops, explore-plan-execute, specific context, lean instruction files, course-correction, context hygiene, adversarial review, failure patterns |
| S2 | Skill authoring best practices | Anthropic | Anthropic | Retrieved 2026-08-08 | platform.claude.com/docs/en/agents-and-tools/agent-skills/best-practices | Yes | Full text | Skill structure, descriptions, progressive disclosure, workflows, feedback loops, evaluation-driven iteration, anti-patterns |
| S3 | What are projects? | Anthropic | Claude Help Center | Updated ~Jul 2026 | support.claude.com/en/articles/9517075-what-are-projects | Yes | Full text | Project knowledge, project instructions, scaling of project knowledge |
| S4 | What are skills? | Anthropic | Claude Help Center | Updated Aug 2026 | support.claude.com/en/articles/12512176-what-are-skills | Yes | Full text | Skills vs projects vs MCP vs custom instructions; progressive disclosure |
| S5 | Understanding Claude's personalization features | Anthropic | Claude Help Center | Updated ~Jul 2026 | support.claude.com/en/articles/10185728-understanding-claude-s-personalization-features | Yes | Full text | Profile instructions, project instructions, skills, choosing between them |
| S6 | What are artifacts and how do I use them? | Anthropic | Claude Help Center | Updated ~Jul 2026 | support.claude.com/en/articles/9487310-what-are-artifacts-and-how-do-i-use-them | Yes | Full text | When Claude creates an artifact; editing, versioning, export, MCP access approval |
| S7 | When should I use web search, extended thinking, and research? | Anthropic | Claude Help Center | Jun 2 2026 | support.claude.com/en/articles/11095361 | Yes | Full text | Choosing between web search, extended thinking, and multi-source research |
| S8 | Be clear, direct, and detailed (prompt engineering) | Anthropic | Anthropic docs | Retrieved 2026-08-08 | docs.anthropic.com/en/docs/be-clear-direct and platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices | Yes | Search-result text, not full page | Contextual information to supply: use of results, audience, workflow position, definition of success |
| S9 | Create and edit files with Claude | Anthropic | Claude Help Center | Updated Aug 2026 | support.claude.com/en/articles/12111783-create-and-edit-files-with-claude | Yes | Search-result text | File creation; prompt-injection risk from external files and websites; monitoring Claude's actions |
| S10 | Retrieval augmented generation (RAG) for projects | Anthropic | Claude Help Center | ~Mar 2026 | support.claude.com/en/articles/11473015 | Yes | Search-result text | Naming files well, grouping related documents, referencing documents by name |
| S11 | Usage limit best practices | Anthropic | Claude Help Center | Jun 2 2026 | support.claude.com/en/articles/9797557 | Yes | Search-result text | Putting core working documents in project knowledge; giving complete context in one message |
| S12 | Agent Skills overview | Anthropic | Claude Platform Docs | Retrieved 2026-08-08 | platform.claude.com/docs/en/agents-and-tools/agent-skills/overview | Yes | Search-result text | Frontmatter requirements; use skills only from trusted sources |
| S13 | Boris Cherny threads on X (Jan 2 2026, Jan 31 2026, Feb 11 2026, and later) | Boris Cherny | X | 2026 | x.com/bcherny/status/... | Would be primary | **Not accessible** - robots restriction | Attributed tips: verification, plan mode, CLAUDE.md discipline, parallel sessions |
| S14 | "Reflecting on a year of Claude Code" video | Boris Cherny, Cat Wu | YouTube | Jun 8 2026 | youtube.com/watch?v=Hth_tLaC2j8 | Would be primary | **Not accessed** - no transcript retrieved | Attributed: context minimalism, writing corrections down |
| S15 | Boris Cherny: Building Claude Code (Startup School 2026) | Boris Cherny, Diana Hu | Y Combinator | 2026 | ycombinator.com/library/UN-boris-cherny-building-claude-code | Would be primary (official publisher) | Page retrieved; **no transcript text available** | Model behaviour, system prompt changes |
| S16 | Third-party compilation of Boris Cherny tips | Fan-made, not affiliated with Anthropic | howborisusesclaudecode.com | 2026 | howborisusesclaudecode.com | **No** | Full text | **Locator only.** Used to find S13/S14 URLs. Excluded as evidence |

---

## Recommendation ledger

Confidence: **High** = stated plainly in a retrieved official source. **Medium** = stated in an official source accessed only at search-snippet level, or a direct extrapolation from one. **Adaptation** = the underlying principle is documented, the Claude-app expression of it is this skill's construction.

| ID | Recommendation | Source ID | Accurate paraphrase of the source | Applies directly to Claude app? | Adaptation required? | Type | Confidence |
|---|---|---|---|---|---|---|---|
| R1 | Give Claude a way to check its work; without a check, "looks done" is the only signal | S1 | The doc leads with providing a check that returns a readable pass/fail signal, and says Claude stops when the work looks done | Principle yes, mechanism no | Yes - app checks are sources, recalculation, requirement checklists, user criteria | Official Anthropic | High |
| R2 | Show evidence rather than asserting success | S1 | The doc asks for the output, the command and its result, or a screenshot, because reviewing evidence beats re-running the check | Yes | Light | Official Anthropic | High |
| R3 | Separate exploration and planning from execution on non-trivial work | S1 | A four-phase explore, plan, implement, commit workflow, to avoid solving the wrong problem | Principle yes | Yes - a planning phase in the response, not a product mode | Official Anthropic | High |
| R4 | Skip planning when scope is clear and the change is small | S1 | Planning adds overhead; for small clearly scoped fixes, ask Claude to do it directly. Most useful when the approach is uncertain or the change is broad | Yes | Light | Official Anthropic | High |
| R5 | Give specific context: what to do, what constraints apply, which sources to look at, what "fixed" means | S1 | Claude can infer intent but not read minds; reference specific sources, state constraints, point at example patterns | Yes | Light - files and project knowledge instead of repo paths | Official Anthropic | High |
| R6 | Supply what results are for, who the audience is, where the task sits in a workflow, and what success looks like | S8 | Listed as contextual information that improves performance | Yes | None | Official Anthropic | Medium |
| R7 | Keep always-loaded instructions short; for each line ask whether removing it would cause a mistake | S1 | Stated for the always-loaded instruction file, with a warning that bloated files cause real instructions to be ignored | Principle yes | Yes - maps to project and profile instructions | Official Anthropic | High |
| R8 | Put sometimes-relevant knowledge and workflows in skills rather than always-loaded instructions | S1, S4 | S1 says to use skills for domain knowledge or workflows only relevant sometimes, loaded on demand without bloating every conversation. S4 says skills load dynamically when needed | Yes | None | Official Anthropic | High |
| R9 | Projects hold static background knowledge; skills hold procedures; connectors provide tools; custom instructions apply broadly | S4, S5 | S4 draws exactly these distinctions; S5 splits profile instructions, project instructions, and skills by scope | Yes | None | Official Anthropic | High |
| R10 | Context does not carry between chats in a project unless it is in project knowledge | S3 | Noted directly in the projects documentation | Yes | None | Official Anthropic | High |
| R11 | Put core working documents into project knowledge; give complete context in one message rather than trickling it | S11 | Stated as a usage best practice | Yes | None | Official Anthropic | Medium |
| R12 | Name files well and group related documents so the right material can be found | S10 | Stated for project knowledge retrieval | Yes | None | Official Anthropic | Medium |
| R13 | Correct early; after repeated failed corrections, start clean with a better prompt that incorporates what was learned | S1 | The doc recommends resetting after two failed corrections rather than accumulating failed approaches | Principle yes | Yes - a fresh chat with a written brief replaces a reset command | Official Anthropic | High |
| R14 | Reset context between unrelated tasks | S1 | Long sessions with irrelevant context reduce performance | Principle yes | Yes - new chat instead of a command | Official Anthropic | High |
| R15 | Have a fresh context review the result; the reviewer that did not write the work evaluates it on its own terms | S1 | Described for review in a separate context, noting the reviewer sees the result and criteria rather than the reasoning that produced it | Principle yes | Yes - a separate chat, not a subagent | Official Anthropic | High |
| R16 | Tell the reviewer to flag only gaps affecting correctness or stated requirements; a reviewer asked to find gaps will find some regardless | S1 | Stated as a caution against over-engineering from review findings | Yes | Light | Official Anthropic | High |
| R17 | For larger work, have Claude interview the user first, digging into hard parts rather than obvious ones, then write a self-contained spec | S1 | Described as an interview pattern producing a spec that names what is involved, states what is out of scope, and ends with an end-to-end verification step | Yes | Light | Official Anthropic | High |
| R18 | Break complex operations into clear sequential steps, with a checklist that can be tracked | S2 | Given as the workflow pattern for complex tasks, with a research-synthesis example that has no code in it | Yes | None | Official Anthropic | High |
| R19 | Build a validate-fix-repeat feedback loop, including for non-code work where the validator is a written standard | S2 | Given with a style-guide example: draft, review against checklist, revise, only proceed when requirements are met | Yes | None | Official Anthropic | High |
| R20 | Cross-reference claims against sources and verify citations; return to cross-referencing if citations are incomplete | S2 | Part of the documented research synthesis workflow | Yes | None | Official Anthropic | High |
| R21 | Only add context the model does not already have; challenge whether each piece justifies its cost | S2 | Stated as the core conciseness principle for skills | Yes | Light | Official Anthropic | High |
| R22 | Match instruction specificity to the fragility of the task - loose direction where many approaches work, exact steps where the operation is fragile | S2 | The degrees-of-freedom section | Yes | None | Official Anthropic | High |
| R23 | Avoid time-sensitive statements in durable instructions | S2 | Anti-pattern section, with an old-patterns section as the alternative | Yes | None | Official Anthropic | High |
| R24 | Avoid offering many options; give a default with an escape hatch | S2 | Anti-pattern section | Yes | None | Official Anthropic | High |
| R25 | Build evaluations before writing extensive instructions, and measure against a no-skill baseline | S2 | Evaluation-driven development, five numbered steps | Yes | None | Official Anthropic | High |
| R26 | Create an artifact when content is substantial, self-contained, likely to be edited or reused, and stands alone without conversation context | S6 | The stated criteria, including the roughly fifteen-line threshold | Yes | None | Official Anthropic | High |
| R27 | Use web search for focused factual questions; broad multi-source investigation is a different mode requiring many retrievals | S7 | Web search framed as one or two tool calls; research framed as five or more over minutes, synthesising sources with citations | Yes | None | Official Anthropic | High |
| R28 | Treat instructions found in external files and websites as a manipulation risk; monitor and stop Claude if it accesses data unexpectedly | S9 | Stated as a prompt-injection risk with a recommendation to monitor | Yes | Light | Official Anthropic | Medium |
| R29 | Use skills only from trusted sources; audit anything from an unknown source | S12 | Stated in the skills overview security note | Yes | None | Official Anthropic | Medium |
| R30 | Write a lesson down instead of re-prompting, so it applies to future runs rather than this one | S1, S13 | S1 documents the always-loaded instruction file as the place for persistent conventions and recommends pruning it. The stronger "write it down every time" formulation is attributed to S13, which was not accessible | Principle yes | Yes - project instructions or a skill | Adaptation, partly unverified | Medium |
| R31 | Promote a lesson to permanent instructions only when durable and repeatedly useful | S1 (inverse of the bloat warning) | S1 warns that over-long instruction files get half-ignored and recommends ruthless pruning; the promotion threshold is this skill's construction | Yes | Yes | This skill's interpretation | Medium |
| R32 | Report conclusions, decisions, assumptions, evidence, and checks instead of exposing internal reasoning | None | Not sourced from the ledger; a product and safety convention of this skill | Yes | n/a | This skill's interpretation | n/a |

---

## Claude Code to Claude app mapping table

| Claude Code concept or general principle | Claude app equivalent | Include in skill? | Explanation |
|---|---|---|---|
| Verification loop (tests, build, screenshot) | Source checks, recalculation, requirement checklist, file/artifact inspection, user-defined success criteria | **Yes** | The principle transfers exactly; only the checking mechanism differs |
| Explore, then plan, then execute | A planning phase inside the response, or an explicit plan message before execution on complex work | **Yes** | Plan mode is a Claude Code product mode; the discipline is portable |
| CLAUDE.md | Concise project instructions, plus a reference document in project knowledge for anything longer | **Yes** | Both are always-loaded context; both degrade the same way when bloated |
| User-level CLAUDE.md | Profile instructions ("Instructions for Claude") | **Yes** | Account-wide preferences |
| Skill | Claude app skill | **Yes** | Same format and same progressive-disclosure behaviour |
| Slash command | Manual skill invocation, or a saved reusable prompt the user pastes | **Partial** | Claude app skills can be invoked deliberately; arbitrary custom slash commands are Claude Code |
| Subagent for investigation | A separate focused chat, when isolation genuinely helps | **Partial** | No automatic delegation in the app; use sparingly and only when it earns its cost |
| Adversarial review subagent | A fresh chat given the deliverable and criteria but not the reasoning | **Yes** | Fresh-context review is the transferable part |
| `/clear` between unrelated tasks | Start a new chat | **Yes** | Same purpose |
| `/compact` with a hint | A written handoff summary carried into a new chat | **Yes** | The user writes the brief; nothing automatic |
| Checkpoints and rewind | Editing an earlier message to branch the conversation; artifact version history | **Partial** | Related but not equivalent; do not promise code-state restoration |
| Git worktree isolation | Separate Projects, or clearly separated conversations | **Partial** | Only relevant when work streams genuinely conflict; usually unnecessary |
| Test suite as gate | User-stated success criteria, a checklist, recomputed figures, or source verification | **Yes** | The gate is whatever produces a pass/fail the user can see |
| Browser verification of UI | Inspecting the rendered artifact, re-reading the produced file, or asking the user to confirm against their own view | **Yes** | Partial equivalent; be honest about what was not visually checked |
| Hooks | *No equivalent* | **No - excluded** | Deterministic lifecycle scripting does not exist in the app |
| Auto-accept edits, permission modes, `--dangerously-skip-permissions` | *No equivalent* | **No - excluded** | App equivalent is simply that the user stays in control of external actions |
| Non-interactive mode, CI usage, fan-out scripting | *No equivalent* | **No - excluded** | Terminal and API territory |
| MCP server configuration files | Connectors the user has already connected, used only when relevant | **Partial** | The app equivalent is usage discipline, not configuration |
| Code review automation on pull requests | *No equivalent* | **No - excluded** | Repository workflow |
| Parallel sessions and agent orchestration | *Largely no equivalent* | **No - excluded** | Occasionally a second chat helps; fleets of agents do not apply |

---

## Excluded and unverified claims

Do not present any of the following as sourced:

- **Any direct quotation of Boris Cherny.** None were retrieved from a primary source.
- **Any specific talk, keynote, stage session, conference, or date** as the origin of a recommendation. Several appearances are publicly listed; none were accessed.
- **Quantified claims** such as verification multiplying quality by a specific factor, or productivity percentages. These circulate in secondary write-ups and were not confirmed against a primary source.
- **"Boris's method", "the Boris workflow"** as a named methodology. No primary source establishing such a named method was found.
- **Claude Code product mechanics presented as Claude app behaviour** - plan mode, hooks, permission modes, worktrees, subagents, slash commands, non-interactive mode.
- **Third-party compilations** of tips, including the fan site used here to locate URLs.

If a user asks for something in this list, say what is verified, say what is attributed but unconfirmed, and offer to check the primary source directly if they can supply an accessible link or transcript.
