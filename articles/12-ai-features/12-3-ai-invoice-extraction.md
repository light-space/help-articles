# AI Invoice Data Extraction

Light's AI parsing module automatically extracts financial data from uploaded invoices and bills. This article explains how to use the invoice extraction feature and what data Light can capture.

[Open in Light →](https://app.light.inc/dashboard)

## Overview

When you upload an invoice or bill to Light, the AI parsing engine processes the document and extracts key financial information. The system handles PDFs, images, and scanned documents, making it easy to record vendor bills without manual typing.

## What Light Extracts

Light's AI parsing module extracts the following invoice data:

- **Vendor Information**: Vendor/supplier name and domain
- **Invoice Amount**: Total amount in the original currency
- **Invoice Date**: Date the invoice was issued
- **Location**: City and country where the transaction occurred
- **Transaction Description**: Line-item details from the invoice
- **Line Items**: Individual line-by-line breakdown of charges with amounts and descriptions
- **Account Codes**: Suggested reimbursement or expense category based on the invoice content
- **Custom Properties**: Additional fields configured for your company's needs

The extracted data is presented in Light's structured format, ready to be recorded in your ledger.

## How to Upload and Extract Invoices

1. Navigate to the **Invoices** or **Bills** section in Light
2. Click the **Upload Invoice** button
3. Select your invoice document (PDF, JPEG, or PNG)
4. Light processes the document and displays the extracted data
5. Review the extracted information for accuracy
6. Make any corrections needed in the preview screen
7. Click **Confirm and Save** to record the invoice in your ledger

> Good to know: Light's extraction typically completes within a few seconds. Complex invoices with many line items may take slightly longer to process.

## Handling Extraction Errors

If Light misreads part of your invoice, you can correct it before saving:

- Click any extracted field to edit it
- The AI parsing module learns from your corrections, improving accuracy for future invoices from that vendor
- If extraction fails entirely, you can manually enter the invoice details

For consistently problematic invoices (unusual formats, poor image quality, handwritten sections), manual entry may be faster.

## AI Learning and Improvement

The AI extraction engine improves over time through machine learning:

- When you correct extracted data, Light learns the pattern
- Invoices from the same vendor become more accurate as Light becomes familiar with their format
- Regular vendors' invoices are typically extracted with high accuracy after the first few uploads

## Extraction Accuracy Tips

To maximize extraction accuracy:

- Upload clear, well-lit photos of invoices
- Ensure all text is legible and not cut off
- Avoid tilted or rotated images
- For scanned PDFs, use good quality scans (not heavily compressed images)
- Include the full invoice including header and footer sections

## Custom Field Extraction

If your company uses custom invoice fields, Light's parsing module can be configured to extract those as well. Contact Light support to set up custom field extraction for your account.

> Tip: Test the extraction feature with a few sample invoices from your regular vendors before rolling out to your entire team. This helps ensure Light's AI is configured correctly for your documents.

## Related Articles

- How Light uses AI
- AI-powered data cleaning
- AI receipt capture and categorization
