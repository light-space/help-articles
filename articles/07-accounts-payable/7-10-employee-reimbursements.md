# Employee Reimbursements

Light's reimbursement module handles employee expenses submitted for company reimbursement. Employees submit expenses; managers approve; Finance processes reimbursement payments.

[Open in Light →](https://app.light.inc/reimbursements)

## Understanding Employee Reimbursements

Reimbursement is when an employee pays for a business expense out-of-pocket and is paid back by the company. This is different from corporate card spending (which is billed directly to company).

Common reimbursable expenses:
- Travel (airfare, hotel, car rental, meals)
- Office supplies purchased from personal funds
- Client entertainment
- Professional development
- Healthcare expenses (if company covers)

## Setting Up Employees for Reimbursement

### Adding Employees

Employees are set up as users in Light:

1. Navigate to **Users** ([Open in Light →](https://app.light.inc/users))
2. Click **+ Create user**
3. Enter:
   - **Employee Name**
   - **Email**: Employee email address
   - **Role**: Assign the reimbursement role for the employee to be able to file reimbursements

4. Click **Create**

### Employee Banking Information

Add banking details for reimbursement payments:

1. Open the employee's profile
2. Navigate to **Banking Details**
3. Enter:
   - **Bank Name** and **Country**
   - **Account Number**
   - **Routing Number** (for US employees)
   - **Or IBAN** (for international employees)

4. Optionally, add **secondary account**
5. Click **Save**

Light uses this to automatically pay reimbursements.

### Employee Reimbursement Settings

Configure reimbursement preferences:

1. Open the employee's profile
2. Navigate to **Reimbursement Settings**
3. Set:
   - **Default Cost Center**: Default GL account for expenses

4. Click **Save**

## Submitting Expenses for Reimbursement

Employees submit expenses, which creates bills/reimbursements in the AP module. See Expense Management articles (8.x) for detailed submission instructions.

Once submitted, expenses appear as:

1. In **Pending Reimbursements** queue
2. Require manager approval (via Expense Approval Workflows)
3. After approval, become AP reimbursement bills
4. Finance processes reimbursement payments

## Expense Aggregation

### Grouping Individual Expenses

Multiple expenses submitted by one employee can be:

1. Reviewed individually by manager
2. Approved individually or as group
3. Reimbursed individually or batched

When processing reimbursements:

1. Navigate to **Reimbursements**
2. View approved expenses by employee
3. Click **Create Reimbursement Batch** (groups expenses with same employee)
4. Light shows:
   - Employee name
   - Total approved amount
   - Individual expenses included
   - Any duplicates or suspicious items flagged

## Reimbursement Approval

### Manager Review

Managers review submitted expenses:

1. Navigate to **My Approvals**
2. View pending expense reimbursements
3. Click on employee's reimbursement request
4. Review each expense:
   - Receipt image (uploaded by employee)
   - Description and amount
   - Date and category
   - GL account assignment

5. Click **Approve** or **Request Changes**

If requesting changes, employee gets notification and can adjust.

### Finance Review (Optional)

Before processing payment, Finance can do final review:

1. Navigate to **Reimbursements** > **Approved**
2. Select reimbursements ready to process
3. Click **Review**
4. Check:
   - All receipts present
   - Amounts reasonable
   - GL accounts appropriate
   - No policy violations

5. Click **Approve for Payment** or **Return for Correction**

## Processing Reimbursements

### Creating Reimbursement Bills

Once approved, create bills for accounting:

1. Navigate to **Reimbursements** > **Approved**
2. Select reimbursements to process
3. Click **Create Reimbursement Bills**
4. Light creates reimbursement records for each employee:
   - Employee: Name from user profile
   - Amount: Total approved expenses
   - Line items: Expense categories from submitted receipts
   - GL accounts: Posted to appropriate accounts

5. Click **Create**

### Automatic Payment

With configured automation, Light can:

1. Automatically create reimbursement bills
2. Post them to GL
3. Create payment batch
4. Execute payment to employee bank account

Enable in **Settings** > **Automation** > **Auto-Process Reimbursements**

### Manual Payment Processing

For more control:

1. Review and confirm reimbursement bills
2. Navigate to **Payments**
3. Select reimbursement bills to pay
4. Click **Create Payment**
5. Enter payment date
6. Click **Schedule Payment** or **Execute Payment**

## Reimbursement Reconciliation

### Tracking Reimbursement Status

1. Navigate to **Reimbursements**
2. View status of all reimbursements:
   - **Submitted**: Employee submitted, awaiting approval
   - **Approved**: Manager approved, waiting for Finance
   - **Processing**: Finance approved, bill created
   - **Paid**: Payment executed to employee

3. Click on a reimbursement to see full details

### Employee Reimbursement Portal

Employees can check reimbursement status:

1. Access employee portal or Light app
2. Click **Reimbursements**
3. View all submitted reimbursements:
   - Status (submitted, approved, paid, denied)
   - Amount approved
   - Date approved/paid
   - Payment reference (if paid)

4. Download receipt images or expense receipts

## Expense Policies and Limits

Enforce compliance through policies:

1. Navigate to **Settings** > **Reimbursement Policies**
2. Create policies defining:
   - **Eligible expenses**: What can be reimbursed
   - **Limits**: Maximum per category (e.g., meal limit of $75)
   - **Documentation**: Receipt requirements
   - **Pre-approval**: When approval needed before spending

3. Assign policies to employees or departments
4. Light validates submissions against policies
5. Flags policy violations for manager review

## Duplicate Detection

Light detects potential duplicate reimbursements:

1. When reviewing expenses, Light checks for:
   - Duplicate expense descriptions and amounts
   - Same receipt submitted multiple times
   - Same expense submitted by multiple employees

2. Duplicates are flagged with warning
3. Manager confirms legitimacy or rejects duplicate

## Reimbursement Reports

### Reimbursement Analytics

1. Navigate to **Reports** > **Reimbursement Summary**
2. View:
   - Total reimbursements by period
   - By employee (who submits most)
   - By category (common expenses)
   - Average reimbursement size
   - Approval time (days to process)

3. Filter by employee, department, date range
4. Export for analysis

### Policy Compliance

Monitor policy compliance:

1. Navigate to **Reports** > **Policy Compliance**
2. View violations detected:
   - Exceeded limits
   - Ineligible expenses
   - Missing documentation

3. See which employees/departments need training
4. Track corrective actions

## Related Articles

- [Entering and ingesting bills](/articles/07-accounts-payable/7-4-entering-bills.md)
- [Submitting expenses via Slack](/articles/08-expense-management/8-2-expenses-slack.md)
- [Expense approval workflows](/articles/08-expense-management/8-7-expense-approval.md)
