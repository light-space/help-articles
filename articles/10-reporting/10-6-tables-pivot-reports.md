# Pivot Table Reports

Pivot tables let you cross-tabulate your ledger data across any combination of dimensions — entity, account, business partner, currency, tax code, and more. Unlike the formula-based Table report, a pivot table is driven by dimension and measure selection rather than manual row definitions.

[Open in Light →](https://app.light.inc/ledger-reports)

## Creating a pivot table

1. Navigate to **Planning & Reports → Reports**
2. Click **+ Create report**
3. Select **Pivot table** from the dropdown
4. The pivot table builder opens with a two-panel layout:
   - **Left panel** — configuration (chart name, values, rows, columns)
   - **Right panel** — table preview and filters

## Configuring the pivot table

### Chart name

Enter a name for the report (required). This is what appears in the reports list.

### Values

Select the **single measure** to aggregate in each cell:

| Option | Description |
|---|---|
| **Transaction amount** | Amount in the original transaction currency |
| **Local amount** | Amount in the entity's functional currency |
| **Group amount** | Amount translated to the group currency |

### Rows and Columns

Select up to **2 dimensions** for rows and up to **2 dimensions** for columns. A dimension cannot be used in both rows and columns at the same time.

Available dimensions:

| Dimension | Notes |
|---|---|
| **Document type** | AP, AR, JE, etc. |
| **Transaction currency** | The currency of the original transaction |
| **Account type** | Asset, liability, revenue, expense, etc. |
| **Account** | Individual GL account |
| **Tax code** | Tax code applied to the line |
| **Tax type** | Grouped tax type |
| **Company entity name** | The posting entity |
| **Target company entity name** | For intercompany transactions |
| **Business partner ID** | Customer or vendor identifier |
| **Business partner name** | Customer or vendor name |
| **Business partner type** | Customer, vendor, etc. |
| **Debit / Credit** | D or C sign of the line |
| **Month** | Calendar month |
| **Year** | Calendar year |
| **Custom properties** | Any custom property group configured in your organisation |

Each selected dimension has an **Ascending / Descending** sort order selector.

### Testing and saving

1. Click **Test table** (bottom of the left panel) to generate a preview in the right panel
2. Review the results — apply filters if needed (see below)
3. Click **Save table** (top right) to save the report

## Filters

While building or viewing a pivot table, use the filter bar in the right panel to narrow the data:

| Filter | Notes |
|---|---|
| **Company entity** | One or more entities |
| **Posting date** | Date range |
| **Document type** | One or more document types |
| **Transaction currency** | One or more currencies |
| **Ledger account** | One or more GL accounts |
| **Account type** | One or more account types |
| **Report category** | P&L, Balance Sheet, etc. |
| **Tax** | One or more tax codes |
| **Tax type** | One or more tax types |
| **Business partner** | One or more partners |
| **Business partner type** | Customer, vendor, etc. |
| **Debit / Credit** | Debit or credit sign |
| **Custom property** | Any configured custom property (multiple instances allowed) |

## Viewing a saved pivot table

Open any saved pivot table from **Planning & Reports → Reports**. The view shows:
- Report title and description
- Filter bar
- Pivot table data
- **Download** button — exports the current view as CSV
- **Edit** button — reopens the configuration panel to modify rows, columns, and values

## Drilldown

Click any cell in the pivot table to open the drilldown view. This shows the individual ledger transaction lines that make up that cell's value, with infinite scrolling, column visibility controls, and a CSV export button.

The drilldown totals column depends on the selected measure:
- **Transaction amount** → totals in transaction currency
- **Local amount** → totals in local currency
- **Group amount** → totals in group currency

## Editing a pivot table

1. Open the saved pivot table
2. Click **Edit**
3. Modify the chart name, values, rows, columns, or order
4. Click **Test table** to preview changes
5. Click **Save table** to update

## Duplicating a pivot table

1. Go to **Planning & Reports → Reports**
2. Click the menu (⋮) on a pivot table report
3. Select **Duplicate**

The copy opens in edit mode with a timestamp appended to the name.

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Custom reports and filters](10-9-custom-reports.md)
- [Exporting reports](10-11-exporting-reports.md)
