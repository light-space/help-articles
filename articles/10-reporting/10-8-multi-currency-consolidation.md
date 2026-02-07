# Multi-Currency Consolidation

When your organization operates in multiple currencies through subsidiary companies in different countries, consolidating requires translating foreign subsidiary results to the group's reporting currency. Light automates foreign currency translation following IFRS and GAAP standards.

[Open in Light →](https://app.light.inc/ledger-reports)

## Multi-currency consolidation overview

Consolidation of foreign subsidiaries involves:

1. **Translate subsidiary P&L accounts**: Revenue, expense, COGS → average period exchange rates
2. **Translate subsidiary balance sheet accounts**: Assets, liabilities → period-end exchange rates
3. **Translate subsidiary equity**: Opening balance at historical rates, add translated profit, deduct dividends
4. **Record translation differences**: Differences from rate changes → other comprehensive income (OCI)
5. **Eliminate inter-company transactions**: As with single-currency consolidation
6. **Combine results**: Sum translated figures with parent company

The result is consolidated statements in the group's reporting currency with separate disclosure of translation gains/losses.

> Good to know: Translation differences are not recognized in profit/loss (they're in OCI) because they're not realized cash impacts.

## Functional vs. presentation currency

Light distinguishes between two currencies for each entity:

**Functional currency**: The currency in which the entity operates day-to-day.
- UK subsidiary: GBP
- German subsidiary: EUR
- US subsidiary: USD

Financial statements are first prepared in functional currency.

**Presentation currency**: The currency in which consolidated statements are presented (group currency).
- Multinational group: Often USD or EUR

If functional and presentation currencies differ, translation is required.

## Translation methods

Light supports two translation methods:

**Current-noncurrent method**:
- Current assets and liabilities: Period-end rate
- Non-current assets and liabilities: Historical rate
- Equity: Historical rates
- P&L: Average rates
- Translation differences to retained earnings

Less common under IFRS, but required in some jurisdictions.

**Temporal method** (most common under IFRS):
- Assets/liabilities recorded at fair value: Period-end rate
- Assets/liabilities at historical cost: Historical rate
- Equity: Historical rates
- P&L: Average rates
- Translation differences to other comprehensive income

Light defaults to temporal method, which is IFRS-compliant.

## Choosing exchange rates

**Average rate** (for P&L): Calculate average exchange rate for the entire period.

- Sum daily rates for the month
- Divide by number of days
- Apply to revenue, expense, COGS accounts

Light can use:
- Monthly average
- Quarterly average
- Annual average

**Period-end rate** (for balance sheet): Spot exchange rate on the last day of the period.

Configure your rate source in consolidation settings.

> Tip: Some companies use a published rate (e.g., ECB average) for consistency and auditability. Others use their internal rates.

## Recording translation differences

When exchange rates change, translation differences arise. Example:

Foreign subsidiary starts year with EUR 100,000 equity when 1 EUR = 1.20 USD (USD 120,000 equivalent).

At year-end, 1 EUR = 1.15 USD, so EUR 100,000 = USD 115,000 equivalent.

Translation loss of USD 5,000 records as:

Dr. Other Comprehensive Income USD 5,000
Cr. Consolidated Equity USD 5,000

Light calculates and records translation differences automatically in consolidation.

## Multi-entity, multi-currency consolidation

For complex structures (e.g., US parent with UK and German subsidiaries):

1. Each subsidiary has functional currency and local P&L/balance sheet
2. Light translates each to group currency (USD)
3. Light then consolidates all translated results
4. Eliminates inter-company transactions between entities
5. Result: USD consolidated statements

Light manages this multi-step process automatically.

## Inter-company transactions in multi-currency

When entities transact in different currencies, consolidation must eliminate properly:

Example: UK subsidiary (GBP) sells to German subsidiary (EUR).

1. UK entity: Record sale in GBP (e.g., GBP 100,000)
2. German entity: Record purchase in EUR (translate to EUR using transaction-date rate)
3. In consolidation:
   - Translate UK sale to USD using average rate
   - Translate German purchase to USD using average rate
   - Eliminate the corresponding amounts

Light links inter-company transactions across currencies and eliminates them correctly.

## FX gains and losses on inter-company balances

After consolidation, inter-company balances are eliminated. However, during the period, FX movements on inter-company payables/receivables create gains or losses.

Example: German subsidiary owes GBP 100,000 to UK parent. At invoicing (1 GBP = 1.20 EUR), payable is EUR 120,000. At period-end (1 GBP = 1.22 EUR), payable is EUR 122,000. FX loss of EUR 2,000.

In consolidation:
- The inter-company balance is eliminated (no balance sheet impact)
- The FX gain/loss within the group is also eliminated (no P&L impact)
- Only FX impacts on external transactions remain

Light handles this elimination automatically.

## Dividend translations

Subsidiaries pay dividends to parents in foreign currency. On consolidation:

1. Dividend payment translates at payment-date rate
2. Record in consolidated cash flow
3. Reduces subsidiary retained earnings

If dividend is declared before payment and rates change, record dividend at declaration rate, recognize FX gain/loss on settlement.

## Consolidation date and fiscal year differences

Foreign subsidiaries may have different fiscal year-ends. To consolidate:

1. Translate subsidiary statements as of the group consolidation date
2. If subsidiary's fiscal year differs, prepare interim statements at group date
3. Record adjustments for inter-company transactions between subsidiary fiscal year-end and group date

Light helps coordinate this timing.

## Translated P&L analysis

After consolidation, P&L appears in group currency. Analysis considers translation impacts:

**Reported revenue growth** = Organic growth + FX impact

Example: German subsidiary's EUR revenue grew 10%, but EUR weakened against USD by 5%, so reported USD growth is 5%.

Light separately tracks:
- Organic growth (growth in functional currency)
- FX impact (effect of rate changes)

This helps management understand true operational performance vs. currency effects.

## Multi-currency balance sheet analysis

Compare balance sheet items across currencies:

**Total assets**: Sum of:
- Parent assets (in group currency)
- German subsidiary assets (translated to group currency)
- UK subsidiary assets (translated to group currency)

Changes reflect:
- Operational changes (profit, capital expenditure)
- FX translation differences
- Consolidation eliminations

Separately reporting translation differences clarifies the real impacts.

## Hedging of net investments

Companies sometimes hedge foreign subsidiary investments to offset translation losses.

Example: USD parent invests in EUR subsidiary. EUR weakens relative to USD. Translation loss occurs. Parent enters EUR debt (which gains when EUR weakens) to offset translation loss.

Light tracks:
- Foreign investment net asset
- Hedging instrument position
- Translation gain/loss on investment
- Effective hedge relationship

This supports comprehensive reporting of hedge impacts.

## Disclosure of translation impacts

Consolidated financial statements should disclose FX translation effects:

1. **Translation differences in OCI**: Total FX translation gains/losses for the period
2. **Cumulative translation differences**: Accumulated translation gains/losses
3. **By subsidiary**: If material, disclose by significant foreign subsidiary
4. **Related hedges**: If you hedge foreign investments, disclose hedge relationships

Light maintains detailed translation schedules supporting these disclosures.

## Deferred tax on translation differences

Under IFRS, deferred tax on translation differences is generally not recognized (they're non-taxable). However, some jurisdictions require tax on translation differences.

Configure deferred tax treatment for translation:

1. Navigate to **Settings (gear icon)** and configure deferred tax
2. Specify treatment of translation differences
3. Light applies the correct approach per jurisdiction

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Multi-entity consolidation](10-7-multi-entity-consolidation.md)
- [Multi-currency revenue recognition](../09-revenue-compliance/9-4-multi-currency-revenue.md)
- [Balance sheet](10-2-balance-sheet.md)
