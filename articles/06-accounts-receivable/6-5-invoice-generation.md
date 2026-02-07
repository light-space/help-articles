# Invoice Generation and Customization

Light's invoice generation tools allow you to create, customize, and manage customer invoices efficiently. Invoices are the core accounting documents in the AR module.

[Open in Light →](https://app.light.inc/invoice-receivables)

## Creating an Invoice

Invoices can be created from contracts or manually:

**From a Contract:**
1. Navigate to **Revenue & Invoicing → Contracts**
2. Select the contract
3. Click **Generate Invoice**
4. Review line items and amounts
5. Click **Create**

**Manual Invoice Creation:**
1. Navigate to **Revenue & Invoicing → Sales invoices**
2. Click **Create Invoice**
3. Select the **Customer**
4. Choose the **Company Entity**
5. Set the **Posting Date** and **Document Date**

## Invoice Components

Each invoice contains:

- **Header Information**: Invoice number, dates, customer details
- **Line Items**: Products/services with quantities, unit prices, discounts, and taxes
- **Totals**: Subtotal, tax, discounts, and total amount
- **Payment Terms**: When payment is due
- **Payment Instructions**: Bank account or payment portal details
- **Additional Notes**: Custom text or terms

## Configuring Line Items

When adding line items to an invoice:

1. Click **Add Line Item**
2. Select a **Product** (or leave blank for non-catalog items)
3. Enter **Description** (auto-populated from product if selected)
4. Set **Quantity** and **Unit Price**
5. Choose the **Line Discount** (optional):
   - Amount: Fixed discount
   - Percentage: Percentage reduction
6. Select **Tax Category**
7. Light automatically calculates **Tax Amount** and **Line Total**

> Tip: You can override product defaults on each line item without affecting the product master data.

## Applying Discounts

Light supports multiple discount methods:

**Line-Level Discounts:**
- Apply to individual line items
- Can be fixed amount or percentage
- Reduce the taxable amount (tax applied to discounted price)

**Invoice-Level Discounts:**
- Applied after summing all line items
- Useful for bulk purchase discounts
- Optional tax treatment configuration

**Volume Discounts:**
- Can be set up in contracts for automatic application
- Applied at invoice generation time

## Invoice Customization

### Custom Fields

Add internal notes or custom information to invoices:

1. Open the invoice in edit mode
2. Navigate to **Custom Fields**
3. Click **Add Field**
4. Enter the field value
5. Click **Save**

Custom fields appear on invoice reports and can be used for filtering.

### Payment Instructions

Configure how customers should pay:

1. Open the invoice
2. Navigate to **Payment Instructions**
3. Select payment method (Bank Transfer, Credit Card, ACH, etc.)
4. Enter method-specific details
5. Click **Save**

These instructions appear on the invoice PDF sent to the customer.

## Invoice States and Workflow

Invoices progress through these states:

- **DRAFT**: Created but not yet finalized
- **POSTED**: Confirmed and sent (creates GL entries)
- **OPEN**: Posted and awaiting payment
- **PARTIALLY_CLEARED**: Partial payment received
- **CLEARED**: Fully paid
- **ARCHIVED**: No longer needed

To change states:
1. Open the invoice
2. Click the current state
3. Select the new state
4. Provide a reason (optional)
5. Click **Confirm**

## Applying Payments to Invoices

When payments are received:

1. Navigate to the invoice
2. Click **Add Payment**
3. Enter the **Payment Amount**
4. Select the **Payment Date**
5. Enter the **Payment Reference** (check number, bank transfer ID)
6. Click **Save**

Light automatically updates the invoice state to PARTIALLY_CLEARED or CLEARED based on the total received.

## Managing Invoice History

Invoices maintain full audit trails:

1. Open an invoice
2. Click **History**
3. View all changes including:
   - Who created/modified the invoice
   - When changes were made
   - What was changed
   - Reason for changes

## Related Articles

- [Invoice templates](/articles/06-accounts-receivable/6-6-invoice-templates.md)
- [Sending invoices and payment reminders](/articles/06-accounts-receivable/6-7-sending-invoices.md)
- [Creating and managing contracts](/articles/06-accounts-receivable/6-3-contracts.md)
- [Tracking payments and outstanding balances](/articles/06-accounts-receivable/6-8-tracking-payments.md)
