# Multi-Entity Consolidation

Light's consolidated report view combines the financial results of multiple entities into a single report, with a dedicated column for intercompany eliminations. This article explains how to run consolidated reports and how the consolidation view works.

[Open in Light →](https://app.light.inc/ledger-reports)

## What consolidation shows

When you select multiple entities and switch to consolidated view, the report displays:

| Column | Description |
|---|---|
| **[Entity name]** | One column per selected entity showing that entity's figures |
| **Subtotal** | Sum of all individual entity columns |
| **Eliminations** | Intercompany amounts flagged for elimination (see [Intercompany documents](/articles/05-general-ledger/5-11-intercompany-documents.md)) |
| **Consolidated** | Subtotal minus Eliminations — the final consolidated figure |

## Running a consolidated report

1. Navigate to **Planning & Reports → Reports**
2. Open any financial statement report (Balance Sheet, P&L, etc.)
3. In the entity selector, click **Consolidated**
4. Select the entities to include
5. Set the date range, currency, and any other filters
6. The report renders with per-entity columns plus Subtotal, Eliminations, and Consolidated

> **Good to know:** The "Consolidated" option appears at the top of the entity selector dropdown alongside individual entities.

## Filters in consolidated view

| Filter | Notes |
|---|---|
| **Entity selector** | Multi-select with a **Consolidated** toggle at the top |
| **Date range** | Start and end date for the report period |
| **Currency** | **Entity Crcy** (each entity in its own functional currency) or **Group Crcy** (all entities translated to the group currency). Note: Entity Crcy cannot be used when selected entities have different currencies |
| **Comparison** | Compare with 1, 3, 6, 9, or 12 prior months, or 1, 2, or 3 prior years |
| **Custom properties** | Filter report data by custom property values |

## Comparison mode and consolidated view

When a comparison period is selected in consolidated view, the report hides individual entity columns and shows only:
- **Consolidated** — current period consolidated figure
- **Consolidated [comparison label]** — the prior period consolidated figure

This keeps the report readable when comparing across time.

## Reordering entity columns

Click **Entity order** (the ↕ icon button above the report) to reorder the entity columns via drag and drop. The updated order is saved and persists for all users.

## Drilldown in consolidated view

Click any cell to drill into the underlying ledger transactions:

- **Clicking an entity column** — drilldown is filtered to that entity only. The drilldown title shows the row label (e.g. *Accounts Receivable*).
- **Clicking the Subtotal, Eliminations, or Consolidated column** — drilldown spans all entities. The title shows the row label plus the column type (e.g. *Accounts Receivable — Consolidated*).

Drilldown results can be filtered further and exported as CSV.

## How eliminations are calculated

Eliminations are driven by the **Intercompany configuration** set up in **Accounting → Chart of accounts**. Lines flagged with the **Eliminate** toggle in intercompany journal entries are included in the Eliminations column. For more detail, see [Intercompany documents](/articles/05-general-ledger/5-11-intercompany-documents.md).

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Multi-currency consolidation](10-8-multi-currency-consolidation.md)
- [Intercompany documents](/articles/05-general-ledger/5-11-intercompany-documents.md)
- [Balance sheet](10-2-balance-sheet.md)
- [Profit and loss](10-3-profit-loss.md)
