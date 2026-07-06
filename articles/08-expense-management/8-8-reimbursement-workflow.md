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

Individual expenses move through these statuses:

1. **IN_DRAFT**: Employee is preparing the expense
2. **SUBMITTED_FOR_REVIEW**: Expense has been submitted as part of a reimbursement
3. **CANCELLED**: Expense was cancelled

When an employee submits, their draft expenses are grouped into a single reimbursement (expense report), which progresses through these states:

1. **IN_PROGRESS**: Reimbursement submitted, processing started
2. **SUCCEEDED**: A reimbursement bill was created in AP
3. **FAILED**: Processing failed — the expenses return to draft so they can be resubmitted
4. **REJECTED**: The reimbursement was declined during review
5. **RESET**: A rejected reimbursement was reset — its expenses return to draft so the employee can correct and resubmit them

## Automatic Reimbursement

Light can automatically process submitted expense reports using the expense submission workflow:

1. Configure the workflow in **Settings** → **Workflows**
2. When an employee submits an expense report, Light's AI agent reviews it against your expense policies
3. Based on the review:
   - **Compliant**: The reimbursement is approved automatically
   - **Non-compliant**: The reimbursement is sent to the Inbox for manual review

4. Light automatically:
   - Creates a reimbursement bill in AP
   - Routes it to approval and payment processing

Light can also automatically submit reimbursement bills for approval once all approvers are set (enabled per company — contact Light to turn this on).

With automation, compliant expense reports are processed without Finance intervention.

## Manual Reimbursement Processing

For more control, process reimbursements manually:

### Reviewing Submitted Reimbursements

1. Navigate to **Reimbursements**
2. View all submitted reimbursements
3. Each reimbursement groups one employee's submitted expenses
4. Open a reimbursement to see:
   - List of included expenses
   - Total to reimburse
   - The employee to pay

### Creating AP Bill for Reimbursement

1. Light automatically creates an **AP bill** for each submitted reimbursement:
   - **Payee**: The employee (paid as an individual, not a vendor)
   - **Amount**: Total of the submitted expenses
   - **Line items**: Individual expense line items
   - **GL accounts**: Each line is coded to the GL account of its reimbursement category

2. Bill appears in **Bills** and on the **Reimbursements** page
3. Bill shows status: **Draft** and lands in the Inbox for review (unless auto-approved)

### Approving the Bill

1. Open the reimbursement bill
2. Review amounts and GL accounts
3. Submit it for approval when ready
4. Once approved, accounting entries are created and the bill becomes ready for payment

### Creating Payment

1. After approval, schedule the payment
2. Light shows payment details:
   - Employee banking information from their reimbursement profile
   - Amount to pay

3. Payments are sent as bank transfers to the bank details in the employee's reimbursement profile:
   - Reimbursement currency and bank country
   - IBAN (with BIC), or
   - Local account number and routing/bank code (e.g., US account and routing number)

4. Payments are grouped into payment batches for release

### Executing Payment

1. If scheduled, payment executes on set date
2. Light initiates a bank transfer using the appropriate payment rail (domestic or international)
3. Bank processes payment (1-3 days typical)
4. Employee receives funds and a notification: "Your reimbursement has been paid"

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

Pay multiple employees' reimbursements together:

1. Each reimbursement produces its own AP bill (one per employee)
2. Light shows:
   - Employee 1: $345
   - Employee 2: $120
   - Employee 3: $890
   - Total batch: $1,355

3. Payments are grouped into a single payment batch
4. Release the batch to pay all at once
5. Each employee receives their own bank transfer

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
   - Bank transfers typically take 1-3 business days

2. If delayed:
   - Confirm the payment batch was released
   - Check for payments returned due to invalid bank account details
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
2. Navigate to **Expenses**
3. View:
   - Draft expenses (not yet submitted)
   - Submitted (waiting for review and payment)
   - Paid (with payment date and amount)
   - Rejected (a rejected reimbursement can be reset, returning its expenses to draft for correction and resubmission)

4. See expected payment date
5. Can open tickets if payment not received

## Related Articles

- [Expense approval workflows](/articles/08-expense-management/8-7-expense-approval.md)
- [Employee reimbursements](/articles/07-accounts-payable/7-10-employee-reimbursements.md)
- [Issuing and managing corporate cards](/articles/08-expense-management/8-10-corporate-cards.md)
