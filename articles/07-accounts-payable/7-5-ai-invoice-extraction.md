# AI Invoice Extraction

When you upload a bill (PDF, image, or CSV) to Light, the document is run through AI extraction to pre-fill the bill's header and line items. You then review and adjust the extracted fields before the bill moves on through the workflow.

## How It Works

1. Upload one or more documents via **Upload bills** (see [Entering bills](/articles/07-accounts-payable/7-4-entering-bills.md))
2. Light extracts:
   - Vendor (matched against your vendor list)
   - Invoice number, invoice date, due date
   - Currency and totals
   - Line items (description, quantity, unit price, amount)
   - Tax amounts (where present on the document)
3. The bill appears in the **Inbox** with the extracted data pre-filled
4. Open the bill to review the extracted fields side-by-side with the original document (PDF viewer is shown alongside the form)
5. Edit any field that needs correction

## Supported File Types

PDF, JPG, JPEG, PNG, TIFF/TIF. CSV is also accepted but it is treated as structured input — no extraction is needed.

## When the Vendor Isn't Recognised

If the extracted vendor name doesn't match an existing vendor in Light, you'll be prompted to either:
- Pick a different existing vendor from the list, or
- Create a new vendor from the extracted information (see [Managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md))

## After Review

Once you've confirmed the bill's data is correct, the bill moves on through the standard workflow: into approval (see [Bill approval](/articles/07-accounts-payable/7-6-bill-approval.md)) and then to payment scheduling.

## Related Articles

- [Entering bills](/articles/07-accounts-payable/7-4-entering-bills.md)
- [Bill approval](/articles/07-accounts-payable/7-6-bill-approval.md)
- [Managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md)
