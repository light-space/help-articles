# Multi-Currency Reconciliation

Reconciling bank accounts and transactions in multiple currencies adds complexity but Light handles most of it automatically. This article explains how multi-currency reconciliation works.

[Open in Light →](https://app.light.inc/bank-reconciliation)

## Multi-Currency Account Setup

A bank account operates in a single currency (the account's base currency):

- **USD account** - All transactions are in USD
- **EUR account** - All transactions are in EUR

However, you can receive deposits or make payments in other currencies, which the bank converts to the base currency.

When setting up a multi-currency account:

1. Specify the **base currency** (USD, EUR, GBP, etc.)
2. The bank provides conversion rates
3. Light imports both the original and converted amounts
4. FX gain/loss is calculated and posted to GL

## Imported Transaction Data

When importing a multi-currency transaction, Light captures:

**Original Amount** - Transaction amount in the currency used (e.g., 100 GBP)

**Original Currency** - The currency of the original amount (GBP)

**Converted Amount** - Amount converted to account currency by the bank (e.g., 120 USD)

**Conversion Rate** - Rate used by the bank (1.20 USD/GBP)

**Date** - Transaction date used for FX rate determination

Light uses this data to match GL entries and calculate FX differences.

## Matching Multi-Currency Transactions

When matching a bank transaction to a GL entry in different currencies:

1. Bank transaction: 100 EUR (converted to 120 USD by bank)
2. GL entry: Created for 100 EUR invoice
3. Light converts both to USD using daily rates:
   - 100 EUR × today's rate (e.g., 1.18) = 118 USD
4. Comparison: 120 USD (bank) vs. 118 USD (GL) = $2 difference
5. Result: Close match (difference attributable to rate volatility)

The system auto-matches because the amounts are sufficiently close.

## FX Adjustments

When the exchange rate changes between transaction date and posting date, FX gain/loss occurs:

**Scenario:**
- Invoice created on Jan 1: 100 GBP at rate 1.20 = 120 USD posted to GL
- Payment received on Jan 15: 100 GBP at rate 1.25 = 125 USD received

**FX Gain/Loss:**
- Expected: 120 USD
- Actually received: 125 USD
- FX Gain: 5 USD (you gained money due to GBP appreciation)

Light automatically calculates and posts FX adjustments:

1. GL entry for 120 USD (original posting)
2. Bank transaction for 125 USD (actual payment)
3. FX adjustment: 5 USD to FX Gain account
4. Now both sides match at 125 USD

## Posting Multi-Currency Entries

When posting an accounting document in a foreign currency:

1. Enter the amount in the **document currency** (GBP, JPY, etc.)
2. Specify the **posting date** (for FX rate determination)
3. Light converts to:
   - **Local currency** (company entity's currency)
   - **Group currency** (consolidated reporting currency)
4. All three amounts are stored and used in matching/reporting

When reconciling, Light matches using the local currency amount.

## FX Rate Sources

Light uses exchange rates from:

**ECB (European Central Bank)** - For EUR and many other currencies

**Daily Published Rates** - Updated daily, automatically fetched

**Manual Override** - You can override rates for specific dates if needed

Rates are determined by the **posting date** of the transaction. If you change the posting date, the FX rate changes.

## Reconciliation with FX Rate Overrides

You can override FX rates for specific transactions:

1. Open the document
2. Go to **Posting Details > FX Rates**
3. Click **Override** for local or group currency
4. Enter the custom rate
5. Re-post the document

Light recalculates the conversion and all related amounts using your rate.

Use rate overrides for:
- Forward contracts at fixed rates
- Internal transfer pricing
- Special negotiations with trading partners

## Dealing with Pending Transactions

Multi-currency pending transactions can be tricky:

**Problem:** Bank shows amount as "pending" at rate 1.20; you posted GL entry at same rate. Next day rate changes to 1.18 and bank finalizes—now amounts don't match.

**Solution:**
1. Don't reconcile pending transactions until they're finalized
2. Once finalized, the bank shows the actual settled amount
3. If rates changed, create an FX adjustment GL entry to account for the difference

> Good to know: Some banks show provisional FX rates for pending transactions. Always wait for the transaction to finalize before reconciling.

## Reconciliation Accuracy

Due to rounding and rate changes, expect small discrepancies:

- **Acceptable:** Differences under 0.10% of the transaction amount
- **Investigate:** Differences over 1% may indicate errors

For a 100,000 USD transaction:
- Under 100 USD difference: likely acceptable
- Over 1,000 USD difference: investigate

Adjust the tolerance in your automation rules based on your transaction volumes and acceptable thresholds.

## Group vs. Local Currency Reconciliation

For consolidated companies:

**Local Reconciliation** - Entities reconcile to local GL in their base currency

**Group Reconciliation** - Corporate office reconciles consolidated GL in group currency

Light handles both:
- Local entities match local currency amounts
- Group GL shows converted group currency amounts
- FX differences roll up to group level

## Currency-Specific Matching Rules

Create rules for specific currency pairs:

1. Go to **Accounting → Bank reconciliation → Automation Rules**
2. Create rule with condition: "Original Currency = GBP"
3. Set matching criteria for GBP transactions
4. Specify FX tolerance (e.g., allow 1% rate variation)

Example: "GBP to USD transactions, allow 2% difference to account for rate volatility"

## Common Multi-Currency Scenarios

**Scenario 1: Foreign Customer Payment**
- Customer in UK sends 10,000 GBP
- You created invoice for 10,000 GBP
- Bank receives at rate 1.25 = 12,500 USD
- GL entry for 10,000 GBP × 1.20 = 12,000 USD
- Difference: 500 USD FX gain (GBP appreciated)
- Create FX adjustment and reconcile

**Scenario 2: Multi-Currency Vendor Invoice**
- Invoice from supplier in Switzerland: 5,000 CHF
- Paid in USD: 5,500 USD (at rate 1.10)
- GL entry for 5,000 CHF was posted at rate 1.10 = 5,500 USD
- Bank transaction: 5,500 USD
- Perfect match; reconcile directly

**Scenario 3: Hedged Transaction**
- You have forward contract: 100,000 EUR at fixed 1.18 (cost: 118,000 USD)
- Invoice created at spot rate 1.20 = 120,000 USD
- On payment date, pay forward at 1.18 = 118,000 USD
- Create adjustment entry for 2,000 USD gain (hedge benefit)
- Reconcile to bank at 118,000 USD

## Reporting and Analysis

For multi-currency accounts:

1. Go to **Accounting → Bank reconciliation → Reports**
2. View FX impact summary:
   - Gains vs. losses by currency
   - FX impact on reconciliation
   - Volatility by currency pair
3. Export for analysis

Use this to understand your FX exposure and hedge decisions.

## Best Practices

- **Match frequently** - Weekly for volatile currency pairs
- **Monitor rates** - Track rate changes to understand FX impact
- **Use consistent conventions** - Always post in the original currency first
- **Understand your counterparties** - Know which currencies customers/vendors use
- **Calculate reserves** - For pending transactions, estimate FX impact
- **Review FX gains/losses** - Understand and explain FX impact in reports
- **Consider hedging** - For large multi-currency positions, consider hedging strategies

## Related Articles

- [Automated bank reconciliation](/mnt/help-articles/articles/04-bank-reconciliation/4-4-automated-reconciliation.md)
- [FX revaluations](/mnt/help-articles/articles/05-general-ledger/5-10-fx-revaluations.md)
- [Clearing, FX gain/loss, and CTA](/mnt/help-articles/articles/05-general-ledger/5-12-clearing-fx-cta.md)
