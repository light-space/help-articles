# Expense Approval Workflows

Expense approval workflows ensure submitted expenses are reviewed and approved by appropriate managers before reimbursement. Workflows can be simple (manager approval) or complex (manager → finance → executive).

[Open in Light →](https://app.light.inc/expenses)

## Understanding Approval Workflows

An approval workflow defines:

- **Approval levels**: How many levels of review (1, 2, or 3+)
- **Approvers**: Who reviews at each level (usually managers)
- **Escalation**: What happens if approver doesn't respond (escalate to manager's manager)
- **Rules**: When different rules apply (e.g., approvers vary by department)

Most organizations use **manager approval**: Employee submits, manager approves, Finance processes reimbursement.

## Default Approval Workflow

Light includes standard workflow:

- **Level 1**: Employee's direct manager reviews and approves
- **Escalation**: If manager doesn't approve within 3 days, escalate to their manager

You can customize or create additional workflows.

## Setting Up Approval Workflows

### Creating a Workflow

1. Navigate to **Settings** > **Approval Workflows**
2. Click **Create Workflow**
3. Enter **Workflow Name** (e.g., "Standard Expense Approval")
4. Choose **Default**: Whether this applies to all expenses
5. Click **Create**

### Adding Approval Levels

1. In the workflow, click **Add Level**
2. Set the **Level Number** (1, 2, 3, etc.)
3. Specify **Approvers**:
   - **By Role**: All managers, all team leads (flexible if people leave)
   - **By User**: Specific people (for fixed authority)
   - **By Department**: Different approvers per department

4. Set approval **Authority**:
   - **All expenses**: Approver reviews everything
   - **By Amount**: Different approvers for different thresholds (e.g., amounts under $1,000 vs. over)

5. Set **Timeout** and **Escalation**:
   - Days before escalation (e.g., 3 days)
   - Who to escalate to (manager of manager, VP, etc.)

6. Click **Add Level**

### Conditional Approval Rules

For complex scenarios, define rules:

1. Click **Add Rule**
2. Set the **condition** (IF):
   - If Department = Engineering
   - If Expense Amount > $500
   - If Category = International Travel
   - If Employee Level = Contractor

3. Set the **action** (THEN):
   - Then Assign to [Manager/Finance]
   - Then Require 2 Approvals
   - Then Require VP Approval

4. Set **Rule Priority**: Order of evaluation
5. Click **Add Rule**

## Manager Approval Process

### Receiving Expense for Approval

Managers receive notifications when employees submit expenses:

1. **Email notification**: "New expense from John Smith ($245) awaits your approval"
2. **In-app notification**: Alert in Light interface
3. **Slack/Teams notification** (if enabled): Message in chat app

Click notification to open expense for review.

### Reviewing an Expense

1. Click notification or navigate to **Approvals** > **Pending**
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

4. Click **Approve** or **Request Changes**

### Approval Actions

**Approve Expense**:
1. Click **Approve**
2. Optionally add comment: "Looks good"
3. Click **Confirm Approval**
4. Expense moves to payment queue
5. Employee gets notification: "Your expense was approved"

**Request Changes or Clarification**:
1. Click **Request Changes** or **Need Clarification**
2. Type specific request:
   - "What business purpose was this for?"
   - "This seems high. Please explain."
   - "Receipt is unclear. Can you provide original?"

3. Click **Send Request**
4. Employee receives request and can respond
5. After response, expense returns to your queue for re-review

**Reject Expense**:
1. Click **Reject**
2. Provide reason:
   - "Non-business expense"
   - "Exceeds policy limit"
   - "Already reimbursed in error"

3. Click **Confirm Rejection**
4. Employee is notified with reason
5. Employee can revise and resubmit or dispute

## Batch Approvals

Approve multiple expenses at once:

1. Navigate to **Approvals** > **Pending**
2. View all expenses awaiting your approval
3. Scan quickly to spot issues
4. Select multiple legitimate expenses (checkboxes)
5. Click **Bulk Approve**
6. Optionally add comment applying to all
7. Click **Approve All**

All selected expenses are approved together.

## Delegation

Temporarily delegate approval authority:

1. Navigate to **Approval Settings**
2. Click **Delegate Approvals**
3. Select **Delegate To**: Person taking over
4. Set **Duration**: Until what date
5. Select **Approval Levels**: Which approvals to delegate
6. Click **Delegate**

Delegated person receives all notifications until delegation expires.

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

## Escalation and Timeouts

### Escalation Triggers

If approver doesn't respond:

1. Clock starts when expense is assigned to approver
2. Default timeout: 3 days (configurable)
3. If not approved by timeout:
   - Escalate to escalation target (usually manager's manager)
   - Escalation target is notified

4. Escalation target can approve or return to original approver

### Escalation Notification

Original approver is notified that expense was escalated:

- "Expense XYZ has been escalated. VP needs your feedback."
- Creates urgency for approval

### Adjusting Timeouts

By workflow or by department:

1. In Workflow settings, set **Timeout Days**
2. Or by rule: Engineering might have 2-day timeout, others have 5 days
3. Short timeouts (2-3 days): Fast processing but may frustrate approvers
4. Long timeouts (7+ days): Less pressure but slower for employees

## Approval Dashboard

Manager view of all expenses awaiting approval:

1. Navigate to **My Approvals** or **Approvals** in app
2. See:
   - **Pending count**: How many expenses waiting for you
   - **Overdue**: Expenses past your timeline (if escalation is set)
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
2. Navigate to **Approvals**
3. View pending expenses
4. Tap any expense to see:
   - Receipt photo
   - Full details
   - Employee notes

5. Tap **Approve** or **Request Changes**
6. Add comment if needed
7. Confirm

Mobile approval supports fingerprint/face authentication for security.

## Escalation Analytics

Monitor approval workflow health:

1. Navigate to **Reports** > **Approval Metrics**
2. View:
   - **Average approval time**: How long expenses take to approve
   - **Escalation rate**: % of expenses escalated
   - **Rejection rate**: % of expenses rejected
   - **Bottleneck approvers**: Who slows down workflow

3. Use to identify problems and improve process

## Related Articles

- [Expense management overview](/articles/08-expense-management/8-1-expense-overview.md)
- [Reimbursement workflow](/articles/08-expense-management/8-8-reimbursement-workflow.md)
- [Expense policies and spending limits](/articles/08-expense-management/8-13-expense-policies.md)
