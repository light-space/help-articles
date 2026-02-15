# Light Command Interface (LCI)

Light's Command Interface (LCI) is an AI assistant built into the platform that lets you interact with your financial data through natural language. Powered by the Model Context Protocol (MCP), LCI can search bills and vendors, approve invoices, generate financial reports using text-to-SQL, answer policy questions, and navigate the platform — from the web app, mobile app, Slack, or Microsoft Teams.

[Open in Light →](https://app.light.inc/dashboard)

## Overview

LCI is the AI layer behind @Light. When you type a message — whether in the Light web app, the mobile app, or in Slack or Teams — LCI processes your request through an orchestrator that selects and runs the right tools against your financial data. It respects your role and permissions, maintains conversation context, and returns structured answers with links back into the platform.

LCI is available to all authenticated users. The tools available to each user depend on their role.

## How LCI Works

When you send a command to LCI, the system runs an iterative loop:

1. Your message is sent to the AI model along with your user profile (name, roles, company entity, currency) and the list of tools available to your role.
2. The AI model decides which tools to call and with what parameters.
3. LCI executes the tools against Light's data and collects the results.
4. The model reviews the results and may call additional tools if needed.
5. After up to five rounds of tool calls, LCI returns a text response along with any structured data (entity lists, reports, navigation links).

LCI maintains conversation threads so follow-up questions work naturally. Threads are reused for one hour, then a new thread is created.

## Available Tools

LCI includes 31 tools organized into categories. The tools available to you depend on your role.

### Search Tools

Search across Light's financial data using natural language filters.

- **Search bills** — Find bills by state (draft, pending approval, approved, rejected, posted, cleared, archived), vendor name, due date range, or amount. Returns up to 20 results with vendor, invoice number, amount, state, and dates.
- **Search vendors** — Look up vendors by name or other criteria.
- **Search customers** — Find customers in the system.
- **Search GL accounts** — Search the chart of accounts.
- **Search company entities** — Look up entities (divisions) within the organization.
- **Search purchase orders** — Find purchase orders by criteria.
- **Search purchase requests** — Find purchase requests.
- **Search tax codes** — Look up tax codes.
- **Search users** — Find users in the system.

### Bill Management Tools

Review and act on bills directly through LCI. These tools require specific roles.

- **Get bill details** — Retrieve full bill details including line items. Available to AP clerks, controllers, and admins.
- **Approve bill** — Approve a bill that's pending your approval. Requires the **Invoice Approver** role.
- **Reject bill** — Reject a bill with a note explaining why. Requires the **Invoice Approver** role.
- **Submit bill for approval** — Submit a draft bill into the approval workflow. Requires the **AP Clerk** role.
- **Update bill line** — Update a single line item on a bill, including custom properties. Requires the **AP Clerk** role.
- **Get approval queue** — See your pending approval tasks filtered by status (pending, approved, queued, rejected).

### Report and Query Tools

Generate financial reports and query company policies.

- **Create report** — Describe the report you want in natural language (e.g., "Show me total spending by vendor for Q4 2025"). LCI generates a SQL query, executes it, and returns the results as a table. If the first query has errors, LCI retries up to three times with error feedback.
- **Edit report** — Refine an existing report by describing what to change (e.g., "Add a column for percentage of total" or "Filter to only vendors over $10,000").
- **Query policy** — Ask questions about your company's policies (e.g., "What's our travel expense policy?" or "What are the approval thresholds?"). LCI searches all uploaded company policies and returns an answer with a link to the source policy section.
- **Get database schema** — Retrieve schema information for context when building reports.

### Navigation and Help Tools

- **Navigate to entity** — Get a direct link to a specific entity in Light's UI (bill, vendor, report, etc.). LCI supports 32 entity types including bills, invoices, vendors, customers, accounts, transactions, purchase orders, reimbursements, and more.
- **Get help articles** — List available help center articles.
- **Read help article** — Read the full content of a specific help article.

### Business Process Tools

- **Create journal entry** — Create a new journal entry in the system.
- **Create purchase order** — Create a new purchase order.

> Good to know: LCI distinguishes between personal and company scope. When you say "my bills" or "what do I need to approve," it returns data scoped to you personally. When you say "all pending bills" or "company spending," it returns company-wide data.

## Using LCI in the Web App

### Accessing LCI

LCI is accessible from the Light web app. Type your command in the LCI input field and press Enter. LCI supports streaming responses — you see the answer as it's generated.

### Conversation Threads

LCI maintains a conversation thread so you can ask follow-up questions. For example:

> **You:** Show me all pending bills from Acme Corp
>
> **LCI:** I found 3 pending bills from Acme Corp: [list of bills with amounts and dates]
>
> **You:** Approve the first one
>
> **LCI:** I've approved bill INV-2025-0142 from Acme Corp for $4,200.

Threads are reused for one hour. After that, a new thread starts automatically.

### Response Types

LCI responses can include:

- **Text** — A natural language answer to your question
- **Entity lists** — Clickable lists of bills, vendors, customers, or other entities that link to their detail pages
- **Reports** — Tables with columns and rows generated from your data via SQL
- **Policy answers** — Answers to policy questions with a link to the source policy section
- **Navigation** — Direct links to specific pages in the Light app

## Using LCI in Slack

### How It Works

Message @Light in Slack — either in a direct message or by mentioning @Light in a channel. LCI processes your message through the same AI orchestrator used in the web app.

When you send a message, Light shows progress updates ("thinking ...", "gathering data ...", "typing ...") and then replaces them with the final answer.

### Setup

1. Navigate to **Settings (gear icon) → Integrations → Slack**
2. Click **Connect to Slack**
3. Authorize Light in your Slack workspace
4. @Light appears as a bot user in your workspace

### What You Can Do

Everything the LCI orchestrator supports works in Slack: searching bills, approving invoices, generating reports, querying policies, and more. The same role-based permissions apply — you can only access data your role permits.

### Invoice Approval Threads

When a bill needs approval, Light sends a notification in Slack. You can reply directly in that notification thread to ask questions about the bill or take action. LCI detects that you're replying in an invoice approval thread and uses the bill context automatically.

### Receipt Uploads and Smart Routing

Upload a receipt image (JPG, PNG, or PDF) to @Light in Slack. Light's receipt router determines where the file should go based on the user's roles:

- **Cardholder + Reimbursement roles**: Light first tries to auto-match the receipt to a recent card transaction. If a match is found, the receipt is attached to the transaction automatically. If no match is found, Light asks the user: "We couldn't match the receipt to a card transaction. Do you want to create a reimbursement from this item?" — with **Reimbursement** and **Discard** buttons.
- **Reimbursement role only**: Light routes the file directly to the expense handler, extracts the receipt details, and provides a link to review and submit in the web app.
- **Cardholder role only**: Light tries to match to a card transaction. If successful, the receipt is attached. If not, Light notifies the user.
- **Neither role**: Light tells the user they're missing required roles and suggests contacting their admin.

### Card Transaction Receipt Threads

When a cardholder makes a purchase, Light sends a notification in Slack: "We are missing a receipt from your card transaction." The user uploads the receipt directly in that notification thread, and Light attaches it to the transaction. This guided upload flow works even when the user has multiple roles.

### Policy Source Links

When you ask a policy question in Slack, LCI includes a link to the specific policy section in its response. Click the link to view the full policy in Light.

> Tip: Use direct messages with @Light for questions involving sensitive financial data. Channel conversations are visible to everyone in the channel.

## Using LCI in Microsoft Teams

### How It Works

LCI works in Teams the same way as Slack. Message the Light bot, and it processes your request through the MCP orchestrator. Teams responses use Bot Framework activities with text formatting.

### Setup

1. Navigate to **Settings (gear icon) → Integrations → Microsoft Teams**
2. Complete the admin consent flow to authorize Light in your Teams tenant
3. The Light bot appears in Teams

### What You Can Do

The same LCI capabilities available in Slack work in Teams: search, bill management, reports, policy queries, receipt uploads, and navigation. Role-based permissions apply identically.

### Receipt Uploads in Teams

Upload a receipt file in a Teams chat with the Light bot. Light processes the file through the same receipt routing pipeline as Slack — the same role-based smart routing applies (auto-matching to card transactions for cardholders, reimbursement routing for reimbursement-eligible users, and disambiguation when both roles are present).

## Using LCI on Mobile

LCI is accessible from the Light mobile app via `POST /mobileapp/v1/lci/command`. The mobile interface provides the same command capabilities but with a simplified response format optimized for smaller screens (text blocks only, no complex tables).

## Roles and Permissions

LCI filters available tools based on your role. Here's what each role can do:

**Company Admin / Controller** — Full access to all 31 tools. Can search across all data, approve or reject bills, generate reports, query policies, create journal entries and purchase orders.

**Invoice Approver** — Can approve and reject bills, view approval queue, search bills, and use general query and navigation tools.

**AP Clerk / AP Preparation** — Can submit bills for approval, update bill lines, search bills and vendors, and use general tools.

**Employee roles** (approver, reimbursement, cardholder, requester) — Can use search tools scoped to their data, navigation, help articles, and policy queries.

If you try to use a tool your role doesn't allow, LCI tells you it can't complete the request and suggests an alternative (like contacting an admin or navigating to the relevant page).

## Assistant Instructions

Admins can configure custom AI instructions that guide how LCI parses specific document types. These instructions are set per company and apply to four categories:

- **Contract parsing** — Custom rules for how AI should extract data from contracts
- **Bill parsing** — Custom rules for invoice data extraction
- **Reimbursement parsing** — Custom rules for receipt and reimbursement processing
- **Intake** — Custom rules for general document intake

Configure these in **Settings (gear icon) → AI Assistant → Instructions**.

## Privacy and Security

- LCI respects Light's role-based access controls at the tool level — each tool declares which roles can use it
- All LCI requests are authenticated — the `LciPolicy` requires a valid session
- Conversation threads are stored per user and per company with full audit trail
- Slack and Teams messages are processed through Light's secure integration layer
- Financial data is never used to train public AI models
- In Slack and Teams, user identity is resolved via OAuth tokens — LCI maps Slack/Teams users to their Light accounts

## Limitations

Some tasks are better handled in Light's full web interface:

- Multi-step workflows that require interactive forms (creating complex bills with many line items)
- Bulk operations (batch approvals are not yet supported via LCI)
- Configuration changes to accounting settings, chart of accounts, or approval workflows
- File uploads other than receipts (contracts, multi-page documents)
- Tasks that exceed five tool-call rounds in a single request

For these, LCI can navigate you to the right page in Light with a direct link.

## Troubleshooting

### LCI Doesn't Respond

- Verify you're authenticated in the Light web app, or that the Slack/Teams integration is connected (**Settings (gear icon) → Integrations**)
- In Slack, ensure you're messaging @Light directly or mentioning @Light in a channel
- In Teams, ensure the Light bot is installed in your tenant

### Wrong Data Returned

- LCI distinguishes between personal and company scope. If you asked "my bills" but got all company bills, rephrase: "bills assigned to me" or "bills I need to approve."
- For reports, provide specific time periods, entity names, and categories. Instead of "show me spending," try "show me spending by department for Q4 2025."

### "I Can't Do That" Response

- Your role may not have access to the requested tool. Check with your admin about your assigned roles.
- Some actions (like approving a bill) require specific roles (Invoice Approver). LCI will tell you which role is needed.

### Report Errors

- If a report query fails, LCI retries up to three times with error correction. If it still fails, try rephrasing with simpler criteria or a narrower date range.
- Very complex reports with multiple joins may exceed the SQL generation capability. Use **Planning & Reports → Reports** in the web app for these.

## Related Articles

- [How Light Uses AI](12-1-how-light-uses-ai.md)
- [Natural Language Q&A in Slack](12-5-ai-slack-qa.md)
- [AI-Assisted Reconciliation](12-6-ai-reconciliation.md)
- [Slack Integration](../11-integrations/11-4-slack.md)
- [Microsoft Teams Integration](../11-integrations/11-5-microsoft-teams.md)
- [Submitting Expenses via Slack](../08-expense-management/8-2-expenses-slack.md)
- [Submitting Expenses via Microsoft Teams](../08-expense-management/8-3-expenses-teams.md)
