# Data Import and Migration Tools

Light provides flexible data import capabilities for bringing data from spreadsheets, CSV files, and other systems. Whether setting up a new company or migrating from another accounting system, import tools streamline the process.

[Open in Light →](https://app.light.inc/settings/integrations)

## Import capabilities

Light supports importing:

- **Chart of accounts**: GL accounts and account structure
- **Customer and vendor master**: Customer and vendor information
- **Historical transactions**: Past invoices, bills, payments (with limits)
- **Opening balances**: GL account balances as of transition date
- **Inventory**: Products and SKUs
- **Fixed assets**: Asset register
- **Budgets**: Budget data for planning

This enables comprehensive data setup.

## Preparing import files

Data must be in structured format:

**Excel (.xlsx)**: Recommended format, most flexible

**CSV (.csv)**: Tab or comma-delimited text

**JSON**: For API-based imports

**Fixed-width text**: Legacy format (rarely needed)

File requirements:

- First row contains column headers (Account Code, Account Name, Balance, etc.)
- Data types must match (numbers, dates, etc.)
- No special characters in field names
- UTF-8 encoding (for international characters)

Prepare a sample file following Light's import template.

## Accessing import tools

Start an import:

1. Navigate to **Settings (gear icon) > Import Data**
2. Click **New Import**
3. Select import type (Chart of Accounts, Customers, Transactions, etc.)
4. Download import template (shows required and optional fields)
5. Fill template with your data
6. Upload file
7. Light validates and previews
8. Confirm and import

Light guides you through each step.

## Importing chart of accounts

Create your GL account structure:

1. Download COA template
2. Fill in:
   - **Account Code**: Unique identifier (1000, 1100, 1110)
   - **Account Name**: Descriptive name (Cash, Accounts Receivable, etc.)
   - **Account Type**: Asset, Liability, Equity, Revenue, Expense
   - **Parent Account**: (optional) Code of parent for hierarchical structure
3. Upload file
4. Light validates account codes are unique
5. Light creates GL accounts
6. You can now post transactions

> Good to know: Use consistent numbering for account codes (e.g., 1000s = assets, 2000s = liabilities). This makes navigation easier.

## Importing customer master

Load customer information:

1. Download customer template
2. Fill in:
   - **Customer ID**: Unique identifier (Acme, ACME-001)
   - **Customer Name**: Full company name
   - **Contact Name**: Primary contact person
   - **Email**: Customer email
   - **Billing Address**: Full address
   - **Phone**: Customer phone
   - **Terms**: Payment terms (Net 30, Net 60)
   - **Currency**: Default invoice currency
3. Upload file
4. Light validates customer IDs are unique
5. Light creates customer records
6. Customers are ready for AR invoicing

## Importing vendor master

Load vendor information:

1. Download vendor template
2. Fill in:
   - **Vendor ID**: Unique identifier
   - **Vendor Name**: Full company name
   - **Contact Name**: Primary contact
   - **Email**: Vendor email
   - **Payment Address**: Full address
   - **Phone**: Vendor phone
   - **Terms**: Payment terms
   - **Currency**: Default invoice currency
   - **Tax ID**: Vendor tax/VAT number
3. Upload file
4. Light validates vendor IDs are unique
5. Light creates vendor records
6. Vendors ready for AP invoicing

## Importing historical transactions

Migrate past transactions from old system:

1. Download transaction template
2. For each transaction, fill in:
   - **Document Type**: AP, AR, JE, etc.
   - **Date**: Transaction date
   - **Amount**: Total amount
   - **Customer/Vendor**: (for AR/AP)
   - **Description**: Transaction description
   - **Line items**: Account, amount, tax treatment
3. Upload file
4. Light validates amounts balance (debits = credits)
5. Light creates transactions in draft status
6. You review and approve before posting

This migrates transaction history.

> Important: Typically, only migrate current-year transactions and open receivables/payables. Close prior-year transactions with opening balance approach.

## Importing journal entries

Upload journal entries via CSV with the following format:

### Required columns

| Header | Description |
|--------|-------------|
| `entry id` | Groups lines into one journal entry |
| `date` | Posting date (YYYY-MM-DD) |
| `currency` | Currency code (e.g., USD, EUR) |
| `debit` | Debit amount |
| `credit` | Credit amount |
| `tax amount` | Tax amount |
| `account code` | Ledger account code |
| `tax code` | Tax code identifier |
| `entry description` | Description for the entry |
| `line description` | Description for the line |
| `business partner name` | Name of the business partner (required) |

### Optional columns

| Header | Description |
|--------|-------------|
| `business partner id` | UUID of the business partner |
| `local currency rate` | FX rate for local currency |
| `group currency rate` | FX rate for group currency |
| `ledger name` | e.g., PRIMARY, ELIMINATION |
| `target entity code` | For intercompany entries |
| `accounting release template id` | Template for amortization |
| `accounting release start date` | Amortization start |
| `accounting release end date` | Amortization end |

### Business partner fields

- **business partner name** — Required string field. Must match an existing customer or vendor name in Light.
- **business partner id** — Optional field. If provided, must be a valid UUID of an existing business partner.

> Good to know: Use `entry id` to group multiple lines into a single journal entry. All lines with the same `entry id` will be combined into one balanced entry.

## Opening balance import

Set GL account starting balances:

1. Download opening balance template
2. Fill in:
   - **Account Code**: GL account
   - **Balance**: Opening balance amount (positive or negative)
3. Upload file
4. Light validates balances sum correctly (for each GL side)
5. Light creates opening balance JE
6. All GL accounts initialized with correct starting balances

This sets up accounting starting position.

## Data validation

Light validates all imports:

- **Format validation**: Correct data types, required fields present
- **Reference validation**: Customer/vendor/account codes exist
- **Amount validation**: Amounts are numeric, balance properly
- **Duplicate validation**: No duplicate IDs
- **Consistency validation**: Related data matches

If validation fails, Light provides error report showing exactly what to fix.

## Import preview

Before committing, review import preview:

1. After uploading file, Light shows preview
2. Review first 10-20 rows to verify data looks correct
3. Check that field mapping is correct (columns mapped to right fields)
4. If preview looks good, confirm
5. If issues, cancel and fix file

The preview catches most errors before they're created.

## Handling import errors

If import fails validation:

1. Light displays error report
2. Error report shows:
   - Row number with error
   - Field that failed
   - Error message (duplicate, wrong type, etc.)
3. Fix the issue in your file
4. Re-upload and re-validate
5. Once validation passes, import succeeds

Iterative approach ensures clean data import.

## Bulk updates

Update existing data in bulk:

1. Export current data from Light (e.g., customer list)
2. Make updates in Excel
3. Upload updated file
4. Light matches to existing records and updates

This enables bulk changes without manual entry.

## Multi-currency import

When importing with multiple currencies:

1. Include currency column in template
2. Specify currency code (USD, EUR, GBP) for each transaction
3. Light converts to GL currency using historical rates (if needed)
4. All amounts recorded correctly in GL

This handles multi-currency imports.

## Scheduled imports

Automate recurring imports from external systems:

1. Navigate to **Settings > Import > Scheduled Imports**
2. Create scheduled import:
   - File location (SFTP, cloud storage, API endpoint)
   - Import frequency (daily, weekly, monthly)
   - File format and field mapping
3. Light automatically imports on schedule
4. Failures trigger alerts for investigation

This automates ongoing data sync.

## Import audit trail

Light maintains complete audit of all imports:

1. Navigate to **Settings > Import > Audit Trail**
2. View:
   - Date/time of import
   - File name and size
   - Number of records imported
   - User who triggered import
   - Changes made
3. Export audit trail for compliance

This provides evidence of data integrity.

## Rollback failed imports

If an import creates bad data:

1. Navigate to **Settings > Import > [Failed Import]**
2. Click **Rollback**
3. Light reverses all changes from that import
4. Accounts return to pre-import state
5. Fix the import file and re-import

This enables recovery from failed imports.

## Best practices for importing

**Test first**: Always test imports with sample data before importing full dataset.

**Validate data**: Verify source data is clean before importing (no duplicates, required fields populated).

**Plan mapping**: Understand which source fields map to which Light fields.

**Backup first**: Create a backup before bulk imports (in case rollback needed).

**Schedule off-peak**: Import during off-peak times to avoid impacting users.

**Monitor closely**: After import, review results and verify accuracy before considering complete.

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [Data migration from E-Conomic](11-14-migration-economic.md)
- [Data migration from QuickBooks](11-15-migration-quickbooks.md)
- [Cutover fundamentals and execution](11-16-cutover.md)
- [API access and custom integrations](11-12-api-access.md)
