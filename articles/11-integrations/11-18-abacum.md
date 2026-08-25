# Abacum Integration

Light shares your ledger data with Abacum, the financial planning & analysis platform, through a dedicated S3 bucket. Light provisions the connection, and once both sides are set up, your data syncs once a day.

[Open in Light →](https://app.light.inc/settings/integrations)

## Setting up your Light connection

Light's team handles the Light side; the steps you carry out yourself happen in Abacum.

1. Contact your Light representative to request data sharing with Abacum.
2. Light's engineering team provisions a dedicated S3 bucket and credentials for your company, and configures which data exports to it. Both are manual steps, so allow time.
3. Light provides your credentials (**Access key ID**, **Secret access key**, **S3 Bucket name**).
4. In Abacum, go to **Integrations**.
5. Select **Light via S3** and click **Connect**.
6. Enter the **Access key ID**, **Secret access key**, and **S3 Bucket name** Light gave you.
7. Click **Connect to Amazon S3**.

> Good to know: your credentials are unique to your company and scoped to your bucket alone. If a key is compromised, contact Light support to rotate it.

If your bucket is still empty a day after setup (no CSV files), the export config on Light's side is incomplete — contact Light support.

## What data is synced

Light drops CSV files into your bucket. There are two CSV schemas, and a customer typically receives three files per posting month:

- **Balance Sheet** (`BALANCESHEET…csv`) — a report of actuals.
- **Trial Balance** (`TRIALBALANCE…csv`) — a report of actuals.
- **Ledger transaction lines** — GL transaction lines by posting month, enriched with entity names and custom properties.

Which reports you get is configurable — Balance Sheet and Trial Balance are the common pair, but Income Statement, Cash Flow, General Ledger, and VAT reports are also supported. The export covers actuals only; budget data stays in Light.

## Sync frequency

The job runs once a day at **02:00 UTC**. Each run re-exports the last 12 posting months — one CSV file per month per dataset (file names end `…YYYY_MM.csv`). Reports run off the current date (so a month's report is available on the 1st of the following month); transaction lines run off the previous day.

## Excluded postings

Transaction lines exclude:

- Year-closing entries (document type `YC`)
- Elimination-offset lines (the auto-generated counterparts of inter-company eliminations); the original transactions remain

## File conventions

- Encoding UTF-8; comma-delimited; values with commas/quotes/newlines are double-quoted, embedded quotes doubled.
- Dates ISO `YYYY-MM-DD`; currencies ISO 4217.
- Sign convention: debits positive, credits negative.
- Report files carry a leading `date` column (the posting month's closing date) so you can union months. Transaction-line files do not — they begin with `id` and carry `posting_date`.

## Reconciliation

For any GL account, its closing balance on a report equals the running sum of transaction-line `group_amount` values posted up to the file's date.

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [Budget scenarios and overview](../10-reporting/10-10-budget-scenarios.md)
- [Profit and loss](../10-reporting/10-3-profit-loss.md)
- [Multi-entity consolidation](../10-reporting/10-7-multi-entity-consolidation.md)
