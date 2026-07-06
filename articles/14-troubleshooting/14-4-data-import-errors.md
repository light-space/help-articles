# Data Import Errors

This article covers common errors that occur when importing financial data via CSV and how to fix them.

[Open in Light →](https://app.light.inc/dashboard)

## Overview

Light supports importing financial data via CSV (Comma-Separated Values) files. This is useful for bulk uploads, migrating from other systems, or importing data that isn't available through integrations. This article helps you understand and resolve common import errors.

## CSV Format Requirements

Before troubleshooting errors, understand the required format:

### Basic Requirements

- **Format**: CSV text file for most imports (the chart of accounts import also accepts Excel files)
- **Encoding**: UTF-8 (standard text encoding)
- **Line Endings**: Unix (LF) preferred, but Windows (CRLF) is accepted
- **Column Headers**: First row must contain column names
- **Data Types**: Values must match expected types for columns

Imports in Light are started from the page for each record type (for example **Journal entries**, **Bills**, **Vendors**, or a bank account) — there is no central import page. Each import type expects its own set of columns.

### Common Column Names

- **Bank transactions**: Date, Payer/Payee Name, Transaction Id, Reference, Amount, Memo (Date and Amount are required)
- **Journal entries**: Entry Id, Date, Currency, Debit, Credit, Account Code, Entry Description, Line Description, Business Partner Name, plus optional columns such as Tax Code and Tax Amount
- **Bills**: Invoice Id, Company Entity Code, Currency, Pay From Account, Invoice Date, Invoice Total, Vendor Name, Status, Ledger Account Code, Tax Code, Amount
- **Vendors** and **chart of accounts**: column headers are mapped automatically by AI, so exact header names are not required

> Tip: When in doubt, download the template from the import dialog on the relevant page to see the expected format. Required columns are marked with **(required)** in the template.

## Issue 1: "File Format Not Recognized"

### Symptoms

- Error: "Invalid file format" or "File not recognized"
- File upload is rejected
- Light doesn't let you preview the data

### Solutions

1. **Verify File Extension**:
   - Ensure file ends with **.csv** (not .xlsx, .txt, or others)
   - Rename file if extension is wrong
   - On Mac, make sure .xlsx files aren't hidden as .csv
2. **Check File Encoding**:
   - File must be UTF-8 encoded text
   - Open CSV in text editor (Notepad, VS Code, Sublime)
   - Go to **File** > **Save As**
   - Select **UTF-8** from encoding dropdown
   - Save the file
3. **Verify It's Not Excel Format**:
   - Don't save as .xlsx or .xls
   - If you have an Excel file:
     - Open in Excel
     - Click **File** > **Save As**
     - Choose **CSV (Comma Delimited)** format
     - Save as .csv
4. **Check for Binary Data**:
   - Don't include images, PDFs, or non-text data
   - CSV can only contain text values
   - If you need to import files, use document upload instead
5. **Test with Simple CSV**:
   - Create a test CSV in a text editor
   - Add simple headers: name,amount,date
   - Add one line of sample data
   - Try importing the test file
   - If test works, your main file has specific issues

## Issue 2: "Column Not Found" or "Missing Required Column"

### Symptoms

- Error: "Column 'X' not found"
- "Missing required fields" message
- Only some columns are accepted

### Solutions

1. **Verify Column Headers**:
   - Open CSV in text editor
   - Check the header row (first row)
   - Column names must match what Light expects
   - Column names are not case-sensitive, and leading or trailing spaces are trimmed
   - Spaces and underscores in column names are interchangeable (e.g., "account code" and "Account_Code" both work)
2. **Check Required Columns**:
   - Different record types require different columns
   - Bank transactions require: Date, Amount
   - Bill imports require: Invoice Id, Company Entity Code, Currency, Pay From Account, Invoice Date, Invoice Total, Vendor Name, Status, Ledger Account Code, Tax Code, Amount
   - Verify your file has the minimum required columns
3. **Export Template**:
   - Light can provide a template CSV
   - Download the template from the import dialog on the relevant page (for example the journal entry import)
   - Use the template to understand correct column names — required columns are marked with **(required)**
   - Copy your data into the template structure
4. **Rename Columns**:
   - If your CSV uses different column names, rename them
   - Open in text editor or Excel
   - Change column names to match Light's expectations
   - Save and retry import
5. **Remove Extra Columns**:
   - Light ignores extra columns (usually)
   - But sometimes extra columns cause issues
   - Delete columns you don't need
   - Keep only columns Light expects

## Issue 3: "Invalid Data Type" or "Type Mismatch"

### Symptoms

- Error: "Invalid data type for column 'amount'"
- "Expected number, got text"
- Row import fails for specific columns

### Solutions

1. **Check Data Types**:
   - **Dates**: YYYY-MM-DD (2024-01-15) works for all imports; bank transaction, bill, sales invoice, credit note, and customer credit imports also accept DD/MM/YYYY, DD.MM.YYYY, and DD-MM-YYYY. MM/DD/YYYY is not supported
   - **Amounts**: Numbers only, no currency symbols ($100 is wrong, 100 is right)
   - **Numbers**: Thousands-separator commas are stripped automatically (1,000 is read as 1000), but commas as decimal separators are not supported
   - **Text**: Anything can be text (no special handling)
2. **Fix Date Format**:
   - Convert all dates to YYYY-MM-DD (accepted by every import)
   - Excel: Format column as YYYY-MM-DD, then export
   - Spreadsheet trick: Change format first, then export CSV
3. **Fix Amount Format**:
   - Remove currency symbols: change "$1,000.50" to "1000.50"
   - Remove commas: change "1,000" to "1000"
   - Decimals are fine: "1000.50" is correct
   - Use negative sign for negative amounts: "-1000.50"
4. **Check for Hidden Characters**:
   - Amounts may have extra spaces: " 100 " instead of "100"
   - Open CSV in text editor
   - Look for spaces before or after values
   - Delete spaces
5. **Use Find & Replace**:
   - In spreadsheet app, use Find & Replace
   - Find: "$", Replace: "" (removes all $ signs)
   - Find: ",", Replace: "" (removes all commas)
   - Export again after cleanup

## Issue 4: "Duplicate Entry" or "Record Already Exists"

### Symptoms

- Import rejected because record exists
- "Duplicate invoice number"
- "Vendor already exists"

### Solutions

1. **Check for Existing Data**:
   - Search Light for the record being imported
   - Go to **Transactions** and search by date/amount
   - Go to **Vendors** and search by name
   - If found, remove from CSV before reimporting
2. **Use Update Instead of Insert**:
   - If updating existing records, light usually handles this
   - But check if CSV has a column indicating "update" vs "new"
   - Some imports require explicit action type
3. **Deduplication**:
   - Check CSV for duplicate rows
   - Sort by key field (invoice number, vendor name)
   - Look for identical records appearing twice
   - Delete one of the duplicates
4. **Key Mapping**:
   - If importing with new key field (different ID)
   - Light can't match to existing records
   - Remove records from CSV that already exist
   - Or provide mapping of old IDs to new IDs
5. **Partial Re-import**:
   - If some records are duplicates
   - Split CSV into two files
   - One with new records, one with updates
   - Import the new ones first, then updates

## Issue 5: "Invalid Date" or "Date Out of Range"

### Symptoms

- Error: "Invalid date format"
- "Date out of range"
- Only certain rows rejected for date

### Solutions

1. **Check Date Format**:
   - Use YYYY-MM-DD — this works for every import
   - January must be "01", not "1"
   - September 15, 2024 should be "2024-09-15"
   - Bank transaction and bill/invoice imports also accept DD/MM/YYYY, DD.MM.YYYY, and DD-MM-YYYY
   - Don't use US-style MM/DD/YYYY — it is not supported
2. **Verify Dates Are Logical**:
   - Dates can't be in the future (or very far future)
   - Dates shouldn't be before 1900
   - Transaction dates should be before today
   - Check dates that are getting rejected
3. **Excel Export Gotcha**:
   - Excel may have dates in its native format
   - When exporting, specify CSV and verify format
   - Open CSV in text editor to check format
   - If dates don't look like YYYY-MM-DD, reformat
4. **Fix Format in Text Editor**:
   - Open CSV in text editor
   - Use Find & Replace to fix format if needed
   - Example: Find "(\d{2})/(\d{2})/(\d{4})" Replace "$3-$1-$2"
   - Or manually edit problem rows
5. **Check Timezone Issues**:
   - If dates seem off by one day
   - May be timezone conversion issue
   - Adjust dates by appropriate number of days

## Issue 6: "Invalid Amount" or "Zero Amount Not Allowed"

### Symptoms

- Error: "Invalid amount" or "Amount is zero"
- Some rows rejected for amount field
- "Negative amount not allowed"

### Solutions

1. **Check Amount Values**:
   - Amounts must be non-zero (unless allowed)
   - Remove rows with $0 amounts
   - Check that amounts are actual numbers
2. **Fix Amount Format**:
   - Remove currency symbols ($, €, ¥)
   - Remove commas: "1,000" becomes "1000"
   - Decimals are okay: "1000.50" is fine
   - Negative amounts: "-100.50" is accepted
3. **Check for Text**:
   - Amounts can't be text like "one hundred"
   - Must be numeric: 100
   - Check for "N/A" or other text
   - Replace with actual number or delete row
4. **Sign Conventions**:
   - Check if negative amounts are allowed
   - Some fields require positive; others require negative
   - Expenses should be negative: -100
   - Income should be positive: +100
5. **Decimal Points**:
   - Use period (.) for decimal, not comma
   - "1000.50" is correct
   - "1000,50" is not supported — commas are treated as thousands separators and removed

## Issue 7: "Invalid Vendor/Customer" or "Reference Not Found"

### Symptoms

- Error: "Vendor not found" or "Account does not exist"
- "Invalid reference" error
- Foreign key reference is rejected

### Solutions

1. **Create References First**:
   - If importing transactions with vendor references
   - Vendor must exist before transaction can reference it
   - Create vendors first: export vendor template and import
   - Then import transactions
2. **Check Reference Names**:
   - Vendor names must match exactly
   - "Acme Corp" not "Acme" or "Acme, Inc."
   - Case-sensitive matching may apply
   - Search for vendor in Light first
3. **Verify IDs Match**:
   - If using vendor IDs instead of names
   - IDs must match IDs in Light
   - Check that you're using the same ID system
   - Export existing data to see ID format
4. **Create Missing Records**:
   - For vendors not yet in Light
   - Create them manually or via separate import
   - CSV: name, email, phone, address
   - Do this before importing related transactions
5. **Use Natural Keys**:
   - Bill imports match vendors by name, so the vendor name in the CSV must match an existing vendor exactly
   - Vendors are not created automatically during a bill import
   - Import or create missing vendors first from the [Vendors](https://app.light.inc/vendors) page, then re-run the import

## Issue 8: "Row Rejected" or "Validation Error"

### Symptoms

- Error shows specific row number
- "Row 15 rejected"
- No clear explanation of what's wrong

### Solutions

1. **Review Error Details**:
   - Click "Show Details" or "View Error"
   - Error message should specify the problem
   - It might say "Invalid amount in row 15, column 4"
2. **Check the Specific Row**:
   - Open CSV and go to the numbered row
   - Look at each column's value
   - Compare against other rows
   - One column likely has wrong format
3. **Test Row by Itself**:
   - Create CSV with just headers and problem row
   - Import just this row to isolate issue
   - Error message should clarify the problem
   - Fix and add back to full import
4. **Compare with Template**:
   - Use Light's template CSV
   - Compare your problem row to template
   - See how template row is formatted
   - Match your data to template format
5. **Manual Entry**:
   - For problematic rows, enter manually
   - Remove row from CSV
   - Import CSV without that row
   - Manually create the problematic record

## Issue 9: Import Completes but Data Missing

### Symptoms

- Import shows "successful" but records don't appear
- No error message but can't find imported data
- Some rows imported, others silently failed

### Solutions

1. **Search for Imported Data**:
   - Data may have imported to unexpected location
   - Search by amount, date, or reference
   - Narrow date range to import date
   - Might be in a different account than expected
2. **Check Filters**:
   - Applied filters may be hiding imported data
   - Click **Filters** and remove all filters
   - Expand date range
   - Re-run search
3. **Verify Import Completed**:
   - Open the import history on the page you imported into (for example **Journal entries** or **Bills**)
   - Each import is listed with its filename, status, who uploaded it, and an error count
   - Download the error report to see which rows failed and why
   - Check if all rows were successfully imported
4. **Review Import Summary**:
   - After import completes, review summary
   - Summary shows rows imported vs. rows failed
   - If some rows failed, see details why
   - Fix those rows and re-import
5. **Check Posting Status**:
   - Imported journal entries are created as drafts unless you chose to post them during import
   - Filter the [Journal entries](https://app.light.inc/journal-entries) page by the **Draft** status to find them
   - Bill imports use the **status** column in the CSV (draft, posted, or paid) to determine each record's status

## Issue 10: "File Too Large" or "Upload Timeout"

### Symptoms

- Error: "File too large"
- Upload times out
- Can't import large data sets

### Solutions

1. **Split Large File**:
   - Divide CSV into multiple smaller files
   - Import one batch at a time
   - Combine by date range or record type
   - Light typically handles 10,000+ rows per file
2. **Remove Extra Columns**:
   - Delete columns you don't need
   - Each extra column adds to file size
   - Keep only required columns
   - File size will be smaller
3. **Increase Timeout**:
   - Browser may timeout on large uploads
   - Clear browser cache first
   - Try a different browser
   - Desktop browser handles larger files than mobile
4. **Use Smaller Batch**:
   - Instead of importing all historical data
   - Start with recent data (last 6 months)
   - Import historical data in separate batches later
   - This also lets you validate as you go
5. **Contact Support**:
   - For very large imports (100k+ rows)
   - Light support may be able to help
   - They may be able to import via backend
   - Provide file and explain situation

## Related Articles

- Common issues and solutions
- Bank connection troubleshooting
- Integration sync issues
- Contacting Light support
