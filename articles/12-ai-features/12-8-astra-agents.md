# Astra Agents (Settings → Agents)

Astra Agents are specialized AI assistants you can configure to handle specific tasks in Light — parsing bills, processing reimbursements, managing intake requests, extracting contract data, and powering the LCI conversational assistant. Each agent can follow custom instructions you provide, so the AI processes your documents and responds to commands according to your company's workflows and policies.

[Open in Light →](https://app.light.inc/settings/assistant)

## Overview

The **Agents** settings page (formerly called "Memory") lets you configure five specialized agents. Each agent has a dedicated instructions field where you can provide guidance the AI will follow when performing that agent's tasks.

Access **Settings (gear icon) → Agents** to view all configured agents. The page displays a card for each agent type. Click a card to open the detail page and add or edit instructions.

## The Five Agent Types

Light includes five agent types, each responsible for a different area of work:

**Bill parsing** — Guides how the AI extracts and structures data from vendor invoices and bills. Use this to specify how certain vendors should be handled, how to treat specific line items, or where to route charges.

**Contract parsing** — Guides how the AI extracts data from contracts and agreement documents.

**Intake** — Guides how the AI processes general document intake requests submitted by users.

**Reimbursement parsing** — Guides how the AI extracts details from receipts and expense submissions. Use this to define how specific merchants or categories should be classified.

**LCI assistant** — Guides how the LCI conversational assistant responds to your requests in the web app, Slack, Teams, or mobile. Use this to set tone, preferred formatting, or company-specific context LCI should keep in mind.

## Configuring Agent Instructions

Each agent can have one set of custom instructions. Instructions apply company-wide — all users in your organization will have documents processed and commands handled according to the instructions you set.

**To configure an agent:**

1. Navigate to **Settings (gear icon) → Agents**
2. Click the card for the agent you want to configure
3. Type your instructions in the **Instructions** field
4. Click **Save**

The instructions field is a multi-line text area. You can provide as much guidance as needed. If an agent has no instructions, Light processes documents and requests using default behavior.

**To update instructions:**

1. Open the agent detail page
2. Edit the text in the **Instructions** field
3. Click **Save**

When you save, the new instructions replace any previous instructions for that agent. There's no version history — only the most recent instructions are active.

**To remove all instructions:**

1. Open the agent detail page
2. Clear all text from the **Instructions** field
3. Click **Save**

The agent will revert to default behavior.

## Permissions

- **View agents** — Users with the **assistant.view** permission can access the Agents page and view configured instructions.
- **Edit agents** — Users with the **assistant.edit** permission (typically admins, AP clerks, AP preparation, and vendor management) can create and update agent instructions.

If you don't have edit permission, the instructions field will be read-only and the **Save** button will be disabled.

## Agent Enforcement Capabilities

Agents have access to certain enforcement tools to maintain compliance and data quality. For example, agents can **freeze or unfreeze cards** when needed — such as when a cardholder repeatedly fails to upload required receipts or when a card transaction violates policy.

These enforcement actions are logged and visible to admins. Card freeze/unfreeze actions appear in the card's activity history.

## Good to Know

- **One instruction set per agent** — Each agent type can have only one set of instructions per company. When you save new instructions, they replace the previous instructions immediately.
- **Instructions apply company-wide** — All users' documents and requests will follow the same agent instructions. You cannot configure different instructions for different teams or entities.
- **Agents vs. LCI tools** — Agents are specialized AI assistants for specific tasks (parsing, intake, conversational responses). LCI tools are the individual actions the LCI assistant can perform (searching bills, approving invoices, generating reports). LCI tools respect the LCI assistant agent's instructions when responding to user requests.
- **No examples provided** — Instructions are freeform text. Light doesn't enforce a specific format. Write instructions in plain language describing how the agent should behave for your use case.

## Troubleshooting

### Instructions Aren't Being Followed

- Verify the instructions were saved. Open the agent detail page and confirm your text appears in the **Instructions** field.
- Instructions take effect immediately after saving. Documents processed or requests handled after you save will follow the new instructions.
- Very complex or contradictory instructions may confuse the AI. Try simplifying to clear, specific directives.

### Can't Edit Instructions

- Check your role. The **assistant.edit** permission is required to modify agent instructions. Ask your admin to grant this permission if needed.
- If the **Save** button is disabled, you don't have edit permissions.

### Instructions Disappeared

- Instructions are saved per agent type. If you're looking at a different agent card, you won't see the instructions from another agent.
- Only the most recent instructions are stored. If someone else on your team edited the same agent, their save replaced your previous instructions.

## Related Articles

- [Light Command Interface (LCI)](12-7-ai-conversational-assistant.md)
- [How Light Uses AI](12-1-how-light-uses-ai.md)
- [AI-Assisted Bill Parsing](../06-accounts-payable/6-3-ai-bill-parsing.md) *(if exists)*
- [Expense Submission](../08-expense-management/8-1-expense-submission.md) *(if exists)*
