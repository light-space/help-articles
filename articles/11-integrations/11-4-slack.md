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
2. Find **Slack** under **Add new integration** and select it
3. You're redirected to Slack to authorize Light in your workspace
4. Review the permissions and click **Allow**

Light matches Slack users to Light users by email address, so each person's Slack email must match the email on their Light account. Once connected, a **Re-authenticate** option appears under the same Settings → Integrations page if you ever need to reconnect.

## Submitting receipts in Slack

Employees can submit receipts by sending them to the Light app in a **direct message**:

1. Open a DM with the Light app in Slack
2. Attach the receipt image or PDF and send it
3. Light reacts with an hourglass while processing, then a checkmark when it succeeds (or an X if it fails)
4. Light replies with the extracted details ("Here's what I got from the receipt:"), including the description, original amount, and reimbursement amount

You can send receipts either in a direct message with the Light app or in a channel where it's present. Both are processed the same way.

## Asking the Light assistant

You can chat with the Light assistant from Slack:

- **Direct message**: Send the Light app a question in a DM (for example, about your expenses or reimbursement status) and it replies in the conversation
- **Channel mention**: Mention **@Light** in a channel and the assistant replies in a thread

You can also ask the assistant to post a message to a Slack channel on your behalf. It posts as the Light app, using your company's Slack connection, not your personal Slack identity.

## Invoice approvals in Slack

When an invoice needs your approval, Light sends you a direct message with the invoice details and three buttons: **Approve**, **Reject**, and **Add a comment**.

1. You receive a direct message with the invoice information
2. To add context before deciding, select **Add a comment**. This opens a comment box separate from the approve or reject decision
3. Select **Approve** to approve the invoice. Select **Reject** to reject it. If you haven't already added a comment, rejecting opens a dialog asking for a reason. If you already added one, the rejection goes through immediately
4. Light records your decision and moves the invoice to the next step in the approval workflow

Light also sends approval reminders for invoices still awaiting a decision. If you have several invoices to approve at once, a single message can list them all, with an **Approve All** option to clear them together.

## Notifications

Light sends notifications to users as direct messages from the Light app, including:

- Receipt or expense upload completed or failed
- Expense report rejected
- Reimbursement paid
- Invoice approval requests and reminders
- Requests for missing card transaction receipts
- Card declines and payment failures
- Bank connection expiry
- Purchase order requests
- Task assignments and other workflow updates

Notifications go to whichever Slack account matches your Light account by email. You can control which of these notifications you receive in Slack, separately from web push, mobile, and Microsoft Teams. To change this, go to **Settings → Notifications** and adjust the toggles in the Slack column for each notification type.

## Troubleshooting Slack integration

**Messages or receipts not processed**: Make sure your Slack account email matches the email on your Light account — Light matches users by email, so a mismatch means Light won't recognize the message as yours.

**Notifications not appearing**: Check that the Slack integration is still connected under **Settings (gear icon) → Integrations**, and that Light is still authorized in your Slack workspace. Also check your notification toggles under **Settings → Notifications**. A notification type turned off for Slack won't arrive there even if the integration itself is working.

**Integration disconnected**: Reconnect it from **Settings (gear icon) → Integrations**, using the **Re-authenticate** option.

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [Submitting expenses via Slack](../08-expense-management/8-2-expenses-slack.md)
- [Microsoft Teams integration](11-5-microsoft-teams.md)
