# Exporting Reports

Light exports report data as CSV so you can open it in a spreadsheet application, import it into a BI tool, or share it with auditors and stakeholders.

[Open in Light →](https://app.light.inc/ledger-reports)

## Exporting a report

1. Open any report in **Planning & Reports → Reports**
2. Apply your filters (entity, date range, currency, comparison period)
3. Click the **Export** button
4. Light downloads a CSV file to your browser's default downloads folder

**Filename format:**
- Period reports: `{reportName}_{startDate}_to_{endDate}.csv`
- Snapshot reports (e.g. Balance Sheet): `{reportName}_as_of_{endDate}.csv`

## What the CSV contains

The exported file mirrors what you see on screen:
- Row labels in the first column (indented to reflect hierarchy)
- One column per entity, consolidation field (Subtotal, Elimination, Total), or comparison period
- Header rows showing entity names and period labels
- Rows with all-zero values are excluded for standard system reports

## CSV separator

The separator character (comma or semicolon) follows your organisation's locale setting. If you need to change it, update your CSV separator preference in settings.

## Exporting a drilldown

The drilldown view (opened by clicking a cell in any report) also has its own **Export** button. This exports the underlying ledger transaction lines for that cell as a separate CSV.

## Sharing a report link

Every report in Light has a stable URL. To copy the link:

1. Navigate to **Planning & Reports → Reports**
2. Click the menu (⋮) on any report
3. Select **Link** — the URL is copied to your clipboard

Anyone with access to Light and the appropriate permissions can open the link directly. This is the intended way to share a report with a colleague.

## Formatting and presenting exported data

After exporting, open the CSV in Excel or Google Sheets to:
- Apply formatting, fonts, and colours for presentations
- Build charts and visualisations
- Add narrative commentary for board packs or management reports
- Save as PDF for external distribution

## Common export use cases

**Auditor requests** — Export trial balance, balance sheet, P&L, and aged AP/AR reports as CSV. Auditors can import these directly into their analysis tools.

**Tax compliance** — Export transaction detail by tax code to support VAT returns and income tax schedules.

**BI and analytics tools** — Import CSVs into Tableau, Power BI, Looker, or similar tools for advanced visualisation.

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Custom reports and filters](10-9-custom-reports.md)
- [Audit-ready record keeping](../09-revenue-compliance/9-9-audit-ready-records.md)
