# Bill Approval Workflows

Bill approval workflows in Light ensure appropriate oversight before payment. Workflows can be simple (single approver) or complex (multi-level with escalation rules).

[Open in Light →](https://app.light.inc/payables)

## Understanding Approval Workflows

An approval workflow defines:

- **Approval levels**: How many levels of approval (1, 2, or 3+)
- **Approvers**: Who must approve at each level
- **Approval limits**: Amount thresholds (e.g., finance approves bills over $10,000)
- **Escalation**: What happens if approval times out (escalate to manager)
- **Conditions**: Rules for who approves based on vendor, amount, GL account, etc.

## Default Approval Workflow

Light provides a standard workflow:

- **Level 1**: Manager approves bills under $5,000
- **Level 2**: Finance approves $5,000-$50,000
- **Level 3**: CFO approves over $50,000

You can customize or create additional workflows.

## Creating a Custom Approval Workflow

### Basic Workflow Setup

1. Navigate to **Settings** > **Approval Workflows**
2. Click **Create Workflow**
3. Enter **Workflow Name** (e.g., "Standard AP Approval")
4. Set **Default Approval**: Which workflow applies to bills without specific rules
5. Click **Create**

### Defining Approval Levels

1. In the workflow, click **Add Level**
2. Set the **Level Number** (1, 2, 3, etc.)
3. Specify **Approvers**:
   - Add by **User**: Select specific people
   - Add by **Role**: Anyone with this role (useful when teams change)

4. Set the **Approval Authority**:
   - **Amount Threshold**: Bills up to $X require this level
   - **All Bills**: This level approves everything
   - **Custom Rule**: See Conditional Rules section

5. Optionally, set **Timeout** and **Escalation** (see below)
6. Click **Add Level**
7. Repeat for additional levels

> Good to know: Using role-based approvers makes workflows flexible. If the finance manager leaves, reassign the Finance role to someone new and workflow updates automatically.

### Approval Authorities

You can combine multiple authority types:

- **Amount-based**: Bills under/over certain amounts
- **Vendor-based**: Different approvers for vendor categories
- **GL Account-based**: Different approvers for expense types
- **Department-based**: Different approvers per cost center
- **Custom**: Complex rules (e.g., international vendors only)

## Conditional Approval Rules

For complex scenarios, create rules that route bills to specific approvers:

1. In the workflow, click **Add Rule**
2. Set the **condition** (IF statement):
   - If Vendor Type = International
   - If Amount > $50,000
   - If GL Account = Travel & Expenses
   - If Cost Center = Engineering

3. Set the **action** (THEN):
   - Then assign to [User] for approval
   - Then require 2 approvals instead of 1
   - Then escalate if not approved in 5 days

4. Set **Rule Priority** (rules are evaluated in order)
5. Click **Add Rule**

Repeat to create comprehensive rule sets.

## Bill Routing and Approval Process

### How Bills are Routed

1. Bill is created and posted
2. Light evaluates approval workflow rules
3. Bill is assigned to appropriate approvers
4. Approvers receive notification
5. They review and approve/reject
6. Bill moves to next level (or payment queue if all approved)

### Approver Experience

When approvers receive bills:

1. They see notifications (email, in-app, Slack)
2. Click notification to open bill
3. Review the bill:
   - **Details**: Vendor, amount, date, terms
   - **Line Items**: What was purchased, GL accounts
   - **Supporting Documents**: Any attached receipts or POs
   - **History**: Previous approvals/rejections

4. Click **Approve** or **Reject**
5. Optionally, add a **comment** explaining decision

### Approval Actions

**Approve:**
- Bill moves to next approval level (if applicable)
- Last approver's approval sends bill to payment queue
- Approver who approved last can see status anytime

**Reject:**
- Bill is returned to bill creator with reason
- Bill returns to DRAFT state
- Creator must address issue and resubmit
- Bill enters approval workflow again

**Request Changes:**
- Approver asks for modifications without full rejection
- Bill creator receives request
- Can make minor corrections without restarting workflow
- Updated bill is resubmitted for approval

## Escalation and Timeouts

### Setting Escalation Rules

Prevent bills from getting stuck in approval:

1. In the workflow level, set **Timeout**: Days before escalation (e.g., 5 days)
2. Set **Escalation Action**:
   - **Escalate to Manager**: Route to approver's manager
   - **Auto-Approve**: Automatically approve after timeout
   - **Send Reminder**: Send reminder email to approver

3. Light automatically takes action if approver doesn't respond

### Escalation Example

- Bill assigned to Manager on Monday
- Timeout is 5 days
- Manager doesn't approve by Saturday
- Light escalates to Director (manager's manager)
- Director receives notification and approves

## Approval Dashboard

Monitor approval status:

1. Navigate to **Approvals** > **Pending**
2. See all bills awaiting your approval:
   - Bill number and vendor
   - Amount
   - Days pending
   - Bill date

3. Click a bill to open and approve
4. Filter by:
   - Amount range
   - Vendor
   - Date
   - Department

### Approval Analytics

Track workflow performance:

1. Navigate to **Reports** > **Approval Metrics**
2. View:
   - **Average Approval Time**: How long bills take to approve
   - **Rejection Rate**: % of bills rejected
   - **Common Rejection Reasons**: Top reasons for rejections
   - **Approver Performance**: Which approvers slow down workflow

3. Use to identify bottlenecks and improve processes

## Bulk Actions During Approval

### Batch Approve

Approve multiple bills at once:

1. Navigate to **Approvals** > **Pending**
2. Select multiple bills (checkboxes)
3. Click **Bulk Approve**
4. Add optional **comment** explaining approval
5. Click **Approve All**

All selected bills move forward in workflow.

### Batch Reject

Reject multiple bills:

1. Select bills
2. Click **Bulk Reject**
3. Provide **reason**
4. Click **Reject All**

Use sparingly; rejecting without individual review is risky.

## Mobile Approvals

Approve bills on the go:

1. Use Light mobile app
2. Open **Approvals** section
3. View pending bills
4. Click **Approve** or **Reject**
5. Add comment if needed

Mobile approval supports fingerprint/face authentication for security.

## Delegation

Temporarily delegate approval authority:

1. Open **Approval Settings**
2. Click **Delegate Authority**
3. Select **Delegate To**: The person taking over
4. Set **Duration**: When delegation ends
5. Select which **Approval Levels** they're delegating
6. Click **Delegate**

Useful when on vacation or during leave.

## Related Articles

- [Adding and managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md)
- [Entering and ingesting bills](/articles/07-accounts-payable/7-4-entering-bills.md)
- [Scheduling and executing payments](/articles/07-accounts-payable/7-7-scheduling-payments.md)
