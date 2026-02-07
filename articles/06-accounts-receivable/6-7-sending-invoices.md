# Sending Invoices and Payment Reminders

Light streamlines invoice delivery and automates payment reminders. The system handles multi-channel distribution with full audit trails and customer engagement tracking.

[Open in Light →](https://app.light.inc/invoice-receivables)

## Sending an Invoice

### Manual Sending

1. Open the invoice in DRAFT or POSTED state
2. Click **Send**
3. Verify the **recipient email addresses** (pulled from customer email preferences)
4. Review the email **subject** and **message body**
5. Optionally, add **CC recipients**
6. Click **Send Now** or **Schedule for Later**

Once sent, the invoice moves to OPEN state (if currently POSTED).

### Batch Sending

Send multiple invoices at once:

1. Navigate to **Invoices**
2. Filter to the invoices you want to send (e.g., by due date, customer)
3. Click **Select All** or individually check boxes
4. Click **Bulk Actions** > **Send Invoices**
5. Confirm the send settings
6. Click **Send**

> Good to know: Light sends invoices as PDF attachments in email. You can customize the email subject and body before sending.

## Email Customization

### Using Email Templates

1. Open the invoice
2. Click **Send**
3. Find **Email Template** dropdown
4. Select a predefined template (or create a new one)
5. Review the populated subject and message
6. Click **Send**

### Customizing Email Content

1. When sending, click **Customize**
2. Edit the **Subject Line**
3. Modify the **Message Body** (markdown supported)
4. Add **Call-to-Action** text and button label (e.g., "Pay Now")
5. Include a link to your **payment portal** if available
6. Click **Send**

Custom email content overrides the template for this send only.

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
