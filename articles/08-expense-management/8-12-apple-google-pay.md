# Apple Pay and Google Pay

Light corporate cards can be added to Apple Pay (iPhone/Apple Watch) and Google Pay (Android devices) for contactless mobile payments. This provides convenience while maintaining spending controls.

[Open in Light →](https://app.light.inc/cards)

## Supported Devices

**Apple Pay**:
- iPhone 6s and newer
- iPad Air 2 and newer
- Apple Watch Series 1 and newer
- macOS devices (for online payments)

**Google Pay**:
- Android 4.4+
- NFC-capable devices (for contactless)
- Any device (for online payments)

## Adding Card to Apple Pay

### Step 1: Verify Card in Light App

1. Open Light app
2. Navigate to [**Cards**](https://app.light.inc/user-cards)
3. Select the card to add to Apple Pay (both physical and virtual cards can be added)
4. Ensure card is **activated**

### Step 2: Add Card to Apple Wallet

**From the Light app (recommended):**
Open the card's details drawer in the Light mobile app and tap **Add to wallet**. The card is provisioned directly to Apple Wallet without entering any card details.

**Manually on iPhone/iPad:**
1. Open **Wallet** app
2. Tap **+** (add card)
3. Choose **Credit or Debit Card**
4. Enter the card details (you can reveal the full card number, expiration date, and CVV in the Light app):
   - Card number
   - Expiration date
   - CVV (verification code)

5. Verify with Face ID or Touch ID
6. Card is added to Wallet

**On Apple Watch:**
1. Open **Watch** app on iPhone
2. Navigate to **Wallet & Apple Pay**
3. Tap **+** to add card
4. Follow same steps as iPhone
5. Card syncs to Apple Watch automatically

### Step 3: Use Apple Pay in Store

1. Hold iPhone or Apple Watch near payment terminal
2. Authenticate with Face ID, Touch ID, or passcode
3. Payment processes immediately
4. Receipt displays on screen or via email

### Step 4: Use Apple Pay Online

1. In app or website checkout, select **Apple Pay**
2. Authenticate with Face ID/Touch ID
3. Payment processes
4. No need to enter card details manually

## Adding Card to Google Pay

### Step 1: Verify Card in Light App

1. Open Light app
2. Navigate to [**Cards**](https://app.light.inc/user-cards)
3. Select the card to add (both physical and virtual cards can be added)
4. Ensure card is **activated**

### Step 2: Add to Google Pay

**On Android Phone:**
1. Open **Google Pay** app
2. Tap **Add payment method** or **+**
3. Choose **Credit or Debit Card**
4. Enter the card details (you can reveal the full card number, expiration date, and CVV in the Light app):
   - Card number
   - Expiration date
   - CVV (if prompted)
   - Cardholder name

5. Verify with fingerprint or pattern
6. Card is added

**Setting as Default (optional):**
1. In Google Pay, find your card
2. Tap **More** > **Set as default**
3. Card is used automatically for all payments

### Step 3: Use Google Pay in Store

1. Hold phone near payment terminal (ensure NFC is enabled)
2. Authentication may be required (fingerprint/pattern)
3. Payment processes immediately
4. Confirmation appears on phone

### Step 4: Use Google Pay Online

1. In app or website checkout, select **Google Pay**
2. Review payment information
3. Authorize with fingerprint/face/pattern
4. Payment processes
5. Card details not shared with merchant

## Security Features

### Card Data Protection

- **Tokenization**: Actual card number not stored on phone. Phone stores encrypted token instead.
- **Device-Specific**: Token only works on enrolled device
- **Unique Transaction Code**: Each transaction has unique code (cannot be reused)
- **Offline Capable**: Payment can work without internet (for contactless)

### Biometric Authentication

- **Face ID/Touch ID** (Apple Pay): Authenticate before payment
- **Fingerprint/Pattern** (Google Pay): Required for payment authorization
- **PIN** (optional): Additional security layer for large purchases

### Fraud Protection

Light monitors Apple Pay/Google Pay transactions:

- **Velocity Checking**: Multiple transactions in short time
- **Amount Checking**: Unusually large single transactions
- **Merchant Checking**: Known high-risk merchants

Large or suspicious transactions may be:
- Declined
- Flagged for verification
- Reviewed by Finance team

### Privacy

- **Merchant Never Sees Card**: Merchant sees only transaction token, not card number
- **Company Never Sees Location**: Payment location not visible to your company (unless card also used offline)
- **No Data Sharing**: Apple Pay/Google Pay don't share purchase data with your company

## Managing Cards in Payment Apps

### Temporarily Disable Card

If card is lost or suspected fraudulent:

1. In **Apple Pay** (iPhone): Settings > Wallet & Apple Pay > Card > **Suspended**
2. In **Google Pay**: Open card settings > **Temporarily suspend**
3. Card is disabled for payment immediately
4. Can be re-enabled later

You can also freeze the card in Light. A frozen card is declined everywhere, including Apple Pay and Google Pay, until it is unfrozen.

### Removing Card

Permanently remove card from device:

1. **Apple Pay**: Settings > Wallet & Apple Pay > Card > **Remove**
2. **Google Pay**: Open card > **More** > **Remove**
3. Card is deleted from device
4. Must be re-added to use again

### Updating Card

If card details change (expiration, PIN):

1. Update in Light app first
2. Apple Pay/Google Pay automatically syncs
3. No action needed on phone (happens automatically)

## Transaction Reconciliation

### Expense Tracking

All Apple Pay/Google Pay transactions:

1. Appear in Light expense module (fed from card processor)
2. Show:
   - Merchant name
   - Transaction amount
   - Date and time
   - Device used (may show "mobile" or "contactless")

3. Can be categorized by employee
4. Go through normal approval workflow

### Receipt Collection

For Apple Pay transactions:

1. Receipt may print at register or appear as email
2. Light may prompt you to upload the receipt (for example, as a reply to the card transaction notification in Slack)
3. Upload the receipt to the transaction in Light if your company's policy requires it

## Limits and Controls

### Spending Limits

Apple Pay/Google Pay respect same spending limits as physical card:

- **Per-transaction limit**: Max per single transaction (e.g., $5,000)
- **Weekly limit**: Max per week (e.g., $10,000)
- **Monthly limit**: Max per month (e.g., $50,000)

Transactions exceeding limits are declined.

### Merchant Restrictions

Blocked merchants apply to mobile payments:

- If merchant is blocked in policy: Apple Pay/Google Pay transaction declined
- If merchant category is blocked (e.g., gambling): Transaction declined
- Works same way as physical card swipes

## Troubleshooting

### Card Not Added to Apple Pay/Google Pay

**Issue**: Unable to add card to mobile wallet

Solutions:
1. **Verify card is activated**: Ensure physical card is activated in Light
2. **Check device compatibility**: Device must support Apple Pay/Google Pay
3. **Check card eligibility**: Some card types or issuers may not support mobile wallets
4. **Retry add process**: Remove and re-add card carefully

### Transaction Declined

**Issue**: Payment declined at terminal despite having funds

Causes:
1. **Spending limit exceeded**: Transaction exceeds per-transaction, weekly, or monthly limit
2. **Merchant blocked**: Policy blocks this merchant/category
3. **Device issue**: NFC may not be working
4. **Card frozen**: Card may have been frozen in Light

Solutions:
1. Check spending limits in Light
2. Verify merchant is allowed
3. Ensure NFC is enabled (Android)
4. Contact support if card appears frozen

### Lost Phone

If phone is lost:

1. **Immediately**: Freeze the card in Light (if you have access)
2. **Or contact**: Light support to freeze card
3. **Remove card**: Once you get a new phone, remove old card from any cloud backup
4. **Request new physical card**: Get replacement card shipped

Card on lost phone is only usable if unlocked. Biometric authentication prevents unauthorized use.

## Best Practices

1. **Keep Device Secure**: Use strong passcode and biometric authentication
2. **Monitor Transactions**: Review card activity regularly in Light
3. **Report Issues**: Immediately report suspicious transactions
4. **Use Default When Possible**: Leverage Apple Pay/Google Pay to reduce physical card exposure
5. **Combine with Expense Tracking**: Submit receipt photos even with card for documentation

## Related Articles

- [Issuing and managing corporate cards](/articles/08-expense-management/8-10-corporate-cards.md)
- [Virtual cards](/articles/08-expense-management/8-11-virtual-cards.md)
- [Setting up Light cards (KYC)](/articles/08-expense-management/8-9-light-cards-kyc.md)
