# Expense Approval Workflows

Expense approval workflows ensure submitted expenses are reviewed and approved by appropriate managers before reimbursement. Workflows can be simple (manager approval) or complex (manager → finance → executive).

[Open in Light →](https://app.light.inc/expenses)

## Understanding Approval Workflows

An approval workflow defines:

- **Approval steps**: How many approval nodes a submission passes through (1, 2, or 3+)
- **Approvers**: Who reviews at each step — specific users, user groups, the requester's manager, or the manager of the previous approver
- **AI agent review**: Light can review expense reports against your expense policies and auto-approve compliant ones
- **Conditions**: When different approval paths apply (e.g., approvers vary by amount or entity)

Most organizations use **manager approval**: Employee submits, manager approves, Finance processes reimbursement.

## Default Approval Workflow

Light includes a default **Expense Reimbursement** workflow, triggered when an expense report is submitted:

- **AI agent review**: Light reviews the expense report against your expense policies
- **Compliant**: The expense report is approved automatically
- **Non-compliant**: The expense report is sent to the inbox for manual review

You can customize this workflow in the visual editor.

## Setting Up Approval Workflows

### Opening the Workflow Editor

1. Navigate to **Settings → Workflows** ([Open in Light →](https://app.light.inc/settings/workflows))
2. Click the **Expense Reimbursement** workflow to open its visual editor
3. Use the toolbar at the bottom to add **Action** or **Condition** nodes
4. Connect nodes to define the approval flow
5. Click **Publish** to activate your changes — draft workflows don't apply to new submissions

### Adding Approval Steps

1. In the visual editor, add an approval node
2. Specify **Approvers**:
   - **Specific users**: Fixed people with approval authority
   - **User groups**: Members of a group can approve
   - **Manager of requester**: The submitting employee's manager
   - **Manager of previous approver**: For chained, multi-level approvals

3. Mark each approver as required or optional
4. Each approval node branches into **if approved** and **if rejected** paths — connect each to the next step
5. To vary approvers by amount or other criteria, route submissions into different approval nodes using condition nodes

### Conditional Approval Rules

For complex scenarios, add condition nodes:

1. In the visual editor, add a **Condition** node
2. Set the **condition** (IF), for example:
   - If Amount > $500
   - If Entity = [specific entity]
   - If Reimbursement submitter = [specific user]
   - If a custom property has a certain value

3. Connect each branch — including the "else" default path — to the appropriate approval step
4. Conditions are evaluated in order, and the first match determines the path

## Manager Approval Process

### Receiving Expense for Approval

Managers receive notifications when employees submit expenses:

1. **Email notification**: "New expense from John Smith ($245) awaits your approval"
2. **In-app notification**: Alert in Light interface
3. **Slack/Teams notification** (if enabled): Message in chat app

Click notification to open expense for review.

### Reviewing an Expense

1. Click the notification or navigate to **Tasks** ([Open in Light →](https://app.light.inc/user-tasks))
2. View expense details:
   - **Receipt image**: See what was purchased
   - **Amount and merchant**: What was spent and where
   - **Category**: What type of expense
   - **Employee notes**: Context about expense
   - **Spending limit**: Whether it's within policy

3. Review for:
   - **Legitimacy**: Is this a real business expense?
   - **Policy compliance**: Does it violate company policies?
   - **Reasonableness**: Is the amount appropriate?
   - **Accuracy**: Is category correct?

4. Click **Approve** or **Reject**

### Approval Actions

**Approve Expense**:
1. Click **Approve**
2. Optionally add comment: "Looks good"
3. Click **Confirm Approval**
4. Expense moves to payment queue
5. Employee gets notification: "Your expense was approved"

**Reject Expense**:
1. Click **Reject**
2. Provide reason:
   - "Non-business expense"
   - "Exceeds policy limit"
   - "Already reimbursed in error"

3. Click **Confirm Rejection**
4. Employee is notified with the reason
5. Employee can reset the rejected expense report, which moves its expenses back to draft so they can revise and resubmit

## Batch Approvals

Approve multiple expenses at once:

1. Navigate to **Tasks** ([Open in Light →](https://app.light.inc/user-tasks))
2. View all expenses awaiting your approval
3. Scan quickly to spot issues
4. Select multiple legitimate expenses (checkboxes)
5. Click **Bulk Approve**
6. Optionally add comment applying to all
7. Click **Approve All**

All selected expenses are approved together.

## Finance Review (Optional)

Some organizations have Finance review before reimbursement:

1. After manager approval, expense moves to Finance queue (if configured)
2. Finance team reviews:
   - **GL account mapping**: Correct account for reimbursement
   - **Cost center**: Correct allocation
   - **Documentation**: All details present
   - **Duplicate**: Not already paid

3. Finance approves or returns to manager if issues

This adds control but increases processing time.

## Approval Dashboard

Manager view of all expenses awaiting approval:

1. Navigate to **Tasks** ([Open in Light →](https://app.light.inc/user-tasks))
2. See:
   - **Pending count**: How many expenses waiting for you
   - **Overdue**: Tasks past their due date
   - **By employee**: Grouped by who submitted
   - **By amount**: Sorted by expense amount

3. Click filters:
   - Show only **over a certain amount** ($500+)
   - Show only specific **categories** (travel, meals, etc.)
   - Show only from **specific employees**

4. Sort by:
   - **Date received**: Oldest first (don't forget old ones)
   - **Amount**: Largest first (focus on significant ones)
   - **Employee**: Group by person

## Mobile Approvals

Approve expenses on the go:

1. Open Light mobile app
2. Navigate to **Tasks**
3. View pending expenses
4. Tap any expense to see:
   - Receipt photo
   - Full details
   - Employee notes

5. Tap **Approve** or **Reject**
6. Add comment if needed
7. Confirm

Mobile approval supports fingerprint/face authentication for security.

## Related Articles

- [Expense management overview](/articles/08-expense-management/8-1-expense-overview.md)
- [Reimbursement workflow](/articles/08-expense-management/8-8-reimbursement-workflow.md)
- [Expense policies and spending limits](/articles/08-expense-management/8-13-expense-policies.md)
