# Slack Integration

> **What's this page about: **How to connect Slack to Light, and how to submit receipts, approve invoices, use the Light assistant, and manage notifications from Slack. Includes troubleshooting if something isn't working.

## On this page

- Integration capabilities
- Setting up the Slack integration
- Submitting receipts in Slack
- Asking the Light assistant
- Approving invoices in Slack
- Notifications
- Troubleshooting
- Related articles

Light's Slack integration connects your Slack workspace to the Light app, so your team can submit receipts, approve invoices, ask the Light assistant questions, and receive financial notifications directly in Slack.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

The Slack integration supports:

- **Receipt submission.** Send a receipt to the Light app in Slack (direct message or channel) and Light processes it automatically.
- **Invoice approvals.** Approve or reject invoices directly in Slack using interactive buttons, with the option to add a comment.
- **AI assistant.** Ask the Light assistant a question in a direct message, or mention @Light in a channel.
- **Notifications.** Get direct messages about expense uploads, rejected expense reports, paid reimbursements, invoice approval requests, missing card transaction receipts, and more, with control over which notifications go to Slack.

## Setting up the Slack integration

To connect Slack to Light:

1. Open the Light app and go to Settings (gear icon) to Integrations.
2. Find Slack under Add new integration and select it.
3. Light redirects you to Slack to authorise the connection to your workspace.
4. Review the requested permissions and select Allow.

Light matches each Slack account to a Light account by email address. Make sure the email on your Slack profile matches the email on your Light account, or Light won't recognise you.

Once connected, a Re-authenticate option appears under the same Settings to Integrations page if you ever need to reconnect.

## Submitting receipts in Slack

You can send a receipt straight to the Light app in Slack instead of uploading it in the Light app.

1. Open a direct message with the Light app, or go to a channel where the Light app is present.
2. Attach the receipt image or PDF and send it.
3. Light reacts with an hourglass while it processes the receipt, then a checkmark once it succeeds, or an X if it fails.
4. Light replies with the details it extracted: the description, the original amount, and the reimbursement amount.

You can send receipts either in a direct message with the Light app or in a channel where it's present. Both are processed the same way.

## Asking the Light assistant

You can ask the Light assistant questions from inside Slack, the same way you'd ask it in the Light app.

- Direct message. Send the Light app a question, for example about your expenses or the status of a reimbursement, and it replies in the conversation.
- Channel mention. Mention @Light in a channel and the assistant replies in a thread.

You can also ask the assistant to post a message to a Slack channel on your behalf. It posts as the Light app, using your company's Slack connection, not your personal Slack identity.

## Approving invoices in Slack

When an invoice needs your approval, Light sends you a direct message with the invoice details and three buttons: Approve, Reject, and Add a comment.

1. You receive a direct message with the invoice information.
2. To add context before deciding, select Add a comment. This opens a comment box separate from the approve or reject decision.
3. Select Approve to approve the invoice. Select Reject to reject it. If you haven't already added a comment, rejecting opens a dialogue asking for a reason. If you already added one, the rejection goes through immediately.
4. Light records your decision and moves the invoice to the next step in the approval workflow.

Light also sends approval reminders for invoices still awaiting a decision. If you have several invoices to approve at once, a single message can list them all, with an Approve All option to clear them together.

## Notifications

Light sends notifications to each user as direct messages from the Light app. These include:

- Receipt or expense upload completed or failed
- Expense report rejected
- Reimbursement paid
- Invoice approval requests and reminders
- Requests for missing card transaction receipts
- Card declines and payment failures
- Bank connection expiry
- Purchase order requests
- Task assignments and other workflow updates

Notifications go to whichever Slack account matches your Light account by email. You can control which of these notifications you receive in Slack, separately from web push, mobile, and Microsoft Teams. To change this, go to Settings to Notifications and adjust the toggles in the Slack column for each notification type.

## Troubleshooting

Messages or receipts not processed. Check that your Slack account email matches the email on your Light account. Light matches users by email, so a mismatch means Light won't recognise the message as yours.

Notifications not appearing. Check that the Slack integration is still connected under Settings to Integrations, and that Light is still authorised in your Slack workspace. Also check your notification toggles under Settings to Notifications. A notification type turned off for Slack won't arrive there even if the integration itself is working.

Integration disconnected. Reconnect it from Settings to Integrations, using the Re-authenticate option.

## Related articles

- [Integrations overview](https://help.light.inc/integrations/integrations-overview)
- [Submitting expenses via Slack](https://help.light.inc/employee-expenses-reimbursements/employee-expenses-via-slack)
- [Microsoft Teams integration](https://help.light.inc/integrations/microsoft-teams)

---

*Also searched as: Light Slack bot, connect Slack to Light, Slack expense receipts, approve invoices in Slack, @Light Slack assistant, Slack notification settings, reconnect Slack integration, Slack email matching Light, disconnected Slack integration.*
