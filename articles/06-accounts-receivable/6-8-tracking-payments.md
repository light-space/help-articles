# Tracking Payments and Outstanding Balances

Light tracks the status of every sales invoice and exposes payment information at the invoice level and at the customer level.

[Open in Light →](https://app.light.inc/invoice-receivables)

## Tracking Payment Status from the Invoices List

The Sales invoices list shows the state of each invoice. Open invoices that have received payments transition automatically based on the matched amount:

| State | UI Label | Meaning |
|---|---|---|
| `OPEN` | **Open** | Posted; no payments received yet |
| `PAYMENT_PENDING` | **Payment pending** | A payment is initiated but not yet cleared |
| `PARTIALLY_PAID` | **Partially paid** | One or more payments received; balance remaining |
| `PAID` | **Paid** | Fully paid |
| `ARCHIVED` | **Void** | Voided |

Use the filters above the table to narrow the list to a specific state or customer.

## Recording Payments via Bank Reconciliation

Payments received from customers are recorded in Light through **bank reconciliation**: the bank transaction is matched to the open invoice. As matches post, the invoice's payment state updates automatically.

See [Bank reconciliation](/articles/04-bank-reconciliation/) for the matching workflow.

## Customer Payment History

To see all payments received from a specific customer:
1. Open the customer from [Customers](https://app.light.inc/customers)
2. Go to the **Payment history** tab

Each payment row opens a payment details drawer showing:
- **Payment type** — Bank payment or Customer credit
- **Amount** and **currency**
- **Date**
- **Linked invoices**

## Customer Aging Widget

Each customer's overview shows an **aging widget** with these buckets:

| Bucket | Range |
|---|---|
| **Current** | Not yet due (current/future) |
| **1–30 days** | 1 to 30 days past due |
| **31–60 days** | 31 to 60 days past due |
| **61–90 days** | 61 to 90 days past due |
| **91+ days** | More than 90 days past due |

Click a bucket to drill into the underlying invoices.

## Activity Log

Each invoice has an activity log on its detail page showing posting, sending, payment, and other events.

## Related Articles

- [AR aging](/articles/06-accounts-receivable/6-12-ar-aging.md)
- [Customer credits](/articles/06-accounts-receivable/6-9-customer-credits.md)
- [Bank reconciliation overview](/articles/04-bank-reconciliation/)
