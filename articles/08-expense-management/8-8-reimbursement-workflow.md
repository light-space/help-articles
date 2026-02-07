# Reimbursement Workflow

The reimbursement workflow is the process from expense approval through payment to employees. Light automates most of this process but provides Finance control where needed.

[Open in Light →](https://app.light.inc/expenses)

## Understanding Reimbursement

Reimbursement occurs when:

- **Employee paid from personal funds**: Submitted expense from own pocket (travel, meal, supply purchase)
- **Corporate card not available**: Employee used personal card or cash
- **Advance request**: Employee requesting advance before spending

Reimbursement is distinct from corporate card settlement (card is billed directly to company).

## Reimbursement Workflow States

Approved expenses progress through states:

1. **APPROVED**: Manager approved, awaiting Finance processing
2. **IN_DRAFT**: Finance is preparing reimbursement batch
3. **SUBMITTED_FOR_REVIEW**: Finance submitted to payment system
4. **PAYMENT_PROCESSED**: Payment executed to employee
5. **CLEARED**: Reimbursement complete and reconciled

## Automatic Reimbursement

Light can automatically process approved expenses:

1. Configure in **Settings** > **Automation** > **Reimbursement**
2. Enable **Auto-Process Approved Expenses**
3. Set options:
   - **Timing**: Process daily, weekly, or on-demand
   - **Minimum Amount**: Only pay if batch exceeds (e.g., $100)
   - **Maximum Amount**: Safety limit per batch
   - **Day of Week**: Which day to process (e.g., Fridays)

4. Light automatically:
   - Creates reimbursement bill in AP
   - Routes to payment processing
   - Pays employee on schedule

With automation, approved expenses are paid automatically. No Finance intervention needed.

## Manual Reimbursement Processing

For more control, process reimbursements manually:

### Creating Reimbursement Batch

1. Navigate to **Reimbursements** > **Approved**
2. View all approved expenses awaiting reimbursement
3. Filter to expenses ready to pay:
   - **By employee**: Pay one person at a time
   - **By date**: Pay weekly or monthly batches
   - **By amount**: Batch similar amounts together

4. Select expenses (checkboxes)
5. Click **Create Reimbursement Batch**
6. Light shows:
   - List of selected expenses
   - Total to reimburse
   - Each employee's amount

7. Click **Create Batch**

### Creating AP Bill for Reimbursement

1. Light creates an **AP bill** for the batch:
   - **Vendor**: The employee (as User vendor)
   - **Amount**: Total of all selected expenses
   - **Line items**: Individual expenses from the batch
   - **GL accounts**: Posted to appropriate accounts based on category

2. Bill appears in **AP** > **Bills** > **Reimbursements**
3. Bill shows status: **DRAFT**

### Posting the Bill

1. Open the reimbursement bill
2. Review amounts and GL accounts
3. Click **Post** when ready
4. GL entries are created
5. Bill moves to **POSTED** state

### Creating Payment

1. After posting, click **Create Payment**
2. Light shows payment details:
   - Employee banking information
   - Amount to pay
   - Payment method (default from employee setup)

3. Confirm payment method:
   - **Direct deposit**: ACH to employee bank account
   - **Check**: Mail check to employee
   - **Other**: Credit card or other method

4. Click **Schedule Payment** or **Execute Payment**

### Executing Payment

1. If scheduled, payment executes on set date
2. If immediate, Light processes payment now:
   - For ACH: Submits ACH file to your bank
   - For Check: Prints check (if configured)
   - For other methods: Routes accordingly

3. Employee receives notification: "Reimbursement of $X is being processed"
4. Bank processes payment (1-3 days typical)
5. Employee receives funds

## Reimbursement by Employee

View what each employee is owed:

1. Navigate to **Reimbursements** > **By Employee**
2. View each employee with:
   - **Total to reimburse**: Sum of approved, unpaid expenses
   - **Last reimbursement**: When last paid
   - **Pending expenses**: Number of approved expenses

3. Click employee to see:
   - Individual expenses
   - Dates of expenses
   - Amounts
   - Categories

4. Optionally, create batch for just that employee

## Grouping Reimbursements

Batch multiple employees' expenses together:

1. Select expenses from multiple employees
2. Light shows:
   - Employee 1: $345
   - Employee 2: $120
   - Employee 3: $890
   - Total batch: $1,355

3. Create single AP bill for entire batch
4. Post and pay all at once
5. Individual employees are reimbursed separately

## Advance Payments

Process advances before expenses:

1. Employee requests advance: "I need $500 for upcoming trip"
2. Manager approves advance
3. Create **Advance Bill** in AP:
   - **Vendor**: Employee
   - **Amount**: $500
   - **GL Account**: Advances (asset account)

4. Post and pay advance
5. Employee receives funds
6. Employee submits expense receipts after trip
7. Expenses are approved
8. Final reimbursement = (Actual Expenses) - (Advance Paid)
9. Either reimburse additional or employee returns overage

## Reconciling Reimbursements to Receipts

Ensure all approved expenses are reimbursed:

1. Navigate to **Reimbursement Reports**
2. View:
   - **Approved Not Yet Reimbursed**: Expenses approved but not paid
   - **Days Pending**: How long expense has been pending payment

3. Identify stalled expenses and process

### Following Up on Late Payments

If payment hasn't reached employee:

1. Check bank status:
   - For ACH: Typically 1-3 business days
   - For checks: 5-10 business days (mail time)

2. If delayed:
   - Confirm bank received ACH file
   - Check for checks returned due to invalid account info
   - Follow up with bank

3. Reissue payment if needed

## Handling Reimbursement Issues

### Duplicate Expense

If employee is paid twice for same expense:

1. Identify duplicate (Light may flag)
2. Contact employee: "We paid you for this already"
3. Options:
   - Employee voluntarily returns overpayment
   - Company recoups from next paycheck
   - Deduct from future reimbursement

4. Reverse the duplicate payment in AP
5. Update bill to reflect single payment only

### Incorrect Amount

If paid wrong amount:

1. If overpaid:
   - Process credit to employee
   - Adjust next reimbursement, or
   - Request employee to return overpayment

2. If underpaid:
   - Process additional payment for difference
   - Issue separate check for shortfall

3. Investigate cause (data entry error, forgotten receipt, etc.)

## Reimbursement Timing

### Daily Processing

For companies that process daily:

1. Approved expenses paid same or next business day
2. Fast for employees
3. Requires automated setup

### Weekly Processing

Most common:

1. Process every Friday or Monday
2. Approved expenses paid weekly
3. Employees know to expect payment specific day
4. Finance controls batch size

### Monthly Processing

For companies with fewer expenses:

1. Process once a month (e.g., on 15th)
2. Employee must wait up to month for payment
3. Reduces Finance overhead
4. Can be stressful for employees

## Reimbursement Portal Access

Employees can track their reimbursements:

1. Login to Light app or portal
2. Navigate to **My Reimbursements**
3. View:
   - Pending approval (waiting for manager)
   - Approved and scheduled (waiting for payment)
   - Paid (with payment date and amount)
   - Declined (with reason)

4. See expected payment date
5. Can open tickets if payment not received

## Related Articles

- [Expense approval workflows](/articles/08-expense-management/8-7-expense-approval.md)
- [Employee reimbursements](/articles/07-accounts-payable/7-10-employee-reimbursements.md)
- [Issuing and managing corporate cards](/articles/08-expense-management/8-10-corporate-cards.md)
