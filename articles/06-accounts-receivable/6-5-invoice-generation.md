# Invoice Generation

Sales invoices (AR documents) are created from the Sales invoices page. This article covers creating, editing, and posting them.

[Open in Light →](https://app.light.inc/invoice-receivables)

Navigate via **Revenue & Invoicing → Sales invoices**.

## Creating an Invoice

1. Click **+ Create sales invoice** — a dialog opens
2. Fill in the create dialog:
   - **Customer** — required
   - **Entity** — the company entity issuing the invoice
   - **Currency** — defaults to the currency of the customer's most recent issued invoice (if available), otherwise the entity's local currency; you can change it before creating
3. Click **Create** — the invoice opens in DRAFT state, ready for line items and details

## Duplicating an Invoice

If you need to create a new invoice similar to an existing one, open any invoice and click the **⋮** (three-dot menu) in the top right, then choose **Duplicate**. Light creates a new draft with the same customer, entity, currency, line items, and custom properties. You can then edit the draft as needed before posting.

## Invoice Detail Form

Once created, the invoice opens in its detail view. The header section includes:

- **Entity**
- **Customer**
- **Currency**
- **Payment type** — the method of payment expected (e.g., Stripe, ACH, bank transfer)
- **Net terms** — payment terms in days
- **Document template** — controls the invoice layout and email defaults

The body is a line items table with **+ Add line** to add items.

### Line Item Fields

Each line item supports:
- **Product** — pick from your products catalog (auto-fills price, tax, ledger account)
- **Description**
- **Quantity**
- **Unit price**
- **Discount**
- **Tax code**
- **Ledger account**
- **Amortization** — applies a release template to spread revenue over a date range (see [Deferred entries](/articles/05-general-ledger/5-5-deferred-entries.md))

Tabs in the invoice detail include the line items, an activity log, and (if applicable) accruals/deferred revenue.

## Invoice States

| State | UI Label | Description |
|---|---|---|
| `DRAFT` | **Draft** | Editable, not yet posted |
| `OPEN_IN_PROGRESS` | **Open pending** | Posting in progress |
| `OPEN` | **Open** | Posted; awaiting payment |
| `PAYMENT_PENDING` | **Payment pending** | Payment initiated |
| `PARTIALLY_PAID` | **Partially paid** | Some payment received |
| `PAID` | **Paid** | Fully paid |
| `ARCHIVED` | **Void** | Voided |
| `REVERSED` | **Reversed** | Reversed via reverse & reissue (a reversal credit note); locked from further changes |

## Editing an Invoice

Invoices in **Draft** can be freely edited. Once posted (Open or beyond), amounts can no longer be changed and edits are restricted to a limited set of fields.

### Editing Custom Properties After Posting

Even after an invoice is posted, you can still add, change, or remove the custom properties (department, cost center, project code, etc.) on its line items — no need to void and recreate the invoice to fix a tag.

1. Open the posted invoice
2. Enter edit mode on the line item you want to update
3. Add, change, or remove its custom properties
4. Confirm the changes when prompted, then save

Amounts, quantities, and prices stay locked. Beyond custom properties, the same posted-invoice modification flow also lets you update line descriptions, ledger accounts, and tax codes, as well as header fields such as posting date, document date, description, and PO number. Every change is recorded in the invoice's modification history, and the line item re-locks after saving. See [Custom Properties](/articles/02-organization-setup/2-3-custom-properties.md) for more.

## Posting an Invoice

To post an invoice, open it and use the action button in the top right:
- **Post only** — posts to GL without sending
- **Post & send invoice** — posts and emails the invoice in one action

For posting and sending in bulk, see [Sending invoices](/articles/06-accounts-receivable/6-7-sending-invoices.md).

## Related Articles

- [Sending invoices](/articles/06-accounts-receivable/6-7-sending-invoices.md)
- [Invoice templates](/articles/06-accounts-receivable/6-6-invoice-templates.md)
- [Tracking payments](/articles/06-accounts-receivable/6-8-tracking-payments.md)
- [Customer credits](/articles/06-accounts-receivable/6-9-customer-credits.md)
