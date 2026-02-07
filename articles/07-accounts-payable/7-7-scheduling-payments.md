# Scheduling and Executing Payments

Light's payment scheduling and execution tools help you manage cash flow, meet payment deadlines, and maintain vendor relationships through on-time payments.

[Open in Light →](https://app.light.inc/payables)

## Payment Methods

Light supports multiple payment methods:

- **Bank Transfer (Wire)**: Electronic funds transfer (domestic or international)
- **ACH**: Automated Clearing House (US banks)
- **Check**: Mailed physical checks
- **Credit Card**: Pay vendors via company credit card
- **Virtual Card**: Single-use card numbers for online vendors
- **Payment Platform**: Third-party systems (PayPal, Stripe, etc.)

Each vendor specifies their preferred method. You can override per payment.

## Recording Payments

### Paying Approved Bills

When a bill is approved and ready to pay:

1. Navigate to **Payments**
2. Click **Create Payment** or **Record Payment**
3. Select the **bill(s)** to pay (or group to pay together)
4. Light shows:
   - Vendor name
   - Amount due
   - Payment terms
   - Preferred payment method

5. Confirm **Payment Amount** (can be partial payment)
6. Select **Payment Method**
7. Enter **Payment Reference** (check number, transaction ID, etc.)
8. Set **Payment Date** (when payment is made)
9. Click **Record Payment** or **Schedule Payment**

### Partial Payments

Pay part of an outstanding bill:

1. Open the bill
2. Click **Add Payment**
3. Enter **Payment Amount** (less than bill total)
4. Select payment method and details
5. Click **Record**

Bill state becomes PARTIALLY_CLEARED. Outstanding balance remains due.

## Payment Scheduling

### Scheduling Future Payments

Schedule payments for future dates (pay bills when due or when cash allows):

1. When creating a payment, click **Schedule Payment**
2. Set the **Payment Date** (future date)
3. Confirm payment details
4. Click **Schedule**

Payment is held until the specified date, then automatically executed (if automated) or appears in payment queue.

### Batch Payment Scheduling

Schedule multiple payments in one operation:

1. Navigate to **Bills** > **Ready to Pay**
2. Filter to bills you want to pay
3. Select multiple bills (checkboxes)
4. Click **Bulk Actions** > **Schedule Payment**
5. Set the **Payment Date** for all selected
6. Review the batch (total amount to pay)
7. Click **Schedule Batch**

Useful for consolidating payments to the same vendor or paying on specific dates.

## Payment Execution

### Manual Payment Execution

For non-automated payment methods (checks, manual bank transfers):

1. Navigate to **Payments** > **Ready to Execute**
2. View payments due today or soon
3. Sort by:
   - **Vendor**: Group payments to same vendor
   - **Payment Method**: Group checks, wires, etc.
   - **Amount**: Largest first or smallest first

4. For **Bank Transfers**:
   - Get payment details from system (vendor bank, amount, reference)
   - Initiate transfer in your bank's system
   - Return to Light and record confirmation

5. For **Checks**:
   - Print checks from Light (or use check stock)
   - Record check number in Light
   - Mail or deliver checks to vendors

6. For **Credit Card**:
   - Use company credit card in vendor's system
   - Record card last 4 digits and confirmation number
   - Light reconciles with card statement automatically

### Automated Payment Execution

Enable automated payments for efficiency:

1. Navigate to **Settings** > **Payment Automation**
2. Enable **Automated Payment Execution**
3. Configure **approved payment methods**:
   - Bank Transfer: Light connects to your bank via API
   - ACH: Light can file ACH batches with your bank
   - Check: Light prints and signs checks automatically (requires digital signature setup)

4. Set **spending limits**:
   - Daily limit for automated payments
   - Per-transaction limit
   - By payment method limits

5. Light automatically executes scheduled payments within these limits

## Payment Batch Management

### Creating Payment Batches

Group payments by vendor, date, or method:

1. Navigate to **Payments**
2. Click **Create Batch**
3. Add bills/payments to batch:
   - Select multiple bills or existing payments
   - Light calculates total

4. Set batch details:
   - **Batch Name**: For reference (e.g., "2/7 Standard Payables")
   - **Payment Date**: When to execute
   - **Approval Required**: Whether approver sign-off needed

5. Click **Create Batch**

### Batch Approval

Batches can require approval (especially for large amounts):

1. Click **Send for Approval**
2. Batch is routed to configured approver
3. Approver reviews total and vendor list
4. Approver clicks **Approve Batch** or **Reject**
5. If approved, batch moves to ready-to-execute
6. If rejected, is returned for review

## Cash Flow Management

### Payment Calendar

Visualize upcoming payments:

1. Navigate to **Dashboard** > **Payment Calendar**
2. View calendar showing:
   - Scheduled payments by date
   - Total due each day
   - Payment method breakdown

3. Click a date to see details of payments due
4. Use to manage cash flow and plan for liquidity

### Payment Forecasting

Project future payment requirements:

1. Navigate to **Reports** > **Payment Forecast**
2. Set time horizon (next 30, 60, 90 days)
3. Light shows:
   - Total payments due each week/month
   - By vendor (largest exposures)
   - By payment method
   - By GL account (category of expense)

4. Export forecast to Excel for cash planning
5. Use to budget cash and coordinate with treasury

## Multi-Currency Payments

### Paying in Foreign Currencies

1. Open bill in foreign currency
2. Click **Create Payment**
3. Choose payment currency:
   - **Original Currency**: Pay in currency of bill
   - **Company Currency**: Convert using FX rate
   - **Other Currency**: Convert from/to any currency

4. Light shows FX rate and calculates payment amount
5. Set **FX Rate Source**:
   - **Market Rate**: Current mid-market rate
   - **Override Rate**: Enter custom rate (for quotes given to vendors)

6. Click **Record Payment**

### Payment Confirmation

After payment is executed:

1. Light shows **Payment Confirmation** with:
   - Payment date and amount
   - FX rate used (if applicable)
   - Actual cash transferred (including bank fees)
   - Payment reference/confirmation number

2. Optionally, attach **bank confirmation** (email or document)
3. Click **Save**

Bill state updates to CLEARED when payment amount equals bill amount.

## Payment Reconciliation

### Matching Payments to Bank Activity

Light integrates with Bank Reconciliation module:

1. When payment executes, Light records it in AP
2. When bank statement arrives, bank rec team matches payment
3. Payment shows as cleared in both AP and bank rec
4. Discrepancies (timing, fees, etc.) are flagged

### Late or Missing Payments

If expected payment doesn't appear in bank statement:

1. Navigate to **Payments**
2. Filter to **Discrepancies**: Scheduled payments not yet cleared
3. Click on payment to investigate
4. Options:
   - **Confirm Sent**: Receipt confirmed from bank
   - **Resend**: Request payment again (for ACH or wire)
   - **Cancel**: Payment is no longer needed
   - **Dispute**: Investigate discrepancy

5. Contact vendor or bank if needed

## Related Articles

- [Bill approval workflows](/articles/07-accounts-payable/7-6-bill-approval.md)
- [Multi-currency payments](/articles/07-accounts-payable/7-8-multi-currency-payments.md)
- [AP aging reports](/articles/07-accounts-payable/7-13-ap-aging.md)
