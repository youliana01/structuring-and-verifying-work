# Example: reviewing before finalising

Shows a real self-review that finds things, and the fresh-context review for work that is expensive to redo.

## Request

> Review your last answer before I send it.

## Tier

Medium. The review itself is the task.

## What a real review looks like

Not a summary of what was written. A pass against the original request, looking for specific classes of defect.

```
Checked against your original request:

Present
- three-year projection: yes
- headcount plan: yes
- sensitivity on churn: yes

Missing
- you asked for the assumption list as a separate section. It is
  scattered through the narrative instead. Fixing.

Numbers
- recomputed all totals. One error: the year-2 revenue line does not
  match the sum of its segments (£1.42m stated, £1.38m from segments).
  The £1.42m came from an earlier draft with a different churn rate.
  Corrected to £1.38m; two downstream figures move with it.

Claims
- the market-size figure is from a source I did not retrieve in full -
  I saw it in a search summary. Treat it as unconfirmed or let me
  verify it properly.

Consistency
- section 2 says "launch in Q1", section 4 assumes revenue from month 1.
  Those disagree by a quarter. Which is right?

Not checked
- whether the churn assumption is realistic for your segment. That is
  a judgement about your business, not something I can verify.
```

## What makes this a review rather than a re-summary

- It found an arithmetic error and traced its cause.
- It found an internal contradiction and asked rather than picking silently.
- It flagged a claim that was snippet-level rather than retrieved.
- It named what it could not check.
- It checked against the **original request**, not against the outline that was written.

A review that reports no findings on a substantial deliverable usually means the review did not happen.

## The counterweight

Anthropic's guidance notes that a reviewer asked to find gaps will usually find some, whether or not the work is sound, and that chasing every finding leads to over-engineering. So: flag what affects correctness or the stated requirements. Style preferences are optional and should be labelled as such.

## When to use a fresh chat instead

Self-review cannot catch a blind spot in the reasoning that produced the work. For anything expensive to redo, start a new chat and give it the deliverable and the criteria - but **not** the reasoning:

```
Review the attached against these requirements: [list].
Check every requirement is met, all figures are internally consistent,
and no claim is unsupported.
Report only gaps affecting correctness or the stated requirements.
Do not rewrite it.
```

Withholding the reasoning is the point. A reviewer given the argument tends to grade the argument rather than the artifact.

## Reporting the review

Lead with whether it is ready. Then what was fixed, what needs the user's decision, and what remains unverified. Do not close with a description of the reviewing process.
