# Issuing and Managing Corporate Cards

Light corporate cards provide employees and vendors with virtual payment cards for business expenses. Cards integrate with expense management for automatic reconciliation and spending control.

[Open in Light →](https://app.light.inc/cards)

## Supported Regions

Light cards can be issued to entities in the **United States**, **United Kingdom**, and **European Union**.


## Cards Page Overview

The Cards page has three tabs:

- [**Transactions**](https://app.light.inc/cards?tab=transactions): View all card transactions. Default columns: Date, Merchant, Ledger account, Amount, Tax code, Entity. Additional columns available: Owner, Card, Posted, Receipt, Account, Description.
- [**Cards**](https://app.light.inc/cards?tab=cards): View all issued cards. Columns: Owner, Vendor, Type, Card, Description, Spend, Account, Entity.
- [**Accounts**](https://app.light.inc/cards?tab=accounts): View card accounts. Columns: Account number, Account name, Currency, Entity, Cards connected, Spent this month, Available funds.

## Creating Cards

To create a new card, click **+ Create card** from the Cards page. Light supports two card types:

### Employee Cards

Use for employee expenses like travel or supplies.

1. Click **+ Create card**
2. Select **Employee card**
3. Fill in the details:
   - **Owner**: Select the employee from the dropdown
   - **Authentication phone number**: Phone number for 3D Secure verification
   - **Card account**: Select which card account to link
   - **Card description**: A label for this card (optional)
   - **Limits**: Select a limit interval (Unlimited, Per transaction, Weekly, or Monthly) and enter an amount

4. Click **Create card**

### Vendor Cards

Use for recurring vendor payments like subscriptions.

1. Click **+ Create card**
2. Select **Vendor card**
3. Fill in the details:
   - **Owner**: Select the card owner from the dropdown
   - **Authentication phone number**: Phone number for 3D Secure verification
   - **Card account**: Select which card account to link
   - **Vendor**: Select the vendor (or click **Quick-add vendor** to create one inline)
   - **Card description**: A label for this card (optional)
   - **Limits**: Select a limit interval (Unlimited, Per transaction, Weekly, or Monthly) and enter an amount

4. Click **Create card**

## Card Accounts

Before issuing cards, you need at least one card account. To create one:

1. Go to the [**Accounts**](https://app.light.inc/cards?tab=accounts) tab on the Cards page
2. Click **+ Create account**
3. Fill in:
   - **Entity selection**: The company entity this account belongs to
   - **Currency**: The account currency
   - **Account number**: A 6-digit number used in your chart of accounts
   - **Account name**: A label for this account (auto-filled based on currency)
4. Click **Create**

Card accounts group cards together and control the funding source and entity association.

## Managing Cards

### Viewing Cards

1. Navigate to [**Cards**](https://app.light.inc/cards?tab=cards)
2. Click a card row to open the card details drawer

The card details drawer shows:
- **Card visual** with last four digits and freeze status
- **Balance**: Remaining balance, limit term, spend vs. limit with progress bar
- **Card details**: Owner, 3DS Password (visible to card owner only). Click **Show more** to see phone, address, entity, account, and tax code.
- **Recent transactions** with a **See all** link

### Editing a Card

1. Open the card details drawer
2. Click **Edit**
3. Update the Owner and/or Limits
4. Click **Save**

### Freezing and Unfreezing Cards

Temporarily freeze a card without closing it:

1. Open the card details drawer
2. Click **Freeze card**
3. The card is immediately frozen — no transactions allowed

To unfreeze:
1. Click **Activate card**
2. The card is immediately active again

### Closing Cards

Permanently close a card:

1. Open the card details drawer
2. Click the three-dot menu (⋯)
3. Click **Close card**
4. Confirm in the dialog — this action cannot be undone

A closed card cannot be reactivated. Issue a new card if needed.

### Add to Wallet

Employee card owners can add their card to Apple Pay or Google Pay directly from the card details drawer using the **Add to wallet** button.

## Transactions

### Viewing Transactions

Card transactions appear automatically in the **Transactions** tab:

1. Navigate to [**Cards → Transactions**](https://app.light.inc/cards?tab=transactions)
2. Use the status filter and search bar to find specific transactions
3. Click a transaction to open its details

### Transaction Statuses

| Status | Description |
|---|---|
| **Authorized** | Transaction initiated — amount may still change. Shown with a pending indicator. |
| **Captured** | Merchant has finalized the charge |
| **Refunded** | Transaction has been refunded |
| **Posted** | Transaction has been posted to the general ledger |

### Card Reconciliation

Card reconciliation works as follows:

1. Individual transactions are posted to the GL once captured
2. The card issuer submits a bill (typically monthly) with all charges
3. Light creates an AP bill grouping the card charges
4. The finance team verifies the transactions match and pays the card issuer bill through the normal AP payment process

## Reporting

Analyze card spending using the reports available under [**Planning & Reports → Reports**](https://app.light.inc/ledger-reports). You can create custom reports to track card spending by employee, merchant, category, or time period. Export reports to CSV for further analysis.

## Related Articles

- [Setting up Light cards (KYC)](/articles/08-expense-management/8-9-light-cards-kyc.md)
- [Virtual cards](/articles/08-expense-management/8-11-virtual-cards.md)
- [Expense management overview](/articles/08-expense-management/8-1-expense-overview.md)
