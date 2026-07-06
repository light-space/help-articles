# Astra Agents

Astra is Light's autonomous financial operations agent. It works in the background — without anyone typing a prompt — monitoring your company's books, investigating issues, and reporting findings to the people you designate. Astra runs several types of scheduled analyses, each with a different scope and cadence, and remembers what it learns between runs.

[Open in Light →](https://app.light.inc/dashboard)

## Overview

Unlike LCI (Light's conversational assistant), Astra is not something you chat with. It runs on its own schedule as a dedicated AI agent for your company. On each run, Astra:

1. Reads your **Company Memory** — the instructions your admins have written for it — plus its own notes from previous runs
2. Reviews a feed of recent platform errors (failed sales invoices, bills, card transactions, reimbursements, and batch operations)
3. Investigates using Light's internal tools — searching bills, invoices, expenses, journal entries, and more — before drawing any conclusions
4. Produces **findings** (issues worth your attention) and **observations** (notes it logs for future reference)
5. Delivers findings as a message to the recipients named in Company Memory

Astra is enabled per company by Light. If Astra isn't active for your company, contact Light support.

## The Analysis Types

Astra runs four types of analyses:

**Daily health check** — Astra's core monitoring run. It reviews recent activity and error states, investigates anything unusual, and reports material issues. The cadence is adaptive: at the end of each health check, Astra itself decides when to check back based on your company's transaction volume, open items, and upcoming deadlines — anywhere from every 10 minutes to once every 24 hours (6 hours by default).

**Weekly review** — Runs every Monday at 3 AM UTC. Astra looks at the week's activity, compares it week-over-week, and cross-references recurring issues from its observations, reporting only significant patterns.

**Monthly deep review** — Runs on the first day of each month at 4 AM UTC. Astra produces the monthly close memo, a structured record of the prior period for finance leaders. See [Astra Monthly Review](12-9-astra-monthly-review.md).

**Introspection consolidation** — Runs daily at 1 AM UTC. Astra reviews what it has learned across prior runs and consolidates durable insights into Company Memory as tagged blocks (`[astra:insight]`, `[astra:pattern]`, `[astra:resolved]`). This is the only run type where Astra writes to Company Memory. Observations older than 90 days are pruned. See [Configuring Company Memory in Astra](12-10-astra-company-memory.md).

## Findings and Delivery

Each finding Astra reports includes:

- **Severity** — Info, Warning, or Critical
- **Category** — for example payment, invoice, approval, or bank feed
- **Title and description** — what Astra found, what it did, and what it recommends
- **Actions taken** — anything Astra already executed, such as creating a support ticket
- **Entity references** — links to the specific bills, invoices, expenses, card transactions, or other records it investigated

Findings are delivered as a direct message to the recipients named in Company Memory, over the channel specified there (for example Slack or email). If Company Memory doesn't name a recipient, Astra records its findings but doesn't send messages.

Astra avoids repeating itself: findings it already reported in the last 24 hours are not re-sent unless something meaningful has changed. When an issue calls for it, Astra can also open a support ticket with Light on your behalf and reference the ticket in its finding.

## Configuring Astra

Astra's configuration surface is **Company Memory** — plain-text instructions your admins write that Astra treats as authoritative on every run. Use it to tell Astra who should receive findings and on which channel, company-specific context, and custom workflows. See [Configuring Company Memory in Astra](12-10-astra-company-memory.md) for details.

> Good to know: Astra's Company Memory is distinct from **Assistant Instructions**, which guide how Light's AI parses specific document types (bills, contracts, intake documents, and reimbursements). Assistant Instructions don't affect Astra's monitoring runs.

## Run History

Every Astra run is logged with its analysis type, start and completion time, result, findings count, and a summary. Each run also keeps a full transcript — the instructions Astra received, the tool calls it made, and its final analysis — so admins can audit exactly what Astra did and why.

Users with finance roles (such as company admin, controller, auditor, AP preparation, AR clerk, or invoice approver) can also trigger an Astra analysis on demand rather than waiting for the next scheduled run.

## Good to Know

- **Astra acts as its own user** — Runs are performed by a dedicated AI agent principal for your company, not by any human user's account.
- **Investigation before communication** — Astra is instructed to always investigate with real data before reporting, and to include specific numbers and entity references in its findings.
- **Company Memory wins** — Instructions in Company Memory override Astra's default behavior. If Astra is doing something you don't want, write a directive in Company Memory.
- **Bounded runs** — Each analysis has a hard cap on the number of tool calls, after which Astra summarizes what it found so far.

## Troubleshooting

### Not Receiving Astra Findings

- Confirm Astra is enabled for your company (it's activated per company by Light).
- Check that Company Memory names a recipient and channel for findings. Without a named recipient, Astra logs findings but sends nothing.
- Astra doesn't re-send findings it already reported in the last 24 hours unless something changed — silence may just mean nothing new.

### Astra Reports Too Often (or Not Often Enough)

- The daily health check cadence is adaptive and set by Astra based on your company's activity. You can guide it with a directive in Company Memory (for example, which issues matter and which don't).
- Weekly and monthly runs are fixed-schedule and can't be moved.

## Related Articles

- [Astra Monthly Review](12-9-astra-monthly-review.md)
- [Configuring Company Memory in Astra](12-10-astra-company-memory.md)
- [Light Command Interface (LCI)](12-7-ai-conversational-assistant.md)
- [How Light Uses AI](12-1-how-light-uses-ai.md)
