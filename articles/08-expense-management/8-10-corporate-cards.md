# Issuing and Managing Corporate Cards

Light corporate cards provide employees and vendors with virtual payment cards for business expenses. Cards integrate with expense management for automatic reconciliation and spending control.

[Open in Light →](https://app.light.inc/cards)

## Cards Page Overview

The Cards page has three tabs:

- [**Transactions**](https://app.light.inc/cards?tab=transactions): View all card transactions with Date, Merchant, Ledger account, Amount, and Tax code. Filter by status and search by keyword.
- [**Cards**](https://app.light.inc/cards?tab=cards): View all issued cards with Owner, Vendor, Type, Card, and Description columns.
- [**Accounts**](https://app.light.inc/cards?tab=accounts): View card accounts with Account number, Account name, Currency, Entity, and Cards connected.

## Creating Cards

To create a new card, click **+ Create card** from the Cards page. Light supports two card types:

### Employee Cards

Use for employee expenses like travel or supplies.

1. Click **+ Create card**
2. Select **Employee card**
3. Fill in the details:
   - **Owner**: Select the employee from the dropdown
   - **Authentication phone number**: Phone number for card verification
   - **Card account**: Select which card account to link
   - **Card description**: A label for this card (optional)
   - **Limits**: Set a spending limit (Monthly by default) with the currency and amount

4. Click **Create card**

The virtual card becomes available immediately.

### Vendor Cards

Use for recurring vendor payments like subscriptions.

1. Click **+ Create card**
2. Select **Vendor card**
3. Fill in the details:
   - **Owner**: Select the card owner from the dropdown
   - **Authentication phone number**: Phone number for card verification
   - **Card account**: Select which card account to link
   - **Vendor**: Select the vendor (or click **Quick-add vendor** to create one)
   - **Card description**: A label for this card (optional)

4. Click **Create card**

## Card Accounts

Before issuing cards, you need at least one card account. To create one:

1. Go to the [**Accounts**](https://app.light.inc/cards?tab=accounts) tab on the Cards page
2. Click **+ Create account**
3. Configure the account details including account name, currency, and entity

Card accounts group cards together and control the funding source and entity association.

## Managing Cards

### Viewing Cards

1. Navigate to [**Cards**](https://app.light.inc/cards?tab=cards)
2. See all cards with:
   - **Owner**: Who the card is assigned to
   - **Vendor**: The associated vendor (for vendor cards)
   - **Type**: Employee or Vendor
   - **Card**: Card identifier
   - **Description**: Card label

3. Click a card to see its details and manage it

### Adjusting Card Limits

Increase or decrease individual card limits:

1. Open the card
2. Click **Edit Limit**
3. Adjust the limit amount
4. Click **Save**

New limit takes effect immediately.

### Blocking/Unblocking Cards

Temporarily block a card without cancelling:

1. Open the card
2. Click **Block Card**
3. Optionally, select a reason: Under investigation, Unusual activity, etc.
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
3. Provide a reason: Employee left, Card replaced, etc.
4. Light immediately:
   - Cancels card
   - Freezes any pending transactions
   - Prevents future use

5. Card cannot be reactivated (new card must be issued)

## Transactions and Reconciliation

### Viewing Transactions

Card transactions appear automatically in the **Transactions** tab:

1. Navigate to [**Cards → Transactions**](https://app.light.inc/cards?tab=transactions)
2. Each transaction shows:
   - **Date**: When the transaction occurred
   - **Merchant**: Where the card was used
   - **Ledger account**: The GL account for this transaction
   - **Amount**: Transaction amount
   - **Tax code**: Applicable tax code

3. Use the status filter and search bar to find specific transactions

### Card Reconciliation

Reconcile card transactions through bank reconciliation:

1. Navigate to [**Accounting → Bank reconciliation**](https://app.light.inc/bank-reconciliation)
2. Light matches:
   - **Transactions**: Individual card charges
   - **Card Bill**: Aggregate bill from issuer
   - **Approved Expenses**: Expenses approved in Light

3. Verify:
   - All transactions appear on bill
   - No duplicate charges
   - Amounts match

4. Click **Reconcile** to mark settled

### Card Settlement

Settlement happens automatically:

1. Card issuer submits bill to company (monthly typical)
2. Light creates an **AP bill** for card charges:
   - **Vendor**: Card issuer
   - **Amount**: Total card charges
   - **Line items**: Grouped by employee or department
   - **GL accounts**: Posted to respective expense accounts

3. Finance team pays card issuer
4. Reconciliation complete

## Spending Controls

### Policy Enforcement

Spending policies can be configured under [**Settings → Policies**](https://app.light.inc/settings/guardrails/policies) to limit what can be purchased:

- **Monthly Limit**: Max spending per month
- **Merchant Category Limits**: Limits by category (e.g., meals, travel)
- **Blocked Merchants**: No purchases allowed

Light enforces policies at transaction time. If a transaction violates a policy, it is declined.

### Spending Approvals

Require approvals for large purchases:

1. Configure spending thresholds in your approval workflows
2. When an employee makes a large card purchase:
   - Transaction pending (card charges immediately)
   - Manager receives approval request
   - If approved: Expense is approved, posting continues
   - If rejected: Refund is initiated, charge reversed

## Reporting

Analyze card spending using the reports available under [**Planning & Reports → Reports**](https://app.light.inc/ledger-reports). You can create custom reports to track card spending by employee, merchant, category, or time period. Export reports to Excel for further analysis.

## Fraud Detection

Light monitors for suspicious patterns:

1. **Velocity Checking**: Too many transactions in short time
2. **Amount Checking**: Unusually large transactions
3. **Merchant Checking**: Known high-risk merchants

Flagged transactions are:
- Temporarily held
- Employee notified to confirm
- Finance team alerted if suspicious
- Investigation initiated if fraud suspected

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
