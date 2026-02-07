# Entering and Ingesting Bills

Light provides multiple methods to enter vendor bills: manual entry, file upload (with AI extraction), and vendor portal submission. This article covers all bill entry methods.

[Open in Light →](https://app.light.inc/payables)

## Bill Concepts

A bill in Light represents a vendor invoice. Bills contain:

- **Header**: Vendor, bill date, due date, amount, currency
- **Line Items**: What was purchased (product, service), quantity, price, GL account, cost center
- **Tax**: Tax amounts and GL accounts
- **Terms**: Payment terms and conditions

Bills progress through states: DRAFT → POSTED → PARTIALLY_CLEARED → CLEARED → ARCHIVED.

## Manual Bill Entry

### Creating a Bill Manually

1. Navigate to **Spend management → Bills**
2. Click **Create Bill**
3. Select the **Vendor** (or create inline)
4. Set bill metadata:
   - **Bill Number**: Vendor's invoice number
   - **Bill Date**: Invoice date
   - **Due Date**: When payment is due
   - **Company Entity**: Which entity is receiving the bill
   - **Currency**: Billing currency
   - **Description**: Internal notes (optional)

5. Click **Next** to add line items

### Adding Line Items

1. Click **Add Line Item**
2. Enter line details:
   - **Description**: What was purchased
   - **Quantity** and **Unit Price**
   - **GL Account**: Which account to charge (e.g., Office Supplies, Professional Services)
   - **Cost Center** (optional): Department or project
   - **Tax Category**: If applicable
   - **Amount**: Automatically calculated

3. Light calculates **Line Total** including tax
4. Click **Add**
5. Repeat for each line

> Good to know: You can override tax calculations per line if needed, though Light generally calculates tax correctly.

### Adding Taxes

1. In the bill details, navigate to **Tax**
2. Light may auto-calculate based on vendor location and products
3. Review calculated tax:
   - **Tax Rate** used
   - **Tax Amount**
   - **GL Account** for tax

4. Override if needed and click **Save**

The total amount (subtotal + tax) is shown at the bottom.

## Uploading Invoices with AI Extraction

### Upload a PDF or Image

Light's AI automatically extracts invoice data from PDF and image files:

1. Navigate to **Spend management → Bills**
2. Click **Create Bill**
3. Choose **Upload Invoice**
4. Select a **PDF or image file** (JPG, PNG)
5. Light extracts data and creates a draft bill
6. Review and correct extracted information
7. Click **Create**

> Tip: Invoice PDFs work best; clear photos of printed invoices also work well.

### Reviewing Extracted Data

After upload, review the AI extraction:

1. Light shows the original invoice image and extracted data side-by-side
2. Verify:
   - **Vendor**: Correct vendor selected
   - **Bill Number**: Invoice number
   - **Bill Date and Due Date**: Dates extracted correctly
   - **Line Items**: Products/services and amounts
   - **Total Amount**: Grand total

3. Click on extracted fields to correct if needed
4. If vendor or line items are incorrect, click **Correct** and make changes
5. Click **Confirm Extraction**

AI is typically 90%+ accurate on standard invoices.

## Batch Bill Import

### CSV Import

Upload multiple bills at once from a spreadsheet:

1. Navigate to **Spend management → Bills**
2. Click **Bulk Actions** > **Import Bills**
3. Download the **CSV template**
4. Fill in bill data:
   - Vendor Name
   - Bill Number
   - Bill Date
   - Amount
   - GL Account
   - Description
   - Line items

5. Save as CSV
6. Click **Upload CSV**
7. Light validates and shows preview
8. Click **Import**

Light creates draft bills for all valid rows and reports any errors.

## Bill States and Workflow

Bills progress through these states:

- **DRAFT**: Created but not posted; no GL entries yet
- **POSTED**: Confirmed and GL entries created; ready for matching/approval
- **OPEN**: Posted and waiting for payment or approval
- **PARTIALLY_CLEARED**: Partial payment received
- **CLEARED**: Fully paid or matched to a payment
- **ARCHIVED**: No longer active; retained for history

To change a bill's state:

1. Open the bill
2. Click **Change Status**
3. Select the target state
4. Light validates the transition is allowed
5. Add a **Reason** (optional)
6. Click **Confirm**

## Three-Way Match

The three-way match validates that Purchase Order (PO), receipt, and bill align:

1. Open the bill
2. Navigate to **Three-Way Match**
3. Light checks for linked **PO** and **Receipt**
4. Review:
   - **PO Amount** vs. **Bill Amount**: Should match (within tolerance)
   - **PO Quantity** vs. **Receipt Quantity**: Should match
   - **Receipt Date** vs. **Bill Date**: Should be close (within tolerance)

5. If mismatches exist, Light highlights them
6. Click **Resolve** to document discrepancies
7. Choose action: Approve despite discrepancy, reject bill, or request correction

> Good to know: Three-way matching can be configured to auto-approve if all fields match within tolerance (e.g., amount within 2%).

## Linking to Purchase Orders

Associate a bill with a Purchase Order:

1. Open the bill
2. Navigate to **Related Documents**
3. Click **Link to PO**
4. Search for and select the **PO**
5. Light validates:
   - Same vendor
   - Same items
   - Amount matches (or tolerance exceeded with note)

6. Click **Link**

Linked POs show on the bill; linked bills show on the PO.

## Bill Duplicate Detection

Light flags potential duplicate bills:

1. When creating a bill, Light checks for:
   - Same vendor and bill number
   - Same amount and date
   - Same line items

2. If potential duplicate found:
   - Light shows a warning
   - Displays the existing bill
   - You can:
     - **Skip**: Ignore and create the new bill anyway
     - **Cancel**: Don't create (duplicate not needed)
     - **Merge**: Combine with existing bill

## Bill Amendments

To correct information on an existing bill:

1. Open the bill
2. If DRAFT: Click **Edit** and make corrections
3. If POSTED: Click **Amend Bill**
4. Light creates an adjustment record
5. Make corrections
6. Click **Save Amendment**

Amendments maintain audit trail of original and corrected amounts.

## Related Articles

- [AI-driven invoice data extraction](/articles/07-accounts-payable/7-5-ai-invoice-extraction.md)
- [Vendor portal and magic links](/articles/07-accounts-payable/7-3-vendor-portal.md)
- [Bill approval workflows](/articles/07-accounts-payable/7-6-bill-approval.md)
- [Scheduling and executing payments](/articles/07-accounts-payable/7-7-scheduling-payments.md)
