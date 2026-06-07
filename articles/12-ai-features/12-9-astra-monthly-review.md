# Astra Monthly Review

Once a month, Astra produces a close memo — a structured observation about how your business changed over the prior month. This memo is for finance leaders (CFO, controller, segment finance leads) and is delivered through your configured notification channel.

[Open in Light →](https://app.light.inc/dashboard)

## When It Runs

Astra's monthly review runs automatically on the first day of each month at 4 AM UTC. The review analyzes the prior month's closed data after period close.

## What You Receive

The close memo is a single message with a 4-line headline and six sections:

**Headline:**
- Close memo · {month}
- Three things that changed
- One thing to watch

**Sections:**
1. **Structural shifts** → CFO  
   Customer concentration, vendor concentration, segment mix, headcount-adjusted ratios compared to prior months.

2. **Trend breaks** → Controller  
   Series that crossed thresholds or changed direction compared to trailing months.

3. **Collections & AR posture** → AR lead  
   Aging patterns, collection activity, customer payment behavior.

4. **Spend, vendors, commitments** → AP lead  
   Vendor spend patterns, new commitments, recurring spend changes.

5. **Controls & manual activity** → Controller  
   Manual journal entries, approval queue patterns, control exceptions.

6. **What I flagged this month and what happened to it** → CFO  
   Status of findings Astra raised during daily and weekly runs: resolved, dismissed, recurring, or ignored.

Each section is brief (typically under 120 words) and includes specific numbers, comparison periods, and data sources. If a section has nothing material to report, Astra states "Nothing material this month" and moves on.

## Where You Read It

Astra delivers the close memo through your configured notification channel — the same channel used for other Astra findings. The channel is specified in Company Memory (the instructions you provide to Astra).

If you receive Astra notifications in Slack, the close memo arrives as a direct message from @Light. If you receive them in Microsoft Teams, it arrives from the Light bot. If you receive them in the web app, the memo appears in your notification feed.

## Who Should Care

The monthly close memo is designed for:

- **CFO** — Structural shifts, trend breaks, summary of what Astra flagged and what happened
- **Controller** — Trend breaks, controls and manual activity
- **AR lead** — Collections and AR posture
- **AP lead** — Spend, vendors, and commitments
- **Segment finance leads** — Structural shifts and trends relevant to their segment

Each section is tagged with its primary owner in the memo header.

## What the Memo Covers

The monthly review draws on Astra's full view of your closed financials:

- General ledger and subledgers for the closed period
- Bank balances, AR/AP aging, contract roster
- Vendor and customer master data
- Astra's own memory: observations, flags, dismissals, and resolutions from hourly, daily, and weekly runs over the prior 13 months
- Approval queues, manual journal entry log, control exceptions

Astra compares the closed month against trailing months (typically 6–13 months) to identify what changed, what stopped, and what matters.

## What the Memo Is Not

- **Not a P&L recap.** Reporting tools already provide this. The close memo focuses on what changed and why it matters, not raw financial statement totals.
- **Not a recommendations document.** The memo observes with evidence. It does not prescribe actions unless Astra has earned that trust through prior cycles.
- **Not comprehensive.** The memo surfaces the 6–10 things that matter, not everything notable. Materiality beats completeness.

## Good to Know

- Astra only produces the close memo if you have configured a notification recipient in Company Memory. Without a recipient, Astra logs the memo internally but does not deliver it.
- The memo references specific entity IDs (bills, invoices, vendors, journal entries) from Light's data. Click through to view the entity details in the platform.
- If two data sources disagree on a number, Astra states the conflict explicitly rather than choosing one.
- If Astra lacks a baseline for comparison (for example, your first few months in Light), the memo states "no prior baseline" rather than inventing one.
- The monthly review runs whether or not you have daily or weekly Astra runs enabled. It operates independently.

## Related Articles

- [How Light Uses AI](12-1-how-light-uses-ai.md)
- [Light Command Interface (LCI)](12-7-ai-conversational-assistant.md)
