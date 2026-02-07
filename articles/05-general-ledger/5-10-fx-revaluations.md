# FX Revaluations

Foreign exchange (FX) revaluation adjusts GL accounts for currency fluctuations. This article explains how to set up and use FX revaluation entries.

[Open in Light →](https://app.light.inc/journal-entries)


## Understanding FX Revaluation

FX revaluation addresses the mismatch between transaction date and settlement date:

**Scenario:**
- Invoice AR customer for 100,000 EUR on January 1 at rate 1.20 USD/EUR = 120,000 USD
- Post to GL as 120,000 USD receivable
- By January 15 (when customer pays), rate is 1.18 USD/EUR
- Customer sends 100,000 EUR = 118,000 USD (at new rate)
- Gain/loss: 120,000 - 118,000 = 2,000 USD gain

FX revaluation entries record this gain/loss and adjust GL balances.

## Which Accounts Revalue?

Revaluation applies to accounts that:

- **Hold foreign currency** - Cash in EUR, GBP, JPY, etc.
- **Are unsettled** - Not yet matched to offsetting transaction
- **Are temporary** - Will be settled in the future

**Accounts that revalue:**
- Accounts Receivable (in foreign currency)
- Accounts Payable (in foreign currency)
- Cash in foreign currency
- Intercompany payables/receivables
- Forward contracts

**Accounts that don't revalue:**
- Fixed assets (typically valued at historical rate)
- Long-term debt (under hedge accounting, may be valued at spot)

## Setting Up Revaluation

To set up automatic FX revaluation:

1. Go to **General Ledger > FX Revaluation**
2. Click **Create Revaluation Rule**
3. Configure:
   - **Accounts to revalue** - Which GL accounts
   - **Revaluation method** - Temporal, current, or custom
   - **Rate source** - ECB, Reuters, custom
   - **Frequency** - Monthly, quarterly, annually
   - **Valuation date** - When to measure FX impact
4. Click **Save**

The rule will now generate revaluation entries automatically.

## Revaluation Methods

**Temporal Method** - Different rates for different accounts
- Current assets/liabilities: Spot rate at valuation date
- Fixed assets: Historical rate at acquisition
- Most common for US GAAP

**Current Method** - All accounts at spot rate
- All assets and liabilities at current exchange rate
- Used under IAS (IFRS)
- Common for foreign subsidiaries

**Custom Method** - You define the rate for each account
- Most control but most complex
- Used for hedge accounting or regulatory requirements

## Revaluation Process

When automatic revaluation runs:

1. **Identify accounts to revalue**
2. **Get current FX rates** - From ECB or other source
3. **Calculate revaluation**:
   - For each account, calculate what balance would be at current rate
   - Compare to carrying amount in GL
   - Difference = unrealized gain or loss
4. **Create GL entries**:
   - Debit/Credit: Asset or Liability account (to adjust to current value)
   - Debit/Credit: FX Gain/Loss account
5. **Post entries** - New balances reflect current rates

## FX Gain and Loss Accounts

Track unrealized and realized FX impacts:

**Unrealized FX Gain/Loss**
- Post when revaluation happens
- Flows through P&L
- Can be deferred to Other Comprehensive Income (OCI) under some rules

**Realized FX Gain/Loss**
- Post when foreign currency transaction settles
- Final, actual gain/loss

**Deferred FX (OCI)**
- Unrealized gains/losses that don't hit P&L (under certain rules)
- Flows to equity until realized
- More complex accounting

Light can post to either P&L or OCI accounts depending on your setup.

## Manual Revaluation

If you prefer to control revaluation manually:

1. Go to **General Ledger > FX Revaluation**
2. Click **Run Revaluation**
3. Select:
   - **Valuation date** (typically period-end)
   - **Accounts to revalue**
   - **Revaluation method**
   - **Exchange rates** (or use current rates)
4. System shows:
   - Current GL balances
   - Proposed balances at new rates
   - Unrealized gain/loss
5. Review and click **Post Entries**

Manual revaluation gives you chance to review before posting.

## Multi-Currency Accounts Receivable

For AR with mixed currencies:

1. **Account: AR in USD** - Settled, no revaluation
2. **Account: AR in EUR** - Unsettled, revaluate
3. **Account: AR in GBP** - Unsettled, revaluate

Each currency sub-ledger revalues independently using its rate.

## Net vs. Gross Revaluation

**Gross revaluation:**
- Revalue every transaction individually
- Every invoice that isn't settled gets adjusted
- More detailed but produces many GL entries

**Net revaluation:**
- Net out all transactions by currency
- One entry per currency per account
- Cleaner GL but less detail

Most companies use net revaluation for cleaner books.

## Revaluation at Period-End

Typically revalue on the last day of the month/quarter/year:

1. All other transactions for the period are posted
2. At period-end (before close), run revaluation
3. Unsettled foreign currency items revalue to current rates
4. FX gains/losses post to P&L
5. Period is closed with final balances

Revaluation BEFORE period close so it's included in period results.

## Settlement and Realized Gains/Loss

When a revalued item settles:

**Example:**
- AR revalued: Owed 100,000 EUR, revalued to 118,000 USD
- Customer pays: Sends 100,000 EUR, bank converts at 1.19 = 119,000 USD
- Receive in bank: 119,000 USD
- Record payment: Debit Cash 119,000, Credit AR 119,000
- Result: Realized loss of 1,000 USD (119,000 actual vs. 120,000 expected)

Total P&L impact = unrealized loss of 2,000 (from revaluation) + realized loss of 1,000 (from settlement) = total 3,000 loss.

## Hedging Strategies

For companies with large FX exposure, consider hedging:

**Forward Contracts:**
- Lock in rate for future transaction
- Hedge accounting can defer gains/losses

**Options:**
- Right but not obligation to exchange at set rate
- Limits downside but costs premium

**Natural Hedges:**
- AR in EUR, AP in EUR (offset each other)
- No need to hedge if matched

For hedged items, revaluation may be handled differently—consult your accountant.

## CTA (Cumulative Translation Adjustment)

For consolidation of foreign subsidiaries:

- When translating subsidiary GL from local to group currency, FX differences arise
- These are posted to CTA (Cumulative Translation Adjustment) account
- CTA is part of equity
- When subsidiary is sold, CTA is realized and flows to P&L

Light can track CTA separately if you have foreign subsidiaries.

## Regulatory Considerations

**US GAAP (ASC 830):**
- Temporal method required for most translations
- Unrealized gains/losses flow to P&L

**IFRS (IAS 21):**
- Current method typically used
- Unrealized gains/losses flow to OCI (not P&L)
- Different treatment can significantly impact earnings

**Tax considerations:**
- Some jurisdictions tax only realized FX gains/losses
- Unrealized losses may not be deductible
- Consult tax advisor on revaluation treatment

## Reporting FX Impact

Include FX impact in financial reporting:

1. **Income Statement**
   - Show realized and unrealized FX gains/losses
   - May be combined or separate

2. **Balance Sheet**
   - Show FX-adjusted balances of foreign currency accounts
   - Show CTA in equity section

3. **Notes**
   - Explain FX revaluation policy
   - Show gain/loss detail by currency
   - Discuss hedging strategy

## Best Practices

- **Revalue monthly** - Don't wait until quarter-end; catch changes regularly
- **Document policy** - Be consistent in revaluation method
- **Understand rates** - Know where your FX rates come from
- **Monitor exposure** - Track unhedged FX exposure in foreign currencies
- **Consider hedging** - For large exposures, use hedges
- **Separate realized vs. unrealized** - Track both for analysis
- **Reconcile** - Ensure FX entries reconcile to GL balances
- **Review regularly** - Track FX gains/losses trend over time

## Related Articles

- [Multi-currency reconciliation](/mnt/help-articles/articles/04-bank-reconciliation/4-7-multi-currency-reconciliation.md)
- [Multi-entity ledger management](/mnt/help-articles/articles/05-general-ledger/5-6-multi-entity-ledger.md)
- [Clearing, FX gain/loss, and CTA](/mnt/help-articles/articles/05-general-ledger/5-12-clearing-fx-cta.md)
