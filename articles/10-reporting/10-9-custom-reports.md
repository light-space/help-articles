# Custom Reports

Light's custom report builder lets you create Table reports — structured row-and-column layouts driven by formulas — alongside Pivot tables and AI-generated charts. This article focuses on the **Table** report type, which is the same format used by all of Light's built-in financial statements.

[Open in Light →](https://app.light.inc/ledger-reports)

## Creating a Table report

1. Navigate to **Planning & Reports → Reports**
2. Click **+ Create report**
3. Select **Table** from the dropdown
4. The template editor opens with a blank form

## Template header settings

At the top of the editor, configure the template properties:

| Field | Required | Notes |
|---|---|---|
| **Template name** | ✅ | Displayed in the reports list |
| **Country** | — | Enables country-specific tax tag autocomplete in formulas |
| **Period** | ✅ | Controls how date filters work when the report is run |
| **Exclude year-end transactions** | — | Checkbox — excludes year-closing journal entries from results |

**Period options:**

| Option | Description |
|---|---|
| **Range** | User picks a start and end date when running the report |
| **Monthly** | Report is scoped to a single calendar month |
| **Quarterly** | Report is scoped to a single quarter |
| **Yearly** | Report is scoped to a full year |

## Building the row structure

Rows define what appears in the report. Each row has a **label** and formula cells for each column.

**Adding rows:**
- Click **+ Add row** at the bottom of the table to append a new row
- Hover over any row number to reveal the row actions menu (⋮):
  - **Insert 1 row above**
  - **Insert 1 row below**
  - **Insert child row** — creates an indented sub-row under the current row
  - **Delete row** — deletes the row and all its child rows (requires confirmation)

**Row hierarchy:**
Rows can be nested to create parent/child groupings. Child rows are indented visually by their depth level. Deleting a parent row removes all its children.

## Working with columns

New templates start with a single column (**A**). You can add up to 5 columns (A–E).

- Click **+** in the last column header to add a new column
- Click the column letter (e.g. **A.**) to open the column menu:
  - **Rename** — edit the column label directly in the header
  - **Delete column** — clears all formulas in that column (requires confirmation)

## Writing formulas

Each row/column cell uses a single-line formula editor with autocomplete. Light supports the following functions:

| Function | Syntax | Description |
|---|---|---|
| `SUM` | `SUM(A1, B3, -A4)` | Sums the values of referenced cells in this template |
| `ACP` | `ACP(4, 5, -6)` | Itemises and sums accounts whose code starts with the given prefix |
| `ACPSUM` | `ACPSUM(2, -3, 4)` | Same as ACP but summarised into a single value |
| `ACT` | `ACT(REVENUE, -COST_OF_SALES)` | Itemises and sums accounts by account type |
| `ACTSUM` | `ACTSUM(REVENUE, -COST_OF_SALES)` | Same as ACT but summarised |
| `ACTCUR` | `ACTCUR(BANK, CARD, CASH_AND_EQUIVALENTS)` | Sums accounts by type in their account currency (for bank/cash accounts) |
| `TAXTAG` | `TAXTAG(UK_0, -UK_4)` | Sums amounts by tax tag (only available when a country is set on the template) |

**Tips:**
- Prefix an argument with `-` to subtract it (e.g. `ACP(4, -5)` adds account-code-4 and subtracts account-code-5)
- Use `SUM` to reference other cells in the template — for example `SUM(A1, A2, A3)` to total three rows
- Autocomplete activates as you type and shows context-sensitive suggestions (account types inside `ACT()`, cell references inside `SUM()`, tax tags inside `TAXTAG()`)

## Saving and reusing templates

Click **Save** in the top bar to save the template. The report is immediately available in the reports list under **Planning & Reports → Reports**. Saved templates regenerate with current data every time you open them — no need to reconfigure.

To rename a saved report, edit the template name field and click **Save** again.

## Running a report

Open any saved Table report from the reports list. Use the filters at the top to control the output:

- **Entity** — single entity, multiple entities, or Consolidated view
- **Date range** — determined by the template's Period setting
- **Currency** — Entity Crcy (local) or Group Crcy (group)
- **Comparison** — compare against 1–12 prior months or 1–3 prior years
- **Custom properties** — filter by any custom property value

Click any cell value to drill into the underlying ledger transactions.

## Duplicating a report

To create a variation of an existing template:

1. Go to **Planning & Reports → Reports**
2. Click the menu (⋮) on any Table report
3. Select **Duplicate**

The copy opens with a timestamp appended to the name. Edit and save as needed.

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Tables and pivot reports](10-6-tables-pivot-reports.md)
- [Exporting reports](10-11-exporting-reports.md)
