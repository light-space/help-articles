# Customer Credits

Customer credits are credit documents that reduce a customer's balance. They can be applied to one or more open or partially-paid sales invoices.

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

1. Open the posted credit
2. Click **Apply to invoice**
3. The dialog lists invoices for the same customer in **Open** or **Partially paid** state
4. Pick one or more invoices and enter the amount to apply against each
5. The dialog shows the running totals: total invoice amount, total credit, and remaining credit
6. Confirm to apply

The credit's state updates to **Partially cleared** or **Cleared** based on how much remains.

## Other Actions

From the credit detail header three-dot menu (⋮):
- **Send E-invoice** — submit to the e-invoicing network (when supported)
- **Archive** — archive the credit

## Related Articles

- [Invoice generation](/articles/06-accounts-receivable/6-5-invoice-generation.md)
- [Tracking payments](/articles/06-accounts-receivable/6-8-tracking-payments.md)
