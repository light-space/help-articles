# Multi-Currency Payments

Light handles multi-currency payments for global companies paying vendors in their local currencies. This article covers currency management, FX rates, and payment execution across currencies.

[Open in Light →](https://app.light.inc/payables)

## Understanding Multi-Currency Payments

When paying vendors in foreign currencies:

- Invoice is in vendor's local currency (e.g., EUR, GBP, JPY)
- You may pay in your functional currency or vendor's currency
- FX conversion happens at time of payment
- Gains/losses are recorded in GL

Light automates FX management and provides FX rate controls.

## Setting Vendor Currency Preferences

### Vendor Default Currency

1. Open a vendor
2. Navigate to **Payment Preferences**
3. Set **Preferred Currency** for payment
4. Options:
   - Company currency (you pay in your currency)
   - Vendor's currency (you pay in their local currency)
   - Currency of invoice (pay in whatever currency bill is in)

5. Click **Save**

When you create a bill from this vendor, the bill defaults to their preferred currency.

## Payment Currency Selection

### Choosing Payment Currency

When executing a payment:

1. Open the bill/payment
2. Find **Currency** field
3. Options:
   - **Bill Currency**: Pay in currency of the invoice (most common)
   - **Company Currency**: Convert to your functional currency
   - **Other Currency**: Convert to a third currency (rare)

4. Light calculates payment amount based on selection
5. Shows FX rate used
6. Click **Record**

## Foreign Exchange Rates

### Automatic FX Rates

Light automatically retrieves current FX rates from market data providers:

1. When you select payment currency, Light fetches current mid-market rate
2. Rate is shown: "1 EUR = 1.08 USD" (example)
3. Payment amount is calculated using this rate
4. Automatically sources to your configured rate provider (e.g., ECB, Fed, etc.)

Rates are updated throughout the day as markets open.

### Overriding FX Rates

Use a specific rate instead of market rate:

1. When creating payment, find **FX Rate**
2. Click **Override Rate**
3. Enter the **rate** you want to use
4. Select the **source** (e.g., "Customer Quote", "Internal Policy", "Spot Rate from Vendor")
5. Light recalculates payment amount using your rate
6. Click **Apply**

Override rates when:
- Vendor negotiated a specific rate
- You have a forward contract at a fixed rate
- You want to honor a rate you quoted to customer
- Company policy mandates a specific rate

### Rate Locks and Forward Contracts

For budgeting certainty, use forward contracts:

1. Work with your bank or FX provider to lock a rate
2. When recording payment, select the **forward contract rate**
3. Light records the locked rate for accounting
4. Settlement proceeds at locked rate regardless of market movement

Document the contract details for audit.

## Currency Conversion Process

### How Payments are Converted

When paying a bill in a different currency:

1. **Original Transaction**: Bill created in EUR for 1,000 EUR
2. **FX Rate**: 1 EUR = 1.08 USD (example)
3. **Payment Amount**: 1,000 EUR × 1.08 = 1,080 USD
4. **Bank Processing**: Your bank executes 1,080 USD payment
5. **GL Entry**: Records both original amount (1,000 EUR) and payment (1,080 USD)

If actual received/paid amount differs from calculated (due to bank fees, rate changes at settlement):
- Light records actual amount paid
- Calculates realized gain/loss
- Posts to FX gain/loss GL account

## Multi-Currency Payment Instructions

### Payment Details with Currency Conversion

When vendors require payment in their currency:

1. Open the bill (e.g., in EUR)
2. Click **Create Payment**
3. Select **Payment Currency**: EUR
4. Light displays payment in EUR
5. Your bank converts from USD to EUR at their rate
6. Vendor receives EUR amount

Ensure vendor's banking details are set for international transfer (IBAN, BIC, etc.).

### Payment in Your Currency

If you prefer to always pay in your currency:

1. Select **Payment Currency**: USD (your functional currency)
2. Light converts bill amount from EUR to USD
3. Vendor's bank receives USD
4. Vendor's bank converts to EUR (vendor bears risk)

Use only if vendor has USD account or accepts USD.

## Batch Payments in Multiple Currencies

### Processing Mixed-Currency Batches

When paying multiple vendors in different currencies:

1. Create payment batch with bills in EUR, GBP, JPY, etc.
2. Light calculates payment for each in its currency:
   - Bill 1: 1,000 EUR = 1,080 USD (at 1.08 rate)
   - Bill 2: 500 GBP = 630 USD (at 1.26 rate)
   - Bill 3: 100,000 JPY = 680 USD (at 147 rate)

3. **Total payment**: 2,390 USD (sum of conversions)
4. Approvers see both original and converted amounts
5. Execute as single batch or by currency

### Currency Consolidation

To simplify payment execution, consolidate by currency:

1. Navigate to **Payments**
2. Click **Group by Currency**
3. Light shows total payment due in each currency
4. Execute EUR payments separately, GBP separately, etc.

Reduces complexity and leverages bulk rates from banks.

## FX Gains and Losses

### Realized Gains/Losses

When payment is made at different rate than invoice:

**Example:**
- Bill created: 1,000 EUR at 1.08 rate = 1,080 USD (recorded)
- Payment made: 1,000 EUR at 1.06 rate = 1,060 USD (actual)
- Realized gain: 20 USD

Light automatically:
1. Records actual payment of 1,060 USD
2. Calculates difference (1,080 recorded - 1,060 paid = 20 gain)
3. Posts 20 USD to FX Gain GL account
4. Mark bill as CLEARED

### Unrealized Gains/Losses

For bills not yet paid in foreign currency:

1. Navigate to **Reports** > **FX Exposure**
2. View open bills in foreign currencies
3. Light calculates unrealized gain/loss based on current rates
4. If currencies have moved against you:
   - Originally owed 1,000 EUR @ 1.08 = 1,080 USD
   - Now worth 1,000 EUR @ 1.10 = 1,100 USD
   - Unrealized loss: 20 USD

5. At period end, adjust GL for unrealized FX to comply with accounting standards

Light can automatically create adjusting entries for unrealized gains/losses.

## Managing FX Risk

### Hedging Strategies

For large foreign currency exposure:

1. Work with treasury/risk management
2. Options include:
   - **Forward Contracts**: Lock exchange rate for future payment
   - **Currency Options**: Limit downside while keeping upside
   - **Netting**: Offset payables and receivables in same currency
   - **Natural Hedges**: Match currency of receipts to payments

3. Document hedge relationships for accounting purposes
4. Light can track both hedged and actual payments for effectiveness testing

### FX Rate Forecasting

Prepare for currency movements:

1. Navigate to **Reports** > **FX Forecast**
2. View projected cash flows by currency
3. Set **rate scenarios** (e.g., 5% appreciation/depreciation)
4. See impact on cash needs and P&L
5. Use for treasury planning and risk assessment

## Related Articles

- [Scheduling and executing payments](/articles/07-accounts-payable/7-7-scheduling-payments.md)
- [Adding and managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md)
- [Multi-entity AP operations](/articles/07-accounts-payable/7-12-multi-entity-ap.md)
