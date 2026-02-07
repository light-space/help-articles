# Budget Scenarios

Budgeting is the process of planning your company's financial future. Light's budget functionality enables creating budgets, comparing actual results to budget, and modeling different scenarios (optimistic, pessimistic, base case) to evaluate financial impact.

[Open in Light →](https://app.light.inc/budget)

## Budget overview

A budget is a forward-looking plan of expected revenues, expenses, and capital expenditures. Budgets serve several purposes:

- **Financial planning**: Projecting cash needs and profitability
- **Performance management**: Setting targets and evaluating actual performance
- **Resource allocation**: Determining spending limits by department
- **Scenario analysis**: Modeling impact of different business assumptions

Light allows multiple budgets (annual budget, quarterly forecast, departmental budgets) and comparisons between them.

## Creating a budget

To create a budget:

1. Navigate to **Planning & Reports → Budget**
2. Enter budget details:
   - Budget name (e.g., "FY2025 Annual Budget")
   - Period start and end (fiscal year or custom period)
   - Level of detail: By account, account type, cost center, business partner
3. Select budget scenario: Base case, optimistic, pessimistic, or custom
4. Light displays budget input interface
5. Enter budgeted amounts for each account/period
6. Save the budget

Budgets can be entered manually or imported from Excel or other sources.

## Budget levels and dimensions

Configure budget detail level:

**Account-level budgets**: Budget each GL account separately (high detail, time-consuming).

**Account type budgets**: Budget by expense category (revenue, COGS, operating expense). Higher level, faster to create.

**Cost center budgets**: Budget by department (useful for management accountability).

**Business partner budgets**: Budget by customer revenue or vendor spending.

**Multi-level budgets**: Combine dimensions. For example:
- Row: Expense accounts
- Column: Departments (cost centers)
- Result: A matrix where each cell is a specific account's budget in a specific department

> Tip: Start with account-type budgets (high-level), then drill down to account detail for significant items.

## Budget templates

Create reusable budget templates:

1. Set up your standard budget structure (accounts, periods, cost centers)
2. Click **Save as Template**
3. Next budget season, create new budget from template
4. Adjust figures based on updated assumptions

This saves setup time year-over-year.

## Bottom-up vs. top-down budgeting

Light supports both approaches:

**Top-down budgeting**:
1. Executive leadership sets overall revenue target
2. Overall profit margin target
3. Finance distributes targets to departments
4. Departments build detailed budgets to targets
5. Finance consolidates and reviews

**Bottom-up budgeting**:
1. Each department builds budget from operational assumptions
2. Each salesperson estimates revenue
3. Each manager estimates spending
4. Finance consolidates bottom-up estimates
5. Compare to targets and reconcile differences

Light facilitates both: Enter top-down targets or import bottom-up submissions.

## Budget assumptions and drivers

Effective budgets are built on explicit assumptions:

**Revenue assumptions**:
- Growth rate (% increase from prior year)
- New customer additions
- Churn/retention rates
- Average selling price
- Product mix

**Expense assumptions**:
- Headcount (number of employees)
- Salary growth rate
- Fixed vs. variable spend
- CapEx requirements

Document assumptions in budget narratives. When actual results differ from budget, revisit assumptions to understand drivers.

## Forecasting and rolling forecasts

Beyond annual budgets, maintain forward-looking forecasts:

1. Create a rolling forecast (12-month forward-looking view)
2. Each month, add a new month to the forecast
3. Update forecast monthly based on actual performance and market changes
4. Compare actual vs. forecast to track accuracy

Rolling forecasts are more responsive than annual budgets.

## Scenario analysis

Model different "what-if" scenarios:

**Base case**: Most likely scenario with realistic assumptions.

**Optimistic case**: Higher growth, lower costs, better customer retention.

**Pessimistic case**: Lower growth, higher costs, higher churn.

**Stress case**: Severe recession or major business disruption.

Compare scenarios to understand:
- Upside and downside potential
- Key drivers of outcomes
- Financial impact of assumptions changing

Light lets you create multiple scenarios and compare them side-by-side.

## Budget vs. actual analysis

Once actual results are recorded, compare to budget:

1. Navigate to **Planning & Reports → Reports**
2. Select budget and actual period
3. Light displays budget, actual, and variance ($ and %)
4. Highlight variances >threshold (e.g., >10%)

Investigate significant variances to understand what drove differences:
- Did we achieve revenue targets?
- Did expenses stay within budget?
- What changed from plan and why?

## Rolling forecasts and reforecasting

During the year, forecasts may need updating:

1. Each quarter, create an updated forecast for the remainder of the year
2. Incorporate actual results year-to-date
3. Update assumptions based on market changes
4. Reforecast full-year results

This is more responsive than a static annual budget.

## Budget performance reporting

Create reports showing budget performance:

1. **Variance report**: Actual vs. budget by account
2. **Variance trend**: Variances over time (are they improving?)
3. **Responsibility accounting**: Actual vs. budget by cost center (for management accountability)
4. **Segment budget**: Budget by customer, product, or geography

These reports support management discussions and decision-making.

## Budget allocation and resource planning

Use budgets for resource decisions:

**Headcount planning**: Plan headcount by department, multiply by average salary to determine budget.

**Capital planning**: Plan major asset acquisitions and their impact on depreciation.

**Marketing spend**: Budget by channel (digital, sales, events) to optimize ROI.

Light helps model these allocations and their P&L impact.

## Consolidating departmental budgets

For multi-department organizations:

1. Each department manager submits budget (bottom-up)
2. Finance consolidates all departmental budgets
3. Compare to corporate targets
4. Reconcile differences
5. Get executive approval

Light consolidates budgets automatically across departments and entities.

## Budget vs. actual by cost center

Assign accountability using cost center budgets:

1. Create budget by cost center (department)
2. Allocate cost center to transactions as they're recorded
3. Compare actual by cost center to budgeted by cost center
4. Department managers are accountable for their cost center performance

This supports responsibility accounting and management accountability.

## Capital expenditure budgeting

Plan for asset purchases separately:

1. Create CapEx budget with planned asset purchases
2. Schedule over periods (monthly, quarterly)
3. Track actual CapEx spend against budget
4. Project depreciation impact on future P&L

Light helps manage capital projects and their financial impact.

## Multi-currency budgeting

For multinational organizations:

1. Create budgets in each entity's functional currency
2. Consolidate to group currency using budgeted FX rates
3. Compare actual (translated) to budget (translated at budgeted rates)
4. Analyze FX variance separately

This shows impact of FX assumptions on profitability.

## Budget approval workflow

Establish a budget approval process:

1. Department managers submit budgets
2. Finance reviews for completeness and reasonableness
3. Consolidate across departments
4. CFO and executive team review and revise
5. Board approval
6. Final budget locked for the year

Light tracks who created, reviewed, and approved each budget.

## Linking budgets to planning

Use budgets as input to broader planning:

**Cash flow planning**: Use budgeted P&L to project cash flows.

**Funding planning**: If cash flow is negative, plan for financing.

**Headcount planning**: Align budgeted spending with hiring plans.

**Capital planning**: Plan for major asset purchases and their financing.

Light integrates budgets with other planning tools.

## Budget accuracy and variance trending

Track budget accuracy over time:

1. After each fiscal year, compare budget to actual
2. Calculate variance percentage
3. Identify which accounts/departments were over/under budget
4. Learn from variances to improve future budgets

Light trends this data, showing whether budget accuracy improves over time.

> Tip: Variances of 5-10% are normal. Investigate variances >15% to identify process breakdowns or assumption changes.

## Budget templates for recurring transactions

For recurring items (rent, salaries, utilities):

1. Create a template showing typical monthly amounts
2. Adjust for known changes (salary increases, new hires)
3. Replicate across months
4. Reduces manual entry

Light supports template-based budget entry.

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Profit and loss](10-3-profit-loss.md)
- [Custom reports and filters](10-9-custom-reports.md)
- [Real-time dashboards and KPIs](10-12-dashboards-kpis.md)
