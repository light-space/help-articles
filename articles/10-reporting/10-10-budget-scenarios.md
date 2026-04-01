# Budget Scenarios

Light's budget feature lets you upload one or more budget scenarios as CSV files and compare them against your actual ledger data. You can maintain multiple scenarios simultaneously — for example a base plan and a revised forecast — and switch between them in the overview.

[Open in Light →](https://app.light.inc/budget)

## Uploading a budget scenario

Budgets are uploaded as CSV files. Light does not have a manual budget entry interface.

1. Navigate to **Planning & Reports → Budget**
2. Click **+ Upload budget**
3. In the **Upload budget** dialog:
   - Drag and drop a CSV file, or click to browse
   - Use the **Download template** button to get the correct CSV structure
   - Click **Upload**
4. Light processes the file. The scenario appears in the list with a **Synching...** status while it is being processed
5. Once complete the status changes to **Complete**. If the file fails validation the status shows **Failed** with an error tooltip

> **Good to know:** Only CSV files are accepted. Download the template from the upload dialog to ensure your file is structured correctly.

## Budget dimensions

Each uploaded scenario has up to three hierarchical dimension levels, determined by the columns in your CSV. Supported dimension types are:

| Dimension type | Description |
|---|---|
| Account | GL account |
| Account code | GL account code |
| Account label | GL account label |
| Business partner | Customer or vendor |
| Company entity | Legal entity |
| Custom property | Any custom property group configured in your organisation |

Dimensions are read-only after upload. To change dimensions, upload a new scenario.

## Managing scenarios

All uploaded scenarios are listed in the **Budget** settings view with the following columns:

| Column | Description |
|---|---|
| **Budget name** | Editable — click to rename |
| **Levels** | The dimension types in this scenario (shown as badges) |
| **Status** | Complete, Synching..., or Failed |
| **Created by** | The user who uploaded the scenario |
| **Created at** | Upload timestamp |

You can filter the list by status and search by name. Failed scenarios show an error description on hover.

## Budget overview

The **Overview** tab shows how your actuals compare to the selected budget scenario.

### Filters

| Filter | Notes |
|---|---|
| **Budget scenario** | Required — select which uploaded scenario to compare against |
| **Report category** | Defaults to Profit & Loss |
| **Ledger account** | Narrow to specific accounts |
| **Ledger account type** | Filter by account type |
| **Ledger account classification** | Filter by classification |
| **Date range** | The period to analyse |

### Summary statistics

- **YTD planned accuracy** — the ratio of actual to planned amounts expressed as a percentage. Above 100% means spending exceeded plan.
- **YTD variance** — the difference between planned and actual amounts in your group currency. Negative values are shown in parentheses.

### Actuals vs. planned chart

A bar chart showing per-period data with three series:
- **Actual** — what was recorded in the ledger (dark blue bars)
- **Approved** — approved budget amounts (light blue bars)
- **Planned** — the uploaded budget figure (white line)

### Budget table

The table below the chart shows the full breakdown by account and period. Click any cell to drill into the underlying ledger transactions for that figure.

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Profit and loss](10-3-profit-loss.md)
- [Custom reports and filters](10-9-custom-reports.md)
