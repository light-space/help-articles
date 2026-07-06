# Importing Bank Transactions

In addition to automatic bank feeds, you can manually import bank transactions from CSV files. This is useful when bank feeds aren't available or for historical data.

[Open in Light →](https://app.light.inc/bank-reconciliation)

## Manual Transaction Import

To manually import transactions from a CSV file:

1. Go to **Settings → Bank accounts**
2. Find the account and click **Import Transactions**
3. Click **Upload File** and select your CSV file
4. Click **Import** to process the file

The system validates the file format and matches CSV columns to transaction fields by their header names.

## CSV File Format

Your CSV must include a header row with these required columns:

**Date** - Transaction date (format: YYYY-MM-DD, DD/MM/YYYY, DD.MM.YYYY, or DD-MM-YYYY)

**Amount** - Transaction amount in the account's currency. Use a positive amount for money in and a negative amount for money out. The amount cannot be zero.

Additional optional columns:

- **Payer/Payee Name** - Payer or payee name
- **Reference** - Reference number
- **Transaction ID** - Unique identifier from your bank
- **Memo** - Free-text memo

## Column Names

Light matches CSV columns by their header names, so headers must use the names listed above. Header matching is case-insensitive, and both comma and semicolon delimiters are detected automatically.

If your bank's export uses different column names, rename the headers in the file before uploading. Light provides a downloadable CSV template you can use as a starting point.

## Transaction Validation

Light validates each transaction before importing:

- **Date format** - Must be a valid date in one of the supported formats
- **Amount format** - Must be a valid, non-zero number
- **Required columns** - The Date and Amount columns must be present

If validation fails, you'll see which rows have errors (e.g., "Invalid date on row 3"). No transactions are imported until all errors are fixed - correct the CSV and re-upload.

## Handling Duplicates

Light does not automatically detect duplicates in CSV imports - uploading the same transactions twice creates duplicates. Review your file before uploading, and avoid overlapping date ranges between imports.

For bank feed imports, duplicate transactions are detected automatically and marked as **Excluded** so they don't affect reconciliation.

If you accidentally import duplicates from a CSV, exclude them on the Bank reconciliation page.

## Data Cleansing

Light applies some data cleansing during import:

- **Whitespace trimming** - Removes leading/trailing spaces
- **Amount normalization** - Thousands separators written as commas (e.g., "1,000.50") are removed automatically
- **Date parsing** - Interprets the supported date formats listed above

Use a period (.) as the decimal separator in amounts, and remove any currency symbols.

## Import Processing

Imports run in the background:

1. Upload the file
2. The import processes in the background
3. The sync status is shown above the bank transactions list on the Bank reconciliation page
4. Once complete, transactions appear in your account

## Transaction Post-Processing

After import, transactions are available for reconciliation:

1. Go to **Accounting → Bank reconciliation** and select the account
2. Imported transactions appear with the **Unmatched** status
3. Light automatically runs auto-reconciliation after each import
4. Match any remaining unmatched transactions to accounting entries

Reconciliation is covered in more detail in other articles.

## Importing to Multiple Accounts

Each import applies to a single bank account. To import for multiple accounts:

1. Create separate CSV files for each account
2. Upload each file to its corresponding account

## Handling Historical Data

When importing years of historical data:

1. **Start with oldest transactions** - Import year-by-year
2. **Use batch imports** - Split large files into monthly chunks if needed
3. **Monitor progress** - Check that all transactions imported successfully
4. **Reconcile by period** - Reconcile each month as you import it
5. **Build up to current** - Once historical data is imported, ongoing imports are easier

## Excluding Incorrect Transactions

Imported bank transactions can't be edited or deleted individually. If a transaction was imported incorrectly:

1. Select it on the **Bank reconciliation** page
2. Click **Exclude** - the transaction is marked **Excluded** and removed from reconciliation
3. If needed, re-import a corrected version from an updated CSV

You can undo an exclusion at any time to bring the transaction back into reconciliation.

## File Format Examples

**CSV with required columns:**
```
Date,Payer/Payee Name,Amount
2024-01-15,Office Supplies Co,-500.00
2024-01-16,Customer Payment,2500.00
```

**CSV with additional details:**
```
Date,Payer/Payee Name,Amount,Reference,Transaction ID,Memo
15/01/2024,Wire Transfer OUT,-10000.00,WIR-12345,TXN-001,Vendor payment
16/01/2024,ACH Deposit,5000.00,ACH-67890,TXN-002,Customer deposit
```

## Troubleshooting Import Issues

**"Invalid date on row X"** - Use YYYY-MM-DD, DD/MM/YYYY, DD.MM.YYYY, or DD-MM-YYYY format consistently

**"Invalid amount on row X"** - Remove currency symbols, use a period as the decimal separator, and make sure the amount isn't zero

**"Missing required headers"** - The file must include Date and Amount columns with those exact header names

**"Encoding error"** - Save CSV as UTF-8 (not UTF-16 or other encodings)

## Scheduling Regular Imports

For accounts not supported by bank feeds:

1. Export transactions from your bank monthly
2. Set a calendar reminder to import
3. Follow the import process
4. Reconcile immediately after import

This keeps your Light account current even without automated feeds.

## Best Practices

- **Use bank feeds when available** - Feeds are more reliable than manual imports
- **Validate CSV before upload** - Check a few rows for correct format
- **Import frequently** - Weekly or monthly prevents large backlogs
- **Reconcile immediately** - Don't wait weeks to reconcile imported transactions
- **Keep original export files** - Archive your bank exports for audit trail
- **Start from the template** - Use Light's CSV template so column names match

## Related Articles

- [Connecting bank accounts](/mnt/help-articles/articles/04-bank-reconciliation/4-1-connecting-bank-accounts.md)
- [Setting up bank feeds](/mnt/help-articles/articles/04-bank-reconciliation/4-2-bank-feeds.md)
- [Automated bank reconciliation](/mnt/help-articles/articles/04-bank-reconciliation/4-4-automated-reconciliation.md)
