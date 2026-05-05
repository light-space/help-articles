# Configuring Company Memory in Astra

Company Memory is where admins write custom instructions that guide how Astra — Light's autonomous financial agent — operates for your company. These directives let you tailor Astra's behavior to your team's specific workflows, policies, and communication preferences.

When you write a directive in Company Memory, Astra follows it strictly when performing its scheduled checks (daily health checks, weekly reviews, monthly close memos, and introspection consolidation runs). Memory is shared across all of Astra's analysis types, so instructions you write once apply to every run.

[Open in Light →](https://app.light.inc/dashboard)

## What Company Memory Is For

Use Company Memory to tell Astra:

- **Who should receive findings** — The email address(es) and messaging channel (Slack, Teams, web app) where Astra should send its observations
- **Company-specific context** — Business rules, fiscal calendar dates, approval thresholds, entity structures, or other operational details Astra should know when interpreting your financial data
- **Custom workflows** — Steps Astra should take (or skip) when it detects specific conditions
- **Tone and formatting preferences** — How Astra should structure messages or reports

Company Memory is plain text. Write directives in natural language as if you're briefing a new team member.

> Good to know: Company Memory is where you configure Astra's behavior. This is distinct from **Assistant Instructions** (configured at **Settings → AI Assistant → Instructions**), which guide how Light's AI assistant (LCI) parses specific document types like invoices, contracts, and receipts.

## How Astra Uses Company Memory

When Astra runs an analysis, it reads Company Memory at the start of the run and applies your directives throughout its work. Your instructions remain in effect until you update or remove them.

Astra also writes back into Company Memory during **introspection consolidation** runs. After observing patterns across many runs, Astra distills its learnings into structured blocks tagged with:

- **[astra:insight]** — A pattern or rule Astra has learned about your company's operations
- **[astra:pattern]** — A recurring behavior or trend Astra has observed
- **[astra:resolved]** — A previously flagged issue that has been addressed

These blocks accumulate over time and help Astra remember what it has learned across previous runs. Admin-authored directives and Astra-generated blocks coexist in the same memory.

## Accessing Company Memory

Company Memory is accessible through the `UPSERT_COMPANY_MEMORY` tool, which admins can call via LCI (Light's conversational AI assistant) or programmatically via API.

**To view current Company Memory through LCI:**
- Open the LCI interface (web app, Slack, or Teams)
- Type: *"Show me the current company memory"*

**To update Company Memory through LCI:**
- Open the LCI interface
- Type: *"Update company memory: [your new directive]"*

When you call `UPSERT_COMPANY_MEMORY`, you provide the full updated content. The system replaces the existing memory with your new version.

> Tip: When updating memory, copy the existing content first, make your edits, and then upsert the full updated text. This preserves existing directives and Astra-generated insights unless you intentionally remove them.

## What to Write

Company Memory supports any directive you can express in plain text. Common examples include:

**Notification recipients:**
```
Send all Astra findings to finance-ops@company.com via email.
```

**Fiscal calendar context:**
```
Our fiscal year ends March 31. Month-end close reviews should reference fiscal months, not calendar months.
```

**Workflow instructions:**
```
When you find overdue bills from vendors tagged "strategic," create a support ticket and notify ap-lead@company.com in Slack immediately.
```

**Approval threshold context:**
```
Bills over $50,000 require CFO approval. Bills under $10,000 auto-approve after department head signs off.
```

Write directives as clearly as you would write them in an internal wiki or onboarding doc. Astra interprets natural language, so you don't need special syntax beyond the tagged blocks Astra itself writes.

## Who Can Edit Company Memory

Company Memory is a company-level configuration. Only admins with appropriate permissions can view or update it. When Astra writes introspection blocks back into memory, it appends them without overwriting your admin-authored directives.

During introspection consolidation, Astra may prune its own blocks (those tagged `[astra:insight]`, `[astra:pattern]`, or `[astra:resolved]`) if they are outdated, superseded, or duplicates. Astra never modifies or removes admin-authored content (any text not inside one of its own tagged blocks).

## When Changes Take Effect

Changes to Company Memory take effect immediately on Astra's next scheduled run. Astra reads the latest memory at the start of each analysis, so there is no caching or delay. If you update memory at 2:00 PM and Astra's next daily health check runs at 2:15 PM, the new directives apply to that run.

## Good to Know

- **Memory is shared across all Astra analysis types** — Directives you write for daily health checks also apply to weekly reviews, monthly close memos, and introspection runs
- **Astra's own blocks grow over time** — Introspection consolidation appends new insights as Astra learns. This is intentional and helps Astra build institutional knowledge
- **If memory grows too large, Astra prunes during consolidation** — Only Astra-generated blocks (`[astra:*]`) are pruned. Admin content is never automatically removed
- **Company Memory is plain text** — No special schema, no YAML, no JSON. Write in natural language

## Related Articles

- [Light Command Interface (LCI)](12-7-ai-conversational-assistant.md)
- [How Light Uses AI](12-1-how-light-uses-ai.md)
