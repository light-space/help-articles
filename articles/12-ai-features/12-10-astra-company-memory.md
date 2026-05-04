# Configuring Company Memory in Astra

Company Memory is Astra's instruction layer — a shared space where admins set explicit guidance on how the AI should operate. When you configure Company Memory, those directives supersede all default rules, trigger workflows, and tool descriptions. Astra treats Company Memory as a direct, binding directive from the team it works for.

[Open in Light →](https://app.light.inc/dashboard)

## Overview

Company Memory is where you tell Astra **how** you want it to work. Think of it as the operating manual for your AI financial assistant. When Astra runs its autonomous workflows — monitoring your books, detecting patterns, and taking action — it reads Company Memory first and follows those instructions strictly, even when they conflict with Astra's default behavior.

Company Memory is available to all admins with the **Company Admin** or **Controller** role. It's configured in **Settings (gear icon) → AI Assistant → Company Memory**.

## How Company Memory Works

Astra reads Company Memory at the beginning of every run, before it evaluates triggers or reads tool descriptions. The instructions you write in Company Memory take absolute priority over everything else in Astra's prompt.

**Instruction priority:**

1. **Company Memory** — Your explicit directives (highest priority)
2. Trigger workflow defaults — The standard workflows built into each trigger
3. Tool descriptions — The guidance in each tool's documentation
4. Astra's default rules — The baseline behavior rules

If anything in Company Memory conflicts with a trigger workflow, a tool description, or Astra's own judgment, Company Memory wins. This priority is unconditional — there are no carve-outs or hard constraints that override your directives.

> Good to know: Company Memory applies company-wide. All Astra triggers and workflows read the same shared memory. If you need trigger-specific instructions, write them as conditional rules in Company Memory (e.g., "When running the month-end close trigger, always send the summary to finance@company.com").

## What You Can Configure

Use Company Memory to:

- **Override default workflows** — Change how Astra handles specific scenarios (e.g., "When you detect duplicate bills, archive the older one automatically without asking")
- **Set communication preferences** — Tell Astra who to notify and how (e.g., "Send all findings to finance@company.com via Slack instead of email")
- **Define company-specific rules** — Teach Astra your organization's conventions (e.g., "Categorize all AWS charges to the Engineering cost center")
- **Control action thresholds** — Set limits on when Astra should act vs. suggest (e.g., "Auto-approve bills under $500 from pre-approved vendors; flag everything else for manual review")
- **Customize entity handling** — Specify how Astra should treat specific vendors, accounts, or transaction types

Company Memory is freeform text. Write instructions as natural language directives — Astra reads them the same way it reads user messages.

## No Hard Constraints

Company Memory supersedes **all** other instructions, with no exceptions. Unlike earlier versions of Astra, there are no hard constraints that limit what Company Memory can override. This means you have full control over Astra's behavior, but it also means you're responsible for ensuring your directives are safe and align with your company's policies.

**What this means in practice:**

- You can tell Astra to post journal entries automatically — but you should only do so if you've validated the logic and understand the accounting impact
- You can override recipient lists for notifications — but ensure sensitive financial data only goes to authorized users
- You can change how Astra handles entity IDs and data lookups — but verify the instructions produce correct results

Astra will follow your directives faithfully. If an instruction in Company Memory conflicts with a safety rule (like "never fabricate entity IDs"), Company Memory wins — so write instructions carefully.

## Astra-Generated Memory Blocks

In addition to admin-authored instructions, Company Memory includes blocks that Astra writes itself during introspection runs. These blocks are tagged with prefixes:

- **[astra:insight]** — Patterns Astra has learned about your company (e.g., "Vendor XYZ always submits invoices 5 days late")
- **[astra:pattern]** — Recurring workflows Astra has identified (e.g., "Monthly AWS bills arrive on the 3rd and are approved by engineering@company.com")
- **[astra:resolved]** — Notes about issues Astra has already handled (e.g., "Duplicate bill from Acme Corp on 2025-01-15 resolved by archiving INV-002")

Astra treats these tagged blocks as its own durable memory — notes it wrote to itself during prior runs. It uses them to avoid repeating analysis, recognize recurring patterns, and maintain continuity across runs.

You can edit or delete these blocks if they're incorrect, but Astra may regenerate them during future introspection runs if it rediscovers the same patterns.

## Writing Effective Directives

**Be specific and actionable:**

Good: "When you detect duplicate bills from the same vendor with the same invoice number, archive the older one and add a note explaining the deduplication."

Weak: "Handle duplicates appropriately."

**Use conditional logic for trigger-specific rules:**

Good: "When running the cash forecast trigger, always include the next 90 days. When running the vendor spend analysis, only include the current fiscal year."

Weak: "Use 90-day windows." *(Which triggers? All of them?)*

**Name entities explicitly:**

Good: "Send all month-end close findings to Jane Doe (jane@company.com) and CC the CFO at cfo@company.com."

Weak: "Send findings to finance." *(Who specifically? Which channel?)*

**Set thresholds with clear criteria:**

Good: "Auto-approve bills under $1,000 from vendors in the 'Pre-Approved' tag group if they match an open purchase order. Flag everything else for manual review."

Weak: "Approve low-value bills automatically." *(How low? Which vendors?)*

**Test incrementally:**

Start with low-risk directives (like communication preferences) and verify they work as expected before adding high-impact rules (like auto-posting journal entries). Monitor Astra's runs to confirm your directives are being followed correctly.

## Safety Best Practices

Because Company Memory overrides all other instructions, follow these practices to keep your Astra instance safe:

1. **Limit who can edit Company Memory** — Only admins and controllers should have access. Treat Company Memory like production code.
2. **Document your directives** — Add comments explaining why each rule exists so future admins understand the intent.
3. **Avoid fabricating data** — Never tell Astra to create entity IDs, amounts, or dates from scratch. Always ground directives in real data from Light's database.
4. **Audit high-risk actions** — If you instruct Astra to post journal entries or send messages, log those actions and review them regularly.
5. **Test in staging first** — If you have a staging environment, test Company Memory changes there before applying them to production.
6. **Version your memory** — Keep a backup of your Company Memory instructions outside Light so you can roll back if a change causes unexpected behavior.

> Good to know: Company Memory is the most powerful lever you have over Astra's behavior. Use it intentionally. If you're unsure whether a directive is safe, start with "suggest" language instead of "do" language — tell Astra to recommend an action instead of taking it automatically.

## Accessing Company Memory

**To configure Company Memory:**

1. Navigate to **Settings (gear icon) → AI Assistant → Company Memory**
2. Write or edit your instructions in the text editor
3. Click **Save**

Changes take effect on Astra's next run. If you need to verify a change immediately, trigger a manual Astra run from **Settings → Astra → Run Now**.

You can also read and update Company Memory programmatically via the LCI assistant memory tools:

- Say "Show me the current Company Memory" to retrieve all instructions
- Say "Update Company Memory to [your new instructions]" to replace or append directives

## Troubleshooting

### Astra Isn't Following My Directive

- **Check for conflicts:** If you have multiple instructions that contradict each other, Astra may prioritize the first one it reads. Consolidate conflicting rules into a single, clear directive.
- **Verify specificity:** Vague instructions like "handle invoices better" are hard for Astra to follow. Rewrite with explicit actions and conditions.
- **Look at run logs:** Review Astra's reasoning in the run report to see whether it read your directive and how it interpreted it.

### Astra Is Doing Something Unexpected

- **Review recent memory changes:** If Astra's behavior changed suddenly, check whether a recent Company Memory edit introduced a new rule.
- **Check for Astra-generated blocks:** Look for [astra:insight], [astra:pattern], and [astra:resolved] blocks that might be influencing behavior. Edit or delete them if they're incorrect.
- **Test with a narrower directive:** Temporarily remove broad directives and add them back one at a time to isolate which instruction is causing the issue.

### Company Memory Isn't Saving

- Verify you have the **Company Admin** or **Controller** role. Only admins can edit Company Memory.
- Check for syntax errors in your instructions. While Company Memory is freeform text, very long blocks (over 10,000 characters) may fail to save. Break large instruction sets into multiple sections.

## Related Articles

- [How Light Uses AI](12-1-how-light-uses-ai.md)
- [Light Command Interface (LCI)](12-7-ai-conversational-assistant.md)
- [AI Assistant Instructions](12-8-ai-assistant-instructions.md)
