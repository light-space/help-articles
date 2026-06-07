# Bill Approval

Once a bill's data is complete in the Inbox, it moves to the **Approving** tab and is routed to the configured approvers. Approvers can approve or reject the bill from the detail view.

[Open in Light →](https://app.light.inc/payables?tab=approving)

Navigate via **Spend management → Bills → Approving**.

## Approving a Bill

1. Open a bill in the **Approving** tab
2. Review the header, line items, GL coding, and attached document
3. Use the action buttons:
   - **Approve** — approves the bill and advances it through the workflow
   - **Reject** — opens a dialog where you can add an optional comment, then declines the bill

A rejected bill moves to the `DECLINED` state and appears under the **Discarded** tab.

## Approval Log

Each bill has an **Approval log** showing the full audit trail of approval activity:

- Who was assigned as approver
- Each approver's action (Approved / Declined / Pending / In review)
- Timestamps and any comments added

## Multi-Step Approval Chains

Bills may require multiple approvers based on your organisation's policy (configured at the vendor level and in policies). The approval log shows the current step and any pending approvers.

## What Happens After Approval

After all required approvals are recorded, the bill transitions through:

- `APPROVED_ACCOUNTING_ENTRY_PENDING` — finalising the accounting entry
- `READY_FOR_PAYMENT_RELEASE` — ready to be scheduled and paid

From here it's picked up by the payment-scheduling workflow — see [Scheduling payments](/articles/07-accounts-payable/7-7-scheduling-payments.md).

## Related Articles

- [Entering bills](/articles/07-accounts-payable/7-4-entering-bills.md)
- [Scheduling payments](/articles/07-accounts-payable/7-7-scheduling-payments.md)
- [Managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md)
