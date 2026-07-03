# Light Command Interface (LCI)

Light's Command Interface (LCI) is an AI assistant built into the platform that lets you interact with your financial data through natural language. Powered by the Model Context Protocol (MCP), LCI can search bills and vendors, approve invoices, generate financial reports using text-to-SQL, answer policy questions, freeze or unfreeze cards, submit expenses for reimbursement, and navigate the platform — from the web app, mobile app, Slack, or Microsoft Teams.

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
5. After up to ten rounds of tool calls (the final round always produces a text answer), LCI returns a text response along with any structured data (entity lists, reports, navigation links).

LCI maintains conversation threads so follow-up questions work naturally. In Slack direct messages, the most recent thread is reused for one hour, then a new thread is created.

## Available Tools

LCI includes more than 80 tools organized into categories. The tools available to you depend on your role and on the channel you're using (for example, chart tools are only offered where charts can be rendered). The list below highlights commonly used tools — LCI also includes tools for sales invoices, customer credits, contracts, journal entries, card transactions, expenses, documents and templates, workflows, skills, and messaging.

### Search Tools

Search across Light's financial data using natural language filters.

- **Search bills** — Find bills by state (draft, pending approval, approved, ready for payment, scheduled, paid, cancelled), vendor name, due date range, or amount. Returns up to 20 results with vendor, invoice number, amount, state, and dates.
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

- **Get bill details** — Retrieve full bill details including line items. Available to admins, AP preparation, and invoice approvers.
- **Approve task** — Approve or reject a task that's pending your approval, with an optional note (for example, the reason for a rejection). Covers bill approvals, purchase request approvals, credit note approvals, vendor approvals, and card approvals. Only the task's assignee can complete it.
- **Submit bill for approval** — Submit a draft bill into the approval workflow. Requires the **AP Clerk** role.
- **Update bill** — Update a bill or reimbursement: change header fields, update line items, or delete line items. Available to admins, AP clerks, and AP preparation.
- **Search user tasks** — See the tasks assigned to you, covering every approval type in your task queue: bill approvals, vendor approvals, card approvals, card transactions, credit note approvals, and purchase requests. Available to all roles.
- **Get user details** — Retrieve full details of a specific user including name, email, roles, company entity, and notification channel. Available to admins, AP preparation, and invoice approvers.

### Customer Management Tools

Create and update customers directly through LCI. Requires the **Company Admin** or **AR Clerk** role.

- **Create customer** — Create a new customer with name, email, country, and optional details like customer type (business, consumer, government), VAT number, and business registration number. Example: "Create a customer named Acme Corp with email info@acme.com."
- **Update customer** — Update an existing customer's details. Use **search customers** to find the customer ID first, then specify what to update. Example: "Update customer ABC123 to change their email address to newemail@acme.com."

### Report and Query Tools

Generate financial reports and query company policies.

- **Create report** — Describe the report you want in natural language (e.g., "Show me total spending by vendor for Q4 2025"). LCI generates a SQL query, executes it, and returns the results as a table. If the first query has errors, LCI retries up to three times with error feedback.
- **Edit report** — Refine an existing report by describing what to change (e.g., "Add a column for percentage of total" or "Filter to only vendors over $10,000"). Available in channels that can render charts (the web app).
- **Query policy** — Ask questions about your company's policies (e.g., "What's our travel expense policy?" or "What are the approval thresholds?"). LCI searches all uploaded company policies and returns an answer with a link to the source policy section.

### Navigation and Help Tools

- **Navigate to entity** — Get a direct link to a specific entity in Light's UI (bill, vendor, report, etc.). LCI supports more than 40 entity types including bills, invoices, vendors, customers, accounts, transactions, purchase orders, reimbursements, and more.
- **Get help articles** — List available help center articles.
- **Read help article** — Read the full content of a specific help article.

### Expense and Card Tools

- **Submit expenses** — Submit all of a user's current draft expenses for reimbursement in a single command. LCI validates the user's address and reimbursement configuration before submitting. Requires the **Reimbursement** role.
- **Manage cards** — Search your cards, get card details, and freeze or unfreeze a card.
- **Card transactions** — Search card transactions, get transaction details, and attach receipts to card transactions.

### Business Process Tools

- **Create journal entry** — Create a new journal entry with debit and credit lines. Requires the **Company Admin** or **Controller** role.
- **Create purchase request** — Create a purchase request (PR) with a description, amount, and vendor. The request is submitted for review and goes through an approval workflow. Available to users with purchase request permissions, such as the **Purchase Requester** role.

### Assistant Memory Tools

- **Get assistant memories** — Retrieve all AI assistant instructions (memories) configured for the company. Returns a list of instructions organized by type (bill parsing, contract parsing, reimbursement parsing, intake). Available to admins, AP clerks, AP preparation, and vendor management.
- **Update assistant memory** — Create or update an AI assistant instruction for a specific parsing category. Available to admins, AP clerks, AP preparation, and vendor management.

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

Each conversation is stored as a thread with an automatically generated title. You can keep asking follow-up questions in the same thread, or start a new conversation at any time.

### Response Types

LCI responses can include:

- **Text** — A natural language answer to your question
- **Entity lists** — Clickable lists of bills, vendors, customers, or other entities that link to their detail pages
- **Reports** — Tables with columns and rows generated from your data via SQL
- **Charts** — Chart visualizations (e.g., bar, line, pie) of your data
- **Policy answers** — Answers to policy questions with a link to the source policy section
- **Navigation** — Direct links to specific pages in the Light app

### Skills

Skills are user-created shortcuts for prompts you run frequently. When you create a skill, you give it a name (like `cash-flow` or `renew-contract`) and the prompt it runs. After that, you can trigger it by typing `/` followed by the skill name — or by clicking the **Run skill** button in the LCI toolbar.

**To trigger a skill:**
1. Type `/` in the LCI input — the skills dropdown opens and lists your skills
2. Type part of the skill name to filter the list (e.g., `/cash` shows only skills starting with "cash")
3. Select a skill from the list or press Enter to insert it

Alternatively, click the **Run skill** button (next to the attachment button) to open the skills dropdown without typing.

**If you don't have any skills yet:**

When you type `/` for the first time, LCI asks: "You don't have any skills yet. Would you like to create one?" with two options:

- **Yes, show me an example** — LCI fills the input with an example prompt you can send to create your first skill (e.g., "Create a skill that summarizes all my draft sales invoices and convert the sum to EUR")
- **No thanks** — Closes the dropdown

Once you've created skills, typing `/` always opens the skills list. If you type a name that doesn't match any of your skills, LCI shows "No matching skills."

### File Attachments

You can attach files directly to your LCI messages using the paperclip button in the input area. The AI reads the file contents and acts on them as part of your request.

**To attach a file:**
1. Click the paperclip icon in the LCI input area
2. Select a file from your device
3. Type your request and send — for example:
   - "Import these journal entries" *(CSV of journal entries)*
   - "Create these accounts from the list" *(CSV of chart of accounts)*
   - "Book these vendor invoices" *(PDF invoices)*
   - "Match these transactions to the right accounts" *(bank statement or expense export)*
   - "Set up these employees as users" *(HR export)*

**Limits:** Up to 10 files per message, maximum 10 MB per file. Text input accepts up to 10,000 characters per message, so you can paste detailed instructions or large text blocks without truncation.

Attachments are saved in the thread history so you can refer back to them in follow-up messages. The AI can also reference files uploaded earlier in the same conversation — you don't need to re-upload them.

## Using LCI in Slack

### How It Works

Message @Light in Slack — either in a direct message or by mentioning @Light in a channel. LCI processes your message through the same AI orchestrator used in the web app.

When you send a message, Light shows progress updates ("thinking ...", "gathering data ...", "typing ...") and then replaces them with the final answer.

In direct messages, LCI reuses your most recent conversation thread for one hour, then starts a new one. When you mention @Light in a channel, LCI uses that Slack thread's messages as context instead — every participant sees the same conversation.

### Setup

1. Navigate to **Settings (gear icon) → Integrations → Slack**
2. Click **Connect to Slack**
3. Authorize Light in your Slack workspace
4. @Light appears as a bot user in your workspace

### What You Can Do

Most of what the LCI orchestrator supports works in Slack: searching bills, approving invoices, generating reports, querying policies, and more. Channel-dependent capabilities — chart visualizations and in-app navigation responses — are only available in the web and mobile apps. The same role-based permissions apply — you can only access data your role permits.

### Invoice Approval Threads

When a bill needs approval, Light sends a notification in Slack with interactive buttons — **Approve**, **Deny**, **Add Note**, and **Start Conversation**. Users can click a button to take immediate action, or reply directly in the notification thread to ask questions about the bill. LCI detects that you're replying in an invoice approval thread and uses the bill context automatically.

### Proactive Notifications

Light sends proactive notifications through Slack (and Teams) for key events. These are delivered to the user's direct message channel:

- **Receipt processed** — After a user uploads a receipt, Light notifies them when the AI has extracted the receipt details (merchant, amount, date, category) and provides a link to review the expense in the web app.
- **Receipt processing failed** — If the AI cannot extract details from the receipt, Light notifies the user and provides a link to fill in the details manually.
- **Reimbursement rejected** — When a reimbursement is rejected, Light notifies the employee with the rejection reason from the finance team and a link to view the rejected expenses.
- **Reimbursement paid** — When a reimbursement payment is processed, Light notifies the employee with the payment amount.
- **Missing card receipt** — When a cardholder makes a purchase, Light sends a notification asking them to upload the receipt for that transaction.

Notifications are delivered to the user's configured notification channel (Slack, Teams, or web app) and simultaneously to the mobile app as push notifications.

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

The same LCI capabilities available in Slack work in Teams: search, bill management, reports, policy queries, receipt uploads, vendor card requests, expense submission, and navigation. Role-based permissions apply identically. Invoice approval notifications in Teams use adaptive cards with **Approve**, **Reject**, **Add Comment**, and **Submit Comment** actions.

### Receipt Uploads in Teams

Upload a receipt file in a Teams chat with the Light bot. Light processes the file through the same receipt routing pipeline as Slack — the same role-based smart routing applies (auto-matching to card transactions for cardholders, reimbursement routing for reimbursement-eligible users, and disambiguation when both roles are present). Teams uses a file consent card flow — Light requests permission to access the uploaded file before processing it.

### Proactive Notifications in Teams

The same proactive notifications available in Slack are delivered in Teams: receipt processing results, reimbursement status updates, and missing card receipt reminders. If the Light bot's conversation with a user is blocked or unavailable, Teams automatically reinstalls the bot to restore the notification channel.

### Onboarding

When a user first opens the @Light app home in Slack, Light checks whether they have a Light account. If they do, Light sends a welcome message and marks them as onboarded. If they don't have a Light account, Light directs them to sign up. This onboarding state is tracked per user so the welcome message only appears once.

## Using LCI on Mobile

LCI is accessible from the Light mobile app. The mobile interface provides the same command capabilities, including in-app navigation, but without chart visualizations (charts are available in the web app). Mobile users also receive push notifications for expense processing results and reimbursement status updates.

## Roles and Permissions

LCI filters available tools based on your role. Here's what each role can do:

**Company Admin / Controller** — Full access to all tools. Can search across all data, approve or reject bills, generate reports, query policies, create journal entries and purchase requests, manage cards, create and update customers, manage assistant instructions, and view user details.

**Invoice Approver** — Can approve and reject bills, view approval queue, get bill and user details, search bills, and use general query and navigation tools.

**AP Clerk** — Can submit bills for approval, update bills, manage assistant instructions, create and update customers, and use general tools.

**AP Preparation** — Can update bills, get bill and user details, create purchase requests, manage assistant instructions, and use general tools.

**Cardholder** — Can view and manage their cards (including freezing and unfreezing), attach receipts to card transactions, view the approval queue, search across financial data, and use navigation and help tools. Receives missing receipt notifications for card transactions.

**Reimbursement** — Can submit draft expenses for reimbursement, search across financial data, and use navigation and help tools. Receives notifications for receipt processing and reimbursement status updates.

**Purchase Requester** — Can create purchase requests, search purchase orders and requests, and use general tools.

**Vendor Management** — Can manage assistant instructions and use general search and navigation tools.

**All authenticated users** — Can search accounts, company entities, vendors, purchase orders, purchase requests, tax codes, and users. Can view the approval queue, navigate to entities, and access help articles.

If you try to use a tool your role doesn't allow, LCI tells you it can't complete the request and suggests an alternative (like contacting an admin or navigating to the relevant page).

## Assistant Instructions

Admins can configure custom AI instructions (called "assistant memories") that guide how LCI parses specific document types. Only one instruction is allowed per instruction type per company — when you update an instruction for a type that already exists, the system automatically replaces it.

Instructions apply to four categories:

- **Contract parsing** — Custom rules for how AI should extract data from contracts
- **Bill parsing** — Custom rules for invoice data extraction
- **Reimbursement parsing** — Custom rules for receipt and reimbursement processing
- **Intake** — Custom rules for general document intake

Configure these in **Settings (gear icon) → AI Assistant → Instructions**, or manage them directly through LCI using the assistant memory tools. For example, you can say "Show me the current bill parsing instructions" or "Update the reimbursement parsing instructions to always categorize Uber receipts as transportation."

When you upsert an instruction via the API or LCI, the system automatically replaces the existing instruction for that type if one exists, or creates a new one if none exists. You don't need to provide an instruction ID.

## Privacy and Security

- LCI respects Light's role-based access controls at the tool level — each tool declares which roles can use it
- All LCI requests are authenticated — the `LciPolicy` requires a valid session
- Conversation threads are stored per user and per company with full audit trail
- Slack and Teams messages are processed through Light's secure integration layer
- Customer data is never used for AI model training or fine-tuning
- In Slack and Teams, user identity is resolved via OAuth tokens — LCI maps Slack/Teams users to their Light accounts

## Limitations

Some tasks are better handled in Light's full web interface:

- Multi-step workflows that require interactive forms (creating complex bills with many line items)
- Bulk operations (batch approvals are not yet supported via LCI)
- Configuration changes to accounting settings, chart of accounts, or approval workflows
- Tasks that exceed ten tool-call rounds in a single request

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
