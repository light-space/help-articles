# ARR and SaaS Metrics

For subscription-based and SaaS companies, traditional accounting metrics (net income, gross margin %) don't fully capture business performance. Light provides dedicated SaaS metrics reporting, tracking subscription health, customer acquisition efficiency, and unit economics.

[Open in Light →](https://app.light.inc/ledger-reports)

## SaaS metrics overview

Critical metrics for SaaS businesses:

**Subscription metrics**:
- Annual Recurring Revenue (ARR)
- Monthly Recurring Revenue (MRR)
- Net Revenue Retention (NRR)
- Churn rate

**Growth metrics**:
- Customer growth rate
- New ARR (from new customers)
- Expansion ARR (from existing customer upsells)
- Churn ARR (from customer losses)

**Efficiency metrics**:
- Customer Acquisition Cost (CAC)
- CAC Payback Period
- Lifetime Value (LTV)
- LTV/CAC Ratio

**Profitability metrics**:
- Gross margin
- Operating margin
- Cash conversion

Light calculates all of these from transaction data.

## Accessing SaaS metrics

Navigate to **Planning & Reports → Reports**. Light displays SaaS metrics including:

- Current MRR and ARR
- Growth rate (month-over-month, year-over-year)
- Customer count and growth
- Churn rate
- Key efficiency ratios

## Annual Recurring Revenue (ARR)

ARR represents total revenue from active subscriptions annualized.

**Calculation**: Sum all active subscription contracts, annualize (multiply monthly by 12), exclude one-time fees.

**Example**: If you have 100 customers paying $100/month, your ARR = 100 × $100 × 12 = $120,000.

Light automatically calculates ARR from AR invoices marked as recurring revenue.

## Monthly Recurring Revenue (MRR)

MRR is ARR ÷ 12. Useful for month-to-month trend analysis.

**Calculation**: Sum all active subscription contracts for the month.

**MRR growth**: Track month-over-month growth (both $ and %).

Monitor MRR trend to identify inflection points in business growth.

## Net Revenue Retention (NRR)

NRR measures total revenue from existing customers, accounting for churn, downgrades, and upsells.

**Calculation**: (Beginning Month ARR + Expansion ARR - Churn ARR) ÷ Beginning Month ARR

**Example**:
- Beginning ARR: $100,000
- Expansion (upsells): +$15,000
- Churn: -$5,000
- Ending ARR: $110,000
- NRR = ($100,000 + $15,000 - $5,000) ÷ $100,000 = 110%

NRR >100% indicates existing customers generate more revenue (expansion outpaces churn). NRR <100% indicates overall contraction.

## Churn rate

Churn is the percentage of customers or revenue lost in a period.

**Customer churn**: % of customers who churned = Churned Customers ÷ Beginning Customers

**Revenue churn**: % of revenue lost = Churned ARR ÷ Beginning ARR

**Annual churn**: If you lose 5% of customers monthly, annual churn = 1 - (0.95^12) = 46%.

Low churn is critical for SaaS sustainability. A 5% monthly churn rate is typical for healthy SaaS (60% annual).

## Cohort analysis

Analyze customer cohorts (groups acquired in the same period):

1. Group customers by acquisition month
2. Track cohort retention over time (% staying after 1 month, 3 months, 6 months, 12 months)
3. Calculate cohort revenue trajectory
4. Compare cohorts to identify which acquisition channels deliver best customers

Example: Customers acquired via partners have 85% 12-month retention; customers acquired via ads have 60%. Shift budget to partner channel.

Light provides cohort reporting that automatically groups customers and tracks retention.

## Customer Acquisition Cost (CAC)

CAC measures how much you spend to acquire a customer.

**Calculation**: Sales & Marketing Expense ÷ New Customers Acquired

**Example**: You spent $100,000 on sales/marketing and acquired 100 customers in the month. CAC = $100,000 ÷ 100 = $1,000 per customer.

Compare CAC to LTV (see below). If LTV/CAC is 3:1 or higher, acquisition is efficient.

## CAC Payback Period

CAC Payback Period measures how long until a customer's revenue pays back the acquisition cost.

**Calculation**: CAC ÷ Monthly Profit per Customer

**Example**:
- CAC = $1,000
- Customer monthly subscription = $100
- Gross profit margin = 80%
- Monthly profit per customer = $100 × 80% = $80
- CAC Payback = $1,000 ÷ $80 = 12.5 months

Shorter payback is better (less time to recoup investment). Typically 12-18 months is healthy.

## Lifetime Value (LTV)

LTV estimates total profit from a customer over their relationship with you.

**Calculation**: Average Customer Profit per Month × Average Lifetime in Months

**Example**:
- Monthly profit: $80 (from above)
- Average customer stays 24 months (based on 5% churn)
- LTV = $80 × 24 = $1,920

LTV should be 3-5x CAC for healthy unit economics.

## Magic Number

Magic Number measures how efficiently you convert revenue into growth.

**Calculation**: (Revenue This Quarter - Revenue Last Quarter) ÷ Sales & Marketing Spend Last Quarter

**Example**:
- Q2 Revenue: $100,000
- Q1 Revenue: $90,000
- Q1 Sales & Marketing: $10,000
- Magic Number = ($100,000 - $90,000) ÷ $10,000 = 1.0

Magic Number of 0.7+ is good growth efficiency.

## Unit economics dashboard

Light provides a dedicated unit economics dashboard:

- CAC (total and by customer segment/channel)
- LTV
- LTV/CAC ratio
- CAC Payback Period
- MRR per employee
- Monthly Burn Rate (if unprofitable)

Use this dashboard to track whether your business model is sustainable.

## Expansion revenue tracking

Track revenue from existing customers (upsells, cross-sells):

1. Create AR invoices for expansion contracts
2. Mark as "Expansion Revenue"
3. Light separately tracks expansion from new customer revenue
4. Monitor expansion as % of total revenue growth

Healthy SaaS companies have 10-20%+ expansion revenue growth.

## Downgrades and contraction tracking

Track customers who downgrade to lower-tier plans:

1. When a customer downgrades, create a credit note for the difference
2. Mark as "Contraction" or "Downgrade"
3. Light tracks downgrades separately from churn
4. Monitor trends

Downgrades indicate product-market fit issues or pricing problems.

## SaaS forecasting

Project future SaaS metrics:

1. Input growth assumptions (new customer acquisition, churn rate)
2. Project MRR/ARR for next 12-24 months
3. Model profitability timeline (when operating cash flow becomes positive)
4. Stress test with different churn assumptions

This is critical for fundraising conversations and investor relations.

## Comparing to benchmarks

Light displays your SaaS metrics; benchmark against industry:

**Typical SaaS benchmarks**:
- MRR growth: 7-10% per month
- Churn rate: 3-7% monthly
- CAC: 12-18 month payback
- LTV/CAC: 3:1 or higher
- Magic Number: 0.7+

If your metrics fall below benchmarks, investigate root causes.

## Cohort retention curves

Visualize customer retention by cohort:

- X-axis: Months since acquisition
- Y-axis: % of cohort retained
- Each line: One acquisition cohort

Healthy cohorts show 80%+ 12-month retention. Declining curves indicate quality issues.

Light automatically generates retention curves for each cohort.

## Rule of 40

A SaaS profitability rule:

Rule of 40 = Growth Rate (%) + Profit Margin (%) ≥ 40

Example:
- Growth rate: 30%
- Profit margin: 15%
- Score: 30 + 15 = 45 (healthy)

Example:
- Growth rate: 50%
- Profit margin: -20%
- Score: 50 + (-20) = 30 (unsustainable, burning cash)

Target Rule of 40 score of 40+. Helps balance growth and profitability.

## CAC Ratio metric

Another efficiency measure:

CAC Ratio = (Sales & Marketing Spend) ÷ (New ARR)

Example:
- Sales & Marketing Spend: $50,000
- New ARR from new customers: $100,000
- CAC Ratio = $50,000 ÷ $100,000 = 0.5 (spend $0.50 to get $1 ARR)

Lower ratios are better. Healthy is 0.3-0.5 depending on stage.

## Customer success metrics

Beyond financial metrics, monitor:

- **NPS (Net Promoter Score)**: Customer satisfaction
- **CSAT**: Customer satisfaction rating
- **Support ticket volume**: Indicator of product issues
- **Feature adoption**: Are customers using key features?

These leading indicators predict churn and expansion.

## Related articles

- [ARR tracking and reporting](../09-revenue-compliance/9-5-arr-tracking.md)
- [Reporting overview](10-1-reporting-overview.md)
- [Real-time dashboards and KPIs](10-12-dashboards-kpis.md)
- [Budget scenarios](10-10-budget-scenarios.md)
