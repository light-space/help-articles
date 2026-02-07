# Real-Time Dashboards and KPIs

Dashboards provide real-time visibility into your financial performance through visual displays of key performance indicators (KPIs). Unlike static reports that show historical data, dashboards update continuously as transactions post to the ledger, enabling rapid decision-making.

[Open in Light →](https://app.light.inc/dashboard)

## Dashboard overview

A dashboard is a collection of visualizations (charts, gauges, numbers) showing critical business metrics. Common financial dashboards include:

- **Finance dashboard**: Revenue, expenses, margin, cash position
- **Balance sheet dashboard**: Assets, liabilities, equity trends
- **Cash dashboard**: Cash position by account, inflows, outflows
- **Expense dashboard**: Top spending categories, departmental costs
- **Sales dashboard**: Revenue trend, sales by customer, pipeline
- **KPI dashboard**: Custom metrics specific to your business

Dashboards update in real-time, giving management current visibility.

## Creating a custom dashboard

Build your own dashboard:

1. Navigate to **Home** to view and customize dashboards
2. Click **Create Dashboard**
3. Name the dashboard (e.g., "Finance Dashboard", "Executive Summary")
4. Select dashboard type: Financial, Operational, or Blank
5. Light provides a template dashboard
6. Customize by:
   - Adding widgets (visualizations)
   - Removing unwanted widgets
   - Adjusting size and position
   - Changing colors and formatting
7. Save the dashboard

Dashboards are automatically populated with current data.

## Dashboard widgets

Widgets are individual visualizations. Common financial widgets:

**Key metrics**: Shows a single number (e.g., "Current Cash: $2,500,000").

**Time series chart**: Shows metric over time (e.g., revenue by month).

**Pie chart**: Shows composition (e.g., revenue by customer or expense by category).

**Bar chart**: Compares values (e.g., budget vs. actual by account).

**Gauge**: Shows metric relative to target (e.g., margin % vs. target 40%).

**Table**: Shows detailed data (e.g., top 10 customers by revenue).

**Trend indicator**: Shows direction (e.g., revenue up 12% vs. prior year).

Add multiple widgets to create comprehensive dashboards.

## Configuring widget data

For each widget, specify:

**Metric**: What you're measuring (revenue, expenses, cash, margin %).

**Dimension**: How to segment (by customer, department, product, entity).

**Time period**: Range to display (last 12 months, last quarter, year-to-date).

**Comparison**: Optional comparison (vs. prior year, vs. budget).

Light calculates the metric from your GL data automatically.

## Key performance indicators (KPIs)

KPIs are metrics that matter to your business:

**Financial KPIs**:
- Revenue (total, by segment)
- Gross profit and margin
- Operating income
- Net profit and margin
- Cash position
- Days sales outstanding (DSO)
- Days payable outstanding (DPO)

**Operational KPIs**:
- Customer count
- Average revenue per customer
- Churn rate
- Customer lifetime value
- Headcount
- Revenue per employee

**Liquidity KPIs**:
- Cash conversion cycle
- Current ratio
- Quick ratio
- Operating cash flow

Configure which KPIs matter for your business, then monitor through dashboards.

## Dashboard refresh rates

Dashboards update automatically:

**Real-time**: Updates continuously as transactions post (1-5 minute lag).

**Hourly**: Updates on the hour.

**Daily**: Updates once daily (typically overnight).

**Manual**: Updates only when you refresh the page.

Configure refresh frequency based on how critical the metrics are. Real-time is good for cash position; daily is sufficient for profit trends.

## Variance dashboards

Monitor performance against plan:

**Actual vs. Budget**: Shows current-year actual compared to approved budget.
- Green: Under budget (spending less, earning more than planned)
- Red: Over budget (spending more, earning less than planned)
- Shows variance in dollars and percentages

**Actual vs. Prior Year**: Shows year-over-year change.
- Green: Growing revenue, declining expenses
- Red: Declining revenue, growing expenses

**Variance by account**: Shows which accounts are driving variance.

## Real-time cash dashboards

Monitor cash position closely:

**Cash balance**: Current balance by account.

**Inflows**: Cash received today, this week, this month.

**Outflows**: Cash paid out today, this week, this month.

**Forecast**: Projected cash position based on outstanding receivables, payables, and debt.

This enables rapid response to cash shortfalls.

## Executive summary dashboards

High-level dashboards for executives:

**One-page dashboard** showing:
- Revenue (this month, YTD, vs. budget)
- Gross margin %
- Operating income
- Net income
- Cash position
- Key metric trends

This supports quick executive review without detailed analysis.

## Departmental dashboards

Each department sees their metrics:

**Sales dashboard**: Revenue, pipeline, sales by rep, conversion rates.

**Operations dashboard**: Headcount, productivity, cost per unit.

**Finance dashboard**: AR/AP aging, cash position, budget variance.

Departmental dashboards provide accountability and focus.

## Cohort analysis dashboards

Track customer cohorts:

**Cohort dashboard** shows:
- New customers acquired by month
- Retention by cohort (what % stay after 1 month, 3 months, 12 months)
- Revenue by cohort
- Cohort lifetime value

This provides insight into customer quality and lifetime value by acquisition period.

## Benchmarking dashboards

Compare to industry:

1. Display your KPI (e.g., gross margin 35%)
2. Add industry benchmark (e.g., industry average 40%)
3. Show variance (e.g., below industry by 5 points)
4. Identify improvement opportunities

Light displays your data; you input benchmark data from industry sources.

## Mobile dashboards

Access dashboards on mobile devices:

1. Dashboards are responsive (adapt to screen size)
2. View on phone or tablet
3. Scroll to see different sections
4. Click widgets to drill down to detail

This enables monitoring metrics while away from your desk.

## Dashboard sharing and access

Share dashboards with specific users:

1. Open a dashboard
2. Click **Share**
3. Select users or teams
4. Set permission: View or Edit
5. Light controls access

Only users you share with can see the dashboard.

## Alerts and notifications

Set up automatic alerts:

1. Define KPI threshold (e.g., "Alert if cash drops below $1M")
2. Light monitors the metric continuously
3. When threshold is exceeded, Light sends:
   - In-app notification
   - Email alert
   - Slack/Teams message (if integrated)
4. Recipient takes action

This enables proactive response to critical metrics.

## Dashboard drill-down and detail

Click any widget to drill down:

1. Click a metric on the dashboard
2. Light displays supporting detail:
   - For revenue metric: shows revenue by customer
   - For expense metric: shows transactions
   - For cash metric: shows transactions by account
3. Further drill to individual transaction level

This enables rapid investigation of exceptions.

## Trend analysis on dashboards

Identify trends visually:

**Trend chart**: Displays metric over time (e.g., 24 months of revenue).
- Visual indication of trend (up, down, flat)
- Trend line showing direction
- Compare to prior-year line

Trends help identify business momentum and problems.

## Comparative dashboards

Compare multiple entities or time periods:

**Entity comparison**: Revenue/expense/profit by subsidiary.

**Time comparison**: Same metric for current year, prior year, and 2 years ago.

Comparisons enable quick identification of differences and issues.

## Customizable dashboards

Allow users to customize:

1. Each user can modify their personal dashboard
2. Add/remove widgets
3. Change metrics or time periods
4. Rearrange layout
5. Save personal settings

This enables each user to focus on metrics important to them.

## Dashboard performance

Optimize dashboard performance for fast loading:

1. Limit number of widgets (10-15 per dashboard)
2. Use simpler visualizations (number, trend) rather than complex charts
3. Filter to date ranges (last 12 months, not all time)
4. Use daily refresh rather than real-time for less-critical metrics

Performance optimization ensures dashboards load quickly.

## Exporting dashboard snapshots

Export a dashboard as an image:

1. Click **Export**
2. Select **Export as Image**
3. Light captures the current dashboard state as PNG
4. Use in presentations, emails, or reports

Snapshots provide point-in-time record of performance.

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Custom reports and filters](10-9-custom-reports.md)
- [Tables and pivot reports](10-6-tables-pivot-reports.md)
- [ARR and SaaS metrics](10-13-arr-saas-metrics.md)
