# Bill Approval Workflows

Bill approval workflows in Light ensure appropriate oversight before payment. Light provides a predefined Bill workflow that you can customize with approval conditions based on your organization's requirements.

[Open in Light →](https://app.light.inc/payables)

## Understanding the Bill Approval Workflow

Light includes a predefined Bill approval workflow that routes bills to the appropriate approvers based on configurable conditions. You can edit this workflow to match your organization's approval policies.

> Good to know: You cannot create additional approval workflows—Light provides a single Bill workflow that you customize to handle all approval scenarios.

## Approval Conditions

The approval workflow routes bills based on the following condition types:

- **Amount**: Route bills based on total amount (e.g., bills over $10,000 require CFO approval)
- **Entity**: Different approval rules per company entity
- **Bill type**: Route based on the type of bill or expense category
- **Custom properties**: Use custom fields on bills to determine routing

You can combine multiple conditions to create sophisticated approval rules that match your internal controls.

## Editing the Approval Workflow

### Accessing Workflow Settings

1. Navigate to **Settings (gear icon)** > **Approval Workflows**
2. Select the **Bill** workflow
3. Click **Edit** to modify the workflow conditions

### Configuring Approval Conditions

1. In the workflow editor, click **Add Condition**
2. Select the condition type:
   - **Amount**: Set threshold (e.g., "Amount greater than $5,000")
   - **Entity**: Select which entities this rule applies to
   - **Bill type**: Choose bill categories
   - **Custom property**: Select a custom field and value

3. Specify the **Approver(s)**:
   - Select specific users
   - Select users by role (recommended for flexibility)

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
- Bill is approved and moves to the payment queue
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

- [Adding and managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md)
- [Entering and ingesting bills](/articles/07-accounts-payable/7-4-entering-bills.md)
- [Scheduling and executing payments](/articles/07-accounts-payable/7-7-scheduling-payments.md)
