# Accounts Payable Overview

Light's Accounts Payable (AP) covers the bill-to-payment workflow: capturing vendor bills, routing them for approval, scheduling and releasing payments, and tracking what's been paid.

[Open in Light →](https://app.light.inc/payables)

## Modules and Pages

| Module | Path | Description |
|---|---|---|
| **Bills** | [/payables](https://app.light.inc/payables) | Vendor bills (invoices payable) |
| **Reimbursements** | [/reimbursements](https://app.light.inc/reimbursements) | Employee expense reimbursements (same UI as bills) |
| **Credit entries** | [/credit-entries](https://app.light.inc/credit-entries) | Credit notes from vendors |
| **Vendors** | [/vendors](https://app.light.inc/vendors) | Vendor records and banking details |
| **Purchase orders** | [/procurement/purchase-orders](https://app.light.inc/procurement/purchase-orders) | POs that match against bills |
| **Purchase requests** | [/procurement/purchase-requests](https://app.light.inc/procurement/purchase-requests) | PR-to-PO workflow |

All appear under **Spend management** in the sidebar.

## Bills List — Tabs

The Bills page is organised into five tabs:

| Tab | Contains |
|---|---|
| **Inbox** | Newly ingested bills awaiting review/approval |
| **Approving** | Bills currently in approval flow |
| **Scheduled** | Bills approved and ready for / in payment |
| **Paid** | Fully paid bills |
| **Discarded** | Declined or cancelled bills |

## Bill Lifecycle

A bill progresses through approval-driven states. Common ones you'll see in the UI:

| State | Meaning |
|---|---|
| `IN_DRAFT` | Draft, editable |
| `APPROVAL_REQUESTED` | Sent for approval |
| `APPROVAL_PENDING` | Awaiting approver action |
| `DECLINED` | Rejected by an approver |
| `APPROVED_ACCOUNTING_ENTRY_PENDING` | Approved; finalising accounting entry |
| `READY_FOR_PAYMENT_RELEASE` | Ready to release the payment |
| `PENDING_PAYMENT_APPROVAL` | Payment batch awaiting approval |
| `PAYMENT_PAUSED` | Payment paused |
| `SCHEDULED` | Payment scheduled for a future date |
| `PAYMENT_PENDING` | Payment initiated |
| `PARTIALLY_PAID` | Partial payment matched |
| `UNPAID` | Posted to GL but not yet paid |
| `PAID` | Fully paid |
| `COMPLETED` | Settled |
| `CANCELLED` | Cancelled |
| `DUPLICATED` | Detected as a duplicate |

## Key Features

- **Multi-channel ingestion** — Upload PDF, image, or CSV; manual entry; email-to-inbox; integrations
- **AI extraction** — Vendor, dates, amounts, line items, and tax are auto-extracted from uploaded documents
- **Approval workflows** — Routing to assigned approvers, Approve/Reject actions, approval log
- **Payment batches** — Group bills, schedule a payment date, send for batch approval, release
- **Multi-entity / multi-currency** — Entity is set per bill; bill currency is independent of payment currency
- **PO matching** — Bills can be tied to purchase orders
- **Credit entries** — Vendor credits applied to one or more open bills; credit entries include a **Payments** tab showing payment history and allowing you to reverse bank payments
- **Reimbursements** — Employee expenses flow into the same AP pipeline as a separate document type

## Related Articles

- [Managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md)
- [Vendor portal](/articles/07-accounts-payable/7-3-vendor-portal.md)
- [Entering bills](/articles/07-accounts-payable/7-4-entering-bills.md)
- [AI invoice extraction](/articles/07-accounts-payable/7-5-ai-invoice-extraction.md)
- [Bill approval](/articles/07-accounts-payable/7-6-bill-approval.md)
- [Scheduling payments](/articles/07-accounts-payable/7-7-scheduling-payments.md)
