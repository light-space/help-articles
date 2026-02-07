# Custom Reports and Filters

While Light provides standard financial statements (balance sheet, P&L, cash flow), custom reports let you analyze data in ways specific to your business. Custom reports combine flexible filtering, dimensioning, and formatting to answer questions like: How profitable is each customer? What's our selling, general, and administrative expense by department?

[Open in Light →](https://app.light.inc/ledger-reports)

## Custom report builder

Light's report builder enables creating reports without SQL or programming:

1. Navigate to **Planning & Reports → Reports**
2. Click **+ Create report**
3. Choose a base report type:
   - Account balances (GL account data)
   - Transaction detail (individual transactions)
   - Aging reports (AR/AP aging)
   - Blank canvas (start from scratch)
4. Configure rows, columns, filters, and calculations
5. Save the report

Light saves the template for reuse and automatic regeneration with current data.

## Configuring report rows

Rows define what you're analyzing:

**Account-based rows**:
- Individual GL accounts
- Account hierarchies (asset class, expense category)
- Account type (asset, liability, revenue, expense)

**Dimension-based rows**:
- Cost center (department, business unit)
- Business partner (customer, vendor)
- Custom property (project, product line, geography)
- Ledger (if using multiple ledgers)

Select the dimension, then specify grouping level. For example, for business partner, you could show:
- All customers combined
- Top 10 customers individually, others grouped
- All customers individually

> Tip: Grouping by cost center is excellent for analyzing spending by department. Grouping by business partner reveals which customers/vendors drive your business.

## Configuring report columns

Columns define how you're slicing the data:

**Time-based columns**:
- Periods (days, weeks, months, quarters, years)
- Comparison (current vs. prior year)
- Fiscal calendar (using your defined fiscal periods)

**Dimension-based columns**:
- Entity (if you operate multiple legal entities)
- Currency (transaction, local, or group)
- Custom properties (dimensions you've assigned)

**Calculated columns**:
- Variance (actual vs. budget or actual vs. prior period)
- Percentage of total
- Running totals
- Growth rates

You can combine multiple column dimensions (e.g., Month and Entity).

## Report filtering

Filter data to specific subsets:

1. Click **Add Filter**
2. Select filter type:
   - **Date range**: Include only transactions within a date range
   - **Specific accounts**: Include only certain GL accounts
   - **Specific entities**: Include only certain company entities
   - **Specific business partners**: Include only certain customers/vendors
   - **Specific cost centers**: Include only certain departments
   - **Custom properties**: Include only transactions with specific custom attributes
3. Specify filter criteria
4. Light applies filters before generating the report

Multiple filters combine (AND logic): all must be true for a row to appear.

## Calculated fields

Add calculations to your report:

**Account-level calculations**:
- Subtotal: Sum of grouped accounts
- Margin: Revenue - COGS, or other calculations
- Percentage: As percentage of parent group or total

**Period calculations**:
- Running total: Cumulative sum from first period
- Growth: Percentage change from prior period
- YTD: Year-to-date cumulative

**Dimension calculations**:
- Percentage of total: As percentage of all customers/departments
- Ranking: Rank by amount (top 10 items)

Formulas support basic arithmetic and aggregation functions.

## Drill-down and detail views

Pivot from summary to detail:

1. Generate a custom report
2. Click any cell in the report
3. Light displays transactions included in that cell
4. Review transaction detail, dates, amounts, business partners
5. Export transaction list if needed

This enables rapid troubleshooting of unexpected values.

## Report formatting

Format reports for presentation:

**Number formatting**:
- Decimal places (no decimals for whole dollars, or 2 decimals for cents)
- Thousands separator
- Currency symbol
- Percentage formatting

**Conditional formatting**:
- Color negative amounts red, positive green
- Highlight values exceeding thresholds (e.g., expenses >$100k)
- Apply data bar charts for visual impact

**Layout formatting**:
- Column width (auto-size or specific)
- Row height
- Header styling (bold, color, alignment)
- Repeat headers on each page (for multi-page reports)

**Page breaks**:
- Page break after each major group
- Fit to page width (for printing)

## Headers and footers

Add context to your reports:

**Headers**:
- Report title
- Report date or period
- Entity name
- Currency

**Footers**:
- Page numbers
- Report generated date/time
- Confidentiality notice
- Signed approval line

Light includes these automatically and allows customization.

## Subtotals and summaries

Organize reports with subtotals:

**Subtotals**: Sum of grouped items
- Subtotal by cost center (sum of all expenses in each department)
- Subtotal by business partner (sum of all sales to each customer)
- Subtotal by account type (sum of all revenue, all expenses)

**Grand total**: Sum of all subtotals

Light automatically calculates subtotals. Specify whether they should appear:
- After each group
- At the end of the report
- Both

## Ratio and KPI calculations

Add business metrics to reports:

**Financial ratios**:
- Gross margin: (Revenue - COGS) / Revenue
- Operating margin: Operating Income / Revenue
- Current ratio: Current Assets / Current Liabilities
- Debt-to-equity: Total Debt / Total Equity

**Operational metrics**:
- Revenue per employee (if you track headcount)
- Customer acquisition cost
- Churn rate
- Days sales outstanding (DSO)

Define these once, reuse across reports.

## Budget vs. actual comparisons

Create variance reports comparing actual to budget:

1. Configure report with actual amounts and budget amounts side-by-side
2. Add calculated columns for variance ($ and %)
3. Light highlights significant variances (e.g., >10%)

This supports management review and variance investigations.

## Saving and reusing reports

Once created, save your report template:

1. Click **Save Report**
2. Enter a descriptive name
3. Optionally add a description
4. Light saves the configuration

Reuse the report:
- Navigate to **Planning & Reports → Reports**
- Click the report name
- Light regenerates with current data
- No need to reconfigure

## Scheduling reports

Automate recurring reports:

1. Open a saved report
2. Click **Schedule**
3. Select frequency (daily, weekly, monthly, quarterly, annually)
4. Select recipients (users or email addresses)
5. Light generates and distributes automatically on the schedule

This eliminates manual report generation and ensures timely distribution.

## Report templates and standardization

Create standard reports your organization uses regularly:

1. **Sales report**: Revenue by customer, by product, by salesperson
2. **Expense report**: Spending by department, by category
3. **Cash position**: Cash by bank account, by entity
4. **AR aging**: Receivables aging by customer
5. **AP aging**: Payables aging by vendor
6. **Variance analysis**: Actual vs. budget by account

Document each report's purpose and usage.

> Tip: Assign report ownership. Someone should be responsible for updating assumptions, validating accuracy, and distributing on schedule.

## Dashboard vs. report

Light provides both dashboards and reports:

**Reports**: Static snapshots as of a specific date/period. Good for formal reporting, archiving, compliance.

**Dashboards**: Real-time views updating continuously. Good for operational monitoring and quick decision-making.

Use both together: Dashboards for daily monitoring, reports for formal periods.

## Exporting custom reports

Export reports for presentation or further analysis:

1. Generate the custom report
2. Click **Export**
3. Select format:
   - **PDF**: Formatted for printing and presentation, maintains formatting
   - **Excel**: Allows further analysis and recalculation by users
   - **CSV**: Raw data for loading into BI tools
4. Light generates and downloads the file

## Performance optimization

Large reports can take time to generate. Optimize:

1. **Filter restrictively**: Exclude unnecessary data (e.g., closed accounts, old dates)
2. **Limit dimensions**: Fewer row/column dimensions = faster generation
3. **Use scheduled reports**: Run at off-peak times (e.g., after-hours)
4. **Archive old data**: Move closed periods to archive to reduce data set

For very large reports, consider using Light's data export to BI tools instead.

## Report sharing and access control

Control who can view reports:

1. After generating a report, click **Share**
2. Select users or teams
3. Set permissions: View only, or Edit (can modify)
4. Light tracks who accessed the report and when

This supports compliance and governance.

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Tables and pivot reports](10-6-tables-pivot-reports.md)
- [Exporting and sharing reports](10-11-exporting-reports.md)
- [Real-time dashboards and KPIs](10-12-dashboards-kpis.md)
