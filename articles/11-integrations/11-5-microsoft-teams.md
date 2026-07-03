# Microsoft Teams Integration

Microsoft Teams is the enterprise messaging and collaboration platform used by many organizations. Light's Teams integration lets employees submit receipts, approve invoices, and chat with the Light assistant directly in Teams, and delivers real-time notifications about financial events as personal messages from the Light bot.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

The Teams integration enables:

- **Receipt submission**: Send a receipt to the Light bot in a Teams chat and it's processed automatically
- **Invoice approvals**: Approve or reject invoices directly in Teams with interactive adaptive cards
- **AI assistant**: Ask the Light assistant questions in a chat with the bot
- **Notifications**: Personal messages about expense uploads, rejected expense reports, paid reimbursements, invoice approval requests and reminders, and more

## Setting up Teams integration

To connect Teams:

1. Navigate to **Settings (gear icon) → Integrations**
2. Find the **Microsoft Teams** integration and click to connect
3. You're redirected to Microsoft to grant admin consent — this step must be completed by a Microsoft 365 administrator for your organization
4. Review the permissions and accept

Granting consent links your Microsoft tenant to your Light organization. Light matches Teams users to Light users by email address, so each person's Microsoft account email must match the email on their Light account.

## Submitting receipts in Teams

Employees can submit receipts by sending them to the Light bot in a chat:

1. Open a chat with the Light bot in Teams
2. Attach the receipt file (or paste an image) and send it
3. Light replies with "Processing your file(s)..." while it works
4. If the receipt matches a card transaction, it's attached to that transaction automatically
5. If no card transaction matches and you're set up for reimbursements, Light asks "Do you want to create a reimbursement from this item?" with **Reimbursement** and **Discard** buttons
6. Once processed, Light sends a card with the extracted details — description, original amount, and reimbursement amount — and a **View expenses** button that opens your expenses in Light

## Asking the Light assistant

You can chat with the Light assistant from Teams: send the Light bot a question in a chat (for example, about your expenses or reimbursement status). The bot replies with "thinking ..." and then updates the message with its answer.

## Invoice approvals in Teams

When an invoice requires your approval, Light sends you a Teams message with the invoice details and interactive buttons:

1. The approver receives an adaptive card with the invoice information
2. Click **Approve** to approve the invoice, or **Reject** to reject it
3. You can also click **Add a comment** to attach a note to the approval before deciding
4. Light can share the invoice document with you in Teams — accept the file consent prompt to receive the PDF
5. Light records the decision and the approval workflow proceeds

Light also sends approval reminders, and supports bulk invoice approvals and payment batch approvals in Teams.

## Notifications

Light sends notifications to users as personal messages from the Light bot, including:

- Receipt or expense upload completed or failed
- Expense report rejected
- Reimbursement paid
- Invoice approval requests and reminders
- Card transaction and task updates, and other workflow events

Notifications are delivered to each user individually based on their matched email address — there is no per-channel notification configuration. Users can turn notification categories on or off per channel in their notification preferences in Light.

## Troubleshooting Teams integration

**Messages or receipts not processed**: Make sure your Microsoft account email matches the email on your Light account — Light matches users by email. Also make sure you're sending receipts in a chat with the Light bot.

**Notifications not appearing**: Verify the Teams integration is connected under **Settings (gear icon) → Integrations** and that the notification category is enabled in your notification preferences.

**Integration disconnected**: Re-connect the Teams integration from **Settings (gear icon) → Integrations** — a Microsoft 365 administrator must grant consent again.

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [Slack integration](11-4-slack.md)
- [Submitting expenses via Teams](../08-expense-management/8-3-expenses-teams.md)
