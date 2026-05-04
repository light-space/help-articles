# Astra Agents (Settings → Agents)

Light's AI assistant, Astra, includes specialized agents that help process different types of documents and requests. You can configure custom instructions for each agent to guide how it extracts data, categorizes transactions, and follows your company's specific workflows. Agents also have enforcement capabilities — they can take actions like freezing cards when policies aren't followed.

[Open in Light →](https://app.light.inc/settings/assistant)

## Overview

Astra Agents are specialized AI assistants that work behind the scenes to process specific types of documents and tasks. Each agent focuses on a particular area — parsing bills, processing reimbursements, handling intake requests, reading contracts, or powering the LCI conversational assistant.

When you configure instructions for an agent, those instructions apply to every document or request that agent processes. For example, if you tell the Bill parsing agent to "Always add delivery charges as a separate line item," it will follow that rule for every bill it processes.

**To access Agents:**
1. Navigate to **Settings (gear icon) → Agents**
2. The Agents page displays five cards, one for each agent type

## Agent Types

Light includes five agent types:

### Bill parsing

The Bill parsing agent extracts data from vendor invoices — vendor name, invoice number, line items, amounts, tax, payment terms, and due dates. Configure custom instructions to teach the agent your company's specific rules for how bills should be processed.

**Example instructions:**
- "Always add Livraison charges as a separate line item"
- "Post rounding differences to GL account Rounding Gain/Loss"
- "Extract purchase order numbers from the invoice reference field"
- "Categorize shipping costs under Freight account 5200"

### Contract parsing

The Contract parsing agent reads contracts and extracts key terms — parties, effective dates, renewal terms, payment schedules, termination clauses, and obligations. Use custom instructions to highlight specific contract elements your finance or legal team needs to track.

**Example instructions:**
- "Flag any auto-renewal clauses in the summary"
- "Extract payment milestones and due dates into a structured list"
- "Identify termination notice periods and highlight them"

### Intake

The Intake agent processes general document uploads and requests that don't fit into other categories. Configure instructions to route these documents correctly or extract specific data your workflows require.

**Example instructions:**
- "Route employee onboarding documents to HR for review"
- "Extract policy numbers from insurance documents"
- "Flag any documents mentioning compliance or audit requirements"

### Reimbursement parsing

The Reimbursement parsing agent processes expense receipts uploaded by employees — merchant name, date, amount, and category. Configure instructions to enforce your expense policies or standardize how certain merchants are categorized.

**Example instructions:**
- "Always categorize Uber receipts as Transportation"
- "Flag meal expenses over $50 for additional review"
- "Extract attendee names from restaurant receipts in the memo field"
- "Categorize Starbucks purchases as Meals unless the amount is under $5, then Office Supplies"

### LCI assistant

The LCI assistant agent powers the conversational interface that lets users interact with Light through natural language — searching bills, approving invoices, generating reports, querying policies, and navigating the platform. Configure instructions to customize how LCI responds or interprets certain requests.

**Example instructions:**
- "When users ask about 'travel expenses,' include both Transportation and Meals categories"
- "Always include vendor payment terms in bill summaries"
- "For spending reports, default to the current quarter unless specified otherwise"

## Configuring Agent Instructions

Each agent can have one set of custom instructions. When you save new instructions for an agent that already has instructions, the new instructions replace the previous ones.

**To add or edit instructions for an agent:**
1. Navigate to **Settings (gear icon) → Agents**
2. Click the card for the agent you want to configure (e.g., Bill parsing, Reimbursement parsing)
3. The agent detail page opens with an **Instructions** text area
4. Type your custom instructions in plain language — describe what you want the agent to do, how to categorize items, what rules to follow, or what data to extract
5. Click **Save**
6. A "Saved" confirmation appears

The instructions apply immediately to all new documents or requests that agent processes. Previously processed documents are not affected.

**To view current instructions:**
- The agent list page shows a preview of each agent's instructions on its card
- Click a card to view the full instructions

**To remove instructions:**
- Open the agent detail page, delete the text from the Instructions field, and click **Save**
- The agent will revert to its default behavior

## Agent Card UI

The Agents page displays five cards in a grid layout, one for each agent type. Each card shows:

- **Icon and name** — Visual identifier for the agent type (e.g., Receipt icon for Bill parsing, Wallet icon for Reimbursement parsing)
- **Instruction preview** — The first few lines of the agent's current instructions, or "No instructions yet." if none are configured

Click any card to open the detail page where you can view and edit that agent's full instructions.

## Astra's Enforcement Actions

In addition to processing documents, Astra agents can take enforcement actions to ensure policies are followed. One example is card management — if a cardholder repeatedly fails to upload receipts for card transactions, Astra can freeze the card until the receipts are submitted. This enforcement helps maintain compliance with expense policies and ensures all transactions are properly documented.

Enforcement actions are configured separately from agent instructions and are controlled by your company's policy settings.

> Good to know: Only one set of instructions is allowed per agent per company. When you update instructions, the system automatically replaces the existing instructions for that agent.

## Permissions

**View Agents** — Available to users with the `assistant.view` permission. Typically granted to Company Admins, AP Clerks, AP Preparation, and Vendor Management roles.

**Edit Agents** — Available to users with the `assistant.edit` permission. Typically granted to Company Admins, AP Clerks, AP Preparation, and Vendor Management roles.

If you can't access the Agents page or the Save button is disabled, contact your admin to check your permissions.

## Tips for Writing Effective Instructions

**Be specific** — Instead of "Categorize meals correctly," write "Categorize restaurant receipts as Meals, coffee shops under $5 as Office Supplies, coffee shops over $5 as Meals."

**Use examples** — "For Uber receipts, categorize as Transportation. For Uber Eats, categorize as Meals."

**Reference your chart of accounts** — "Post shipping costs to GL account 5200 Freight."

**State exceptions clearly** — "Flag meal expenses over $50 for review, except client meals which can be any amount."

**Test incrementally** — Start with one or two instructions, process a few documents, and refine based on results before adding more complexity.

## Related Articles

- [Light Command Interface (LCI)](12-7-ai-conversational-assistant.md)
- [How Light Uses AI](12-1-how-light-uses-ai.md)
- [AI-Assisted Reconciliation](12-6-ai-reconciliation.md)
