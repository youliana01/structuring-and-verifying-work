# Example: complex research with source discipline

Shows tiering to complex, primary-source handling, and honest reporting of an unreachable source.

## Request

> Research what the regulator has actually said about [topic] over the last year - primary sources only, I'm going to quote this in a board paper.

## Tier

Complex. Multi-source, the user will act on it, and a wrong citation in a board paper is expensive.

## What the skill does

**1. Objective and success.** Outcome: a defensible summary of the regulator's own published positions, each quotable with a citation. Success: every claim traces to a document actually retrieved.

**2. Inspect what exists.** Check project knowledge and uploads first - if the user has already added filings or correspondence, use them and say so rather than searching from scratch.

**3. Plan, briefly.**

```
PLAN
Objective:     regulator's published positions on [topic], last 12 months, quotable
Scope:         in - official publications, speeches, consultations, guidance
               out - press commentary, law-firm summaries, trade press
Steps:         1 locate the regulator's publication index
               2 retrieve each relevant document in full
               3 extract positions with dates
               4 note changes in position over the period
               5 build source ledger
Verification:  every claim mapped to a retrieved document; dates checked
Risk:          some documents behind access barriers - flagged, not reconstructed
```

**4. Execute in phases**, searching per item rather than one query covering everything.

**5. Report.**

## Good response shape

Findings first, each carrying its source. Then the ledger:

| ID | Document | Publisher | Date | URL | Primary? | Retrieved | Used for |
|---|---|---|---|---|---|---|---|
| 1 | [title] | [regulator] | [date] | [url] | Yes | Full text | Position on X |
| 2 | [title] | [regulator] | [date] | [url] | Yes | Snippet only | Date of consultation |
| 3 | [speech] | [regulator] | [date] | [url] | Yes | **Not retrieved** - no transcript published | Referenced, not quoted |

Then, plainly:

> Two things I could not confirm. The speech in row 3 is listed in the regulator's events index but no transcript or recording is published, so nothing from it is quoted here. And row 2 was only available as a search excerpt - the date is confirmed, the surrounding wording is not.
>
> Where positions shifted: [X] in [month] is narrower than [Y] in [month]. Both are quoted above so you can see the change rather than take my characterisation of it.

## What the skill refuses to do

- Cite a law-firm summary as though it were the regulator.
- Reconstruct the unpublished speech from press coverage of it.
- Present snippet-level material as fully read.
- Say "verified" without the ledger showing what verification meant.

## Verification performed

- Every claim in the findings maps to a ledger row.
- Dates checked against the documents, not against the search result summaries.
- Contradiction check across the period, surfaced rather than smoothed over.
- Stated explicitly: one source unreachable, one snippet-level.
