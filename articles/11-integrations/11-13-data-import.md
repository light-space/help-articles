# Data Import and Migration Tools

Light provides flexible data import capabilities for bringing data from spreadsheets, CSV files, and other systems. Whether setting up a new company or migrating from another accounting system, import tools streamline the process.

[Open in Light →](https://app.light.inc/settings/integrations)

## Import capabilities

Light supports importing:

- **Chart of accounts**: GL accounts and account structure
- **Vendor master**: Vendor information (customers are created individually or via the API)
- **Historical transactions**: Past sales invoices, bills, credit notes, and customer credits — each via its own CSV import
- **Journal entries**: Bulk journal entries, including opening balances
- **Budgets**: Budget data for planning

This enables comprehensive data setup.

> Good to know: Light does not support importing a fixed asset register directly. To enter fixed assets, create a journal entry, bill, or sales invoice with a **Fixed Asset** release template applied on one or more lines. The fixed asset register itself lives at [**Accounting → Releases**](https://app.light.inc/releases) — filter the page by **Fixed asset** type to view only fixed assets. See [Configuring releases: depreciation, prepayments, deferred revenue](../09-revenue-compliance/9-2-configuring-releases.md) for details.

## Preparing import files

Data must be in structured format:

**CSV (.csv)**: Used by most imports (journal entries, vendors, transactions, budgets)

**Excel (.xlsx)**: Supported for chart of accounts imports

File requirements:

- First row contains column headers (Account Code, Account Name, Balance, etc.)
- Data types must match (numbers, dates, etc.)
- No special characters in field names
- UTF-8 encoding (for international characters)

Prepare a sample file following Light's import template.

## Accessing import tools

Each import lives on the page for the records it creates, rather than a single central import screen:

- **Chart of accounts**: [Settings (gear icon) → Chart of accounts](https://app.light.inc/accounting/ledger-accounts)
- **Vendors**: [Business partners → Vendors](https://app.light.inc/vendors)
- **Journal entries**: [Accounting → Journal entries](https://app.light.inc/journal-entries)
- **Historical transactions** (sales invoices, bills, credit notes, customer credits): the corresponding page for each document type

The general flow is the same everywhere:

1. Open the page for the record type you want to import
2. Open the upload/import action
3. Download the import template (shows required and optional fields)
4. Fill the template with your data
5. Upload the file
6. Light validates the file and reports any errors
7. Review the imported records

## Importing chart of accounts

Create your GL account structure:

1. Download COA template
2. Fill in:
   - **Account code**: Unique identifier (1000, 1100, 1110) — required
   - **Account name**: Descriptive name (Cash, Accounts Receivable, etc.) — required
   - **Account category**: Standard, Sum, or Header (see below) — required
   - **Entity codes**: Which company entities the account belongs to — required
   - **Status**: Account status — required
   - **Account type**: Specific type such as Bank, Accounts receivable, or Cost of sales, grouped under the Asset, Liability, Equity, Revenue, and Expense classifications
   - **Currency**: Account currency (optional)
   - **Aggregation rule**: (for Sum accounts only) Defines which accounts to roll up
3. Upload file (CSV or Excel)
4. Light validates the file and lets you review and fix lines before completing
5. Light creates GL accounts
6. You can now post transactions

### Account categories

Light supports three account categories:

- **Standard**: Regular posting accounts where transactions are recorded
- **Sum**: Roll-up accounts that aggregate balances from other accounts for reporting (no direct posting)
- **Header**: Visual grouping labels that appear on reports with zero balance (no direct posting)

### Aggregation rules for Sum accounts

Sum accounts use an **aggregation rule** to define which accounts roll up into them. The rule specifies account code ranges in the format `start:end`, with multiple ranges separated by commas.

For example, if you have expense accounts 60000–60999 for Operations and 62000–62999 for Administration, you could create a Sum account with the aggregation rule `60000:60999,62000:62999` to show the combined total on reports.

> Good to know: Use consistent numbering for account codes (e.g., 1000s = assets, 2000s = liabilities). This makes defining aggregation rules straightforward, since you can group accounts by code range.

## Customers

Light does not currently support importing customers from a file. Create customers individually at [Business partners → Customers](https://app.light.inc/customers) with **+ Create customer**, or create them programmatically via the API. See [API access and custom integrations](11-12-api-access.md).

## Importing vendor master

Load vendor information:

1. Download the vendor upload template from [Business partners → Vendors](https://app.light.inc/vendors)
2. Fill in the columns you need, including:
   - **Name**: Full company name
   - **Description**: Free-text description
   - **Email**, **Phone**, **Website**
   - **Country**, **City**, **Address**, **Zipcode**
   - **VAT ID**: Vendor tax/VAT number
   - **Bank details**: Bank name, country, account number, BIC, domestic account number/code, Swedish Bankgiro/Plusgiro, recipient name
   - **Currency**: Default currency
   - **Entity codes** and **Default entity code**: Which company entities the vendor belongs to
   - **Ledger account code**: Default expense account
   - **Tax code**: Default tax code
3. Upload file — Light maps your file's columns to these fields, and you can review the mapping
4. Light validates each line; lines with errors are reported so you can fix them
5. Light creates vendor records
6. Vendors ready for AP invoicing

## Importing historical transactions

Migrate past transactions from your old system. Each document type has its own CSV import with its own template:

- **Sales invoices** (AR)
- **Bills** (AP)
- **Credit notes**
- **Customer credits**

For each import:

1. Download the CSV template for that document type — required columns are annotated with `(required)`
2. Fill in the transaction data (dates, amounts, currency, business partner, account codes, tax codes, line items)
3. Upload the file — the import is processed as a background job
4. Light validates each entry; failed entries are collected in a downloadable error report
5. Choose whether imported documents are posted immediately or left for review
6. Journal entries are imported separately via the journal entry CSV upload (see below)

This migrates transaction history.

> Important: Typically, only migrate current-year transactions and open receivables/payables. Close prior-year transactions with opening balance approach.

## Importing journal entries

Upload journal entries via CSV with the following format.

### Downloading the template

Click **Download template** to get a company-specific CSV template that includes:

- All required columns with `(required)` annotations
- Your company's active custom properties with `(custom)` annotations
- Only custom properties relevant to journal entries

The template dynamically reflects your company's configuration, so you can fill it in and upload directly.

### Required columns

| Header | Description |
|--------|-------------|
| `entry id` | Groups lines into one journal entry |
| `date` | Posting date (YYYY-MM-DD) |
| `currency` | Currency code (e.g., USD, EUR) |
| `debit` | Debit amount (zero values are accepted) |
| `credit` | Credit amount (zero values are accepted) |
| `account code` | Ledger account code |
| `entry description` | Description for the entry |
| `line description` | Description for the line |
| `business partner name` | Name of the business partner (required) |

### Optional columns

| Header | Description |
|--------|-------------|
| `tax amount` | Tax amount (can be omitted if not needed) |
| `tax code` | Tax code identifier (can be omitted if not needed) |
| `business partner id` | UUID of the business partner |
| `local currency rate` | FX rate for local currency |
| `group currency rate` | FX rate for group currency |
| `ledger name` | e.g., PRIMARY, ELIMINATION |
| `target entity code` | For intercompany entries |
| `accounting release template name` | Template name for amortization (or use `accounting release template id` with a UUID) |
| `accounting release start date` | Amortization start |
| `accounting release end date` | Amortization end |
| Custom property columns | Use the label name (e.g., "Cost Center") or internal name |

### Using display names

You can use friendly display names instead of internal system names:

- **Custom property columns**: Use the label name (e.g., "Cost Center") instead of the internal name (e.g., "cost_center")
- **Custom property values**: Use value labels (e.g., "New York") instead of internal names (e.g., "new_york") for single-select and multi-select fields
- **Accrual templates**: Use the template name instead of the UUID

Internal names and UUIDs still work for backward compatibility—existing uploads are unaffected.

### Multi-select values

For multi-select custom properties, separate values with semicolons:

```
New York; Los Angeles; Chicago
```

This format works even when labels contain spaces.

### Business partner fields

- **business partner name** — Required string field.
- **business partner id** — (Recommended) The UUID of an existing customer or vendor in Light. Using the business partner UUID is the recommended approach for importing customers and vendors, as it ensures accurate matching and avoids duplicate or mismatched records. If omitted, Light attempts to match by name, which may cause errors if names don't match exactly or if duplicates exist.

> Good to know: Use `entry id` to group multiple lines into a single journal entry. All lines with the same `entry id` will be combined into one balanced entry. Headers with `(required)` and `(custom)` annotations from the template are automatically stripped during import.

### Archiving an import

If you need to remove an import from your books (for example, to correct errors or undo a test import), archive it from the import history table:

1. Go to [Accounting → Journal entries](https://app.light.inc/journal-entries) and open the journal entry import history
2. Find the import you want to archive
3. Click the actions menu (**⋯**) and select **Archive**
4. If the import created journal entries, confirm the action

When you archive an import:

- **Draft entries** are permanently removed from the system
- **Posted entries** are reversed with offsetting journal entries, preserving the audit trail

> Important: Archive requires COMPANY_ADMIN or CONTROLLER permissions. Some entries may fail to archive if they are in closed periods, bank-reconciled, or pending approval. If archiving fails, the import status will show **Archive failed**—contact support to resolve.

## Opening balance import

Opening balances are imported as a journal entry using the journal entry CSV upload described above:

1. Prepare a CSV where all lines share the same `entry id`, dated as of your transition date
2. Enter each GL account's opening balance as a debit or credit line against its `account code`
3. Ensure total debits equal total credits
4. Upload the file
5. Light creates the opening balance journal entry, which you can review before posting

This sets up accounting starting position.

## Data validation

Light validates all imports:

- **Format validation**: Correct data types, required fields present
- **Reference validation**: Customer/vendor/account codes exist
- **Amount validation**: Amounts are numeric, balance properly
- **Duplicate validation**: No duplicate IDs
- **Consistency validation**: Related data matches

If validation fails, Light provides error report showing exactly what to fix.

## Reviewing before completion

Chart of accounts and vendor imports include a mapping and review step:

1. After you upload the file, Light maps your file's columns to Light fields
2. Review that the mapping is correct (columns mapped to right fields)
3. Review the imported lines and fix any lines with validation errors
4. Complete the import

This catches most errors before records are created.

## Handling import errors

If import fails validation:

1. Light records an error for each failed entry
2. Download the error report, which shows:
   - The entry that failed
   - The error message (missing value, invalid value, unbalanced entry, etc.)
3. Fix the issue in your file
4. Re-upload
5. Once validation passes, import succeeds

Iterative approach ensures clean data import.

## Multi-currency import

When importing with multiple currencies:

1. Include currency column in template
2. Specify currency code (USD, EUR, GBP) for each transaction
3. Light converts to GL currency using historical rates (if needed)
4. All amounts recorded correctly in GL

This handles multi-currency imports.

## Import history

Light keeps a history of each import:

- File name
- Import status (in progress, completed, failed)
- User who triggered the import
- Date/time of import
- Error count, with a downloadable error report

Each import type (journal entries, vendors, chart of accounts, transactions) has its own import history on its page.

## Undoing an import

If an import creates bad data, you can undo it from the import history:

1. Find the import in the import history
2. Delete (or archive, for journal entry imports) the import
3. Light removes the documents created by the import — draft documents are deleted, and posted documents are reversed to preserve the audit trail
4. Fix the import file and re-import

The undo runs as a background job; the import status shows whether it succeeded or failed.

## Best practices for importing

**Test first**: Always test imports with sample data before importing full dataset.

**Validate data**: Verify source data is clean before importing (no duplicates, required fields populated).

**Plan mapping**: Understand which source fields map to which Light fields.

**Schedule off-peak**: Import during off-peak times to avoid impacting users.

**Monitor closely**: After import, review results and verify accuracy before considering complete.

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [Data migration from E-Conomic](11-14-migration-economic.md)
- [Data migration from QuickBooks](11-15-migration-quickbooks.md)
- [Cutover fundamentals and execution](11-16-cutover.md)
- [API access and custom integrations](11-12-api-access.md)
