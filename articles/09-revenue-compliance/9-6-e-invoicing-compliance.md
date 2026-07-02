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

> Good to know: Light currently supports sending Peppol invoices to customers in Belgium, Denmark, Germany, Finland, Luxembourg, Norway, and Sweden. Contact support if you need to send to additional countries.

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

> Good to know: Different countries have additional Peppol rules (e.g., Germany requires seller contact details — see below). Light adapts validation based on buyer country.

### Seller contact information (Germany)

If you send Peppol invoices to German customers, you must include at least one seller contact field to meet German compliance rule DE-R-002. Set these using custom properties on the invoice or customer:

- `cbc_seller_contact_name` — Contact person's name
- `cbc_seller_contact_telephone` — Contact phone number
- `cbc_seller_contact_electronic_mail` — Contact email address

Light checks the invoice first, then falls back to the customer record if the property isn't set on the invoice. If all three are missing, German Peppol validation will reject the invoice. For other countries these fields are optional but recommended.

## Enabling Peppol in Light

To activate Peppol e-invoicing:

1. Navigate to **Settings** (gear icon in bottom-left sidebar) > **Integrations**
2. Click **Enable Peppol**
3. Verify your company information:
   - Legal business name
   - VAT number or company registration number
   - Country
   - Complete registered address
4. Select which entities participate in e-invoicing (registration is per entity)
5. Complete the registration through the secure hosted registration flow. You may be asked to upload a proof-of-ownership document to verify your entity
6. Track the registration status: **Pending verification** → **Registration pending** → **Registered** (or **Failed**)

Light validates that your entity's country and VAT number are set before starting Peppol registration.

## Sending Peppol invoices

Once enabled, you can submit invoices via Peppol:

1. Create an AR (accounts receivable) invoice normally
2. Make sure the customer record has the required e-invoice routing fields (EAS code, e-invoice address, e-invoice network)
3. Post and send the invoice, enabling the **e-invoicing toggle** in the send dialog
4. Light converts the invoice to Peppol XML format
5. Light submits it to the Peppol network via its e-invoicing provider

The invoice's e-invoice status badge changes to **Processing** while the submission is in flight, then **Delivered** once receipt is confirmed (or **Failed** if the submission was unsuccessful).

> Tip: Pre-validate invoices before posting by clicking the **Validate** button. This identifies compliance issues early without affecting your ledger.

## Peppol transmission and delivery

When you submit a Peppol invoice:

1. Light passes the invoice to its e-invoicing provider
2. The service provider transmits to a Peppol access point in the buyer's country
3. The buyer's system receives and processes the invoice
4. Delivery confirmation is sent back to you

Light tracks invoice status through the entire transmission process:

- **Not submitted**: The invoice has not been sent to the Peppol network
- **Processing**: Sent to the Peppol network, awaiting confirmation
- **Delivered**: Confirmed received by buyer's access point
- **Failed**: The invoice could not be delivered (with error details)

## Receiving Peppol invoices

If you're a buyer, you can also receive Peppol invoices from suppliers:

1. Light automatically monitors your Peppol inbox
2. Received e-invoices are converted to documents and processed through the bills flow
3. They appear as bills in **Spend management → Bills**
4. You can match them to purchase orders
5. Light auto-populates bill details from the transmitted document

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

**Transmission failures**: Ensure your entity's e-invoicing registration is complete (status **Registered**). Contact Light support if issues persist.

**Failed status**: The invoice could not be delivered. Light provides error details. Common issues: invalid VAT number for buyer, amount mismatch, or unsupported invoice type.

**Status stuck in Processing**: If an invoice remains "Processing" for >24 hours, contact Light support. Network delays can occasionally occur.

> Good to know: You can resubmit a failed invoice after correcting the issue. Light doesn't duplicate ledger entries; resubmission only retransmits the Peppol data.

## Related articles

- [Tax compliance — HMRC (UK) and VAT](9-7-hmrc-vat.md)
- [Tax compliance — AvaTax (US)](9-8-avatax-us.md)
- [Audit-ready record keeping](9-9-audit-ready-records.md)
- [AvaTax integration (US)](../11-integrations/11-10-avatax-us.md)
