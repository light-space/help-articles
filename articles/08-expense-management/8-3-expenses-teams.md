# Submitting Expenses via Teams

Microsoft Teams users can submit expenses directly from Teams without leaving their chat application. Send receipts to the Light bot in a chat, and Light handles receipt processing and keeps you updated with status messages.

[Open in Light →](https://app.light.inc/expenses)

## Setting Up Teams Integration

### Installation

1. Navigate to **Settings (gear icon)** → **Integrations**
2. Click **Connect** on the Microsoft Teams integration
3. A Microsoft **admin consent** flow opens — a Microsoft 365 administrator must approve Light for your organization
4. Once consent is granted, your Microsoft tenant is linked to your Light company and the Light bot is ready to use

### How users are matched

There is no per-channel configuration. Light matches each Teams user to their Light account by **email address** — the email on your Microsoft 365 account must match the email on your Light user. The bot then works with you through **chat messages**.

To submit expenses via Teams you need:

- An active Light user with the same email as your Microsoft 365 account
- The reimbursement role and an active reimbursement setup in Light

If either is missing, the bot replies telling you what to fix (for example, "You are not set up for reimbursements" or "You are missing the required roles to use this feature") and to contact your admin if needed.

## Submitting an Expense via Teams

### Chat with the Light Bot

1. Open Teams and start a chat with the **Light** bot
2. Attach your receipt (image or PDF) to the message and send it — you can attach several files at once, or paste an image directly into the chat
3. Light replies "Processing your file(s)..." and updates the message as it works
4. Light's AI extracts the details and sends you a card with what it found

Supported file types include PDF and common image formats (JPEG, PNG, HEIC, TIFF). Files above the maximum file size are rejected with a message telling you the limit.

> Note: If you are also a cardholder, Light first tries to match the receipt to a card transaction. If no transaction matches, the bot asks "We couldn't match the receipt to a card transaction. Do you want to create a reimbursement from this item?" with **Reimbursement** and **Discard** buttons — click **Reimbursement** to create an expense.

## Reviewing Extracted Data in Teams

After processing, Light sends a card:

**"Your receipt was successfully uploaded."**

The card displays:
- **Description**: What the expense appears to be
- **Original amount**: The amount and currency on the receipt
- **Reimbursement amount**: The amount converted to your reimbursement currency
- A **View expenses** button that opens Light

The expense is created as a draft. To correct any details (description, amount, date, category), open the [Expenses](https://app.light.inc/expenses) page in the Light web app and edit the draft there.

If extraction fails, Light tells you "There was an issue extracting the details from the receipt" — the receipt is still uploaded, and the card includes an **Open Light** button so you can fill out the missing details in the web app.

### Submitting your expense report

Draft expenses are grouped into an expense report (reimbursement). Once you are done uploading all of your receipts, you can either:

- Tell the Light bot in the chat to submit your expense report, or
- Submit it from the [Expenses](https://app.light.inc/expenses) page in the web app

Submitting sends the report for review through your company's approval workflow.

## Tracking Reimbursement Status

Light sends these status updates as Teams messages:

1. **Upload confirmation**: "Your receipt was successfully uploaded" with the extracted details
2. **Rejection notification**: "Your expense report was rejected", including the reason from the finance team and a link to reset your expenses
3. **Payment notification**: "Your reimbursement has been paid" with the amount sent to your account

### Checking Your Expense Status

Ask the Light bot directly — there are no special commands. In the chat, ask in natural language, for example:

- "What's the status of my reimbursement?"
- "Which of my expenses are still in draft?"

The bot shows "thinking ..." while it works, then answers using your data in Light.

## Batch Submitting Multiple Receipts

Submit multiple expenses at once:

1. In your chat with the Light bot, attach several receipt files to a single message
2. Send the message — Light processes each file and creates a draft expense per receipt
3. When you're done uploading, submit them together as one expense report

## Receipt Attachment Best Practices

For best AI extraction:

1. **Quality**: Take clear photo with good lighting (natural light preferred)
2. **Angle**: Photo should be straight-on, not at angle
3. **Framing**: Full receipt in frame, not cropped
4. **Format**: JPEG, PNG, HEIC, TIFF, or PDF

## Troubleshooting Common Issues

### Extraction Didn't Work

If Light couldn't read the receipt, it sends: "There was an issue extracting the details from the receipt." The receipt is still uploaded — go to the [Expenses](https://app.light.inc/expenses) page in the web app to fill out the missing details manually.

### File Was Rejected

If a file fails validation, Light replies explaining the problem:

- The file exceeds the maximum file size
- The file has an unsupported file type

Fix the file (or take a new photo) and resend the message with valid files. If the upload itself fails, Light asks you to try submitting again or contact an admin for assistance.

### Bot Doesn't Recognize You

If the bot replies that you are not set up, your Microsoft 365 email may not match a Light account, or you may be missing the reimbursement role or reimbursement setup. Ask your admin to check your Light user.

### Wrong Details Extracted

Open the draft expense on the [Expenses](https://app.light.inc/expenses) page and correct the details before submitting your expense report.

## Mobile Teams App

Submitting via Teams mobile works the same way as on desktop:

1. Open your chat with the **Light** bot in the Teams mobile app
2. Attach a receipt photo (or take one with your camera) and send it
3. Light processes it and replies with the extracted details

## Related Articles

- [Submitting expenses via Slack](/articles/08-expense-management/8-2-expenses-slack.md)
- [Submitting expenses via email](/articles/08-expense-management/8-4-expenses-email.md)
- [Mobile receipt capture](/articles/08-expense-management/8-5-receipt-capture.md)
- [Expense management overview](/articles/08-expense-management/8-1-expense-overview.md)
