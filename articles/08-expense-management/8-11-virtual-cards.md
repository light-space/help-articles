# Virtual Cards

Virtual cards are digital Light cards that are issued without a physical card to ship. They provide enhanced security and spending control for online purchases, subscriptions, and vendor payments.

[Open in Light →](https://app.light.inc/cards)

## Understanding Virtual Cards

Virtual cards are:

- **Digital Only**: No physical card needed
- **Issued Instantly**: Ready to use as soon as the card is created
- **Spending Limits**: Set a per-transaction, weekly, or monthly limit for each card
- **Wallet-Ready**: Can be added to Apple Pay and Google Pay
- **Auto-Reconcile**: Transactions feed to expense module automatically

Benefits:
- **Security**: Each card has its own unique number, so one exposed card never affects others
- **Control**: Spending limited to the card's spending limit
- **Compliance**: Automatic policy enforcement

## When to Use Virtual Cards

Virtual cards are ideal for:

- **SaaS Subscriptions**: Monthly software charges (dedicated card per subscription)
- **Online Purchases**: Amazon, Salesforce, etc. (single vendors)
- **Vendor Trials**: Free trials that require card (freeze or close the card after the trial)
- **Third-Party Vendors**: Less-trusted merchants
- **High-Risk Categories**: Travel, entertainment (higher fraud risk)
- **Contractor Payments**: Paying 1099 contractors electronically

## Requesting a Virtual Card

### Self-Service Card Request

Employees can request their own virtual cards:

1. Open Light app or portal
2. Navigate to **Cards** and request a new card
3. Enter:
   - **Merchant/Vendor**: Who you're buying from (e.g., "Salesforce")
   - **Purpose**: What the purchase is for (e.g., "Software subscription")
   - **Amount**: The spending limit (e.g., $500)
   - **Limit Interval**: Per transaction, weekly, or monthly
   - **Notes**: Any special instructions

4. Submit the request

The request is routed through the card approval workflow. Once approved, Light issues the card with:
- **Card Number**: 16-digit number unique to this card
- **Expiration Date**: The card's printed expiry date
- **CVV**: 3-digit security code

5. View the card details securely in the app and use them for online purchases

### Manager-Requested Virtual Cards

For policy control, manager can request on behalf of employee:

1. Navigate to **Cards** > **Request Card for Employee**
2. Select employee
3. Enter card details (same as above)
4. Light generates card
5. Card is assigned to the employee, who can view its details securely in the app
6. Employee uses for purchase

### Admin Virtual Cards

Finance can issue virtual cards for specific purposes:

1. Navigate to **Cards** > **Create Virtual Card**
2. Set card type:
   - **Employee Card**: Card for an employee's business expenses
   - **Vendor Card**: Card dedicated to a specific vendor or subscription

3. Configure:
   - **Amount**: Spending limit
   - **Limit Interval**: Per transaction, weekly, or monthly
   - **Assigned To**: Who can use this card

4. Generate and distribute to employee

## Using Virtual Cards

### Online Purchase Checkout

1. Receive virtual card number from Light
2. Go to vendor website checkout
3. Enter card details:
   - **Card Number**: 16-digit number provided
   - **Expiration**: MM/YY format (e.g., 05/24)
   - **CVV**: 3-digit code provided

4. Enter your company **billing address** if requested
5. Complete purchase
6. Card processes payment

You can also add the card to Apple Pay or Google Pay for mobile payments.

### Handling Subscription Services

For recurring subscription services:

1. Create a dedicated virtual vendor card for the subscription
2. Set a **monthly** spending limit that matches the expected charge
3. The subscription charges the same card each billing cycle
4. Charges above the limit are declined
5. To stop future charges, freeze or close the card

## Managing Virtual Cards

### Viewing Active Virtual Cards

1. Navigate to **Cards** > **Virtual Cards**
2. See active virtual cards:
   - **Merchant**: Who card is for
   - **Amount**: Spending limit
   - **Used**: How much has been spent
   - **Remaining**: Amount left
   - **Expires**: When card expires

3. Click to see details:
   - Full card number
   - Expiration date
   - CVV
   - Transaction history (if used)

### Adjusting Card Limits

Company admins and controllers can adjust a card's spending limit:

1. Open card details
2. Edit the spending limit amount
3. Choose the limit interval: per transaction, weekly, or monthly
4. Transactions that would exceed the limit are declined

Prevents accidental overspend.

### Freezing and Closing Virtual Cards

Freeze or close cards no longer needed:

1. Open card details
2. **Freeze** the card to temporarily block all transactions (it can be unfrozen later)
3. **Close** the card to permanently deactivate it
4. Closed cards cannot be reused

Use if circumstances change and the card is no longer needed.

## Security Features

### Card Number Security

- **Unique Number**: Each virtual card has its own unique number
- **Secure Reveal**: Card details are only revealed securely in the app
- **Non-Transferable**: Card not usable by anyone except intended user
- **Tokenization**: Wallet payments use encrypted network tokens instead of the card number

### Fraud Prevention

Light monitors virtual card usage:

- **Spending Limit**: Card cannot exceed authorized amount
- **Velocity Checking**: Flags multiple transactions in short time
- **Amount Checking**: Alerts if unusually large charge
- **Instant Freeze**: Cards can be frozen immediately if misuse is suspected

### PCI Compliance

Virtual cards reduce PCI compliance burden:

- **Merchant Never Sees Company Details**: Doesn't see other company cards or payment methods
- **Encrypted Transmission**: Card details encrypted in transit
- **Reduced Liability**: Less sensitive data exposed

## Virtual Card Reconciliation

### Transaction Tracking

Virtual card transactions automatically appear in expense module:

1. Transaction posts immediately (within hours)
2. Shows:
   - **Merchant**: Where charge occurred
   - **Amount**: Charge amount
   - **Date**: Transaction date
   - **Card**: Which virtual card was used

3. Can be tracked and reconciled

### Expense Categorization

Transactions can be:

1. **Auto-Categorized**: AI assigns category based on merchant
2. **Manually Categorized**: Employee selects category
3. **Approved**: Manager approves through normal workflow
4. **Posted**: GL entry created based on category

### Cost Center Allocation

Track spending by cost center:

1. When creating virtual card, assign **Cost Center** (optional)
2. When card is used, cost center is automatically charged
3. Finance can track spending by cost center/department
4. Accountability is clear

## Approval Workflows for Virtual Cards

### Pre-Approval for Virtual Cards

For large purchases, require approval first:

1. Configure policy: "Virtual cards over $1,000 require approval"
2. When employee requests $2,000 virtual card:
   - Request goes to manager for approval
   - Manager reviews request
   - If approved: Card is generated
   - If rejected: Request is denied, no card generated

3. Prevents unauthorized spending

### Post-Transaction Approval

Even after card is used:

1. Configure policy: "Expense approval required"
2. Transaction posts to Light
3. Manager is notified and reviews
4. Manager approves or rejects
5. If rejected: Refund is processed

## Virtual Card Reporting

### Virtual Card Usage

1. Navigate to **Reports** > **Virtual Card Usage**
2. View:
   - **Cards Generated**: Total created
   - **Cards Used**: How many were actually used
   - **Unused**: Cards with no transactions yet
   - **Average Amount**: Typical virtual card spending
   - **By Employee**: Who uses virtual cards most
   - **By Merchant**: Most frequent vendors

3. Filter by date range or employee

### Cost Analysis

1. Navigate to **Reports** > **Virtual Card Costs**
2. View:
   - **Processing Fees**: Per-transaction cost
   - **Total Cost**: Cumulative fees
   - **Cost per Transaction**: Average
   - **ROI**: Fraud savings vs. fees

Use to justify virtual card program investment.

## Related Articles

- [Issuing and managing corporate cards](/articles/08-expense-management/8-10-corporate-cards.md)
- [Apple Pay and Google Pay](/articles/08-expense-management/8-12-apple-google-pay.md)
- [Setting up Light cards (KYC)](/articles/08-expense-management/8-9-light-cards-kyc.md)
