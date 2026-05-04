# Astra Monthly Review

When you close a period, Astra automatically produces a monthly close memo on the first business day after the close. This memo helps CFOs, controllers, and segment finance leads understand how the business changed last month and how that fits into longer trends — without duplicating the P&L recap you already see in your dashboard.

[Open in Light →](https://app.light.inc/dashboard)

## Overview

Astra's monthly review runs once per month, on the first business day after period close. It's the only Astra run with enough distance to see the shape of the business changing and enough proximity to do something about it before quarter-end.

The monthly review produces a single artifact: the **close memo**. This is a structured, observation-focused document delivered as one coherent message (not a thread or series of replies). The memo assumes your team already has access to the income statement and dashboard — it surfaces patterns, breaks, and absences that wouldn't be visible from summary metrics alone.

> Good to know: Astra's monthly review is observation-only. It does not make recommendations or take actions like posting journal entries. Every claim in the memo includes a number, a comparison period, and a source.

## When the Monthly Review Runs

The monthly review runs automatically on the first business day after you close the period. You don't need to schedule or trigger it manually. Light detects the period close event and queues the review to run the next business day.

If the period isn't closed, the review doesn't run. Astra needs the prior period locked and the current period closed to compare trends accurately.

## What the Close Memo Contains

The close memo opens with a 4-line headline summarizing the three things that changed and one thing to watch, followed by six sections:

1. **Structural shifts** → CFO
2. **Trend breaks** → Controller
3. **Collections & AR posture** → AR lead
4. **Spend, vendors, commitments** → AP lead
5. **Controls & manual activity** → Controller
6. **What I flagged this month and what happened to it** → CFO

Each section is tagged to a single owner and capped at 120 words. If a section has nothing material to report, Astra writes "Nothing material this month" rather than padding the section with filler.

### What Gets Included

Astra includes items in the memo based on three criteria:

- **The magnitude matters** — the change is large enough to affect decision-making
- **Someone can act on it** — the observation is actionable, not just informational noise
- **The pattern is genuinely new** — it's a break from the trailing six months, not a continuation of an existing trend

Everything else is filtered out. The memo is done when it's right, not when it's long.

### What Astra Has Access To

When producing the close memo, Astra has access to:

- Full general ledger and subledgers (current period closed, prior periods locked)
- Bank balances, AR/AP aging, contract roster, vendor and customer masters
- Its own memory: every observation, flag, dismissal, and resolution from hourly, daily, and weekly runs over the prior ~13 months
- Open-period operational signals: approval queues, manual journal entry log, control exceptions

Astra does not have access to forecast or budget data. The memo does not compare actuals to budget or project future performance.

## How Astra Builds the Memo

Before writing the memo, Astra works through five thinking steps in order:

1. **Structural snapshot** — Concentration metrics (top-5 customer %, top-10 vendor %), segment mix, unit economics by segment, headcount-adjusted ratios. Compares against the last 6 monthly snapshots in memory, not just last month.

2. **Trend breaks** — Which series crossed a threshold this month that they hadn't in the trailing 6 months? Which changed direction? Pulls prior values from memory.

3. **Cessations and absences** — Recurring patterns that stopped. A customer billed monthly for 11 months and not this one. A vendor going silent. A recurring journal entry template that didn't fire. Silence is only visible with memory — Astra surfaces it.

4. **Self-reflection** — Pulls every flag Astra raised in shorter-cycle runs (hourly, daily, weekly) this month. Categorizes: resolved, dismissed, recurring, ignored. Recurring + ignored is the highest-priority class.

5. **Materiality filter** — From everything above, keeps only items where the three criteria (magnitude, actionability, newness) apply. Discards the rest.

Astra does not write the memo until it completes step 5.

## Evidence Requirements

Every claim in the close memo must include:

- A **number** — the actual metric or amount
- A **comparison period** — "vs. last month," "trailing-6mo avg," "prior peak: 33%, Aug"
- A **source** — "AR subledger, entity DE," "contracts table, MRR snapshot 2026-03-31," "bill search results"

If Astra doesn't have a prior baseline, it writes "no prior baseline" explicitly. If two sources disagree on a number, the memo says so and stops — Astra does not silently pick one.

This rule keeps the memo grounded in what the system actually knows. Astra never invents a cause or fills gaps with speculation.

## What the Memo Does Not Include

The monthly close memo is **not**:

- **A P&L recap.** Your BI tools already produce one. Astra does not duplicate it.
- **A recommendations doc.** The memo observes with evidence and lets humans conclude. Astra may earn the right to recommend later, after several cycles of trusted observations. Until then, no "we should" or "consider doing X."
- **A list of everything notable.** Material beats comprehensive. If Astra flagged 40 things this month, the memo names the 6–10 that matter.

If a section has nothing material to report, Astra writes "Nothing material this month" and moves on. The memo does not include padding, hedging filler ("it appears that," "this could potentially," "interestingly"), emojis, or exclamation marks.

## Tone and Calibration

The close memo uses plain, declarative sentences. Astra writes confidently when the evidence is clear. When it isn't, the memo is explicitly uncertain:

> "I can't tell from the ledger whether X is a billing delay or churn — flagging for review."

Astra never invents a cause. It reports the pattern and lets humans diagnose.

### Example: Good vs. Bad

**Good:**
> Structural shifts. Top-5 customer concentration moved from 28% to 41% of MRR, driven entirely by Customer A's expansion contract closing in March. This is the highest concentration in your trailing 13 months (prior peak: 33%, Aug). Source: contracts table, MRR snapshot 2026-03-31.

**Bad:**
> Structural shifts. Revenue grew this month, which is great to see! Customer concentration may have shifted, and we should potentially keep an eye on top customers going forward.

The first has a number, a comparison, and a source. The second has none of those.

## How to Access the Memo

Astra delivers the monthly close memo to the company's configured notification channel (Slack, Microsoft Teams, or the Light web app). The memo appears as a single message from @Astra, not a threaded reply.

If your team uses Slack or Teams, you'll see the memo in your direct message channel with the Light bot. If you don't have Slack or Teams connected, Astra delivers the memo in the Light web app.

## Safety Guardrails

Astra's monthly review is read-only. It does not:

- Post journal entries or accruals
- Approve or reject bills
- Change tax codes or configurations
- Modify chart of accounts or approval workflows

The monthly review produces a memo. That's it. Any actions based on the memo are taken by humans through the normal workflows in Light.

> Good to know: Earlier versions of Astra's monthly review included automated tax code validation and vendor-spend accruals. These capabilities were removed. The monthly cadence is now focused on observation, not side-effectful work.

## Limitations

The monthly review depends on Astra's memory from prior runs. If this is your company's first month using Light, the memo may include fewer trend comparisons because Astra doesn't have trailing 6-month baselines yet. After several months, the memo becomes richer as Astra builds memory.

The memo does not include forecast or budget comparisons. If you need actuals-vs-budget reporting, use **Planning & Reports → Reports** in the Light web app.

## Related Articles

- [How Light Uses AI](12-1-how-light-uses-ai.md)
- [Light Command Interface (LCI)](12-7-ai-conversational-assistant.md)
- [AI-Assisted Reconciliation](12-6-ai-reconciliation.md)
