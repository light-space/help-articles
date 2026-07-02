# Submitting Expenses via Email

Email submission offers a simple method for employees who prefer email or need to forward receipts from email confirmations. Forward receipts to your company's receipt email address and Light automatically matches them to your card transactions.

[Open in Light →](https://app.light.inc/expenses)

## How Email Submission Works

1. Your organization has a single, company-specific **receipt email address** (e.g., receipts@...). This address is configured at the organization level and is separate from your company's bill (invoice) email address.
2. You send or forward an email with the receipt attached to that address.
3. Light identifies your company from the receipt address the email was sent to, and identifies you by matching your **sender email address** to your Light user account.
4. Light's AI reads each attachment and matches it to one of your card transactions. When a match is found, the receipt is attached to that transaction automatically.

> Good to know: Receipts submitted via email are matched to **card transactions**. To submit an out-of-pocket expense for reimbursement, use the Light web app, mobile app, Slack, or Microsoft Teams instead.

## Setting Up Email Submission

- Each organization has one receipt email address; there are no separate per-department addresses.
- Send from the email address associated with your Light user account. If the sender address is not recognized for your company, the email is rejected. Admins can ask Light to approve additional sender addresses or domains (useful for forwarding rules).
- If you don't know your company's receipt email address, ask your admin.

### Setting Up Automatic Email Forwarding

Instead of manually forwarding receipts, you can set up automatic forwarding rules in your email client to send receipts directly to Light. This is useful for recurring expenses (e.g., SaaS subscriptions, utility bills) that arrive via email.

**Step 1: Create a forwarding rule in your email client**

In Gmail, Outlook, or your email provider, create a forwarding rule or filter to automatically forward emails from specific senders (e.g., receipts from vendors) to your company's Light receipt email address.

**Step 2: Complete email verification**

When you set up automatic forwarding, your email provider sends a verification request to Light's email address. The Light support team will accept this forwarding request on your behalf. This may take up to one business day.

If your forwarding rule isn't working after 24 hours, contact Light support at **help@light.inc** to confirm the verification was completed.

**Step 3: Test the rule**

Once approved, send a test email to confirm receipts are being forwarded automatically.

> Good to know: Automatic forwarding works best for predictable receipts from known vendors. For one-off expenses, manually forwarding or using the mobile app may be faster.

## Submitting via Email

### Sending a Receipt Email

1. Forward or send an email to your company's receipt email address
2. Include the **receipt as an attachment**:
   - PDF file
   - Image file (JPEG, PNG, HEIC, HEIF, TIFF)
3. Send the email

Light processes each attachment and attempts to match it to a card transaction.

> Good to know: Light reads the receipt attachment itself — the email subject line and body text are not used for processing. Make sure the receipt is attached as a file; a forwarded email without an attached receipt cannot be matched.

### Multiple Attachments

You can attach multiple receipts to a single email. Each attachment is processed and matched separately.

## What Happens After You Send

1. Light identifies your company and your user account from the email addresses
2. Light's AI compares the receipt against your unmatched card transactions
3. If a match is found, the receipt is converted to PDF and attached to the card transaction — you can see it on the transaction in Light
4. If no match is found, the receipt is not stored

Light does not send a reply or confirmation email. To verify the receipt was attached, open the card transaction in Light.

## Email Submission Best Practices

### File Formats
- **PDF**: Email confirmations and invoices in PDF work well
- **Images**: JPEG, PNG, HEIC, HEIF, and TIFF are supported
- **Multiple receipts**: One receipt per attachment

### Timing
- Submit receipts after the card transaction appears in Light, so there is a transaction to match against
- Submit before month-end close for timely bookkeeping

## Troubleshooting Email Issues

### Receipt Not Attached to a Transaction

1. **Check the sender address**: Send from the email address on your Light user account
2. **Check the recipient address**: Confirm you used your company's receipt email address
3. **Check the transaction exists**: The card transaction must already be visible in Light for a match to be made
4. **Check the attachment**: The receipt must be attached as a file (PDF or supported image format) and be legible
5. **Resubmit another way**: You can also attach the receipt directly to the transaction in the Light app, or via Slack or Teams
6. **Contact support**: If the issue persists, contact **help@light.inc**

## Related Articles

- [Submitting expenses via Slack](/articles/08-expense-management/8-2-expenses-slack.md)
- [Submitting expenses via Teams](/articles/08-expense-management/8-3-expenses-teams.md)
- [Mobile receipt capture](/articles/08-expense-management/8-5-receipt-capture.md)
- [AI receipt categorization](/articles/08-expense-management/8-6-ai-receipt-categorization.md)
