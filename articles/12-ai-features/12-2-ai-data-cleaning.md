# AI-Powered Data Cleaning

Light helps keep your financial records accurate by screening uploaded documents, flagging duplicate bills, enriching vendor and bank data, and using AI to clean up data during imports. This article explains what each of these capabilities does and how you stay in control.

[Open in Light →](https://app.light.inc/dashboard)

## Non-Bill Document Detection

When you upload a document to your payables inbox, Light's AI checks whether it is actually a bill, invoice, or credit note that belongs in accounts payable. Documents that are clearly something else — such as marketing flyers, contracts without an amount due, screenshots, shipping labels, or unreadable files — are flagged, and a warning banner explains why the document does not look like a bill.

The detection is deliberately conservative: a document is only flagged when the AI is highly confident it is not a bill, so real bills are not held up.

## Duplicate Bill Detection

Light automatically flags duplicate bills so the same invoice is not processed twice:

- A bill is treated as a duplicate when another bill from the same vendor has the same invoice (document) number
- Duplicates are moved to a **Duplicated** state instead of continuing through your approval workflow, with a reference to the bill they match
- If the original bill is later cancelled or archived, the oldest duplicate automatically returns to **Draft** so a legitimate bill is never lost

Duplicate matching is deterministic — it is based on an exact vendor and document number match, not on AI guesses — so you get consistent, predictable results.

## Vendor and Bank Data Enrichment

Light enriches records so they are complete and consistent without manual research:

- **Vendor enrichment**: When vendors are created (for example from parsed documents or card transactions), Light looks up brand data such as the vendor's website domain, logo, and address, combining external brand databases with AI
- **Bank details enrichment**: Bank details extracted from documents are enriched and structured with AI assistance

## AI-Assisted Import Cleaning

When you migrate data into Light through CSV imports, AI helps clean and structure it:

- **Chart of accounts import**: AI maps the columns in your file to Light's account fields and processes the rows into structured ledger accounts, including account types and categories. Rows the AI cannot map are handled by fallback logic instead of failing the whole import.
- **Vendor import**: AI maps your file's columns — including custom properties — to Light's vendor fields.

AI-suggested column mappings are validated against your actual file and company configuration before they are used, and imported lines are created as drafts so you can review them before running the import.

## Review and Control

You maintain full control over your data:

- AI-extracted and AI-mapped values are suggestions — you can review and edit them before records are posted
- Import lines stay in draft until you run the import
- Bills flagged as duplicates or non-bill documents remain visible so you can verify and resolve them yourself

## Related Articles

- How Light uses AI
- AI invoice data extraction
- AI receipt capture and categorization
