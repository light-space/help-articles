# E-Invoicing Compliance (Peppol)

E-invoicing is the digital exchange of invoices between businesses and government authorities. Peppol (Pan-European Public Procurement OnLine) is the standard framework for e-invoicing across Europe and is increasingly required for tax compliance and government B2B transactions.

[Open in Light →](https://app.light.inc/invoice-receivables)

## What is Peppol?

Peppol is a set of standards and governance rules enabling secure, reliable digital invoice exchange. It specifies:

- **Format standards**: XML structure (UBL, CII) for invoice data
- **Network protocols**: How invoices are transmitted securely
- **Validation rules**: Required fields, calculations, and compliance checks
- **Identifier schemes**: Standardized business and country identifiers

Most EU countries now require Peppol-compliant e-invoicing for B2B transactions and all B2G (business-to-government) transactions. Light automates Peppol compliance, converting your invoices to compliant format and managing transmission.

## Peppol invoice requirements

A Peppol-compliant invoice must include:

**Identifiers**: Unique invoice number, issue date, due date, and invoice type code.

**Party information**: Seller and buyer identification using standardized identifiers (VAT numbers, company registration numbers).

**Line items**: Detailed description, quantity, unit price, and tax treatment for each invoice line.

**Amounts**: Net amount, tax amount (per tax code), and total invoice amount.

**Tax information**: Tax applicable at line and document level with appropriate tax codes and rates.

**Payment terms**: Due date, payment method, and banking details.

**Attachments**: Supporting documents in PDF or structured format.

Light validates all invoices against Peppol rules before submission. If validation fails, you receive detailed error messages indicating which fields don't comply.

> Good to know: Different EU countries have additional Peppol rules (e.g., Italy requires Cassa Fiscale reporting, France requires specific VAT treatments). Light adapts validation based on buyer country.

## Enabling Peppol in Light

To activate Peppol e-invoicing:

1. Navigate to **Settings** (gear icon in bottom-left sidebar) > **Integrations**
2. Click **Enable Peppol**
3. Verify your company information:
   - Legal business name
   - VAT number or company registration number
   - Country
   - Complete registered address
4. Configure your Peppol identifier (typically your VAT number)
5. Select which entities participate in e-invoicing
6. Save and confirm

Light validates that your company data is complete and compliant before enabling Peppol submission.

## Sending Peppol invoices

Once enabled, you can submit invoices via Peppol:

1. Create an AR (accounts receivable) invoice normally
2. Verify all required fields are complete (Peppol validates automatically)
3. Click **Post** to record in the ledger
4. Click **Send via Peppol** to transmit digitally
5. Light converts the invoice to Peppol XML format
6. Light submits to your Peppol service provider
7. You receive a transmission confirmation

The invoice status changes to **Submitted** in your system. Light maintains a record of the Peppol submission ID and transmission timestamp.

> Tip: Pre-validate invoices before posting by clicking the **Validate** button. This identifies compliance issues early without affecting your ledger.

## Peppol transmission and delivery

When you submit a Peppol invoice:

1. Light passes the invoice to your configured Peppol service provider (e.g., Avalara's e-invoicing service)
2. The service provider transmits to a Peppol access point in the buyer's country
3. The buyer's system receives and processes the invoice
4. Delivery confirmation is sent back to you

Light tracks invoice status through the entire transmission process:

- **Submitted**: Sent to Peppol network, awaiting confirmation
- **Delivered**: Confirmed received by buyer's access point
- **Accepted**: Buyer's system processed the invoice
- **Rejected**: Buyer's system could not process the invoice (with error details)

## Receiving Peppol invoices

If you're a buyer, you can also receive Peppol invoices from suppliers:

1. Light automatically monitors your Peppol inbox
2. Received invoices appear in **Accounting > Accounting documents** (in Platform section)
3. You can match invoices to purchase orders
4. Create AP (accounts payable) invoices from received Peppol data
5. Light auto-populates invoice details from the transmitted document

This significantly reduces manual data entry and improves three-way matching accuracy.

## Peppol validation rules

Light validates invoices against Peppol rules before transmission:

**Line item validation**: Each line must have quantity, unit price, and tax treatment. Total line amount must match quantity × unit price (allowing rounding).

**Tax validation**: Tax rates must match your configured ledger tax codes. Tax amounts must be calculated correctly. All tax lines must sum to the total tax.

**Party validation**: Buyer and seller identifiers must be valid and formatted correctly for their country.

**Amount validation**: Net + tax must equal the invoice total (within rounding tolerance).

If validation fails, Light displays errors and prevents submission. Correct the issues and re-submit.

## Multi-currency Peppol invoices

Peppol supports invoicing in any currency. Light:

- Accepts any currency on your invoice
- Converts amounts to words if required by local rules
- Includes the original currency code in the XML
- Handles FX rates if local currency amounts differ from invoice currency

However, verify local requirements. Some countries require invoices in the local currency or EUR.

## Archiving and retention

Peppol invoices must be retained for audit purposes (typically 6-7 years). Light:

- Stores transmitted invoices in your ledger with complete audit trail
- Maintains copies in an immutable archive
- Provides certificate of transmission and delivery
- Generates tax-compliant export reports for auditors

You can export Peppol invoice history for compliance reviews:

1. Navigate to **Planning & Reports > Reports**
2. Select date range and entities
3. Click **Export**
4. Download CSV or PDF format for audit files

## Troubleshooting Peppol submissions

**Validation errors**: Check error messages; typically missing required fields like VAT numbers or incorrect tax codes. Fix and resubmit.

**Transmission failures**: Ensure your Peppol service provider is configured and connected. Contact your e-invoicing provider if issues persist.

**Delivery rejection**: The buyer's system rejected the invoice. Light provides rejection codes. Common issues: invalid VAT number for buyer, amount mismatch, or unsupported invoice type.

**Status stuck in Submitted**: If an invoice remains "Submitted" for >24 hours, contact your Peppol service provider. Network delays can occasionally occur.

> Good to know: You can resubmit a rejected invoice after correcting the issue. Light doesn't duplicate ledger entries; resubmission only retransmits the Peppol data.

## Related articles

- [Tax compliance — HMRC (UK) and VAT](9-7-hmrc-vat.md)
- [Tax compliance — AvaTax (US)](9-8-avatax-us.md)
- [Audit-ready record keeping](9-9-audit-ready-records.md)
- [AvaTax integration (US)](../11-integrations/11-10-avatax-us.md)
