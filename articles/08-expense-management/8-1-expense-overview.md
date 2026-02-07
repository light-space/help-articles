# Expense Management Overview

Expense management in Light handles employee spending across physical and virtual cards, as well as out-of-pocket reimbursements. The module streamlines submission, approval, and reimbursement while automating receipt processing and policy compliance.

[Open in Light →](https://app.light.inc/expenses)

## What is Expense Management?

Expense management is the complete workflow from when an employee spends money on business expenses to when they're reimbursed or the company settles the card bill:

1. **Expense Capture**: Employee submits receipt via multiple channels (Slack, Teams, email, app, mobile)
2. **Data Extraction**: AI automatically extracts expense details from receipts
3. **Categorization**: AI categorizes the expense and assigns GL accounts
4. **Approval**: Manager or team lead approves the expense
5. **Reimbursement**: Finance processes reimbursement or settles card
6. **Reporting**: Analyze spending patterns and policy compliance

Light integrates with corporate card providers and expense submission channels for seamless workflow.

## Key Concepts

**Expenses** represent individual business transactions (flight, hotel, meal, supplies). Multiple expenses can be grouped into a **Reimbursement Request** for approval as a unit.

**Receipts** are supporting documentation (receipt image, email confirmation, PDF). Light's AI extracts receipt data automatically.

**Spending Categories** organize expenses (Travel, Meals, Office Supplies, etc.). Categories map to GL accounts for accounting.

**Policies** define rules (meal limits, pre-approval requirements, ineligible categories). Light enforces policies and flags violations.

**Corporate Cards** can be physical (issued to employee) or virtual (single-use numbers). Card expenses automatically feed to the expense module.

> Good to know: Light uses AI to extract receipt data with 90%+ accuracy, reducing manual data entry for employees and saving Finance time on review.

## Submission Methods

Employees can submit expenses through multiple channels:

- **Slack**: Fast and easy for employees already using Slack
- **Microsoft Teams**: For organizations using Teams
- **Email**: Forward receipts to a company email address
- **Mobile App**: Capture receipt photos and submit on the go
- **Web App**: Upload receipts and enter details manually
- **Corporate Card**: Automatic import from card provider

Choose the method that fits your employee workflow best.

## Expense Workflow

### Typical Submission and Approval

1. **Employee Submits**: Takes photo of receipt and sends via Slack/Teams/email or uploads in app
2. **AI Processing**: Light extracts expense details automatically
3. **Employee Confirms**: Reviews extracted information and corrects if needed
4. **Policy Check**: Light validates against company policies (limits, categories, etc.)
5. **Manager Approval**: Employee's manager receives notification and approves or requests changes
6. **Finance Review** (optional): Finance team does final check before reimbursement
7. **Reimbursement Processing**: Finance processes reimbursement payment or settles card bill

### Expense States

Expenses progress through states:

- **CREATED**: Submitted by employee, awaiting review
- **IN_DRAFT**: Employee reviewing AI extraction
- **SUBMITTED_FOR_REVIEW**: Waiting for manager approval
- **CANCELLED**: Rejected or withdrawn by employee
- Approved → Reimbursement → CLEARED

## Corporate Cards

Light integrates with major corporate card providers:

- **Physical Cards**: Issued to employees, used for in-person and online purchases
- **Virtual Cards**: Single-use card numbers for online purchases
- **Mobile Wallets**: Apple Pay and Google Pay for contactless payments

Card transactions automatically appear in the expense module for categorization and approval.

## Multi-Channel Submission

### Slack Integration

1. Post receipt or forward message in Slack
2. Light bot processes and extracts data
3. Receive link to review extracted information
4. Approve in Slack without leaving conversation

### Teams Integration

1. Share receipt in Teams channel or DM
2. Light bot processes automatically
3. Review and approve in Teams
4. Seamless workflow for Teams-first organizations

### Email Submission

1. Forward invoice/receipt to company email (e.g., expenses@company.com)
2. Light captures email and attachment
3. Sends confirmation link
4. Employee reviews extraction and confirms
5. Expense is recorded

### Mobile App

1. Open Light mobile app
2. Tap **Submit Expense**
3. Take photo of receipt
4. Enter details (amount, category, description)
5. Submit and track status

## AI Receipt Processing

Light's AI:

- **Extracts**: Merchant, date, amount, items from receipt images
- **Categorizes**: Assigns spending category (Travel, Meals, etc.)
- **Validates**: Checks against policy limits and rules
- **Enriches**: Adds context (flight destination, hotel city, etc.)
- **Learns**: Improves accuracy from employee corrections

> Tip: Clear receipt photos result in better data extraction. Light's mobile app includes a photo guide.

## Expense Policies and Compliance

Define policies to control spending and ensure compliance:

- **Spending Limits**: Maximum per category (e.g., meal limit of $75)
- **Ineligible Categories**: What cannot be reimbursed
- **Documentation Requirements**: Receipt required, pre-approval required
- **Pre-Approval**: Large expenses need approval before spending
- **Merchant Restrictions**: Approved vs. prohibited vendors

Light automatically validates submissions against policies and flags violations for manager attention.

## Reimbursement

### Reimbursement Timing

Employees can typically request reimbursement when:
- Expense was paid from personal funds
- Card is not available
- Advance was needed

Reimbursement is processed by Finance on a regular schedule (weekly, bi-weekly, monthly).

### Corporate Card Settlement

For card expenses, Light can:
- Automatically approve if policy-compliant
- Bulk approve into reimbursement for manager sign-off
- Export to card provider for reconciliation

Card issuer processes payment to vendor; employee doesn't need reimbursement.

## Spend Analytics

Light provides visibility into employee spending:

- **By Employee**: Who spends the most
- **By Category**: Which categories represent biggest spend
- **By Merchant**: Where employees buy most
- **By Department**: Spending by cost center
- **Trends**: Month-over-month or year-over-year comparisons
- **Policy Violations**: Where compliance issues are occurring

Use analytics to identify cost-saving opportunities and enforce policies.

## Integration with Accounting

Expense management integrates with GL and AP:

- **GL Posting**: Approved expenses automatically post to appropriate GL accounts
- **Vendor Records**: Recurring merchants are linked to vendor records
- **Cost Centers**: Expenses are allocated to appropriate cost centers
- **Reporting**: Expense data flows into financial statements and management reports

## Related Articles

- [Submitting expenses via Slack](/articles/08-expense-management/8-2-expenses-slack.md)
- [Submitting expenses via Teams](/articles/08-expense-management/8-3-expenses-teams.md)
- [Mobile receipt capture](/articles/08-expense-management/8-5-receipt-capture.md)
- [AI receipt categorization](/articles/08-expense-management/8-6-ai-receipt-categorization.md)
- [Expense approval workflows](/articles/08-expense-management/8-7-expense-approval.md)
- [Expense policies and spending limits](/articles/08-expense-management/8-13-expense-policies.md)
