# Profit and Loss

The Profit and Loss statement (P&L), also called the Income Statement, measures your company's financial performance over a specific period. It shows revenue earned, expenses incurred, and resulting profit or loss. The P&L is essential for evaluating profitability, identifying cost drivers, and assessing business performance against targets.

[Open in Light →](https://app.light.inc/ledger-reports)

## P&L structure

The P&L organizes accounts into sections:

**Revenue** (sales):
- Product revenue: Sales of goods
- Service revenue: Sales of services
- Subscription revenue: Recurring billing
- Other revenue: Licensing, royalties, etc.

Total revenue shows your top-line financial performance.

**Cost of goods sold (COGS)**: Direct costs to produce goods or deliver services:
- Materials
- Labor
- Manufacturing overhead

**Gross profit** = Revenue - COGS. Shows profitability before operating expenses.

**Operating expenses**: Costs to run the business:
- Sales and marketing
- Research and development
- Administrative and general
- Depreciation

**Operating income** = Gross Profit - Operating Expenses. Shows profit from core business operations.

**Other income/expenses**: Non-operating items:
- Interest income or expense
- Gain/loss on asset sales
- Foreign exchange gains/losses

**Profit before tax** = Operating Income + Other Items.

**Tax expense**: Income taxes owed.

**Net profit** = Profit Before Tax - Tax Expense. Bottom-line profitability.

## Accessing the P&L in Light

Generate your P&L statement:

1. Navigate to **Planning & Reports → Reports**
2. Select the reporting period (start and end dates)
3. Select entities to include (single entity or consolidated)
4. Select currency (**Entity Crcy** or **Group Crcy**)
5. Click **Generate**

Light displays the P&L formatted by revenue, expense, and profit categories.

## Interpreting P&L accounts

**Revenue accounts**: Represent sales of products and services. Show before returns and discounts.

**Discount and returns accounts**: Reduce gross revenue to net revenue (revenue after typical reductions).

**Cost of goods sold**: Direct costs that vary with production or service delivery. Excludes overhead and administrative costs.

**Gross margin** = Gross Profit ÷ Revenue. Percentage of revenue remaining after direct costs. High margins indicate pricing power or efficient operations.

**Operating expenses**: Fixed and variable costs to operate the business. Include all support functions.

**EBITDA** = Earnings Before Interest, Taxes, Depreciation, and Amortization.

A metric showing operating profitability before financing and tax impacts (calculated as Operating Income + Depreciation + Amortization).

**Interest expense**: Cost of borrowed money. Shows on P&L when debt is outstanding.

**Tax expense**: Income taxes owed based on taxable income. Includes current and deferred tax.

> Good to know: Some companies show tax as a percentage (effective tax rate) as well as absolute amount for stakeholder understanding.

## P&L analysis metrics

Key performance indicators derived from the P&L:

**Gross margin %** = Gross Profit ÷ Revenue

Shows profitability on each sale before operating expenses.

**Operating margin %** = Operating Income ÷ Revenue

Shows profitability from core business operations.

**Net margin %** = Net Income ÷ Revenue

Shows bottom-line profitability. Industry-specific benchmarks exist.

**Operating leverage**: How much expenses increase relative to revenue growth.

In custom table reports, you can add ratio lines using the **PERCENT** formula, which divides one set of report lines by another. See [Custom reports and filters](10-9-custom-reports.md).

## Revenue recognition on the P&L

Revenue appears on the P&L in the period it's recognized, which may differ from cash receipt:

- Accrued revenue: Earned but not yet invoiced
- Deferred revenue releases: Invoiced but recognized over future periods
- Sales returns: Reduce revenue in current period

The P&L reflects economic reality (when you earned the revenue) rather than cash timing.

## Expense recognition and matching

Expenses appear on the P&L in the period incurred, which may differ from cash payment:

- Accrued expenses: Incurred but not yet paid
- Depreciation: Systematically allocating asset cost over useful life
- Prepaid expenses: Releasing prepayment as benefit is consumed

This matching principle ensures P&L reflects the cost of earning revenue in each period.

## Multi-period P&L analysis

Compare P&L to prior periods:

1. Navigate to **Planning & Reports → Reports**
2. Use the **Comparison** filter to add a prior period (1, 3, 6, 9, or 12 months back) or a prior year (1, 2, or 3 years back)
3. Light displays revenue, expenses, and profit side-by-side
4. Shows variances and percentage changes
5. Click any line to drill into supporting transactions

This identifies profit drivers and problem areas.

## Multi-entity P&L

For organizations with multiple entities:

- Generate P&L for each subsidiary or division
- Generate consolidated P&L combining all entities
- View inter-company eliminations
- Analyze P&L by entity, geography, or business line

Light automatically eliminates inter-company transactions in consolidated reporting.

## Multi-currency P&L

Report P&L in different currencies:

1. Navigate to **Planning & Reports → Reports**
2. Select **Currency**: **Entity Crcy** (local) or **Group Crcy** (group)
3. Light displays amounts in your selected currency

For multinational companies:
- Select **Entity Crcy** to view an entity's P&L in its own functional currency — this option is not available when the selected entities have different local currencies
- Select **Group Crcy** to translate all entities to the group currency, as required for consolidation
- Group-currency amounts are recorded on each ledger line when it is posted, so translated results build up from transaction-date rates

## Segment reporting

Analyze P&L by business segment:

1. Navigate to **Planning & Reports → Reports**
2. Filter by **Custom properties** — any custom property values configured in your organisation (e.g., department, geography, or product line)
3. Light displays revenue and expenses for the selected segment
4. Identify which segments drive profitability

This supports strategic planning and resource allocation.

## Cost center analysis

Analyze expenses by cost center:

1. Navigate to **Planning & Reports → Reports**
2. View revenue and expenses attributed to each cost center
3. Calculate profitability by department or operational unit
4. Identify cost control opportunities

Light tracks cost center on every transaction, enabling detailed analysis.

## Budget vs. actual comparison

Budget comparison is done on the [Budget](https://app.light.inc/budget) page rather than in ledger reports:

1. Navigate to **Planning & Reports → Budget**
2. Upload a budget scenario as a CSV file
3. The budget overview shows actuals vs. planned amounts per period, with YTD variance and planned-accuracy statistics
4. Click any cell in the budget table to drill into the underlying ledger transactions

See [Budget scenarios](10-10-budget-scenarios.md) for details. Investigate variances >10% to understand performance drivers.

## Year-to-date (YTD) reporting

View cumulative P&L from year start:

1. Navigate to **Planning & Reports → Reports**
2. Set the date range from the start of your fiscal year to today
3. Light shows cumulative revenue and expenses since year start

Compare YTD performance to budget or prior year for mid-year assessment.

## Pro forma P&L and forecasting

Light does not generate P&L projections. To maintain a forecast:

1. Build your projection outside Light (e.g., in a spreadsheet), using exported P&L data as the baseline
2. Upload the projection as a budget scenario CSV on the [Budget](https://app.light.inc/budget) page
3. Compare actual results against the forecast as the year progresses

You can maintain multiple scenarios simultaneously — for example a base plan and a stress-tested downside case. Use for planning and to communicate with lenders or investors. See [Budget scenarios](10-10-budget-scenarios.md).

## P&L footnotes and disclosure

Comprehensive P&L reporting includes footnotes:

1. **Accounting policies**: Revenue recognition policy, expense recognition timing
2. **Significant items**: One-time gains/losses, restructuring charges
3. **Segment information**: Profitability by business line
4. **Related party transactions**: Transactions with affiliated parties
5. **Subsequent events**: Items occurring after period-end

Prepare footnotes outside Light as part of your financial statement package, using exported report data to support the underlying schedules.

> Tip: Separate discontinued operations and one-time items from continuing operations for clearer performance analysis.

## Exporting P&L data

Export P&L for external distribution or analysis:

1. Generate the P&L report
2. Click the export button
3. Light downloads a CSV file containing all rows and columns as displayed

You can open the CSV in Excel or Google Sheets for further formatting and distribution. Drilldown transaction lines can also be exported as CSV.

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Balance sheet](10-2-balance-sheet.md)
- [Cash flow statement](10-4-cash-flow.md)
- [Trial balance](10-5-trial-balance.md)
- [Budget scenarios](10-10-budget-scenarios.md)
