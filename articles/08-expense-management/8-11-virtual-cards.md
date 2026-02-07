# Virtual Cards

Virtual cards are single-use or limited-use card numbers generated for specific online purchases. They provide enhanced security and spending control for high-risk or one-time purchases.

[Open in Light →](https://app.light.inc/cards)

## Understanding Virtual Cards

Virtual cards are:

- **Digital Only**: No physical card needed
- **Single-Use**: Automatically expire after one use (or set limit)
- **Short-Lived**: Expire in hours, days, or weeks
- **Spending Limits**: Set specific limit for each card
- **Merchant-Specific**: Can be restricted to single merchant or category
- **Auto-Reconcile**: Transactions feed to expense module automatically

Benefits:
- **Security**: Card number not reused, reducing fraud risk
- **Control**: Spending limited to specific amount
- **Privacy**: Merchant never sees company card number or full details
- **Compliance**: Automatic policy enforcement

## When to Use Virtual Cards

Virtual cards are ideal for:

- **SaaS Subscriptions**: Monthly software charges (avoid recurring charges)
- **Online Purchases**: Amazon, Salesforce, etc. (single vendors)
- **Vendor Trials**: Free trials that require card (expires after use)
- **Third-Party Vendors**: Less-trusted merchants
- **High-Risk Categories**: Travel, entertainment (higher fraud risk)
- **Contractor Payments**: Paying 1099 contractors electronically

## Requesting a Virtual Card

### Self-Service Virtual Card

Employees can request their own virtual cards:

1. Open Light app or portal
2. Navigate to **Cards** > **Request Virtual Card**
3. Enter:
   - **Merchant/Vendor**: Who you're buying from (e.g., "Salesforce")
   - **Purpose**: What the purchase is for (e.g., "Software subscription")
   - **Amount**: How much you'll spend ($500)
   - **Expiration**: How long card should last:
     - Single-use (recommended)
     - 7 days
     - 30 days
     - 90 days
   - **Notes**: Any special instructions

4. Click **Generate Card**

Light instantly generates:
- **Card Number**: 16-digit number unique to this request
- **Expiration Date**: When card becomes invalid
- **CVV**: 3-digit security code
- **Billing Address**: For online checkout

5. Use immediately in online purchase

### Manager-Requested Virtual Cards

For policy control, manager can request on behalf of employee:

1. Navigate to **Cards** > **Request Card for Employee**
2. Select employee
3. Enter card details (same as above)
4. Light generates card
5. Card number is shared with employee
6. Employee uses for purchase

### Admin Virtual Cards

Finance can issue virtual cards for specific purposes:

1. Navigate to **Cards** > **Create Virtual Card**
2. Set card type:
   - **Personal Use**: Employee gets card for personal expenses
   - **Vendor Payment**: Paying a specific vendor
   - **Subscription**: Recurring service charge

3. Configure:
   - **Amount**: Spending limit
   - **Expiration**: Days until auto-expiration
   - **Merchant Whitelist**: Only usable at certain merchant (optional)
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

4. Enter **billing address** provided with card
5. Complete purchase
6. Card processes payment

Card information is never saved by the merchant (one-time use).

### Handling Subscription Services

For subscriptions where merchant tries to charge repeatedly:

1. Virtual card is set to **single-use**
2. First charge goes through
3. Merchant tries to charge again (auto-renewal)
4. Card is declined (number no longer valid)
5. Employee must:
   - Manually authorize renewal on company card, or
   - Request new virtual card, or
   - Switch to manual payment

Alternatively:
1. Generate virtual card with **30 or 90-day expiration**
2. Matches subscription billing cycle
3. Card auto-expires at renewal (prevents surprise charges)

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

### Limiting Virtual Card Scope

Restrict virtual card to specific merchant:

1. When generating card, set **Merchant Whitelist**
2. Enter merchant name (e.g., "Salesforce")
3. Card only works at that merchant
4. Declined if used elsewhere

Prevents accidental misuse.

### Cancelling Unused Virtual Cards

Cancel cards no longer needed:

1. Open card details
2. Click **Cancel**
3. Card becomes invalid immediately
4. Cannot be reused

Use if circumstances change and purchase no longer needed.

## Security Features

### Card Number Security

- **Unique Number**: Each virtual card has unique number (no reuse)
- **Short-Lived**: Expires after set period
- **Non-Transferable**: Card not usable by anyone except intended user
- **Tokenization**: Card details not stored by merchant (encrypted token used)

### Fraud Prevention

Light monitors virtual card usage:

- **Spending Limit**: Card cannot exceed authorized amount
- **Merchant Restriction**: Card only works at specified merchant
- **Velocity Checking**: Flags multiple transactions in short time
- **Amount Checking**: Alerts if unusually large charge
- **Auto-Expiration**: Card automatically expires, preventing misuse

### PCI Compliance

Virtual cards reduce PCI compliance burden:

- **Merchant Never Sees Company Details**: Doesn't see company card or payment method
- **No Card Storage**: Merchant cannot store number for future use
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
   - **Card Expiration**: Which virtual card was used

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
   - **Unused**: Cards that expired without use
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
