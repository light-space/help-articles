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

3. Specify the **Approver(s)**:
   - Select specific users
   - Select users by role (recommended for flexibility)
   - Select user groups—when a bill is routed to a user group, all members of that group see it in their Approving tab and can approve it

4. Click **Save**

### Example Configurations

**Amount-based approval:**
- Bills under $5,000 → Manager approval
- Bills $5,000–$50,000 → Finance approval
- Bills over $50,000 → CFO approval

**Entity-based approval:**
- US Entity bills → US Finance team
- EU Entity bills → EU Finance team

**Combined conditions:**
- Bills over $10,000 AND Entity = US → CFO + US Controller

> Tip: Using role-based approvers instead of specific users makes workflows more resilient to team changes. When someone leaves, reassign the role and the workflow continues working.

## Bill Routing and Approval Process

### How Bills are Routed

1. Bill is created and posted
2. Light evaluates the workflow conditions
3. Bill is assigned to the appropriate approver(s) based on matching conditions
4. Approvers receive notification
5. Approvers review and approve or reject
6. Approved bills move to the payment queue

### Approver Experience

When approvers receive bills:

1. They see notifications (email, in-app, Slack)
2. Click notification to open the bill
3. Review the bill details:
   - **Details**: Vendor, amount, date, terms
   - **Line Items**: What was purchased, GL accounts
   - **Supporting Documents**: Any attached receipts or POs
   - **History**: Previous approvals or rejections

4. Click **Approve** or **Reject**
5. Optionally add a **comment** explaining the decision

### Approval Actions

**Approve:**
- Bill is approved and moves forward based on its **Payment Method**:
  - **Automatic**: Scheduled for payment automatically (requires host-to-host bank connection)
  - **Direct Debit**: Goes straight to Unpaid status — vendor collects payment
  - **Manual**: Goes through guardrails and batch approval, then to Unpaid — paid outside Light
- If multiple approvers are required, bill waits for all approvals

**Reject:**
- Bill is returned to the bill creator with the rejection reason
- Bill returns to DRAFT state
- Creator must address the issue and resubmit
- Bill enters the approval workflow again when resubmitted

**Request Changes:**
- Approver asks for modifications without fully rejecting the bill
- Bill creator receives the request
- Can make minor corrections without restarting the workflow
- Updated bill is resubmitted for approval

## Viewing Pending Approvals

### Finding Bills Awaiting Your Approval

1. Navigate to **Home → Tasks** or click on your **Tasks** in the sidebar
2. See all bills awaiting your approval:
   - Bill number and vendor
   - Amount
   - Bill date
   - Days pending

3. Click a bill to open and review
4. Take approval action directly from the task list

### Filtering and Sorting

Filter pending approvals by:
- Amount range
- Vendor
- Date
- Entity

## Bulk Approval Actions

### Batch Approve

Approve multiple bills at once:

1. Navigate to your pending approvals
2. Select multiple bills (checkboxes)
3. Click **Bulk Approve**
4. Add an optional **comment** explaining the approval
5. Click **Approve All**

All selected bills are approved.

### Batch Reject

Reject multiple bills:

1. Select bills
2. Click **Bulk Reject**
3. Provide a **reason** for rejection
4. Click **Reject All**

> Note: Use batch reject sparingly—rejecting without individual review may miss important details.

## Mobile Approvals

Approve bills on the go using the Light mobile app:

1. Open the Light mobile app
2. Navigate to **Tasks** or **Approvals**
3. View pending bills
4. Tap to review details
5. Click **Approve** or **Reject**
6. Add a comment if needed

Mobile approval supports fingerprint and face authentication for security.

## Best Practices

**Keep conditions simple:** Start with straightforward amount-based rules and add complexity only when needed.

**Use roles, not users:** Assign approvers by role (e.g., "Finance Manager") rather than specific people to avoid workflow disruptions when team members change.

**Document your approval policy:** Maintain an internal policy document that explains your approval thresholds and who is responsible for each level.

**Review regularly:** Periodically review your workflow conditions to ensure they still match your organization's needs as you grow.

## Related Articles

- [Entering bills](/articles/07-accounts-payable/7-4-entering-bills.md)
- [Scheduling payments](/articles/07-accounts-payable/7-7-scheduling-payments.md)
- [Managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md)
