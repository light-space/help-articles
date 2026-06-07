# Employee Reimbursements

Reimbursements are employee expenses that flow into AP for payment. They use the same Bills-style UI (Inbox / Approving / Scheduled / Paid / Discarded) but live on a separate page so finance can manage them independently.

[Open in Light →](https://app.light.inc/reimbursements)

Navigate via **Spend management → Reimbursements**.

## How Reimbursements Get Here

Employees submit expenses via the [Expenses](https://app.light.inc/expenses) page (under **Personal → Expenses** in the sidebar). Once submitted, an expense becomes a reimbursement document that appears in the **Reimbursements → Inbox** for finance review.

The flow: **Expense (employee)** → **Reimbursement (finance)** → **Paid**.

## Reimbursement Tabs

Same tab structure as Bills:

| Tab | Contains |
|---|---|
| **Inbox** | Newly submitted reimbursements |
| **Approving** | Reimbursements in approval |
| **Scheduled** | Approved reimbursements awaiting / in payment |
| **Paid** | Fully paid reimbursements |
| **Discarded** | Declined reimbursements |

## Reviewing a Reimbursement

Open a reimbursement to see:
- Submitting employee
- Entity, currency, amount
- Expense lines (description, GL account, tax, receipt attachments)
- Approval log

The action buttons mirror Bills: **Approve** or **Reject**. Rejecting opens the **Add comment** dialog where you can note the reason; the reimbursement moves to the Discarded tab.

## Payment

Approved reimbursements move into the **Scheduled** tab and are paid through the same payment-batch flow as vendor bills (see [Scheduling payments](/articles/07-accounts-payable/7-7-scheduling-payments.md)). The payment is sent to the employee's reimbursement bank account.

## Related Articles

- [Expenses (employee article)](/articles/15-employee/)
- [Bill approval](/articles/07-accounts-payable/7-6-bill-approval.md)
- [Scheduling payments](/articles/07-accounts-payable/7-7-scheduling-payments.md)
