# Tables and Pivot Reports

Tables and pivot reports provide flexible analysis capabilities, allowing you to reorganize and analyze your financial data across multiple dimensions. Unlike pre-formatted statements (balance sheet, P&L), tables let you define your own row and column structures to answer specific business questions.

[Open in Light →](https://app.light.inc/ledger-reports)

## Understanding pivot reports

A pivot report is a dynamic data analysis tool that reorganizes transactional data into a structured format:

- **Rows**: Define what you want to analyze (accounts, departments, products, customers)
- **Columns**: Define how you want to slice it (periods, entities, currencies, business partners)
- **Values**: What you're measuring (amounts, counts, percentages)
- **Filters**: Constraints on which data to include

This structure provides insights that standard financial statements don't show.

## Creating a pivot report

To create a custom pivot report:

1. Navigate to **Planning & Reports → Reports**
2. Click **+ Create report**
3. Select a base type (transaction data, account balances, or transaction detail)
4. Configure rows:
   - Select dimension: Accounts, Cost Centers, Business Partners, Custom Properties, etc.
   - Specify grouping level (account code, full account, or custom)
5. Configure columns:
   - Select period (daily, weekly, monthly, quarterly, annual)
   - Select secondary dimension (optional): Entity, currency, tax code
6. Select values to display:
   - Amount (debit, credit, net)
   - Transaction count
   - Average amount
7. Add filters as needed (date range, specific accounts, entities)
8. Click **Generate**

Light displays your pivot report with drill-down capabilities.

## Pivot report row dimensions

Available row dimensions depend on your data:

**Accounts**: Organize by GL account. Shows revenue, expense, asset, liability by account.

**Account type**: Group by asset, liability, equity, revenue, expense. Useful for high-level analysis.

**Account code**: Organize by account code prefix for hierarchical analysis.

**Cost centers**: Show data by department or operational unit.

**Business partners**: Segment by customer or vendor. Useful for customer profitability or vendor spend analysis.

**Custom properties**: Organize by any custom attribute you've tagged transactions with (e.g., project, product line, geographic region).

**Document type**: Analyze by transaction type (AP, AR, JE, etc.).

**Ledger**: Segment by ledger if you operate multiple ledgers.

> Tip: Use business partner dimension to analyze your top 10 customers or vendors and their contribution to profit or spend.

## Pivot report column dimensions

Available column dimensions:

**Period**: Group by day, week, month, quarter, or year. Most common for time-series analysis.

**Entity**: Segment by legal entity. Useful for multi-entity companies analyzing which subsidiary contributes to profit.

**Currency**: Show data in transaction currency, local currency, or group currency.

**Tax code**: Organize by tax treatment. Useful for tax compliance analysis.

**Custom properties**: Organize by attributes you've assigned to transactions.

Multiple column dimensions create a cross-tabulated structure.

## Common pivot report use cases

**Revenue by customer and period**: Revenue (rows) × Month (columns) = monthly revenue by customer

Shows which customers drive revenue and seasonal patterns.

**Expense by cost center and month**: Expense accounts (rows) × Month (columns) = monthly spending by department

Identifies high-spending departments and cost control opportunities.

**Receivables aging by customer**: Customer balance (rows) × Age bucket (columns) = AR aging by customer

Shows collection efficiency and credit risk.

**Payables aging by vendor**: Vendor balance (rows) × Age bucket (columns) = AP aging by vendor

Identifies payment obligation timing.

**Profit by product and entity**: Product line (rows) × Entity (columns) = profit contribution by product in each subsidiary

Identifies which products and entities are profitable.

## Table reports vs. pivot reports

Light provides two similar but distinct capabilities:

**Table reports**: Simplified structure with a single row dimension, columns for periods/entities, and simple calculations. Easier to create for basic analysis.

**Pivot reports**: More powerful with multi-dimensional analysis, custom aggregations, drill-down, and filtering. Better for complex questions.

Start with table reports for straightforward questions. Use pivot reports when you need cross-tabulation or complex analysis.

## Filtering pivot reports

Constrain pivot data to specific dimensions:

1. In pivot report configuration, click **Filters**
2. Add filters:
   - **Date range**: Include only transactions within a date range
   - **Specific accounts**: Include only certain GL accounts
   - **Specific entities**: Include only certain company entities
   - **Specific business partners**: Include only certain customers or vendors
   - **Custom properties**: Include only transactions with specific custom attribute values
3. Light applies filters before pivoting data

Filters reduce the data set to focus on relevant dimensions.

## Drill-down analysis

Pivot reports support drilling down to transaction detail:

1. Generate a pivot report
2. Click any cell in the report
3. Light displays transactions included in that cell
4. Review transaction detail
5. Export transaction list if needed

This enables rapid investigation of unusual values or exceptions.

## Calculated columns and rows

Add calculations to pivot reports:

**Calculated columns**: Create new columns that perform calculations:
- Running totals (cumulative from left)
- Period-over-period change
- Percentage of total
- YTD amounts
- Variance calculations (Actual vs. Budget)

**Calculated rows**: Create new rows:
- Subtotals (subtotal of grouped rows)
- Percentage of parent (each item as % of group total)
- Rankings (top 10 customers by revenue)

Light supports common calculations and custom formulas.

## Comparing periods in pivot reports

Analyze year-over-year or period-over-period trends:

1. Create pivot report with Period as column dimension
2. Click **Compare Periods**
3. Light adds columns for:
   - Current period amount
   - Prior year amount
   - Change in dollars
   - Change in percentage
4. Identify positive and negative trends

This is useful for assessing business momentum and identifying problem areas.

## Pivot report formatting

Format your pivot report for presentation:

1. After generating report, click **Format**
2. Options include:
   - **Number format**: Thousands separator, decimal places, currency symbol
   - **Conditional formatting**: Highlight cells based on rules (e.g., negative red, positive green)
   - **Column width**: Auto-size or specify
   - **Header formatting**: Bold, color, alignment
3. Light applies formatting to export

This improves readability and presentation quality.

## Saving and scheduling pivot reports

Save your pivot report template for reuse:

1. Click **Save Report**
2. Enter report name
3. Light saves the configuration

Retrieve the report by name anytime:

1. Navigate to **Planning & Reports → Reports**
2. Click **Open Saved Report**
3. Select the report
4. Light regenerates with current data

Schedule recurring reports:

1. Click **Schedule**
2. Select frequency (daily, weekly, monthly, quarterly)
3. Select recipients
4. Light automatically generates and distributes

## Exporting pivot reports

Export pivot data for external use:

1. Generate pivot report
2. Click **Export**
3. Select format:
   - **Excel**: Retains formatting and allows further analysis
   - **PDF**: Formatted for presentation
   - **CSV**: Raw data for BI tools or analysis
4. Light generates and downloads the file

Excel export preserves your formatting and pivot structure for further analysis.

## Pivot report limitations and best practices

**Performance**: Large pivot reports (>100k rows × many columns) may load slowly. Filter data or reduce dimensions.

**Data quality**: Pivot analysis is only as good as your source data. Ensure consistent account mappings, cost center assignment, and business partner coding.

**Custom properties**: If you rely on custom properties for analysis, ensure all transactions are tagged correctly.

**Documentation**: Document your pivot report definitions (what rows, columns, filters mean) so others can understand and reproduce them.

> Tip: Create a library of standard pivot reports your team uses regularly (revenue by customer, expense by department, profit by product).

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Custom reports and filters](10-9-custom-reports.md)
- [Real-time dashboards and KPIs](10-12-dashboards-kpis.md)
- [Exporting and sharing reports](10-11-exporting-reports.md)
