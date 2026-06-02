# Customer Credits

Customer credits are credit documents that reduce a customer's balance. You can apply the full credit amount or allocate a partial amount to one or more open or partially-paid sales invoices—any unallocated balance remains available for future use.

[Open in Light →](https://app.light.inc/customer-credits)

Navigate via **Revenue & Invoicing → Customer credits**.

## Customer Credit States

| State | UI Label |
|---|---|
| `DRAFT` | **Draft** |
| `POSTED` | **Posted** |
| `PARTIALLY_CLEARED` | **Partially cleared** |
| `CLEARED` | **Cleared** |
| `ARCHIVED` | **Archived** |

A credit moves from Posted → Partially cleared → Cleared as it is applied to invoices.

## Creating a Customer Credit

1. Click **+ Create customer credit**
2. Fill in the form (customer, entity, currency, lines, etc.)
3. Click **Create** — the credit opens in **Draft**

## Posting a Credit

From the credit detail page, use the action button at the top right:
- **Post & send** — posts the credit and emails it (the email composer opens, with the same fields as for invoices)
- **Post only** — posts without sending

Once posted, the credit can be applied to invoices.

## Applying a Credit to Invoices

You can apply all or part of a customer credit to one or more sales invoices. Any unallocated balance stays on the credit for later use.

1. Open the posted credit
2. Click **Apply to invoice**
3. The dialog lists invoices for the same customer and entity in **Open** or **Partially paid** state
4. Select one or more invoices
5. Enter the amount to apply against each invoice (any amount up to the credit's available balance)
6. Review the running totals: total invoice amount, amount being applied, and remaining credit balance
7. Click **Apply** to confirm

**What happens next:**
- Each selected invoice's balance decreases by the applied amount
- The credit's state updates to **Partially cleared** if a balance remains, or **Cleared** if fully allocated
- Partially cleared credits can be applied to additional invoices at any time

## Other Actions

From the credit detail header three-dot menu (⋮):
- **Send E-invoice** — submit to the e-invoicing network (when supported)
- **Archive** — archive the credit

## Related Articles

- [Invoice generation](/articles/06-accounts-receivable/6-5-invoice-generation.md)
- [Tracking payments](/articles/06-accounts-receivable/6-8-tracking-payments.md)
