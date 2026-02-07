# ARR Tracking and Reporting

Annual Recurring Revenue (ARR) is a critical metric for subscription-based and SaaS businesses. It represents the predictable revenue you can expect to receive from existing contracts over one year. Light provides native ARR tracking, automatically calculating and reporting this metric from your subscription agreements.

[Open in Light →](https://app.light.inc/invoice-receivables)

## Understanding ARR

Annual Recurring Revenue is calculated by taking the monthly recurring revenue (MRR) and multiplying by 12. It's particularly important for companies with:

- SaaS or cloud-based products billed annually or monthly
- Subscription services with recurring contracts
- Support and maintenance contracts renewed annually
- Professional services delivered under recurring service agreements

Unlike one-time revenue, ARR provides visibility into predictable, recurring cash flows. It's a key metric for business valuation, cash forecasting, and investor relations.

## ARR formula and calculation

**ARR = Monthly Recurring Revenue × 12**

Light automatically calculates MRR from your subscription contracts:

- Sum all active subscription contracts in a period
- Exclude one-time payments and usage-based amounts
- Account for billing frequency (annual, monthly) and normalize to monthly
- Exclude churned contracts (those with end dates)
- Consider contract value before taxes and discounts

For example, if you have:
- Contract A: EUR 1,000/month
- Contract B: EUR 5,000/year (EUR 416.67/month)
- Contract C: Churned (ended)

Your MRR = EUR 1,416.67, therefore ARR = EUR 17,000.

## Tracking ARR over time

ARR changes as contracts are added, renewed, or churned. Light tracks these movements:

**New ARR** is revenue from new contracts signed in the current period that had no prior contract value.

**Expansion ARR** is the incremental revenue from existing customers through upsells or additional purchases.

**Churn ARR** is revenue lost from contracts that ended or were significantly reduced.

**Renewal ARR** is revenue from contracts that were renewed.

Your net ARR growth = New ARR + Expansion ARR - Churn ARR + Renewal ARR

> Good to know: Tracking these components separately provides insights into whether growth comes from new customers, existing customer expansion, or churn reduction.

## Configuring ARR tracking in Light

ARR tracking is enabled automatically for AR (accounts receivable) invoices with recurring revenue characteristics:

1. Navigate to **Planning & Reports > Reports** for ARR tracking
2. Verify that AR invoices are configured with:
   - Billing frequency (monthly, quarterly, annual)
   - Contract start and end dates
   - Recurring revenue indicator
3. Light automatically aggregates recurring invoice amounts into ARR

For enhanced tracking, associate invoices with subscription contracts:

1. Create or edit an AR invoice
2. Link to the corresponding subscription contract
3. Mark the invoice as recurring revenue
4. Include the contract duration and billing frequency

## ARR reporting and dashboards

Light provides multiple views of ARR data:

**ARR Summary Dashboard** shows:
- Current ARR and MRR
- YoY and QoQ growth rates
- New, expansion, and churn ARR for the period
- ARR by customer segment or business line

**ARR Cohort Analysis** tracks cohorts of customers acquired in the same period:
- Showing which acquisition cohorts generate highest lifetime value
- Revealing cohort retention and churn patterns
- Identifying seasonal trends in customer acquisition and churn

**ARR Forecast** projects future ARR based on:
- Current contracts and renewal dates
- Historical churn rates
- Pipeline of anticipated new contracts

## Multi-currency ARR reporting

For multinational companies, ARR can be reported in transaction currency, local currency, or group currency:

1. Navigate to **Planning & Reports > Reports** for ARR tracking
2. Click **Currency Settings**
3. Select your reporting currency (transaction, local, or group)
4. Light recalculates ARR using appropriate period-end FX rates

When reporting ARR in multiple currencies, use consistent rate sources (typically month-end rates) to avoid calculation inconsistencies.

> Tip: Report ARR in your group currency for board/investor presentations and in local currency for subsidiary-level operational reporting.

## Handling contract changes mid-period

When customers upgrade, downgrade, or churn mid-period, Light adjusts ARR calculations:

**Upgrades (expansion)**: Create a new AR invoice for the incremental amount and mark it as expansion revenue.

**Downgrades**: Create a credit note (CN) to reduce contracted amount and mark churn.

**Churn**: End-date the contract in the subscription tracking system.

Light automatically recalculates ARR in real-time as these changes are recorded.

## ARR vs. GAAP revenue recognition

It's important to note that ARR differs from recognized revenue under IFRS 15:

- **ARR** is a management metric representing the full contract value annualized
- **Recognized revenue** is what appears on your P&L following accounting rules

For example, if a customer pays EUR 12,000 upfront for a 12-month SaaS contract:
- ARR = EUR 12,000
- Month 1 recognized revenue = EUR 1,000 (using deferred revenue release)
- Total Year 1 recognized revenue = EUR 12,000

Light reports both metrics separately: ARR for business management and deferred revenue for financial reporting compliance.

## Integration with forecasting and planning

ARR data feeds into Light's budget and scenario planning features:

1. Use historical ARR and growth rates to build sales forecasts
2. Model impact of different churn assumptions
3. Stress-test revenue impact of pricing changes
4. Forecast cash collections based on billing patterns

See Budget Scenarios for detailed forecasting capabilities.

## Best practices for ARR tracking

**Define recurring clearly**: Establish which contracts qualify as "recurring" (typically 12+ month terms with auto-renewal).

**Clean data discipline**: Ensure all subscription contracts have accurate start/end dates and billing frequency.

**Cohort tracking**: Segment ARR by acquisition channel, customer segment, or geography to identify high-value customer sources.

**Churn monitoring**: Track churn rate monthly and investigate spikes in ARR reduction.

**Reconciliation**: Monthly, reconcile reported ARR to AR aging report and contract management system.

## Related articles

- [Revenue recognition rules overview](9-1-revenue-recognition-overview.md)
- [Configuring releases: depreciation, prepayments, deferred revenue](9-2-configuring-releases.md)
- [Budget scenarios](../10-reporting/10-10-budget-scenarios.md)
- [ARR and SaaS metrics](../10-reporting/10-13-arr-saas-metrics.md)
