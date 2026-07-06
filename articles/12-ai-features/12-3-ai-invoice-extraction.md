# AI Invoice Data Extraction

Light's AI parsing module automatically extracts financial data from uploaded invoices and bills. This article explains how to use the invoice extraction feature and what data Light can capture.

[Open in Light →](https://app.light.inc/payables)

## Overview

When you upload an invoice or bill to Light, the AI parsing engine processes the document and extracts key financial information. The system handles PDFs, images, and scanned documents, making it easy to record vendor bills without manual typing.

## What Light Extracts

Light's AI parsing module extracts the following invoice data:

- **Vendor**: Matched against your existing vendor list; if no match is found, Light extracts the vendor's details (name, address, VAT ID, bank details) so you can create a new vendor
- **Invoice Amount**: Total amount in the original currency
- **Invoice Number and Dates**: The invoice number, issue date, and due date
- **Tax Amounts**: Tax amounts, where present on the document
- **Description**: A summary description of what the invoice covers
- **Line Items**: Line-by-line breakdown with a description and amount per line (for invoices with a quantity column, Light extracts the final line amount, not quantity or price per item)
- **Account and Tax Code Suggestions**: A suggested GL account and tax code for each line, based on your chart of accounts and the vendor's defaults, along with the reasoning behind each suggestion
- **Custom Properties**: Additional fields configured for your company's needs

The extracted data is presented in Light's structured format, ready to be recorded in your ledger.

## How to Upload and Extract Invoices

1. Navigate to **Bills** in Light
2. Click **Upload bills**
3. Select your invoice document (PDF, JPEG, PNG, HEIC/HEIF, or TIFF — CSV is also accepted, but it is treated as structured input and skips AI extraction)
4. The bill appears in the **Inbox** with the extracted data pre-filled
5. Open the bill to review the extracted fields side-by-side with the original document
6. Edit any field that needs correction
7. The bill then continues through your standard approval and payment workflow

> Good to know: Light's extraction typically completes within a few seconds. Complex invoices with many line items may take slightly longer to process.

## Handling Extraction Errors

If Light misreads part of your invoice, you can correct it before saving:

- Click any extracted field to edit it
- If extraction fails entirely, you can manually enter the invoice details

For consistently problematic invoices (unusual formats, poor image quality, handwritten sections), manual entry may be faster.

## How Light Uses Past Invoices

Light does not train AI models on your data or corrections. Instead, when a bill arrives from a vendor you already work with, Light gives the AI your most recent completed bills from that vendor as examples. Account and tax code suggestions for regular vendors therefore follow the way you coded their previous invoices.

## Extraction Accuracy Tips

To maximize extraction accuracy:

- Upload clear, well-lit photos of invoices
- Ensure all text is legible and not cut off
- Avoid tilted or rotated images
- For scanned PDFs, use good quality scans (not heavily compressed images)
- Include the full invoice including header and footer sections

## Custom Field Extraction

If your company uses custom properties, Light extracts values for them automatically — both at the bill header level and per line item — based on the custom property groups configured under Settings → **Custom properties** ([Custom properties](https://app.light.inc/settings/custom-properties)).

> Tip: Test the extraction feature with a few sample invoices from your regular vendors before rolling out to your entire team. This helps ensure Light's AI is configured correctly for your documents.

## Related Articles

- How Light uses AI
- AI-powered data cleaning
- AI receipt capture and categorization
