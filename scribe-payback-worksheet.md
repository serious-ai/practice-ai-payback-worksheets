# AI scribe payback worksheet, written out

The lines and formulas in [scribe-payback-worksheet.xlsx](scribe-payback-worksheet.xlsx), so you can rebuild it anywhere or check the math. Column B is before go-live, column C is after. Method and research: [Did Your AI Scribe Actually Pay for Itself?](https://seriousai.partners/did-your-ai-scribe-pay-for-itself/)

## Inputs (per clinician per month, or a group's average)

| Row | Line | Before (B) | After (C) | Where it comes from |
| --- | --- | --- | --- | --- |
| 4 | Scribe cost per clinician per month, all in | n/a | your number | Contract price plus integration, training and support billed separately |
| 5 | Visits per clinician per month | your number | your number | Billing or scheduling report. Same months before and after, a year apart if you can |
| 6 | Collected per visit | your number | your number | Payments received divided by visits. Hold payer mix steady, and back out any contract rate change |
| 7 | Documentation minutes per visit, proofreading included | your number | your number | EHR audit log, or time a sample of visits yourself |
| 8 | Days to close a chart | your number | your number | EHR report. Cash timing only, so it stays out of the dollar math below |
| 9 | Share of the coding lift a payer could take back | n/a | your guess | Your stress test. Try 50% and 100% |

## Results

| Row | Line | Formula | What it tells you |
| --- | --- | --- | --- |
| 11 | Volume lift | `(C5 - B5) * B6` | Added visits at the old collected amount |
| 12 | Coding lift | `C5 * (C6 - B6)` | Higher collected per visit on the new volume. Count it only if a coder sample says the notes support the level billed |
| 13 | Net payback | `C11 + C12 - C4` | Above zero, the scribe is paying for itself on these numbers |
| 14 | Net payback if payers take back that share | `C11 + C12 * (1 - C9) - C4` | What's left under the stress test |
| 15 | Net payback if payers take back all of it | `C11 - C4` | Does it still pay on volume alone? |
| 16 | Hours of documentation saved | `(B7 - C7) * C5 / 60` | Time, not dollars. Count it only where it went somewhere you can name |
