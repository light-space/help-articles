# Multi-Currency Reconciliation

Reconciling bank accounts and transactions in multiple currencies adds complexity but Light handles most of it automatically. This article explains how multi-currency reconciliation works.

[Open in Light →](https://app.light.inc/bank-reconciliation)

## Multi-Currency Account Setup

A bank account operates in a single currency (the account's base currency):

- **USD account** - All transactions are in USD
- **EUR account** - All transactions are in EUR

However, you can receive deposits or make payments in other currencies, which the bank converts to the base currency.

When setting up a bank account in Light, you specify its currency (USD, EUR, GBP, etc.). Bank providers only deliver transactions in the account's currency, so every imported bank transaction amount is already in the account currency. Any FX gain or loss is calculated automatically when the matched documents are cleared.

## Imported Transaction Data

Every imported bank transaction has a single amount in the bank account's currency. For cross-currency payments, Light's AI additionally parses metadata from the transaction reference (or provider metadata), including:

**Original Amount** - Transaction amount in the currency the payer used (e.g., 100 GBP)

**Original Currency** - The currency of the original amount (GBP)

**Fees** - Any bank fees mentioned in the reference

**Date** - Transaction date used for FX rate determination

Light uses this parsed metadata to match GL entries in other currencies. Banks do not provide a conversion rate field; conversion rates come from Light's FX rate sources (see below).

## Matching Multi-Currency Transactions

When matching a bank transaction to a GL entry in a different currency:

1. Bank transaction: 120 USD on a USD account (originally a 100 EUR payment)
2. GL entry: Created for a 100 EUR invoice
3. Light uses the AI-parsed original amount (100 EUR) to find the matching invoice
4. As a sanity check on the parsed data, Light converts the original amount to the account currency and requires it to be within 10% of the bank transaction amount
5. Any remaining difference between the GL amount and the bank amount is handled as FX gain/loss when the match is cleared

If the parsed original amount fails the 10% sanity check, the transaction is not auto-matched and is left for manual review.

## FX Adjustments

When the exchange rate changes between transaction date and posting date, FX gain/loss occurs:

**Scenario:**
- Invoice created on Jan 1: 100 GBP at rate 1.20 = 120 USD posted to GL
- Payment received on Jan 15: 100 GBP at rate 1.25 = 125 USD received

**FX Gain/Loss:**
- Expected: 120 USD
- Actually received: 125 USD
- FX Gain: 5 USD (you gained money due to GBP appreciation)

Light automatically calculates and posts the FX adjustment when the match is cleared:

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

When reconciling, Light matches using the amount in the bank account's currency.

## FX Rate Sources

Light uses exchange rates from:

**ECB (European Central Bank)** - For EUR and many other currencies

**Daily Published Rates** - Updated daily, automatically fetched

**Manual Override** - You can define custom monthly rates at the company or entity level; entity-level rates take precedence over company-level rates, which take precedence over system rates

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
3. If rates changed, the difference is posted automatically as FX gain/loss during clearing

> Good to know: Some banks show provisional FX rates for pending transactions. Always wait for the transaction to finalize before reconciling.

## Reconciliation Accuracy

Light does not have a configurable matching tolerance. When you reconcile a bank transaction against documents with a different amount, you choose a deviation reason for the difference:

- **FX differences** are calculated automatically during clearing and posted to the FX gain/loss accounts
- Selecting **Bank fees** as the deviation reason automatically creates a journal entry for the fee amount

## Group vs. Local Currency Reconciliation

For consolidated companies:

**Local Reconciliation** - Entities reconcile to local GL in their base currency

**Group Reconciliation** - Corporate office reconciles consolidated GL in group currency

Light handles both:
- Local entities match local currency amounts
- Group GL shows converted group currency amounts
- FX differences roll up to group level

## Automation Rules and Original Amounts

Automation rules can use the AI-parsed original amount of a transaction:

1. Go to **Accounting → Bank reconciliation → Automation rules**
2. Create a rule with conditions on bank transaction fields: account, date, amount, original amount, reference, or fees
3. Choose the action to apply (for example, match with a journal entry)

Rule conditions do not include the original currency or an FX tolerance — FX differences are handled automatically during clearing rather than through rule tolerances.

## Common Multi-Currency Scenarios

**Scenario 1: Foreign Customer Payment**
- Customer in UK sends 10,000 GBP
- You created invoice for 10,000 GBP
- Bank receives at rate 1.25 = 12,500 USD
- GL entry for 10,000 GBP × 1.20 = 12,000 USD
- Difference: 500 USD FX gain (GBP appreciated)
- Light posts the 500 USD FX gain automatically during clearing

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
