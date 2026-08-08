# Example: creating a deliverable

Shows the artifact-versus-chat-versus-file decision, and verification of numbers.

## Request

> Here's our raw sales export [file attached]. Build me a quarterly summary I can send to the leadership team.

## Tier

Medium. Clear objective, real constraints, a deliverable someone else will read.

## Decision: what form?

"Send to the leadership team" means a file. Not chat text they would have to reformat, and not only an in-conversation artifact if the destination is email. Confirm the format in a clause, not a paragraph:

> Building this as a spreadsheet with a summary tab, since the leadership team will likely want to sort and filter. Say if you'd rather have a document.

## What the skill does

**1. Read the actual file before designing anything.** Column names, date range, row count, obvious data problems. Do not assume the structure a sales export "usually" has.

**2. Surface data problems before they become findings.**

> Two things in the export before I summarise: 47 rows have no region, and the date range runs to the 28th, not quarter end. I'll show the no-region rows as "Unassigned" rather than dropping them, and label the period by its actual dates. Say if either should be handled differently.

**3. Build.** Summary first, detail behind it. Only the metrics that answer a leadership question.

**4. Verify - the part that matters.**

- Recalculate every total, not restate it. Sum of segments equals the reported total.
- Percentages recomputed from the same base, and the base stated.
- Period-over-period comparisons use like periods; if the current quarter is short by two days, say so where the comparison appears.
- Row count in equals row count accounted for, including excluded rows.
- Every figure in the summary traceable to a cell in the detail.

**5. Report.**

> `Q3-sales-summary.xlsx` - summary tab plus detail by region and product.
>
> Checked: segment totals sum to the reported total (£X); all percentages recomputed against revenue, not order count; row count reconciles - 2,431 in, 2,431 accounted for, of which 47 sit under "Unassigned" for missing region.
>
> Assumed: "Closed-Won" is the only status counting as revenue. Four other statuses appear in the export and are excluded.
>
> Not checked: whether the export itself is complete for the period. That would need a comparison against the source system.
>
> Next: if the Unassigned rows matter for the regional comparison, someone with CRM access can fill those in and I'll rerun.

## What makes this different from a plausible-looking summary

The unchecked things are named. The assumption about revenue status is stated rather than buried - it is exactly the kind of choice that silently changes every figure. And every number was recomputed, not carried forward from an earlier step.

## Failure modes avoided

| Anti-pattern | What it would look like |
|---|---|
| Declaring done | "Summary complete and verified." |
| Silent handling of dirty data | Dropping the 47 rows and reporting a clean total |
| Restating numbers | Copying a total from the export rather than recomputing it |
| Hidden assumption | Excluding four statuses without saying so |
| Wrong form | Pasting 60 lines of table into the chat |
