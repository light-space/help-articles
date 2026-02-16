# Using Light with Slack and Microsoft Teams

You don't always need to open Light in a browser. If your company connects Light to Slack or Microsoft Teams, you can ask questions about your finances, submit receipts, check on approvals, and look up company policies — all by messaging @Light in the app you already use.

[Open in Light →](https://app.light.inc/dashboard)

## What You Can Do

Light's AI assistant (@Light) lives inside your Slack workspace or Teams environment. Here's what you can do without leaving your messaging app:

**Ask Questions About Your Finances**
Ask things like "Do I have any pending reimbursements?" or "What's the status of my expenses?" and get an instant answer. If your role allows it, you can also ask broader questions like "Show me all pending bills from Acme Corp."

**Submit Receipts and Expenses**
Upload a photo of your receipt to @Light. Light automatically figures out where it belongs — if you're a cardholder, it tries to match the receipt to a recent card transaction. If no match is found (or you only have the reimbursement role), Light asks whether you'd like to create a reimbursement. The AI extracts the merchant, amount, date, and category so you don't have to type anything.

**Attach Receipts to Card Transactions**
When you make a purchase with your Light card, Light sends you a notification asking for the receipt. Upload the receipt directly in that notification thread, and Light attaches it to the transaction automatically.

**Handle Approvals**
If you're a manager or invoice approver, Light sends you approval notifications in Slack or Teams. You can ask questions about the bill right in the notification thread and approve or reject it without logging in to Light.

**Create Purchase Requests and Orders**
Ask @Light to create a purchase request or purchase order through conversation. Describe what you need, and Light walks you through it. For example: "Create a purchase request for new office chairs, $2,500" or "Create a PO for Acme Corp for 100 units at $50 each."

**Request a Vendor Card**
If you have the cardholder role, you can request a new vendor card directly through @Light. Tell Light the vendor name, spending limit, and why you need the card. For example: "Request a vendor card for AWS with a $5,000 monthly limit for cloud infrastructure." Light creates the card request and sends it through the approval workflow.

**Submit Expenses for Reimbursement**
Once you've uploaded your receipts and reviewed the extracted details, tell @Light "Submit my expenses" to send all your draft expenses for reimbursement in one step. Light validates your address and reimbursement configuration, then submits everything. You'll receive a notification when your reimbursement is approved, rejected, or paid.

**Look Up Company Policies**
Ask @Light questions like "What's our travel expense policy?" or "What are the approval thresholds for purchases?" Light finds the answer in your company's uploaded policies and links you to the source.

**Check Your Reimbursement Status**
Ask "What's the status of my reimbursements?" or "Do I have any pending expenses?" to get an instant update without opening the app.

**Get Directed to the Right Page**
If you need to do something that requires the full Light interface, ask @Light and it will give you a direct link to the right page — whether that's your expenses, a specific bill, a card transaction, or your profile.

**Get Notified About Important Updates**
Light proactively sends you notifications — you don't always need to ask. You'll receive messages when your uploaded receipt has been processed (with the extracted details), when a reimbursement is approved and paid, or when a reimbursement is rejected (with the reason from your finance team). If you're a cardholder, Light also reminds you when a card transaction is missing a receipt.

## Getting Started in Slack

### Finding @Light

1. Open Slack
2. Search for **@Light** in the search bar
3. Click to open a direct message with the Light bot
4. Say "Hi" or ask a question — Light responds with an answer

The first time you open the @Light app home in Slack, Light sends a welcome message and confirms your Light account is connected. If you don't have a Light account yet, Light directs you to sign up.

If you don't see @Light in your Slack workspace, your admin needs to enable the integration in **Settings (gear icon) → Integrations → Slack**.

### Sending a Message

Type your question or request as a plain message to @Light. Light shows "thinking ..." while it processes, then updates the message with the answer. You can ask follow-up questions — Light remembers the context of your conversation for up to one hour.

### Submitting a Receipt in Slack

What happens when you upload a file depends on your roles:

**If you have both the cardholder and reimbursement roles**, Light first tries to match the receipt to a recent card transaction. If it finds a match, the receipt is attached automatically. If no match is found, Light asks: "We couldn't match the receipt to a card transaction. Do you want to create a reimbursement from this item?" Click **Reimbursement** to proceed or **Discard** to cancel.

**If you only have the reimbursement role**, Light routes the file directly to the expense handler. It extracts the receipt details (merchant, amount, date) and shows you what it found. You then get a link to review and submit your expenses in the Light web app.

**If you only have the cardholder role**, Light tries to match the receipt to a recent card transaction. If it matches, you're done. If not, Light lets you know it couldn't find a match.

### Attaching Receipts to Card Transactions

When you use your Light card, Light sends you a notification: "We are missing a receipt from your card transaction." Upload the receipt directly in that notification thread. Light matches it to the transaction and confirms with a checkmark.

### Approving Bills in Slack

When a bill needs your approval, Light sends you a notification message with interactive buttons: **Approve**, **Deny**, **Add Note**, and **Start Conversation**. You can:

1. Click **Approve** or **Deny** to take immediate action
2. Click **Add Note** to leave a comment on the bill
3. Click **Start Conversation** or reply directly in the notification thread to ask questions about the bill (e.g., "What are the line items?" or "Who submitted this?") — Light answers using the bill's context
4. Approve or reject through LCI by saying "approve this bill" in the thread

### Creating Purchase Requests

Ask @Light to create a purchase request by describing what you need. For example: "Create a purchase request for new office chairs, $2,500." Light uses the create purchase order tool to start the process.

### Requesting a Vendor Card

If you have the cardholder role, message @Light with the vendor name, spending limit, and business justification. For example: "Request a vendor card for AWS with a $5,000 monthly limit for cloud infrastructure." Light creates the request and routes it through the approval workflow.

### Submitting Expenses

After uploading your receipts and reviewing the extracted details in the Light web app, message @Light "Submit my expenses" to send all draft expenses for reimbursement. Light checks that your profile is complete (address and reimbursement configuration) and submits them. You'll receive a notification when the reimbursement is processed.

## Getting Started in Microsoft Teams

### Finding the Light Bot

1. Open Microsoft Teams
2. Click the **Apps** icon in the sidebar
3. Search for **Light**
4. Click to start a direct message with the Light bot
5. Say "Hi" or ask a question

If the Light app isn't available in your Teams workspace, ask your admin to install it via **Settings (gear icon) → Integrations → Microsoft Teams**.

### Sending a Message

Message the Light bot the same way you would in Slack. Type your question, Light replies with "thinking ..." and then updates with the answer. Follow-up questions work the same way — Light keeps context for up to one hour.

### Submitting a Receipt in Teams

The same role-based routing applies in Teams. Upload a receipt file to the Light bot, and Light routes it based on your roles — matching to card transactions for cardholders, creating reimbursements for reimbursement-eligible users, or asking you to choose if you have both roles.

### Attaching Receipts to Card Transactions in Teams

Card transaction notifications work in Teams just like Slack. When Light asks for a missing receipt, upload it in the conversation and Light attaches it to the transaction.

### Approving Bills in Teams

Bill approval notifications arrive as adaptive cards from the Light bot with **Approve**, **Reject**, and **Add Comment** buttons. Click a button to take action directly, or reply in the thread to ask questions about the bill before deciding.

### Creating Purchase Requests in Teams

Ask the Light bot to create a purchase request the same way you would in Slack — describe what you need, and Light handles it.

### Requesting a Vendor Card in Teams

Request vendor cards through the Light bot just as you would in Slack. Describe the vendor, spending limit, and business justification.

### Submitting Expenses in Teams

Message the Light bot "Submit my expenses" to submit all your draft expenses for reimbursement, the same as in Slack.

## Tips for Better Answers

Light's AI understands natural language, but a few habits get you better results:

- **Be specific about what's yours.** Say "my pending bills" or "bills I need to approve" — Light distinguishes between your personal data and company-wide data. Saying "pending bills" without "my" returns all company bills.
- **Include time periods.** "What did I spend last month?" is clearer than "What did I spend?"
- **Name vendors or categories.** "Show me expenses from Uber" works better than "show me ride expenses."
- **Ask follow-ups.** If Light's first answer isn't quite right, clarify: "No, I meant the EMEA entity" — Light remembers the conversation context.

## What Light Can See (And What It Can't)

Light respects your company's permission settings. The tools available to you depend on your role:

As an employee, you can typically:

- Search for and view your own expenses, reimbursements, and card transactions
- Submit receipts — Light routes them to the right place based on your roles (reimbursement or cardholder)
- Attach receipts to card transactions via notification threads
- Submit all draft expenses for reimbursement (with the reimbursement role)
- Request vendor cards with spending limits (with the cardholder role)
- Create purchase requests and purchase orders (with the purchase requester role)
- Check the status of your reimbursements and expenses
- Receive notifications when receipts are processed, reimbursements are paid or rejected, or card transactions are missing receipts
- Ask about company policies (with links to the source)
- Get directed to specific pages in Light (expenses, cards, profile, purchase requests, etc.)
- View help articles

If you're a manager or approver, you can also:

- View your approval queue (bill approvals, purchase requests)
- Approve or reject bills directly from Slack or Teams using interactive buttons
- Ask questions about a bill in the approval notification thread before deciding
- Ask broader questions about team spending

You typically cannot:

- Access organization-wide financial reports (unless you're an admin or controller)
- Change accounting settings or chart of accounts
- Create journal entries (unless you have an admin or controller role)
- Generate custom SQL reports (unless you're an admin or controller)

If you ask about something you don't have access to, Light lets you know and suggests what to do instead.

## Privacy

Your conversations with @Light are private when sent via direct message. Only you and Light can see them. If you mention @Light in a shared channel, anyone in that channel can see the question and answer.

Light maps your Slack or Teams identity to your Light account through your company's integration setup. The same access controls that apply in the Light web app apply in Slack and Teams.

> Tip: Use direct messages with @Light for anything involving your personal expenses or financial details.

## Troubleshooting

**"I can't find @Light in Slack or Teams"**
The Light integration needs to be enabled by your admin. Ask them to connect Light in **Settings (gear icon) → Integrations**.

**"Light didn't understand my question"**
Try rephrasing with more detail. Instead of "Show me my stuff," try "Show me my pending expense reports." Light works best with specific questions.

**"The receipt details were wrong"**
When Light extracts receipt data, you can review and correct the details before confirming. Your corrections help the AI improve for future receipts.

**"Light said it can't do that"**
Your role may not have access to the tool needed for that request. For example, approving bills requires the Invoice Approver role. Check with your Light administrator about your permissions.

**"I submitted a receipt but nothing happened"**
Make sure you confirmed the routing path when Light asked. If you have both cardholder and reimbursement roles and Light couldn't match a card transaction, it asks you to choose — click **Reimbursement** or **Discard**. Light won't process the file until you respond.

**"Light says I'm missing required roles"**
You need the **reimbursement** or **cardholder** role to upload receipts. Contact your Light administrator to have the appropriate role assigned to your account.

**"Light couldn't match my receipt to a card transaction"**
This happens when the receipt doesn't match any recent card transactions (by amount, date, or merchant). If you have the reimbursement role, you'll be offered the option to create a reimbursement instead. If you only have the cardholder role, try uploading the receipt directly in the card transaction notification thread.

## Related Articles

- [Welcome to Light](e1-1-welcome-to-light.md)
- [Navigating Light as an Employee](e1-2-navigating-light.md)
- [Submitting an Expense for Reimbursement](../e2-expenses-reimbursements/e2-1-submitting-expense.md)
- [Submitting Expenses via Slack](../e2-expenses-reimbursements/e2-2-expenses-via-slack.md)
- [Submitting Expenses via Microsoft Teams](../e2-expenses-reimbursements/e2-3-expenses-via-teams.md)
- [Tracking Your Reimbursement Status](../e2-expenses-reimbursements/e2-6-tracking-reimbursement.md)
