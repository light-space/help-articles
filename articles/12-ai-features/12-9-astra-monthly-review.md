# Astra Monthly Review

Once a month, Astra produces a close memo — a structured observation about how your business changed over the prior month. This memo is for finance leaders (CFO, controller, segment finance leads) and is delivered through your configured notification channel.

[Open in Light →](https://app.light.inc/dashboard)

## When It Runs

Astra's monthly review runs automatically on the first day of each month at 4 AM UTC. The review analyzes the prior month's closed data after period close.

## What You Receive

The close memo is a single message with six numbered sections, in this order:

1. **Executive summary**  
   Three to five sentences: headline P&L number, EBITDA, cash, and anything from sections 5 or 6 that needs flagging.

2. **P&L summary**  
   A variance table (actual / budget / variance / prior month) followed by short driver paragraphs for any line that moved materially. If no budget is provided in Company Memory, the memo benchmarks against the prior month and the trailing-6-month average instead.

3. **Material journal entries**  
   A table of significant entries posted in the period (JE number, description, amount, rationale), including any prior-period error and its materiality assessment.

4. **Balance sheet — key movements**  
   Cash walk, AR aging and DSO, deferred revenue waterfall, accrued expenses composition, intercompany, working capital shifts.

5. **Open reconciling items**  
   Anything not tied out at close: what it is, the amount, the diagnostic, and the expected resolution date.

6. **Controls & compliance**  
   Confirmation that scheduled control checks ran across cash, AR, AP, payroll, intercompany, revenue recognition, and tax, with findings (or "no findings").

Prose is kept terse — roughly 500–800 words total, with tables on top of that — and every numerical claim includes the number, the comparison period, and where it came from. If a section has nothing material to report, Astra states "Nothing material this month" and moves on.

## Where You Read It

Astra delivers the close memo through your configured notification channel — the same channel used for other Astra findings. The channel is specified in Company Memory (the instructions you provide to Astra).

If you receive Astra notifications in Slack, the close memo arrives as a direct message from @Light. If you receive them in Microsoft Teams, it arrives from the Light bot.

## Who Should Care

The monthly close memo is the durable record of the period for the CFO, controller, and segment finance leads:

- **CFO** — Executive summary, P&L variance and drivers, balance sheet movements
- **Controller** — Material journal entries, open reconciling items, controls and compliance
- **Segment finance leads** — P&L drivers and movements relevant to their segment

The memo never attributes work or remediation items to named individuals — Astra writes in its own voice about the checks and reconciliations it performed.

## What the Memo Covers

The monthly review draws on Astra's full view of your closed financials:

- General ledger and subledgers for the closed period
- Bank balances, AR/AP aging, contract roster
- Vendor and customer master data
- Astra's own memory: observations, flags, dismissals, and resolutions from hourly, daily, and weekly runs over the prior 13 months
- Approval queues, manual journal entry log, control exceptions

Astra compares the closed month against the budget provided in Company Memory. If no budget is provided, it benchmarks against the prior month and the trailing-6-month average instead — it never invents targets.

## What the Memo Is Not

- **Not a full P&L recap.** The memo includes a variance summary, but only lines that moved materially get commentary — no four-page recap of every line item, and no re-explaining what you already saw in the dashboard.
- **Not a recommendations document.** The memo observes with evidence and lets humans conclude. It does not prescribe actions.
- **Not comprehensive.** Each section keeps only items where the magnitude matters, someone can act on it, or the pattern is genuinely new. Materiality beats completeness.
- **Not a thread.** A single artifact, delivered once, complete.

## Good to Know

- Astra only produces the close memo if you have configured a notification recipient in Company Memory. Without a recipient, Astra logs the memo internally but does not deliver it.
- The memo references specific entity IDs (bills, invoices, vendors, journal entries) from Light's data. Click through to view the entity details in the platform.
- If two data sources disagree on a number, Astra states the conflict explicitly rather than choosing one.
- If Astra lacks a baseline for comparison (for example, your first few months in Light), the memo states "no prior baseline" rather than inventing one.
- The monthly review is part of the same per-company Astra enablement as the daily and weekly runs — if Astra is enabled for your company, all scheduled runs are active. There is no separate toggle for the monthly review.

## Related Articles

- [How Light Uses AI](12-1-how-light-uses-ai.md)
- [Light Command Interface (LCI)](12-7-ai-conversational-assistant.md)
