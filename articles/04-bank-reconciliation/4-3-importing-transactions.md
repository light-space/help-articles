# Importing Bank Transactions

In addition to automatic bank feeds, you can manually import bank transactions from CSV files. This is useful when bank feeds aren't available or for historical data.

[Open in Light →](https://app.light.inc/bank-reconciliation)

## Manual Transaction Import

To manually import transactions from a CSV file:

1. Go to **Settings > Bank accounts**
2. Find the account and click **Import Transactions**
3. Click **Upload File** and select your CSV file
4. Review the column mapping (shown below)
5. Click **Import** to process the file

The system validates the file format and attempts to map CSV columns to transaction fields.

## CSV File Format

Your CSV must include these required columns:

**Date** - Transaction date (format: YYYY-MM-DD or M/D/YYYY)

**Amount** - Transaction amount in the account's currency

**Description/Name** - Payee or description

**Reference** - Optional reference number or memo

**Type/Sign** - D for debit (withdrawal), C for credit (deposit), or +/- signs

Additional optional columns:

- **Transaction ID** - Unique identifier from your bank
- **Original Amount** - For multi-currency (before conversion)
- **Fees** - Bank fees
- **Balance** - Running account balance

## Column Mapping

If your CSV columns have non-standard names, map them:

1. After uploading, you see a mapping interface
2. Drag CSV column names to match Light fields
3. Mark required columns to map before proceeding
4. Click **Confirm Mapping**

Light learns your CSV format and pre-fills the mapping for future imports.

## Transaction Validation

Light validates each transaction before importing:

- **Date format** - Must be valid date
- **Amount format** - Must be valid number
- **Debit/Credit sign** - Must be D/C or +/-
- **Required fields** - Date, amount, and description must be present

If validation fails, you'll see which rows have errors. Fix the CSV and re-upload.

## Handling Duplicates

Light checks for duplicate transactions using:

- **Date + Amount + Description** - Must match exactly
- **Transaction ID** - If provided, must be unique

If a transaction already exists in Light, the import skips it with a notification. This prevents duplicate posting.

You can force reimport if needed, but duplicates will be created.

## Data Cleansing

Light applies some data cleansing during import:

- **Whitespace trimming** - Removes leading/trailing spaces
- **Amount normalization** - Handles various decimal separators (. or ,)
- **Date parsing** - Interprets common date formats

For amounts with thousands separators (e.g., "1,000.50"), remove separators before uploading.

## Batch Processing

For large files (1,000+ transactions), import runs in the background:

1. Upload the file
2. You see a background job ID
3. Transactions import over a few minutes
4. Notifications update you on progress
5. Once complete, transactions appear in your account

Check **Background Jobs** to monitor large imports.

## Transaction Post-Processing

After import, transactions are available for reconciliation:

1. Go to **Banking > Bank Accounts > [Account Name]**
2. View imported transactions
3. Match them to accounting entries
4. Mark as reconciled

Reconciliation happens separately from import (covered in other articles).

## Importing to Multiple Accounts

To import for multiple accounts:

1. Create separate CSV files for each account
2. Upload each file to its corresponding account
3. Or, use a single CSV with an account field and specify mapping

Multi-account CSV must include an "Account" or similar column to distinguish which transactions go to which account.

## Handling Historical Data

When importing years of historical data:

1. **Start with oldest transactions** - Import year-by-year
2. **Use batch imports** - Split large files into monthly chunks if needed
3. **Monitor progress** - Check that all transactions imported successfully
4. **Reconcile by period** - Reconcile each month as you import it
5. **Build up to current** - Once historical data is imported, ongoing imports are easier

For multi-year imports, plan for a few hours of processing time depending on file size.

## Correcting Imported Transactions

If you need to correct an imported transaction:

1. Open the transaction
2. Edit the **Description**, **Amount**, or other details
3. Click **Save**

Only certain fields can be edited. If you need to change the date or transaction ID, you may need to delete and re-import.

## Deleting Imported Transactions

To remove an incorrectly imported transaction:

1. Open the transaction
2. Click **Delete**
3. Confirm deletion

Once deleted, the transaction is removed from reconciliation. If you accidentally deleted a transaction, you can re-import it from your CSV.

## File Format Examples

**CSV with standard columns:**
```
Date,Description,Amount,Type
2024-01-15,Office Supplies Co,500.00,D
2024-01-16,Customer Payment,2500.00,C
```

**CSV with additional details:**
```
Date,Description,Amount,Sign,TransactionID,Fees
2024-01-15,Wire Transfer OUT,10000.00,-,WIR-12345,0.00
2024-01-16,ACH Deposit,5000.00,+,ACH-67890,0.00
```

**CSV with multi-currency:**
```
Date,Amount,Currency,OrigAmount,OrigCurrency,Description
2024-01-15,535.00,USD,500.00,EUR,Wire from Munich
```

## Troubleshooting Import Issues

**"Date format not recognized"** - Use YYYY-MM-DD or M/D/YYYY format consistently

**"Amount values not valid"** - Remove currency symbols and thousands separators

**"File too large"** - Split into multiple files (max 50,000 rows per file)

**"Encoding error"** - Save CSV as UTF-8 (not UTF-16 or other encodings)

**"Duplicates rejected"** - This is intentional to prevent duplicate posting; use force reimport if certain

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
- **Document mapping** - Keep notes on which CSV columns map to Light fields

## Related Articles

- [Connecting bank accounts](/mnt/help-articles/articles/04-bank-reconciliation/4-1-connecting-bank-accounts.md)
- [Setting up bank feeds](/mnt/help-articles/articles/04-bank-reconciliation/4-2-bank-feeds.md)
- [Automated bank reconciliation](/mnt/help-articles/articles/04-bank-reconciliation/4-4-automated-reconciliation.md)
