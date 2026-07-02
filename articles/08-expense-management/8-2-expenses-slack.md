# Submitting Expenses via Slack

Submitting expenses through Slack offers the fastest, most convenient method for employees. Send receipts to the Light bot without leaving Slack, review the extracted data, and get reimbursement status updates as direct messages.

[Open in Light →](https://app.light.inc/expenses)

## Setting Up Slack Integration

### Installation

1. Navigate to **Settings (gear icon)** → **Integrations**
2. Click **Connect** on the Slack integration
3. Follow the OAuth flow to authorize Light in your Slack workspace
4. The Light bot is installed and ready to use

### How users are matched

There is no per-channel configuration. Light matches each Slack user to their Light account by **email address** — the email on your Slack profile must match the email on your Light user. The bot then works with you through **direct messages**.

To submit expenses via Slack you need:

- An active Light user with the same email as your Slack account
- The reimbursement role and an active reimbursement setup in Light

If either is missing, the bot replies telling you what to fix (for example, "You are not set up for reimbursements") and to contact your admin if needed.

## Submitting an Expense via Slack

### Direct Message to Light Bot

1. Open Slack and start a direct message with the **Light** bot
2. Attach your receipt (image or PDF) to the message and send it — you can attach several files at once
3. Light reacts with an hourglass while processing, then a checkmark when the receipt is uploaded (or an X if something went wrong)
4. Light's AI extracts the details and sends you a message with what it found

Supported file types include PDF and common image formats (JPEG, PNG, HEIC, TIFF). Files above the maximum file size are rejected with a message telling you the limit.

> Note: If you are also a cardholder, Light first tries to match the receipt to a card transaction. If no transaction matches, the bot asks "Do you want to create a reimbursement from this item?" with **Reimbursement** and **Discard** buttons — click **Reimbursement** to create an expense.

## Reviewing Extracted Data

After processing, Light sends you a message:

**"Here's what I got from the receipt:"**

The message shows:
- **Description**: What the expense appears to be
- **Original amount**: The amount and currency on the receipt
- **Reimbursement amount**: The amount converted to your reimbursement currency

The expense is created as a draft. To correct any details (description, amount, date, category), open the [Expenses](https://app.light.inc/expenses) page in the Light web app and edit the draft there.

If extraction fails, Light tells you "There was an issue extracting the details from the receipt" and asks you to go to the web app to fill out the missing details — best done on a computer.

### Submitting your expense report

Draft expenses are grouped into an expense report (reimbursement). Once you are done uploading all of your receipts, you can either:

- Tell the Light bot in the DM to submit your expense report, or
- Submit it from the [Expenses](https://app.light.inc/expenses) page in the web app

Submitting sends the report for review through your company's approval workflow.

## Tracking Reimbursement Status

Light sends these status updates as Slack DMs:

1. **Upload confirmation**: "Your receipt was successfully uploaded" with the extracted details
2. **Rejection notification**: "Your expense report was rejected", including the reason from the finance team and a link to reset your expenses
3. **Payment notification**: "Your reimbursement has been paid" with the amount sent to your account

### Checking Status in Slack

Ask the Light bot directly — there are no special commands. In a DM, ask in natural language, for example:

- "What's the status of my reimbursement?"
- "Which of my expenses are still in draft?"

The bot answers using your data in Light. You can also mention **@Light** in a channel it has been added to and it replies in a thread.

## Batch Submitting Multiple Receipts

Submit multiple expenses at once:

1. In your DM with the Light bot, attach several receipt files to a single message
2. Send the message — Light processes each file and creates a draft expense per receipt
3. When you're done uploading, submit them together as one expense report

## Receipt Photo Tips

For best AI extraction results:

1. **Good Lighting**: Take photo in bright area (natural light best)
2. **Full Receipt**: Include entire receipt in frame, not just part
3. **Flat Surface**: Place receipt flat before photographing (not at angle)
4. **Focus**: Focus camera on receipt before snapping
5. **Recent**: Use receipts within a few weeks (ink doesn't fade)

## Common Issues and Troubleshooting

### Extraction Didn't Work

If Light couldn't read the receipt, it sends: "There was an issue extracting the details from the receipt." The receipt is still uploaded — go to the [Expenses](https://app.light.inc/expenses) page in the web app to fill out the missing details manually.

### File Was Rejected

If a file fails validation, Light replies explaining the problem:

- The file exceeds the maximum file size
- The file has an unsupported file type

Fix the file (or take a new photo) and resend the message with valid files.

### Bot Doesn't Recognize You

If the bot replies that it could not find an active user with your Slack credentials, your Slack email doesn't match a Light account. Ask your admin to check your Light user's email address.

### Wrong Details Extracted

Open the draft expense on the [Expenses](https://app.light.inc/expenses) page and correct the details before submitting your expense report.

## Talking to the Light Bot

The Light bot doesn't use slash commands — it understands natural language:

- **Direct messages**: Ask questions about your expenses, policies, or company data
- **Channel mentions**: Mention **@Light** in a channel where the bot is present and it replies in a thread

## Privacy and Security

Your expense submissions in Slack:

- **Encrypted**: Receipts are encrypted in transit and at rest
- **Private**: The bot works with you in direct messages; expenses are visible to you and your reviewers

## Related Articles

- [Submitting expenses via Teams](/articles/08-expense-management/8-3-expenses-teams.md)
- [Submitting expenses via email](/articles/08-expense-management/8-4-expenses-email.md)
- [Mobile receipt capture](/articles/08-expense-management/8-5-receipt-capture.md)
- [Expense management overview](/articles/08-expense-management/8-1-expense-overview.md)
