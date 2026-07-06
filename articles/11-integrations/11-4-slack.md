# Slack Integration

Slack is the leading team communication and collaboration platform. Light's Slack integration lets employees submit receipts, approve invoices, and chat with the Light assistant directly in Slack, and delivers real-time notifications about financial events as direct messages.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

The Slack integration enables:

- **Receipt submission**: Send a receipt to the Light app in a direct message and it's processed automatically
- **Invoice approvals**: Approve or reject invoices directly in Slack with interactive buttons
- **AI assistant**: Ask the Light assistant questions in a DM, or mention **@Light** in a channel
- **Notifications**: Direct messages about expense uploads, rejected expense reports, paid reimbursements, invoice approval requests, missing card transaction receipts, and more

## Setting up Slack integration

To connect Slack:

1. Navigate to **Settings (gear icon) → Integrations**
2. Find the **Slack** integration and click to connect
3. You're redirected to Slack to authorize Light in your workspace
4. Review the permissions and click **Allow**

Light matches Slack users to Light users by email address, so each person's Slack email must match the email on their Light account.

## Submitting receipts in Slack

Employees can submit receipts by sending them to the Light app in a **direct message**:

1. Open a DM with the Light app in Slack
2. Attach the receipt image or PDF and send it
3. Light reacts with an hourglass while processing, then a checkmark when it succeeds (or an X if it fails)
4. Light replies with the extracted details ("Here's what I got from the receipt:"), including the description, original amount, and reimbursement amount

Receipts are only processed in direct messages with the Light app — files shared in regular channels are not picked up.

## Asking the Light assistant

You can chat with the Light assistant from Slack:

- **Direct message**: Send the Light app a question in a DM (for example, about your expenses or reimbursement status) and it replies in the conversation
- **Channel mention**: Mention **@Light** in a channel and the assistant replies in a thread

The assistant can also post messages to Slack channels on your behalf when you ask it to in chat.

## Invoice approvals in Slack

When an invoice requires your approval, Light sends you a Slack message with the invoice details and interactive buttons:

1. The approver receives a direct message with the invoice information
2. Click **Approve** to approve the invoice, or **Reject** to reject it (rejecting opens a dialog to provide a reason)
3. You can also add a note to the approval before deciding
4. Light records the decision and the approval workflow proceeds

Light also sends approval reminders, and supports approving multiple invoices at once from a single message.

## Notifications

Light sends notifications to users as direct messages from the Light app, including:

- Receipt or expense upload completed or failed
- Expense report rejected
- Reimbursement paid
- Invoice approval requests and reminders
- Requests for missing card transaction receipts
- Task assignments and other workflow updates

Notifications are delivered to each user individually based on their matched email address — there is no per-channel notification configuration.

## Troubleshooting Slack integration

**Messages or receipts not processed**: Make sure your Slack account email matches the email on your Light account — Light matches users by email. Also make sure you're sending receipts in a direct message with the Light app, not in a channel.

**Notifications not appearing**: Verify the Slack integration is connected under **Settings (gear icon) → Integrations** and that Light is still authorized in your Slack workspace.

**Integration disconnected**: Re-authorize the Slack integration from **Settings (gear icon) → Integrations**.

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [Submitting expenses via Slack](../08-expense-management/8-2-expenses-slack.md)
- [Microsoft Teams integration](11-5-microsoft-teams.md)
