# Setting Up Light Cards (KYC)

Light cards are corporate payment cards issued directly by Light for seamless expense management and spending control.

[Open in Light →](https://app.light.inc/cards)

## Understanding Light Cards

Light cards are:

- **Physical Cards**: Issued to employees for in-person and online purchases
- **Virtual Cards**: Digital cards issued instantly for online and contactless payments
- **Account Funded**: Cards spend from card accounts you fund by bank transfer
- **Spend Control**: Limits can be set per card, with default limits per card account
- **Auto-Reconciliation**: Card transactions automatically feed to expense module

Light partners with Adyen to issue cards and process transactions. Cards can be issued to entities in the **United States**, **United Kingdom**, and **European Union**.

## Card Types

**Physical Card**:
- Mastercard
- Issued in employee's name
- Can be used in stores, online, ATM
- PIN protected
- Spending limits configurable per card

**Virtual Card**:
- Digital card number, issued instantly
- No physical card
- Used for online and contactless payments
- Spending limits configurable per card
- Ideal for employee expenses or recurring vendor payments like subscriptions

## KYC Verification Process

KYC (Know Your Customer) verification happens at the **company entity** level, not per employee. Before an entity can issue cards, it must be verified as a card customer. Only company admins can start card onboarding.

### Step 1: Start Onboarding for an Entity

1. A company admin enables cards for the company entity
2. Light registers the entity with Adyen, creating a legal entity and account holder
3. The entity's card customer status moves from **Pre-onboarding** to **Onboarding**

### Step 2: Complete Verification with Adyen

1. Light generates a hosted onboarding link for the entity
2. The admin opens the link and completes Adyen's hosted onboarding, providing:
   - Company legal name and registered address
   - Registration number / Tax ID
   - Beneficial ownership information (required for AML compliance)
   - Supporting documents (e.g., proof of registration, identification for beneficial owners)

3. Documents are submitted directly to Adyen for review
4. Adyen may request additional information if verification is uncertain

### Step 3: Activation

1. Once verification is complete, the entity's card customer status becomes **Active**
2. You can then create card accounts, fund them, and issue cards

### Card Customer Statuses

| Status | Description |
|---|---|
| **Pre-onboarding** | Card onboarding has been started but the entity is not yet registered with the card provider |
| **Onboarding** | The entity is registered with Adyen and verification is in progress |
| **Active** | Verification is complete — the entity can issue cards |

### Employee Requirements

Individual employees do not go through KYC. To receive a card, an employee only needs:

- An active user in Light (the card owner)
- An **authentication phone number** for 3D Secure verification
- A shipping address (physical cards only)

## KYC Compliance

Light must comply with regulations:

**Bank Secrecy Act**: Verify customer identity
**USA PATRIOT Act**: Check against OFAC lists (sanctions)
**AML Regulations**: Monitor for suspicious activity
**GDPR/Privacy**: Protect personal data

KYC process ensures compliance. Verification documents are submitted directly to Adyen through the hosted onboarding flow — Light does not store them.

## Card Setup After Approval

### Funding Your Card Account

Before cards can be used, the card account must be funded. Transfer money to your Adyen wallet in the same currency as the account. Funds are available as soon as Adyen receives and processes the transfer — depending on your bank, this normally shouldn't take more than 2–3 days.

### Activating Physical Card

1. Receive physical card in mail (takes several business days)
2. Open Light
3. Navigate to **Cards** and open the card
4. Click **Activate card**
5. Confirm you are in physical possession of the card
6. View your PIN securely in the app
7. Card is active and ready to use

### Setting Up Virtual Card

1. Go to the [Cards](https://app.light.inc/cards) page and click **+ Create card**
2. Select **Employee card** or **Vendor card** (vendor cards are always virtual)
3. Fill in:
   - **Owner**: Who the card belongs to
   - **Authentication phone number**: For 3D Secure verification
   - **Card account**: Which card account to link
   - **Vendor** (vendor cards only): The vendor the card is for
   - **Limits**: Limit interval and amount

4. Click **Create card**

Virtual cards are issued instantly. The card number, expiration date, and CVV can be revealed securely in the app. Virtual cards remain valid until closed — spending is controlled through the limits you set.

## Card Limits and Controls

### Setting Spending Limits

Card limits are managed by company admins and controllers:

1. Navigate to [**Cards**](https://app.light.inc/cards?tab=cards)
2. Open the card details drawer
3. Click **Edit**
4. Set a limit with an interval:
   - **Per transaction**: Max per purchase
   - **Weekly**: Max per week
   - **Monthly**: Max per month
   - Or leave the card **Unlimited**

5. Click **Save**

Employees can view their cards and limits under **Cards** in the Personal section, but only admins and controllers can change limits.

### Default Limits per Card Account

Admins can also set a **default limit** (interval and amount) on a card account, which applies to cards under that account.

## Card Activity and Reconciliation

### Monitoring Card Transactions

Transactions automatically feed to expense module:

1. Open Light, navigate to [**Cards → Transactions**](https://app.light.inc/cards?tab=transactions)
2. View all recent transactions:
   - Merchant name
   - Amount and currency
   - Date and time
   - Status (authorized, captured, refunded, posted)

3. Transactions show in Expense Management automatically
4. Categorized by AI
5. Manager approval workflow applies

### Fraud Alerts

Light monitors for suspicious activity:

- **Unusual amount**: Transaction far above normal
- **Geographic anomaly**: Card used in unexpected location
- **Multiple rapid transactions**: Quick succession of purchases
- **Merchant suspicious**: Known fraud or high-risk merchants

Alerts trigger:
- Card can be temporarily frozen
- Employee notified to confirm transaction
- Finance team alerted if needed

## Card Replacement and Reissuance

### Lost or Stolen Card

1. Freeze the card immediately in Light (or contact support)
2. Freezing stops all transactions instantly
3. Report details:
   - When lost
   - Suspected fraud (if applicable)

4. Card is closed
5. New card shipped (takes several business days)
6. Meanwhile:
   - Use virtual cards for online purchases
   - Or corporate account for emergencies

### Damaged Card

1. Request replacement in app
2. Light ships new card
3. Old card can be returned or destroyed

### Expired Card

1. Request a new card before expiration
2. Activate new card in app
3. Old card is closed

## Employee Card Offboarding

When employee leaves company:

1. Employee returns physical card
2. Light closes card immediately
3. Any pending transactions are reviewed
4. Final expenses are reimbursed if needed
5. Card activity is archived

Card is deactivated and cannot be used after offboarding.

## Related Articles

- [Issuing and managing corporate cards](/articles/08-expense-management/8-10-corporate-cards.md)
- [Virtual cards](/articles/08-expense-management/8-11-virtual-cards.md)
- [Apple Pay and Google Pay](/articles/08-expense-management/8-12-apple-google-pay.md)
