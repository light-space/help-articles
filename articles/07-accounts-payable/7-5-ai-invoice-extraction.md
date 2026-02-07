# AI-Driven Invoice Data Extraction

Light uses advanced AI and machine learning to automatically extract data from vendor invoices, reducing manual data entry and improving accuracy. This article explains how the extraction works and how to maximize quality.

[Open in Light →](https://app.light.inc/payables)

## How AI Extraction Works

When you upload an invoice PDF or image, Light's AI:

1. **Reads the document**: Converts PDF text or OCR's image to readable format
2. **Identifies fields**: Locates and extracts key invoice data:
   - Vendor name and details
   - Bill number, date, due date
   - Line items (description, quantity, price)
   - Totals and tax
   - Payment terms

3. **Maps to Light fields**: Assigns extracted values to bill fields
4. **Validates data**: Checks for consistency (e.g., line total = qty × price)
5. **Flags uncertainties**: Highlights fields where confidence is low
6. **Presents for review**: Shows original invoice and extracted data side-by-side

## Supported Invoice Formats

Light accepts:

- **PDF**: Native PDFs and scanned PDFs (best quality)
- **Images**: JPG, PNG (higher resolution is better)
- **Email**: Forwarded to the vendor portal
- **Formats**: Standard invoices, receipts, order confirmations

Best results come from clear, legible documents in English. Other languages are supported but may have lower accuracy.

## Uploading and Extracting

### Via Web Interface

1. Navigate to **Bills** > **Create Bill**
2. Click **Upload Invoice**
3. Select a PDF or image file
4. Light extracts data (takes 5-30 seconds)
5. Review the extracted information
6. Make corrections as needed
7. Click **Create Bill**

### Via Email

1. Set up your vendor portal **email address** (e.g., bills@light.company.com)
2. Instruct vendors to email invoices to this address
3. Portal automatically receives and extracts
4. Vendor receives confirmation email with link
5. Bill appears in your **Inbox** for review

### Via Vendor Portal

1. Vendors upload invoices to their portal
2. Light extracts data
3. Vendor can review and correct
4. Bill enters your workflow for approval

## Reviewing Extracted Data

### The Extraction Review Screen

1. Original invoice image displayed on left
2. Extracted fields displayed on right
3. **Confidence indicators** show extraction certainty (green = high, yellow = medium, red = low)
4. **Clickable fields** allow correction of extracted values

### Correcting Extractions

If a field was extracted incorrectly:

1. Click on the field
2. Edit the value or select from suggestions
3. Light re-validates related fields (e.g., if qty changes, recalculates total)
4. Click **Confirm** or continue to next field

Common corrections:
- **Vendor**: Wrong vendor selected; pick correct one
- **Bill Number**: OCR misread characters (0 vs O, 1 vs l)
- **Amounts**: Decimal place misplaced
- **Line Items**: Grouped incorrectly or missed lines

### Handling Uncertain Extractions

When Light is unsure about a value (yellow flag):

1. Review the original document carefully
2. If you can read it clearly, enter the correct value
3. If genuinely unclear, leave blank or enter best guess
4. Add a **Note** explaining the issue
5. You can contact the vendor to clarify later

## AI Training and Accuracy

### Accuracy Metrics

Light tracks extraction accuracy:

- **Vendor Name**: 98%+ accuracy
- **Invoice Number/Date**: 96%+ accuracy
- **Amounts**: 94%+ accuracy
- **Line Items**: 90%+ accuracy
- **Overall**: 90%+ of documents require zero corrections

Accuracy improves over time as Light learns from your invoices.

### Improving Accuracy

Help Light learn from your invoices:

1. After correcting extractions, click **Save Feedback**
2. Light learns that this vendor invoice follows a certain pattern
3. Future invoices from this vendor are extracted more accurately
4. After 5-10 invoices from a vendor, accuracy often approaches 99%

### Machine Learning Models

Light maintains:

- **General Model**: Works on any invoice
- **Vendor-Specific Models**: Optimized for invoices from major vendors
- **Industry Models**: Specialized for construction, tech, manufacturing, etc.

Light automatically selects the best model based on vendor and industry.

## Batch Extraction

### Uploading Multiple Invoices

Extract multiple invoices in one operation:

1. Navigate to **Bills** > **Bulk Upload**
2. Select multiple files (drag and drop or click to browse)
3. Click **Upload All**
4. Light extracts all invoices in parallel
5. Review each extraction individually
6. Correct as needed
7. Click **Create All Bills**

This is useful for:
- Weekly invoice batches
- Catching up on backlog
- End-of-month closing

### Bulk Correction

For common issues across multiple invoices:

1. After extracting batch, click **Bulk Corrections**
2. Select issues to fix:
   - Vendor always identified as wrong one
   - Specific line items consistently misread
   - Date format consistently wrong

3. Apply correction to all affected invoices
4. Review changes and confirm
5. Click **Apply**

## Handling Difficult Invoices

### Complex Invoices

Some invoices are inherently difficult:

- **Multiple currencies**: Invoices with mixed currency line items
- **Promotional text**: Heavy marketing language confuses extraction
- **Unusual layout**: Non-standard invoice formats
- **Poor quality**: Faxed or low-res scanned documents

For these:

1. Upload the invoice
2. Light does its best extraction
3. Carefully review and correct ALL fields
4. Save feedback to help train models
5. Consider requesting cleaner invoices from vendor in future

### Unreadable Invoices

If an invoice is truly unreadable:

1. Light may fail to extract
2. System offers **Manual Entry** option
3. Manually type in all invoice details
4. This is slower but ensures accuracy
5. Consider requesting a cleaner copy from vendor

## Extraction Settings

### Configure Extraction Options

1. Navigate to **Settings** > **Invoice Extraction**
2. Set preferences:
   - **Default Vendor**: Assign vendor automatically if unclear
   - **Tax Auto-Calculation**: Let Light calculate or enter manually
   - **Duplicate Detection**: Flag potential duplicate invoices
   - **Three-Way Match**: Auto-match to POs

3. Click **Save**

### Vendor-Specific Settings

Set extraction preferences per vendor:

1. Open the vendor
2. Navigate to **Extraction Settings**
3. Set:
   - **Invoice Format**: If vendor has standard format
   - **GL Accounts**: Default accounts for their invoices
   - **Currency**: Default currency
   - **Custom Fields**: Vendor-specific data (e.g., project codes)

4. Light uses these when extracting this vendor's invoices

## AI Extraction Analytics

Monitor extraction performance:

1. Navigate to **Reports** > **Extraction Quality**
2. View metrics:
   - **Documents Processed**: Total invoices extracted
   - **Accuracy Rate**: % requiring no corrections
   - **Average Corrections**: Per document
   - **Top Vendors**: Which vendors have best/worst accuracy

3. Filter by time period, vendor, or file type
4. Identify vendors whose invoices are problematic
5. Request better invoice formats or reach out for clarification

## Related Articles

- [Entering and ingesting bills](/articles/07-accounts-payable/7-4-entering-bills.md)
- [Vendor portal and magic links](/articles/07-accounts-payable/7-3-vendor-portal.md)
- [Bill approval workflows](/articles/07-accounts-payable/7-6-bill-approval.md)
