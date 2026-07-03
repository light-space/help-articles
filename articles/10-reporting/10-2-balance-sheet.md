# Balance Sheet

The balance sheet is a financial statement showing your company's assets, liabilities, and equity at a specific point in time. It reflects the accounting equation: Assets = Liabilities + Equity. The balance sheet provides a snapshot of your financial position and is essential for credit analysis, investor evaluation, and regulatory compliance.

[Open in Light →](https://app.light.inc/ledger-reports)

## Balance sheet structure

The balance sheet organizes accounts into three sections:

**Assets** (what you own):
- Current assets: Cash, accounts receivable, inventory, prepaid expenses (recoverable within 12 months)
- Non-current assets: Fixed assets, intangible assets, long-term investments (held beyond 12 months)

**Liabilities** (what you owe):
- Current liabilities: Accounts payable, short-term debt, accrued expenses (due within 12 months)
- Non-current liabilities: Long-term debt, deferred tax liabilities, pension obligations (due beyond 12 months)

**Equity** (owners' stake):
- Share capital: Amount invested by shareholders
- Retained earnings: Accumulated profits not distributed as dividends
- Other comprehensive income: Unrealized gains/losses on certain items

The balance sheet always balances: Total Assets = Total Liabilities + Total Equity.

> Good to know: The balance sheet is also called the statement of financial position or statement of financial condition.

## Accessing the balance sheet in Light

Generate your balance sheet:

1. Navigate to **Planning & Reports → Reports**
2. Select the as-of date (the balance sheet is a snapshot report showing balances as of that date)
3. Select entities to include (single entity or consolidated)
4. Select currency (**Entity Crcy** or **Group Crcy**)
5. Click **Generate**

Light displays the balance sheet formatted by asset, liability, and equity classifications.

## Interpreting balance sheet accounts

**Cash and equivalents**: Available funds in bank accounts and highly liquid investments. Essential for operations and obligations.

**Accounts receivable**: Money owed by customers. Shown net of allowance for doubtful accounts.

**Inventory**: Goods held for sale or raw materials. Valued at cost or market value, whichever is lower.

**Prepaid expenses**: Payments made for future benefits (insurance, rent). Assets because you'll benefit from them.

**Fixed assets**: Buildings, equipment, vehicles, and land. Shown net of accumulated depreciation.

**Intangible assets**: Patents, trademarks, goodwill. Valuable but non-physical assets.

**Accounts payable**: Money owed to suppliers. Obligations that reduce net assets.

**Accrued expenses**: Expenses incurred but not yet paid (utilities, salaries). Recorded to match expenses to revenue.

**Deferred revenue**: Customer payments received but services not yet delivered. Liability because you owe performance.

**Long-term debt**: Loans and bonds due beyond 12 months. Shown with interest rate and maturity date.

**Retained earnings**: Cumulative profits retained in the business. Increases with profit, decreases with losses and dividends.

## Balance sheet analysis

Key metrics derived from the balance sheet:

**Current ratio** = Current Assets ÷ Current Liabilities

Shows ability to pay short-term obligations. A ratio > 1 indicates you have more current assets than current liabilities.

**Quick ratio** = (Current Assets - Inventory) ÷ Current Liabilities

A more conservative measure excluding inventory, which is less liquid.

**Debt-to-equity ratio** = Total Liabilities ÷ Total Equity

Indicates the proportion of debt versus equity financing. High ratios indicate more leverage and financial risk.

**Return on assets (ROA)** = Net Income ÷ Average Total Assets

Measures how efficiently you use assets to generate profit.

In custom table reports, you can add ratio lines using the **PERCENT** formula, which divides one set of report lines by another. See [Custom reports and filters](10-9-custom-reports.md).

## Multi-period balance sheet analysis

Compare balance sheet to prior periods:

1. Navigate to **Planning & Reports → Reports**
2. Use the **Comparison** filter to add a prior period (1, 3, 6, 9, or 12 months back) or a prior year (1, 2, or 3 years back)
3. Light displays the periods side-by-side
4. Click any account to drill into transactions

This helps identify significant balance sheet movements requiring investigation.

## Multi-entity balance sheets

For organizations with multiple entities:

- Generate entity-level balance sheets for each subsidiary or division
- Generate consolidated balance sheet combining all entities
- View inter-company balances (eliminated in consolidated reporting)
- Analyze balance sheet by entity type or geographic region

Light automatically eliminates inter-company transactions in consolidated reporting.

## Multi-currency balance sheets

Report your balance sheet in different currencies:

1. Navigate to **Planning & Reports → Reports**
2. Select **Currency**: **Entity Crcy** (local) or **Group Crcy** (group)
3. Light displays amounts in your selected currency

For multinational companies with subsidiaries in different currencies:
- Select **Entity Crcy** to view an entity's balance sheet in its own functional currency — this option is not available when the selected entities have different local currencies
- Select **Group Crcy** to translate all entities to the group currency, as required for consolidation
- Group-currency amounts are recorded on each ledger line when it is posted, so translated balances build up from transaction-date rates (adjusted by any FX revaluations you run)

## Fixed asset detail

The balance sheet's fixed asset section summarizes accumulated depreciation. To see the **fixed asset register** — the per-asset detail behind those balances:

1. Navigate to [**Accounting → Releases**](https://app.light.inc/releases)
2. Filter by **Fixed asset** type to view only fixed assets
3. Each row shows cost, accumulated depreciation, and remaining book value
4. Open a row to see the depreciation schedule, method, and remaining useful life

Fixed assets are created by applying a **Fixed Asset** release template to a journal entry, bill, or sales invoice line — see [Configuring releases](../09-revenue-compliance/9-2-configuring-releases.md). This supports asset management and planning for replacements.

## Deferred tax balances

If your company recognizes deferred taxes:

1. Calculate deferred tax assets (future tax benefits from deductions)
2. Calculate deferred tax liabilities (future tax payments)
3. Show the net deferred tax position on the balance sheet
4. Maintain detailed schedules of timing differences

Configure deferred tax accounts in your chart of accounts and post deferred tax adjustments as journal entries.

## Off-balance-sheet items

Some obligations don't appear on the balance sheet but require disclosure:

- Operating leases (before adopting IFRS 16/ASC 842 which brought them on-balance-sheet)
- Contingent liabilities (possible but not probable)
- Commitments (contractual obligations)

Document these in balance sheet footnotes and supplementary schedules.

## Balance sheet footnotes

Comprehensive balance sheet reporting includes footnotes:

1. Accounting policies: Valuation methods and depreciation policies
2. Significant estimates: Judgments in calculating allowances and reserves
3. Contingencies: Potential liabilities or assets
4. Subsequent events: Items occurring after balance sheet date
5. Commitments: Contractual obligations

Prepare footnotes outside Light as part of your financial statement package, using exported report data to support the underlying schedules.

## Quarterly vs. annual balance sheets

Generate balance sheets at any frequency:

**Monthly**: For management analysis and trend identification.

**Quarterly**: For investor reporting and SEC compliance (if public company).

**Annual**: For audited financial statements and regulatory filings.

Light maintains all historical balances, enabling easy generation at any frequency.

> Tip: Always report balance sheets as of month-end or quarter-end dates. Mid-month balance sheets are not reliable due to incomplete transaction processing.

## Exporting balance sheet data

Export balance sheet for external distribution or analysis:

1. Generate the balance sheet report
2. Click the export button
3. Light downloads a CSV file containing all rows and columns as displayed

You can open the CSV in Excel or Google Sheets for further formatting and distribution. Drilldown transaction lines can also be exported as CSV.

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Profit and loss](10-3-profit-loss.md)
- [Cash flow statement](10-4-cash-flow.md)
- [Trial balance](10-5-trial-balance.md)
- [Custom reports and filters](10-9-custom-reports.md)
