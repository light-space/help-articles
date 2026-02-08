# Issuing and Managing Corporate Cards

Light corporate cards provide employees with virtual payment cards for business expenses. Cards integrate with expense management for automatic reconciliation and spending control.

[Open in Light →](https://app.light.inc/cards)

## Card Program Management

### Setting Up Card Program

1. Navigate to **Settings (gear icon)** > **Card Program**
2. Configure:
   - **Card Provider**: Light, Visa, or other partner
   - **Card Type**: Credit, Debit, or Prepaid
   - **Spending Limits**: Default per-card and per-employee limits
   - **Merchant Blocks**: Categories not allowed (gambling, nightclubs, etc.)
   - **Approval Required**: If spending requires manager approval first

3. Click **Save**

### Assigning Cards to Employees

Assign cards to employees:

1. Navigate to **Spend management → Cards → Issue Card**
2. Select **Employee** from list
3. Set card details:
   - **Card Limit**: Limit on this card (e.g., $5,000)
   - **Billing Currency**: Usually company currency
   - **Linked Account**: Which GL account for settlement
   - **Expense Categories**: Allowed categories or all

4. Click **Issue Card**

The virtual card becomes available immediately.

### Card Reconciliation

Transactions automatically appear in expense system:

1. Card transactions feed from card processor (daily)
2. Light extracts:
   - **Merchant Name**: Where card was used
   - **Amount**: Transaction amount
   - **Date**: Transaction date
   - **Category**: Expense category (if available from merchant)

3. Transactions appear in expense module with status: **Pending**
4. If employee categorization is needed, employee confirms
5. Manager approval workflow applies
6. Expenses are categorized and approved

### Card Settlement

Settlement happens automatically:

1. Card issuer submits bill to company (monthly typical)
2. Light creates **AP bill** for card charges:
   - **Vendor**: Card issuer
   - **Amount**: Total card charges
   - **Line items**: Grouped by employee or department
   - **GL accounts**: Posted to respective expense accounts

3. Finance team pays card issuer
4. Reconciliation complete

## Managing Employee Cards

### Card Inventory

View all issued cards:

1. Navigate to **Cards** > **Card Inventory**
2. See all cards with status:
   - **Employee Name**: Who card is issued to
   - **Status**: Active, Inactive, Cancelled
   - **Limit**: Current limit
   - **Recent Activity**: Last transaction date
   - **Balance**: Amount remaining (for prepaid)

3. Click card to see details:
   - **Card Number** (last 4 digits only for security)
   - **Expiration Date**
   - **Spending YTD**: Year-to-date spending on card
   - **Recent Transactions**: Last 10 transactions

### Adjusting Card Limits

Increase or decrease individual card limits:

1. Open the card
2. Click **Edit Limit**
3. Adjust the **Card Limit** (e.g., from $5,000 to $10,000)
4. Optionally, add **Reason**: Why limit changed
5. Click **Save**

New limit takes effect immediately. Employee is notified if increased.

### Blocking/Unblocking Cards

Temporarily block a card without cancelling:

1. Open the card
2. Click **Block Card**
3. Optionally, select **Reason**: Under investigation, Unusual activity, etc.
4. Card is immediately frozen (no transactions allowed)
5. Employee is notified

To unblock:
1. Click **Unblock Card**
2. Card is immediately active again

Use blocking to investigate suspicious activity without permanent cancellation.

### Cancelling Cards

Permanently cancel a card:

1. Open the card
2. Click **Cancel Card**
3. Provide **Reason**: Employee left, Card replaced, etc.
4. Light immediately:
   - Cancels card
   - Freezes any pending transactions
   - Prevents future use

5. Card cannot be reactivated (new card must be issued)

## Spending Controls

### Policy Enforcement

Policies limit what can be purchased:

1. Define policy limits:
   - **Daily Limit**: Max transactions per day
   - **Monthly Limit**: Max per month
   - **Merchant Category Limits**: (e.g., meals $75, travel $2,000)
   - **Blocked Merchants**: No purchases allowed

2. Light enforces at transaction time:
   - Transaction exceeds limit: Declined
   - Merchant blocked: Declined
   - Employee over daily limit: Declined

3. Employee can request increase:
   - Manager approves
   - Temporary override granted
   - Or permanent limit increased

### Spending Approvals

Require approvals for large purchases:

1. Configure: **Spending over $X requires approval**
2. When employee makes large card purchase:
   - Transaction pending (card charges immediately)
   - Manager receives approval request
   - If approved: Expense is approved, posting continues
   - If rejected: Refund is initiated, charge reversed

## Reconciliation and Reporting

### Card Settlement Reconciliation

Reconcile card receipts to transactions:

1. Navigate to **Accounting → Bank reconciliation**
2. Light matches:
   - **Transactions**: Individual card charges
   - **Card Bill**: Aggregate bill from issuer
   - **Approved Expenses**: Expenses approved in Light

3. Verify:
   - All transactions appear on bill
   - No duplicate charges
   - Amounts match

4. Click **Reconcile** to mark settled

### Card Spending Reports

Analyze card spending:

1. Navigate to **Planning & Reports → Reports → Card Spending**
2. View:
   - **By Employee**: Spending by person
   - **By Merchant**: Where employees buy most
   - **By Category**: Spending by expense category
   - **Trends**: Month-over-month changes

3. Filter by:
   - **Date Range**: Specific months/years
   - **Employee/Department**: Specific people or teams
   - **Merchant Category**: Type of merchant

4. Export to Excel for analysis

### Fraud Detection

Light monitors for suspicious patterns:

1. **Velocity Checking**: Too many transactions in short time
2. **Amount Checking**: Unusually large transactions
3. **Merchant Checking**: Known high-risk merchants

Flagged transactions are:
- Temporarily held
- Employee notified to confirm
- Finance team alerted if suspicious
- Investigation initiated if fraud suspected

## Card Program Optimization

### Optimizing Card Usage

Use data to improve program:

1. Review card vs. employee reimbursement spending:
   - If many employees still doing reimbursements: Encourage card use
   - If reimbursements declining: Card adoption is working

2. Review declined transactions:
   - Are limits too strict?
   - Should certain merchants be unblocked?
   - Employee frustration indicator

3. Review approval times:
   - Are approvals slowing down process?
   - Should thresholds be adjusted?

### Program Cost Analysis

1. Navigate to **Planning & Reports → Reports → Card Program Cost**
2. View:
   - **Card Fees**: Annual/monthly fees
   - **Transaction Costs**: Processing fees per transaction
   - **Interest Costs**: If using credit cards
   - **Reconciliation Costs**: Staff time to reconcile

3. Compare to:
   - Cost of employee reimbursements (staff time to process)
   - Cost of check writing
   - Cost of ACH payments

4. Justify program ROI or optimization

## Employee Support

### Card Troubleshooting

Employees can get help:

1. **Card Declined**: Contact support to understand why (limit, blocked merchant, etc.)
2. **Wrong Amount**: Investigate transaction and dispute if needed
3. **Duplicate Charge**: Review settlement and request refund

## Related Articles

- [Setting up Light cards (KYC)](/articles/08-expense-management/8-9-light-cards-kyc.md)
- [Virtual cards](/articles/08-expense-management/8-11-virtual-cards.md)
- [Apple Pay and Google Pay](/articles/08-expense-management/8-12-apple-google-pay.md)
- [Expense management overview](/articles/08-expense-management/8-1-expense-overview.md)
