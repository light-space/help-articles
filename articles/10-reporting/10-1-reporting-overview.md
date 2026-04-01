# Reporting Overview

Light's reporting engine generates financial statements, custom reports, and pivot tables directly from your ledger. This article explains the report types available and how to use the core reporting features.

[Open in Light →](https://app.light.inc/ledger-reports)

## Core financial statements

Light includes pre-built system reports for the four primary financial statements:

**Balance Sheet** shows your financial position at a point in time: assets (what you own), liabilities (what you owe), and equity (owners' stake).

**Income Statement (P&L)** shows your financial performance over a period: revenues earned, expenses incurred, and resulting profit or loss.

**Cash Flow Statement** shows how cash moved across operating, investing, and financing activities.

**Trial Balance** lists all GL accounts and their debit/credit balances. Used to verify posting accuracy.

System reports are read-only and cannot be edited or deleted.

## Report types

Light has three types of reports you can create:

**Table** — A custom report template built with a formula-based row and column structure. You define up to 5 columns (A–E) with editable labels and build rows using formula references and tax tags. Rows can be hierarchical (parent/child). This is the format used by all system financial statements.

**Pivot table** — A flexible cross-tabulation of your ledger data. You choose dimensions (rows and columns) and a measure (transaction amount, local amount, or group amount), then apply filters. Useful for ad hoc analysis across entities, accounts, currencies, business partners, and custom properties.

**Text to chart (beta)** — An AI-powered report generator. Describe what you want to see and Light produces a structured table or chart from your ledger data.

## Navigating to reports

Go to **Planning & Reports → Reports** to see your full report list.

The list shows **Name**, **Type**, and **Last updated** for each report. Click any row to open it.

Each report has a menu (⋮) with three actions:
- **Link** — copies the report URL to your clipboard for sharing
- **Duplicate** — creates a copy (available for Table and Pivot table types)
- **Delete** — permanently removes the report (custom reports only; system reports cannot be deleted)

## Creating a report

1. Navigate to **Planning & Reports → Reports**
2. Click **+ Create report**
3. Choose a type from the dropdown:
   - **Pivot table** — opens the pivot table builder
   - **Table** — opens the report template editor
   - **Text to chart (beta)** — opens the AI report assistant

## Report filters

When viewing any report you can control what data is shown:

**Entity** — Select a single entity, multiple entities, or switch to **Consolidated** view (which combines all selected entities and shows subtotals, eliminations, and a group total).

**Date range** — Select start and end dates. Snapshot reports (e.g. Balance Sheet) use a single as-of date.

**Currency** — Two options:
- **Entity Crcy** (local) — reports each entity in its own functional currency
- **Group Crcy** (group) — reports all entities translated to the group currency

> Note: Entity currency cannot be used when multiple entities with different currencies are selected simultaneously.

**Comparison** — Add a prior period or prior year alongside the current period:
- Compare with 1, 3, 6, 9, or 12 months back
- Compare with 1, 2, or 3 years back

**Custom properties** — Filter report data by any custom property values configured in your organisation.

## Exporting reports

Reports can be exported as **CSV**. Click the export button on any report to download a CSV file named `{reportName}_{startDate}_to_{endDate}.csv`.

The CSV includes all rows and columns as displayed, respecting your CSV separator setting. You can open the file in Excel, Google Sheets, or import it into a BI tool for further analysis and presentation.

## Drilldown

Click any cell value in a report to drill into the underlying ledger transactions. The drilldown view shows the individual postings that make up that figure, and can be filtered by posting date, currency, amount, document type, and entity. Drilldown results can also be exported as CSV.

For aged AP and aged AR reports, the drilldown shows invoices grouped by due date ranges.

## Multi-entity consolidation

Select multiple entities and switch to **Consolidated** view to see:
- A column per entity
- A **Subtotal** column (sum of all entities)
- An **Elimination** column (intercompany offsets)
- A **Total** column (consolidated result)

You can drag to reorder entity columns using the entity order control.

## Multi-currency reporting

All reports support two currency views:
- **Entity Crcy** — each entity in its functional currency (useful for entity-level review)
- **Group Crcy** — all entities translated to the group currency (required for consolidation)

## Home dashboard

The **Home** page (`/dashboard`) provides a summary view with fixed widgets showing your bank account balances, pending tasks, card accounts, and a budget YTD accuracy summary. This is a read-only overview and is not customisable.

## Related articles

- [Balance sheet](10-2-balance-sheet.md)
- [Profit and loss](10-3-profit-loss.md)
- [Cash flow statement](10-4-cash-flow.md)
- [Trial balance](10-5-trial-balance.md)
- [Tables and pivot reports](10-6-tables-pivot-reports.md)
- [Multi-entity consolidation](10-7-multi-entity-consolidation.md)
- [Custom reports and filters](10-9-custom-reports.md)
- [Budget scenarios](10-10-budget-scenarios.md)
