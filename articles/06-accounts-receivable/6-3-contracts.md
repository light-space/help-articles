# Creating and Managing Contracts

Contracts in Light define the terms under which you deliver goods or services to customers. They form the basis for multi-period invoicing and revenue recognition.

[Open in Light →](https://app.light.inc/contracts)

## Understanding Contract Structure

A contract links a customer to products, pricing, and delivery terms. Contracts support:

- **One-time invoices**: Single, standalone contracts
- **Recurring contracts**: Monthly, quarterly, annual, or custom intervals
- **Multi-period revenue recognition**: Deferred revenue spread across periods
- **Net terms**: When payment is due relative to invoice date
- **Discounts**: Fixed or percentage-based reductions

## Creating a Contract

1. Navigate to **Revenue & Invoicing → Contracts**
2. Click **+ Create contract**
3. Fill in the contract details:
   - **Contract Name**: Internal identifier (e.g., "Acme Corp - Annual License 2024")
   - **Customer**: Select the customer
   - **Start Date**: When the contract period begins
   - **End Date**: Contract expiration (optional for ongoing contracts)
   - **Company Entity**: Which legal entity is providing the service
   - **Currency**: Billing currency

4. Click **Next** to add products and pricing

## Adding Products and Line Items

Contracts can include multiple line items for different products or services:

1. Click **Add Line Item**
2. Select a **Product** from your catalog (or create inline)
3. Set the **Quantity** and **Unit Price**
4. Apply optional **Line Discount** (amount or percentage)
5. Select the **Tax Category** (if applicable)
6. Click **Add**

> Good to know: You can add as many line items as needed. Light will calculate totals including tax and discounts automatically.

## Payment Terms and Invoicing

Configure how and when invoices are generated:

1. In the contract details, find **Payment Terms**
2. Set the **Net Terms** (e.g., 30, 60, 90 days)
3. Choose the **Invoicing Frequency**:
   - **One-time**: Single invoice at contract start
   - **Monthly**: Recurring invoice each month
   - **Quarterly**: Every three months
   - **Annually**: Every 12 months
   - **Custom**: Define your own schedule

4. If recurring, set the **Number of Invoices** or **End Date**

## Revenue Recognition Setup

For contracts with multi-period revenue:

1. Navigate to the **Revenue Recognition** section
2. Choose the recognition method:
   - **All upfront**: Entire amount recognized on invoice date
   - **Straight-line**: Equal amounts over contract period
   - **Custom schedule**: Define specific amounts per period

3. Set the revenue recognition **Start Date**
4. Review the calculated recognition schedule
5. Click **Save**

The system will automatically create deferred revenue entries in GL when the invoice is posted.

## Contract Amendments and Versioning

Contracts in Light maintain version history:

1. Open an existing contract
2. Click **Edit**
3. Make your changes to products, pricing, or terms
4. Click **Save as New Version**
5. Add a **Reason for Change** (e.g., "Customer requested price reduction")

Previous versions remain accessible for audit and historical reporting.

## Auto-Invoicing

Enable automatic invoice generation from contracts:

1. Open the contract
2. Enable **Auto-Invoice**
3. Set **Invoice Generation Date** (e.g., "1st of each month")
4. Optionally, set **Invoice Reminder Schedule** (e.g., send reminder 5 days before due date)
5. Click **Save**

Light will automatically create and send invoices on schedule. You can review and adjust auto-generated invoices before they're sent.

## Contract Status Lifecycle

Contracts progress through these states:

- **DRAFT**: Contract created but not yet active
- **ACTIVE**: Currently in effect
- **AMENDED**: Contract has been modified (maintains current status)
- **COMPLETED**: All invoicing periods have ended
- **CANCELLED**: Terminated early

## Related Articles

- [Creating and managing customers](/articles/06-accounts-receivable/6-2-customers-contacts.md)
- [Products and pricing](/articles/06-accounts-receivable/6-4-products-pricing.md)
- [Invoice generation and customization](/articles/06-accounts-receivable/6-5-invoice-generation.md)
- [Revenue schedules and deferred revenue](/articles/06-accounts-receivable/6-10-revenue-schedules.md)
