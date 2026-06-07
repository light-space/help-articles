# Entering Bills

Light supports multiple ways to bring vendor bills into AP: uploading files, manual entry, email-to-inbox, and CSV import. All ingested bills land in the **Inbox** tab.

[Open in Light →](https://app.light.inc/payables)

Navigate via **Spend management → Bills**.

## Ways to Enter a Bill

### Upload (PDF, image, or CSV)

1. Click **Upload bills**
2. Drop files into the upload drawer or click to browse
3. Accepted formats: **PDF, JPG, JPEG, PNG, TIFF/TIF**, plus **CSV** for bulk import
4. Bills appear in the Inbox tab once processed

Uploaded files run through AI extraction — see [AI invoice extraction](/articles/07-accounts-payable/7-5-ai-invoice-extraction.md).

> **Good to know:** If the AI extracts a PO number from the bill, Light automatically matches the bill to the corresponding open purchase order for that vendor. You'll see the PO link already filled in when you open the bill in the Inbox.

### Email-to-Inbox

Each entity has a forwarding email address. Email a bill attachment to that address and it lands in the Inbox.

### Manual Entry

For bills without a document (or to add line-level detail), open a bill in the Inbox and edit it directly. You can also create a bill from scratch from a vendor's record.

### CSV Bulk Import

Upload a CSV via the same Upload drawer to create multiple bills at once.

## Bill Detail Fields

Once in the Inbox, open a bill to fill in or edit:

**Header**
- **Vendor**
- **Entity**
- **Currency**
- **Invoice number** / **invoice date** / **due date**
- **Payment method** and **From account** (defaults from the vendor)
- **PO number** (if matching against a purchase order)

**Line items** — for each line:
- Description
- Quantity, unit price, amount
- GL account
- Tax code
- Cost center / custom dimensions
- Amortization (release template start/end date — see [Deferred entries](/articles/05-general-ledger/5-5-deferred-entries.md))

## Duplicate Detection

When a bill is ingested, Light flags potential duplicates. The flagged bill shows a duplicate indicator and may move to the `DUPLICATED` state, where it can be reviewed before being kept or discarded.

## After Inbox

Once a bill's data is complete, it moves into approval. See [Bill approval](/articles/07-accounts-payable/7-6-bill-approval.md).

## Related Articles

- [Managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md)
- [AI invoice extraction](/articles/07-accounts-payable/7-5-ai-invoice-extraction.md)
- [Bill approval](/articles/07-accounts-payable/7-6-bill-approval.md)
- [Scheduling payments](/articles/07-accounts-payable/7-7-scheduling-payments.md)
