# Scheduling and Releasing Payments

Once a bill is approved, it moves into the payment workflow. Light groups approved bills into **payment batches** that you submit for batch approval, then release.

[Open in Light →](https://app.light.inc/payables?tab=scheduled)

Navigate via **Spend management → Bills → Scheduled**.

## The "Ready for Release" Section

Approved bills sit in a **Ready for release** section. Each row shows the bill, vendor, due date, and current payment date.

To prepare a payment batch:

1. Select the bills you want to pay using the checkboxes
2. A floating action bar appears at the bottom of the screen
3. Use the **calendar** icon in the action bar to set the payment date for the selected bills (a "Change payment date" dialog opens with a calendar picker)
4. Optionally, use the **message** icon to add a comment
5. Click **Submit for approval** to send the batch for approval

## Payment Batch States

After submission, the batch (and the bills inside it) move through these states:

| State | Meaning |
|---|---|
| `PENDING_PAYMENT_APPROVAL` | Batch is awaiting approval by the configured approver(s) |
| `PAYMENT_PAUSED` | Batch (or specific bill) has been paused |
| `SCHEDULED` | Batch is approved and scheduled for the chosen payment date |
| `PAYMENT_PENDING` | Payment has been initiated with the bank |
| `PARTIALLY_PAID` | Some matched payment posted; balance remaining |
| `PAID` / `COMPLETED` | Payment fully settled |

The **Paid** tab lists bills that have completed payment. The **Discarded** tab includes cancelled batches.

## Retrying a Failed Payment

If a payment fails, the bill row exposes a **Retry payment** action in its menu so you can re-attempt the payment.

## Marking Bills as Paid Manually

For bills paid outside Light (e.g., manual wire transfer), open the bill or use the batch menu and choose the **Mark as paid** action. This opens a dialog where you record the payment details so the bill transitions to Paid without going through Light's payment rails.

A **Batch mark as paid** action is available on multiple selected bills.

## Related Articles

- [Bill approval](/articles/07-accounts-payable/7-6-bill-approval.md)
- [Multi-currency payments](/articles/07-accounts-payable/7-8-multi-currency-payments.md)
- [Vendor credit notes](/articles/07-accounts-payable/7-9-vendor-credit-notes.md)
