# Sending Invoices and Payment Reminders

Light streamlines invoice delivery and automates payment reminders. The system handles multi-channel distribution — including email and e-invoicing — with full audit trails and customer engagement tracking.

[Open in Light →](https://app.light.inc/invoice-receivables)

## Opening Invoices

Before an invoice can be sent or tracked, it must be opened. Opening finalizes the invoice, transitions it from DRAFT to OPEN status, and locks it for editing. Opening can optionally include sending the invoice via email or e-invoice in a single step.

### Opening a Single Invoice

1. Open a DRAFT invoice
2. Review the invoice details
3. Click **Open**
4. Optionally, choose to send by email and/or submit as an e-invoice:
   - Toggle **Send Email** to email the invoice on open
   - Toggle **Submit E-Invoice** to submit via the e-invoicing channel
5. If sending by email, verify the **email subject**, **reply-to address**, **recipients**, and optionally add **CC recipients** and a **custom message**
6. Confirm the action

The invoice status changes from DRAFT to OPEN. If email or e-invoice delivery was selected, Light handles sending automatically as a background process.

### Batch Opening

Open multiple invoices at once using the batch open feature. This processes invoices as a background job, allowing you to continue working while Light handles the operation.

1. Navigate to **Sales invoices**
2. Filter the table to show DRAFT invoices
3. Select the invoices you want to open — use **Select All** or individually check the invoices
4. Click **Open**
5. Optionally, choose to send by email and/or submit as an e-invoice for all selected invoices
6. If sending by email, configure the shared email settings (subject, reply-to, CC recipients, custom message)
7. Confirm the action

Light creates a batch operation and processes each invoice in the background. During batch processing:

- Invoices are processed in parallel, in groups of up to 20 at a time for optimal performance.
- Each invoice is opened independently — if one invoice fails (e.g., missing required fields like a customer), the rest continue processing normally.
- When sending by email, **recipient email addresses are resolved automatically** from each invoice's customer record. You do not need to specify individual recipients per invoice.
- When submitting e-invoices, the customer's e-invoice address is used. If unavailable, Light falls back to the customer's standard email.

> Important: If you choose to send emails during a batch open, email settings (subject, reply-to, etc.) must be provided. The batch will not proceed without them. However, recipient addresses are pulled automatically from each customer's contact details.

### Monitoring Batch Operations

Track the progress of any batch open operation:

1. After initiating a batch open, Light returns a batch operation with a unique ID
2. Navigate to **Batch Operations** to view all batch operations
3. Each operation shows an overall status:
   - **In Progress** — some invoices are still being processed
   - **Completed** — all invoices were successfully opened (and sent, if requested)
   - **Failed** — one or more invoices encountered an error
4. Expand a batch operation to see per-invoice details, including individual statuses and failure reasons for any that did not succeed
5. Click **Acknowledge** to dismiss a completed or failed batch notification

> Good to know: Batch operations support partial success. If some invoices fail due to validation errors (e.g., missing customer, missing template, or incomplete line items), the successfully processed invoices are still opened and sent. You can review and fix the failed invoices, then re-process them individually or in a new batch.

## Sending an Invoice

### Sending on Open

The simplest way to send an invoice is to include email delivery when opening:

1. Open a DRAFT invoice
2. Click **Open**
3. Toggle **Send Email** on
4. Verify the **recipient email addresses** (pulled from the customer's contact information)
5. Review the email **subject** and **reply-to address**
6. Optionally, add **CC recipients** and a **custom message**
7. Confirm

Light opens the invoice and sends it in a single step.

### Sending a Previously Opened Invoice

To send (or re-send) an invoice that is already in OPEN status:

1. Open the invoice
2. Click **Send Email**
3. Configure the email details:
   - **Subject**: the email subject line
   - **Reply-To**: the address recipients will reply to
   - **Recipients**: one or more email addresses
   - **CC**: optional CC recipients
   - **Custom Message**: optional personalized message
4. Click **Send**

> Note: Sending an email is only available for invoices in OPEN status. If the invoice is still in DRAFT, you must open it first.

### E-Invoice Submission

Light supports submitting invoices via e-invoicing channels:

1. When opening an invoice, toggle **Submit E-Invoice**
2. Light uses the customer's e-invoice address for delivery
3. If no e-invoice address is configured, Light falls back to the customer's standard email address

E-invoicing can be used alongside or instead of email delivery. Both options are available during single and batch open operations.

## Email Customization

### Using Email Templates

1. Navigate to **Invoice Templates**
2. Configure default email settings on a template:
   - **Default Email Subject**
   - **Default Email Message**
   - **Reply-To Email**
   - **CC Emails**
3. When sending invoices that use this template, these defaults are pre-populated

### Customizing Email Content

When sending an invoice, you can override the template defaults:

1. When sending, modify the **Subject Line**
2. Edit the **Custom Message** field
3. Add or change **CC recipients**
4. Click **Send**

Custom email content overrides the template defaults for that send only.

## Payment Reminders and Dunning

Set up automated payment reminders for overdue invoices:

1. Navigate to **AR Settings** > **Dunning Workflows**
2. Click **Create Workflow**
3. Define the dunning schedule:
   - **First Reminder**: 5 days after due date
   - **Second Reminder**: 15 days after due date
   - **Third Reminder**: 30 days after due date

4. Configure each reminder:
   - Select the **email template**
   - Set the **recipient** (primary contact, finance contact, etc.)
   - Customize the **subject and message** (optional)

5. Optionally, escalate after final reminder (increase interest, suspend services, etc.)
6. Click **Create**

### Assigning Dunning Workflows to Invoices

1. Open an invoice
2. Navigate to **Dunning**
3. Select the **Workflow** to apply
4. Light automatically schedules reminders based on the invoice due date
5. Click **Save**

### Monitoring Dunning Activity

1. Navigate to **Reports** > **Dunning Activity**
2. View all reminders sent with:
   - Recipient email
   - Send date
   - Open/click tracking (if enabled)
   - Customer response

## Tracking Email Engagement

Light tracks customer interactions with invoices:

1. Open an invoice
2. Navigate to **Email History**
3. View:
   - **Send Date and Time**
   - **Recipient Email**
   - **Email Status** (Sent, Bounced, Opened, Clicked)
   - **Open Count** (how many times opened)
   - **Click Count** (payment link clicks)

4. Click on a send event to view details

> Tip: Use engagement data to identify customers likely to need payment reminders or payment follow-ups.

## Customer Portal Payments

Enable customers to view and pay invoices online:

1. Navigate to **Customer Portal Settings**
2. Enable **Allow Customers to Pay Online**
3. Optionally, require **authentication** (login required)
4. Set **accepted payment methods** (credit card, bank transfer, etc.)
5. Configure payment **processing fees** (pass through or absorb)

6. When sending invoices, include portal login link in email

Customers can log in to view:
- All invoices (open, paid, and historical)
- Payment options
- Download invoices as PDF
- Set up recurring payments

## Scheduling Invoices

Send invoices at optimal times:

1. When sending an invoice, click **Schedule for Later**
2. Choose the **send date and time**
3. Optionally, choose **timezone** (customer's or your own)
4. Click **Schedule**

The invoice will be automatically sent at the specified time.

## Invoice Delivery Status

Monitor invoice delivery:

1. Navigate to **Invoices**
2. Check the **Status** column for each invoice
3. Look for delivery status indicators:
   - Green: Successfully sent and opened
   - Yellow: Sent, not yet opened
   - Red: Failed to send (e.g., invalid email)

4. Click an invoice to see detailed delivery information

## Related Articles

- [Setting up customers and contacts](/articles/06-accounts-receivable/6-2-customers-contacts.md)
- [Invoice generation and customization](/articles/06-accounts-receivable/6-5-invoice-generation.md)
- [Tracking payments and outstanding balances](/articles/06-accounts-receivable/6-8-tracking-payments.md)
