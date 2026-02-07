# Multi-Currency Revenue Recognition

Multinational companies must handle revenue recognition across different currencies and tax regimes. Light provides comprehensive multi-currency support, automatically managing exchange rate fluctuations while recognizing revenue according to your accounting policies.

[Open in Light →](https://app.light.inc/journal-entries)

## Multi-currency framework

Light operates with three currency perspectives:

**Transaction currency**: The currency of the original business transaction. If you invoice a customer in EUR, that's your transaction currency.

**Local currency**: The functional currency of the legal entity. A UK subsidiary operates in GBP, a German subsidiary in EUR.

**Group currency**: The consolidation currency for your entire organization (often USD or EUR for multinational groups).

When you create a revenue transaction, Light automatically calculates and stores amounts in all three currencies, applying appropriate exchange rates at the transaction date (the valuation date).

## Revenue recognition with FX rates

When revenue is recognized under a release template, each periodic release uses the FX rate from the original transaction date. This preserves the economically-agreed revenue amount while converting correctly for local and group reporting.

Example: You invoice a US customer for USD 12,000 on January 1 with a 12-month deferred revenue release (GBP entity, group USD):

- Transaction currency: USD 12,000
- Local (GBP) amount on Jan 1: GBP 9,500 at 1.2632 rate
- Group (USD) amount: USD 12,000

Each month, Light releases USD 1,000 and GBP 791.67, maintaining the original exchange rate throughout the 12 months. This prevents distortions from changing FX rates between months.

> Good to know: Light uses the valuation date (typically transaction date) for initial rate determination, then applies that rate consistently across all release periods.

## Override FX rates

You can override the default FX rate on any transaction if your company uses a different methodology:

1. Create an AP, AR, or JE document
2. Click the **FX Rates** section
3. Toggle **Override Local Currency Rate** or **Override Group Currency Rate**
4. Enter your preferred rate
5. Light recalculates all amounts using your custom rate

This is useful when your company locks rates internally (e.g., monthly average rates) rather than using spot rates.

## Revenue recognition on transactions with rate changes

For long-duration recognition periods, you may experience significant FX volatility. Light preserves the original FX rate locked at transaction inception, ensuring:

- Revenue amounts remain economically consistent
- Variance analysis can isolate FX impacts from operational changes
- Multi-month releases don't create artificial timing mismatches

If you need to adjust revenue for subsequent FX movements, create a separate FX revaluation (FX) document rather than modifying the original revenue release.

## Handling FX revaluations

An FX revaluation document (FX type) records unrealized gains or losses from currency fluctuations. When held-to-maturity revenue or payables experience FX changes, FX documents systematically adjust reporting values.

To create an FX revaluation:

1. Navigate to **Accounting > Transactions** and create a new document
2. Select document type **FX**
3. Enter the transaction currency and amounts
4. Select the revaluation type: **Monetary Assets** or **Monetary Liabilities**
5. Specify the affected accounts and amounts
6. Light automatically creates offsetting entries to P&L (unrealized gains/losses)

## Multi-entity consolidation with deferred revenue

When deferred revenue spans multiple legal entities, each entity records its portion in its local currency. During consolidation:

- Intercompany eliminations remove entries between entities
- FX translation differences appear in other comprehensive income (OCI)
- Deferred revenue remains correctly stated in both local and group currencies

Light automatically handles these consolidation mechanics, ensuring your consolidated P&L and balance sheet correctly present multinational deferred revenue.

## Currency translation differences

Month-to-month FX fluctuations can create translation differences (especially for balance sheet items like deferred revenue). Light segregates:

- **Realized FX gains/losses**: From actual transactions settled at different rates
- **Unrealized FX gains/losses**: From balance sheet remeasurement at period-end rates
- **Translation differences**: From consolidating foreign subsidiaries at current rates

This segregation is essential for IFRS and GAAP compliance, separating economic FX impacts from accounting translation mechanics.

> Tip: Configure separate GL accounts for realized and unrealized FX movements to simplify variance analysis and reporting.

## Reporting multi-currency deferred revenue

Your balance sheet reports deferred revenue in local and group currencies. Light's reporting engine:

- Shows deferred revenue liability in each entity's functional currency
- Translates balances to group currency at period-end rates
- Separately identifies FX translation impacts
- Supports detailed trial balance reporting by currency

Revenue recognition on the P&L appears in transaction currency initially, then translates to local and group perspective.

## Best practices for multinational revenue recognition

**Lock rates consistently**: Decide whether to use spot rates, monthly average rates, or forward rates, then apply consistently across all entities.

**Separate FX movements**: Use FX documents to record unrealized gains/losses rather than adjusting revenue recognition, maintaining audit trail clarity.

**Document rate source**: Maintain a schedule of which rates were used for which transactions to support audit procedures.

**Test translations**: Run trial balances in each currency periodically to validate that translation differences are within expected ranges.

## Related articles

- [Revenue recognition rules overview](9-1-revenue-recognition-overview.md)
- [Accruals, prepayments, deferred revenue, and depreciation](9-3-accruals-prepayments.md)
- [Multi-entity consolidation](../10-reporting/10-7-multi-entity-consolidation.md)
- [Multi-currency consolidation](../10-reporting/10-8-multi-currency-consolidation.md)
