# Exporting and Sharing Reports

Financial reports need to be shared with stakeholders: management, investors, auditors, tax authorities, and board members. Light provides flexible export and sharing capabilities, enabling you to distribute reports in the format each stakeholder needs.

[Open in Light →](https://app.light.inc/ledger-reports)

## Report export formats

Export reports in multiple formats:

**PDF**: Professional, formatted for printing and presentation. Preserves fonts, colors, and layout. Ideal for formal reporting, distribution, and archiving.

**Excel**: Allows recipients to recalculate, adjust, and further analyze. Preserves formulas if supported. Good for internal management review and variance analysis.

**CSV**: Raw comma-separated data for loading into other systems, BI tools, or databases. No formatting, just pure data.

**HTML**: Web-viewable format for sharing via email or posting to internal portals.

## Exporting a single report

To export a report:

1. Navigate to any report in Light
2. Click **Export**
3. Select format (PDF, Excel, CSV, HTML)
4. Configure export options:
   - **Columns to include**: Choose which columns to export (useful for narrowing export scope)
   - **Rows to include**: Specify if you want summary only, or detail lines also
   - **Formatting**: For Excel/PDF, include/exclude formatting (colors, fonts)
5. Click **Export**
6. Light generates and downloads the file

Your browser downloads the file in your default downloads folder.

## Batch exporting multiple reports

Export several reports at once:

1. Navigate to **Planning & Reports → Reports**
2. Select multiple saved reports to export
3. Select format (all will export in same format)
4. Click **Export All**
5. Light generates a ZIP file containing all reports
6. Download and extract

This saves time when distributing multiple reports to the same group.

## Email distribution

Send reports automatically via email:

1. Open any report
2. Click **Share**
3. Select **Email**
4. Enter email addresses (recipient list)
5. Optionally add message
6. Select format (PDF, Excel, CSV)
7. Click **Send**

Light emails the report to recipients immediately.

> Tip: Use email distribution to send monthly reports automatically. Recipients get the report immediately without manual work.

## Scheduled distribution

Automate recurring report distribution:

1. Open a saved report
2. Click **Schedule Distribution**
3. Enter recipient list (users or email addresses)
4. Select frequency (weekly, monthly, quarterly, annually)
5. Select format (PDF, Excel, or both)
6. Optionally add message text
7. Click **Schedule**

Light generates and distributes the report automatically on the schedule.

## Access control and sharing permissions

Control who can access reports:

1. Generate or open a report
2. Click **Share**
3. Select users or teams to grant access
4. Set permission level:
   - **View**: Read-only access
   - **Edit**: Can view and modify filters/formatting (but not underlying data)
   - **Full**: Can view, modify, and share with others
5. Click **Share**

Light tracks access and restricts based on permissions.

## Shared report library

Create a library of shared reports for your organization:

1. Navigate to **Planning & Reports → Reports**
2. See all reports shared with you
3. Click any report to view or export
4. Search or filter by:
   - Report name
   - Owner (who created/shares the report)
   - Last updated date
   - Report type (balance sheet, custom, etc.)

This creates a central repository reducing duplicate work.

## White-label PDFs

For client-facing reports, customize PDF formatting:

1. Navigate to **Settings (gear icon)** to customize PDF branding
2. Upload logo (appears in PDF header)
3. Add footer text (company name, confidentiality notice, website)
4. Select colors and fonts
5. Save branding

Light applies branding to all exported PDFs automatically.

## Watermarking sensitive reports

Add watermarks to sensitive reports:

1. Export report as PDF
2. In PDF export options, select **Add Watermark**
3. Choose watermark text: "CONFIDENTIAL", "DRAFT", "FOR DISCUSSION ONLY", etc.
4. Light applies watermark to entire PDF

This provides visual indication of sensitivity/status.

## Report annotation and sign-off

For formal reporting, capture approval:

1. Export report as PDF
2. Circulate to approver (email, portal)
3. Approver reviews, signs (digitally or printed)
4. Archive signed report

Light integrates with e-signature tools to streamline approval workflows.

## Linking reports in documents

Reference reports in other documents:

1. Export report and save file name
2. In presentations or documents, insert link to report file
3. Recipients can click to view/download

This is useful when multiple reports support a decision or analysis.

## Comparison reports for presentations

When presenting variances or trends:

1. Create custom report showing budget vs. actual with variance %
2. Highlight significant variances (>threshold)
3. Export to Excel
4. Create charts for presentation deck
5. Reference supporting report for detail

This provides both high-level visual summary and supporting detail.

## Report archiving

Maintain archive of historical reports:

1. Export reports for each period (monthly, quarterly, annual)
2. Name by period (e.g., "P&L_2025_January", "Balance Sheet_2024_Year End")
3. Store in shared folder or Light's document repository
4. Allows comparison to historical periods

Archiving supports audit procedures and trend analysis.

## Financial statement presentation

Format financial statements for presentation or SEC filing:

1. Export balance sheet, P&L, cash flow as PDF
2. Light includes standard formatting:
   - Proper indentation and account classification
   - Subtotals and totals properly labeled
   - Currency clearly indicated
3. Add footnotes and disclosures
4. Submit to regulators or investors

## Auditor data requests

Financial auditors request extensive data. Light simplifies fulfillment:

1. Create a reporting template package:
   - Trial balance (as-of date)
   - Balance sheet and P&L (date and period)
   - Account detail schedules (major accounts)
   - Reconciliation schedules (AR aging, AP aging, bank rec, fixed assets)
   - Consolidation working papers (if applicable)
2. Export all reports at once as ZIP
3. Send to audit firm

Auditors receive comprehensive data with proper formatting and structure.

## Real estate and lease data export

For lease accounting or real estate analysis:

1. Create report showing:
   - Lease obligations by property
   - Right-of-use asset detail
   - Lease expense schedule
2. Export to Excel
3. Lease accountant uses for subledger reconciliation

## Budget vs. actual for board presentations

Prepare executive summaries:

1. Create variance report: Budget vs. Actual
2. Filter to show only significant items (>$1M or >10% variance)
3. Add explanatory narratives for material variances
4. Export as PDF for board book

This provides governance-level summary without overwhelming detail.

## Customer and vendor reports for stakeholders

Share limited reports with external stakeholders:

1. Create statement showing customer account balance, aging, recent transactions
2. Export as PDF
3. Share with customer for their records

Similarly for vendors, showing your outstanding payables.

## Tax compliance reporting

Package tax data for filing or audit:

1. Create tax transaction detail report (by tax code)
2. VAT return supporting documentation
3. Income tax supporting schedules
4. Export as package
5. Send to tax advisor or file with returns

## Data import to BI and analytics tools

Export data for business intelligence:

1. Create report showing underlying transactions (not summarized)
2. Export as CSV
3. Import to analytics tool (Tableau, Power BI, Looker)
4. Create advanced visualizations and dashboards

This bridges Light's reporting to specialized analytics tools.

## Performance benchmarking

Compare your financial metrics to industry:

1. Extract your financial data as CSV
2. Input industry benchmarks
3. Compare in Excel or BI tool
4. Identify areas for improvement

Light provides the data; external benchmarking sources provide comparison targets.

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Custom reports and filters](10-9-custom-reports.md)
- [Real-time dashboards and KPIs](10-12-dashboards-kpis.md)
- [Audit-ready record keeping](../09-revenue-compliance/9-9-audit-ready-records.md)
