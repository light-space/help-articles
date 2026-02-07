# Tracking Payments and Outstanding Balances

Light provides comprehensive payment tracking and AR aging analysis to help you monitor customer payments and identify overdue amounts.

[Open in Light →](https://app.light.inc/invoice-receivables)

## Payment Recording

### Recording Individual Payments

1. Open the invoice
2. Navigate to **Payments**
3. Click **Add Payment**
4. Enter the **Payment Amount**
5. Select the **Payment Date**
6. Enter the **Payment Reference** (check number, bank transfer ID, card last 4 digits)
7. Optionally, note the **Payment Method** (bank transfer, check, credit card, etc.)
8. Click **Save**

The invoice state automatically updates:
- **OPEN** to **PARTIALLY_CLEARED** if payment is less than invoice total
- **OPEN** to **CLEARED** if payment equals invoice total

### Batch Payment Recording

Record multiple payments at once:

1. Navigate to **Payments**
2. Click **Record Batch Payments**
3. Upload a CSV with payment data:
   - Invoice Number or ID
   - Payment Amount
   - Payment Date
   - Payment Reference

4. Review the parsed data
5. Click **Import**

Light validates each payment and shows any errors before importing.

> Good to know: Overpayments are tracked as credits that can be applied to future invoices.

## Payment Application

When a payment can satisfy multiple invoices:

1. Navigate to **Unapplied Payments**
2. Find the payment record
3. Click **Apply Payment**
4. Select which invoice(s) to apply it to
5. Light suggests optimal allocation based on invoice age
6. Click **Apply**

The system updates invoice states accordingly and creates GL entries.

## Tracking Invoice Status

### Invoice States and Meanings

- **DRAFT**: Created but not finalized; no GL entries
- **POSTED**: Finalized and GL entries created; awaiting payment
- **OPEN**: Posted and ready for payment
- **PARTIALLY_CLEARED**: Received partial payment; additional payment due
- **CLEARED**: Fully paid or written off
- **ARCHIVED**: No longer active; retained for historical records

### Viewing Payment History

1. Open an invoice
2. Navigate to **Payment History**
3. View all payments received with:
   - Payment amount
   - Payment date
   - Payment reference
   - Applied-to invoices
   - User who recorded the payment

## Outstanding Balances

### Invoice Balance Dashboard

1. Navigate to **Dashboard** or **AR Summary**
2. View key metrics:
   - **Total Outstanding**: Total amount owed across all customers
   - **Overdue**: Amount past due date
   - **Current**: Amount due within 30 days
   - **Future**: Invoices not yet due

3. Drill down to see detailed invoice listing

### Customer Balance Statement

View what individual customers owe:

1. Open a customer
2. Navigate to **Outstanding Invoices**
3. View all unpaid and partially-paid invoices
4. See customer's **Total Outstanding Balance**
5. Optionally, generate and email a **Statement** to the customer

## AR Aging Analysis

The AR aging report groups outstanding invoices by how overdue they are:

1. Navigate to **Reports** > **AR Aging**
2. Select the **reporting date**
3. View aging buckets:
   - **0-30 Days**: Not yet due or due within 30 days
   - **31-60 Days**: 31-60 days overdue
   - **61-90 Days**: 61-90 days overdue
   - **90+ Days**: More than 90 days overdue

4. See totals and percentages by bucket
5. Click into buckets to see specific invoices
6. Filter by:
   - Customer name or type
   - Currency
   - Company entity
   - Customer status (active/archived)

7. Export the report as Excel or PDF

> Tip: Use AR aging to identify collection priorities. Focus on the 90+ day bucket first.

## Collection Management

Track collection activities on overdue invoices:

1. Open an overdue invoice
2. Navigate to **Collection Notes**
3. Click **Add Note**
4. Record collection activities:
   - Follow-up call made
   - Email sent
   - Payment promised
   - Dispute noted
   - Other actions

5. Click **Save**

These notes are visible to your entire AR team and help coordinate collection efforts.

## Writing Off Invoices

For invoices that cannot be collected:

1. Open the invoice
2. Verify it's in PARTIALLY_CLEARED or CLEARED state
3. Click **Write Off**
4. Enter the **Write-off Amount** (partial or full)
5. Select the **Reason** (bad debt, dispute, etc.)
6. Provide a **Description**
7. Click **Confirm**

Light creates an adjusting journal entry to write off the uncollected balance.

## Customer Credit Management

Credit balances from overpayments or credit notes:

1. Navigate to **Customer Credits**
2. View all customers with credit balances
3. Open a customer's credit
4. Click **Apply Credit to Invoice**
5. Select an open invoice
6. Light automatically applies the credit
7. Click **Apply**

## Related Articles

- [Invoice generation and customization](/articles/06-accounts-receivable/6-5-invoice-generation.md)
- [Sending invoices and payment reminders](/articles/06-accounts-receivable/6-7-sending-invoices.md)
- [Customer credit notes](/articles/06-accounts-receivable/6-9-customer-credits.md)
- [AR aging reports](/articles/06-accounts-receivable/6-12-ar-aging.md)
