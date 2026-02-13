# Submitting Expenses via Email

Email submission offers a simple method for employees who prefer email or need to forward receipts from email confirmations. Forward receipts to a company email address and Light automatically processes them.

[Open in Light →](https://app.light.inc/expenses)

## Setting Up Email Submission

### Email Address Configuration

1. Navigate to **Settings** > **Integrations** > **Email**
2. Configure **Expense Email Address**:
   - Light provides a company-specific address (e.g., expenses@light.company.com)
   - Optionally, set up **alias addresses** for departments (travel@, meals@, etc.)

3. Configure **Auto-Processing**:
   - **Auto-Extract**: Light automatically extracts receipt data
   - **Manual Review**: Light waits for employee to confirm details

4. Save settings

### User Setup

Employees receive instructions:

1. Light sends welcome email with submission instructions
2. Email contains the **expense submission address**
3. Employees save address in contacts
4. Ready to start submitting

### Setting Up Automatic Email Forwarding

Instead of manually forwarding receipts, you can set up automatic forwarding rules in your email client to send receipts directly to Light. This is useful for recurring expenses (e.g., SaaS subscriptions, utility bills) that arrive via email.

**Step 1: Create a forwarding rule in your email client**

In Gmail, Outlook, or your email provider, create a forwarding rule or filter to automatically forward emails from specific senders (e.g., receipts from vendors) to your company's Light expense email address.

**Step 2: Complete email verification**

When you set up automatic forwarding, your email provider sends a verification request to Light's email address. The Light support team will accept this forwarding request on your behalf. This may take up to one business day.

If your forwarding rule isn't working after 24 hours, contact Light support at **support@light.inc** to confirm the verification was completed.

**Step 3: Test the rule**

Once approved, send a test email to confirm receipts are being forwarded automatically.

> Good to know: Automatic forwarding works best for predictable receipts from known vendors. For one-off expenses, manually forwarding or using the mobile app may be faster.

## Submitting via Email

### Sending a Receipt Email

1. Forward or send email to **expenses@light.company.com**
2. Include **receipt attachment**:
   - Image file (JPG, PNG)
   - PDF file
   - Email confirmation (forwarded from merchant)

3. In email body, optionally include:
   - Brief description (Light extracts main details from receipt)
   - Category if obvious (e.g., "Travel - flight receipt")
   - Project or cost center code

4. Send email

Light immediately processes the receipt and sends confirmation.

### Subject Line Tips

Help Light categorize by using keywords in subject:

- "Travel - United Airlines flight receipt"
- "Meals - Client dinner with Acme Corp"
- "Office Supplies - Staples receipts"
- "Conference - SaaS Summit registration"

If subject includes category, Light pre-selects it (employee can change).

## Processing Confirmation

After Light receives your email:

1. Light extracts receipt data automatically
2. Light sends you **confirmation email** with:
   - Extracted details (merchant, amount, date, category)
   - **Review Link**: Click to confirm or edit details
   - Instructions for next steps

3. Click the link in email (or reply to confirm)

### Confirming Extraction

You have options:

**Option 1: Click Link in Email**
1. Click **Review Expense** link in confirmation email
2. Web page opens showing:
   - Original receipt image
   - Extracted details
   - Buttons: "Looks Good" or "Edit"

3. Click **Looks Good** to submit
4. Or click **Edit** to correct details

**Option 2: Reply to Confirmation Email**
1. Receive confirmation email from Light
2. Reply to email with:
   - "Approved" or "OK" - to confirm
   - Corrections needed (e.g., "Amount is $85, not $80")
   - Category change (e.g., "Change to Meals")

3. Send reply
4. Light processes your response

**Option 3: Ignore and Re-submit**
1. If confirmation doesn't work, re-send original email
2. Light detects duplicate and consolidates
3. You can confirm in a different way

> Good to know: If you don't respond to confirmation email, Light holds the expense for 7 days before archiving. You can resubmit if needed.

## Adding Notes to Email Submissions

Provide context with your receipt:

1. In email body (not subject), include description:
   - **Expense Description**: What the purchase was for
   - **Who attended**: For meals shared with others
   - **Project/Purpose**: What business purpose
   - **Policy notes**: Why it might require special approval

2. Example:
   ```
   Expense for: Conference registration
   Event: SaaS Summit SF
   Dates: June 5-7, 2024
   Category: Professional Development
   Notes: Annual conference for team leads.
   Pre-approval was obtained from Director.
   ```

3. Notes appear in expense when submitted for approval

## Batch Email Submissions

Submit multiple receipts in one email:

1. In email body, list each receipt separately:
   - Attachment 1: Receipt image for expense 1
   - Attachment 2: Receipt image for expense 2
   - Etc.

2. In email body, describe each:
   ```
   Expense 1: Hotel - $180
   Expense 2: Flight - $450
   Expense 3: Meals - $65
   ```

3. Send email with all attachments
4. Light processes all and sends confirmation for each

## Managing Multiple Receipts

Some purchases have multiple receipt files:

- **Hotel**: Confirmation email + detailed invoice
- **Flight**: Booking email + receipt
- **Rental Car**: Confirmation + final receipt

You can:

**Option 1: Send multiple emails**
- Send one email per day with different receipts
- Light deduplicates if same receipt

**Option 2: Attach all to one email**
- List in body which receipt is which
- Light processes all

**Option 3: Send main receipt only**
- Light uses primary receipt (hotel bill)
- Attach supplementary emails as reference

## Handling Forwarded Merchant Emails

When merchant sends receipt via email:

1. **Forward email to expenses@light.company.com**
2. Original email is forwarded with all content
3. Light extracts amount and date from email body
4. Light may ask for category (not always visible in email)

5. Respond to confirmation with category if needed

Some merchants include receipts as PDFs in email; some just have text. Both work.

## Receipts with Issues

### Receipt Couldn't Be Processed

Light message: "I couldn't read this receipt. Please try again."

Options:
1. **Check file quality**: Receipt might be too blurry or dark
2. **Resend**: Send email again with better receipt image
3. **Reply with details**: Reply to Light with:
   - "Merchant: Delta Airlines"
   - "Amount: $450.25"
   - "Date: 3/15/2024"

4. Light records the manual entry

### Partially Illegible Receipt

Light might ask for clarification:

1. Light sends email: "I'm unsure about the amount. Can you confirm?"
2. Reply with confirmation:
   - "Amount is $175.50"
   - "Category is Travel"

3. Light uses your confirmation
4. Learns from the clarification

### Missing Receipt

If receipt image didn't attach:

1. Light sends message: "I didn't receive an attachment. Please resend."
2. Send email again with attachment
3. Or reply with details typed in email body
4. Light can create expense from manual entry

## Email Submission Best Practices

### File Formats
- **Images**: JPG, PNG work best (2-5MB typical)
- **PDFs**: Email confirmations in PDF work well
- **Multiple**: One receipt per attachment (clearly labeled if multiple)

### Email Subject
- **Clear category**: "Travel - United flight"
- **Clear date**: Include date if possible: "3/15 - Hotel San Francisco"
- **Description**: "Client dinner - Acme Corp"

Good subjects help Light categorize automatically.

### Timing
- **Same day**: Submit receipts same day as purchase if possible (image freshest)
- **Weekly**: Collect week's receipts and batch submit (efficient)
- **Before close**: Submit before month-end for timely approval

## Checking Email Submission Status

After submitting via email:

1. Look for status emails from Light:
   - Received and processing
   - Ready for your confirmation
   - Submitted for manager approval
   - Approved and reimbursement pending

2. Click links in status emails to see full details

## Troubleshooting Email Issues

### Not Receiving Confirmation Email

1. Check **spam folder**: Confirmation might be marked as spam
2. Confirm email in settings: Make sure email address is correct
3. Resend receipt: Send email again with receipt
4. Contact support: If issue persists

### Can't Click Review Link

1. Copy and paste link into browser
2. Or reply to email with approval
3. Or check Light app for the expense

### Double Submission

If you accidentally send same receipt twice:

1. Light detects duplicate
2. Sends message: "This looks like a duplicate. Combining into one expense."
3. Only one expense created
4. No action needed

## Related Articles

- [Submitting expenses via Slack](/articles/08-expense-management/8-2-expenses-slack.md)
- [Submitting expenses via Teams](/articles/08-expense-management/8-3-expenses-teams.md)
- [Mobile receipt capture](/articles/08-expense-management/8-5-receipt-capture.md)
- [AI receipt categorization](/articles/08-expense-management/8-6-ai-receipt-categorization.md)
