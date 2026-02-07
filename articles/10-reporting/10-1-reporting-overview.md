# Reporting Overview

Financial reporting is the process of communicating your company's financial position, performance, and cash flows to stakeholders including management, investors, creditors, and regulatory authorities. Light provides a comprehensive reporting engine that generates compliant financial statements, custom reports, and real-time dashboards from your centralized ledger.

[Open in Light →](https://app.light.inc/ledger-reports)

## Core financial statements

Light generates four primary financial statements from your ledger:

**Balance Sheet** shows your financial position at a point in time: assets (what you own), liabilities (what you owe), and equity (owners' stake). It's the foundation of financial analysis and compliance reporting.

**Income Statement (P&L)** shows your financial performance over a period: revenues earned, expenses incurred, and resulting profit or loss. It answers the question: how profitable were we this period?

**Cash Flow Statement** shows how cash moved in, out, and between different activities: operations, investing, and financing. It answers: where did our cash come from and where did it go?

**Trial Balance** lists all GL accounts and their balances. It's used to verify that debits equal credits and to identify any posting errors requiring correction.

These statements form the basis of external reporting to auditors, tax authorities, and investors.

## Reporting dimensions

Light's reporting engine segments transactions across multiple dimensions:

**Time periods**: Daily, monthly, quarterly, annual reporting at any granularity.

**Entities**: Report by individual company entity or consolidated across all entities.

**Currencies**: Report in transaction currency, local currency, or group currency.

**Departments/Cost centers**: Analyze performance by organizational unit.

**Business partners**: Segment P&L by customer or vendor.

**Custom dimensions**: Create analysis against your company-specific attributes.

You can combine any dimensions in a single report for sophisticated analysis.

> Good to know: Light maintains multi-period reporting history, allowing you to compare current year to prior year or budget to actual.

## Standard vs. custom reports

Light provides standard reports that every organization needs (balance sheet, P&L, cash flow) pre-configured and ready to use. These conform to IAS standards and GAAP.

For unique reporting needs, create custom reports using Light's report builder:

1. Navigate to **Planning & Reports → Reports**
2. Click **+ Create report**
3. Select a base report type (Balance Sheet, P&L, Cash Flow, or Blank)
4. Configure columns (periods, entities, currencies)
5. Configure rows (accounts, cost centers, business partners)
6. Add calculations and subtotals
7. Save the report

Light saves your custom report template for reuse.

## Real-time dashboard reporting

Beyond static reports, Light provides real-time dashboards:

- **Financial dashboard**: Key metrics updated continuously (revenue, expenses, margin, cash)
- **Balance sheet dashboard**: Assets, liabilities, equity visuals
- **Cash dashboard**: Cash position, inflows, outflows by category
- **Variance dashboard**: Actual vs. budget and actual vs. prior year
- **KPI dashboards**: Custom metrics specific to your business

Dashboards update in real-time as transactions post to the ledger.

## Multi-entity consolidation

When your organization includes multiple legal entities (subsidiaries, branches, divisions), consolidation combines them into a single set of financial statements:

1. Configure parent-subsidiary relationships in your entity structure
2. Light automatically identifies inter-company transactions
3. Light eliminates inter-company entries to prevent double-counting
4. Light translates foreign subsidiary results to group currency
5. Consolidated financial statements present the group as a single entity

This is essential for multinational companies operating through multiple legal structures.

## Multi-currency reporting

For organizations operating in multiple currencies:

- Report in transaction currency (the original invoice currency)
- Report in local currency (the entity's functional currency)
- Report in group currency (the consolidated currency)

Light calculates and maintains all three currency perspectives for every transaction, enabling flexible reporting.

## Variances and actuals-to-budget

Compare actual results to budget and to prior year:

1. Navigate to **Planning & Reports → Reports**
2. Select comparison: Actual vs. Budget or Actual vs. Prior Year
3. View variances by account, department, or business partner
4. Drill into transactions driving significant variances
5. Export detailed variance reports

This supports management review and decision-making.

## Exports and sharing

Export reports in multiple formats:

- **PDF**: For distribution and archiving
- **Excel**: For further analysis and presentation
- **CSV**: For loading into BI tools or data warehouses
- **Print-ready PDF**: Formatted for board presentations

Share reports through Light's platform:

1. Navigate to any report
2. Click **Share**
3. Select users to share with
4. Set permissions (view, edit)
5. Light tracks report access and modifications

## Audit trail on reporting

Light tracks all reporting activities:

- Who generated each report
- When it was generated
- Which parameters were used
- Whether the report was exported or shared

This provides evidence for audit procedures and demonstrates governance of financial reporting.

## Compliance reporting

Light supports compliance reporting for external stakeholders:

- **Auditor reports**: Complete ledgers, trial balances, and supporting schedules
- **Tax compliance reports**: VAT, AvaTax, income tax supporting documentation
- **Regulatory reports**: Entity-specific reporting per jurisdiction
- **Investor reports**: Summaries and schedules per investor agreements

Configure what data each report includes and who can access it.

## Report scheduling and automation

Automate recurring reports:

1. Create and save a custom report
2. Click **Schedule**
3. Select frequency: Daily, weekly, monthly, quarterly, annually
4. Select recipients (users, email addresses)
5. Light generates and distributes the report automatically

This reduces manual reporting work and ensures stakeholders receive timely information.

## Related articles

- [Balance sheet](10-2-balance-sheet.md)
- [Profit and loss](10-3-profit-loss.md)
- [Cash flow statement](10-4-cash-flow.md)
- [Trial balance](10-5-trial-balance.md)
- [Multi-entity consolidation](10-7-multi-entity-consolidation.md)
- [Custom reports and filters](10-9-custom-reports.md)
