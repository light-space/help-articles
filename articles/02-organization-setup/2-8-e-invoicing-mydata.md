# Greek myDATA e-invoicing

This article explains how to configure Greek myDATA e-invoicing in Light. If your company operates in Greece, you can send invoices and credit notes to the Greek tax authority (AADE) via the myDATA network using Light's integration with Invopop.

[Open in Light →](https://app.light.inc/settings/entities)

## What is myDATA?

myDATA is Greece's mandatory e-invoicing and digital reporting system managed by the Greek tax authority (AADE). Key myDATA features:

- **Tax Authority Reporting**: All invoices and credit notes are submitted to AADE in real-time
- **Digital Audit Trail**: Creates a complete electronic record of transactions for tax compliance
- **Mandatory for Greek Businesses**: Required for B2B and B2C transactions in Greece
- **IAPR Acceptance**: Each document receives an IAPR MARK from the tax authority upon acceptance

Light integrates with Invopop to handle myDATA submissions automatically when you finalize invoices and credit notes.

> Good to know: myDATA is specific to Greece. For cross-border EU e-invoicing, see the [Peppol article](/articles/02-organization-setup/2-7-e-invoicing-peppol).

## Configuring myDATA on Greek entities

To enable myDATA on a Greek company entity:

1. Go to [**Settings (gear icon) → Entities**](https://app.light.inc/settings/entities)
2. Click **+ Create entity** (for new entities) or click an existing Greek entity and then **Edit**
3. Ensure the entity's country is set to **Greece**
4. In the **E-invoicing (optional)** section, fill in:
   - **EAS code**: The Electronic Address Scheme identifier for your Greek tax ID (typically **9930** for EU tax ID)
   - **E-invoice address**: Your Greek VAT number registered with AADE
5. Click **Create** or **Save**

Once configured, Light automatically submits finalized invoices and credit notes to myDATA via Invopop.

> Tip: Contact your Greek tax advisor or AADE if you need help determining your correct EAS code and registration details.

## Document numbering requirements

Greek myDATA requires document numbers to follow a specific format:

- **Series**: An alphanumeric prefix (e.g., "INV", "INV2024")
- **Serial number**: A numeric suffix (e.g., "001", "1234")

Example valid document numbers:
- `INV-001` → series: "INV", serial: "001"
- `INV2024-1234` → series: "INV2024", serial: "1234"
- `A-5` → series: "A", serial: "5"

Light automatically splits your document number into series and serial when submitting to myDATA. Non-alphanumeric characters (like hyphens) in the prefix are removed.

> Important: Document numbers must contain at least one letter or digit as a prefix AND at least one digit as the serial number. Pure numeric document numbers (e.g., "12345") will fail myDATA validation.

## VAT rates for Greek myDATA

myDATA only accepts specific VAT rates. Your tax codes must use one of these rates:

**Mainland Greece:**
- 24% (standard rate)
- 13% (reduced rate)
- 6% (super-reduced rate)

**Greek Islands** (Leros, Lesbos, Kos, Samos, Chios):
- 17% (standard rate)
- 9% (reduced rate)
- 4% (super-reduced rate)

If you use a different VAT rate, Light will reject the invoice before submission with a clear error message.

> Good to know: Exempt, reverse-charge, and zero-rated tax codes are supported via EDIFACT codes (see below). The rate restrictions apply only to standard VAT tax codes.

## EDIFACT codes on tax codes

Tax codes used in myDATA invoices **must** have an EDIFACT code configured. This classifies the tax treatment for e-invoicing:

1. Go to [**Accounting → Tax codes**](https://app.light.inc/accounting/ledger-tax-codes)
2. Click **+ Create tax code** or edit an existing tax code
3. Select the appropriate **EDIFACT (optional)** code from the dropdown:
   - **S**: Standard rate (24%, 13%, 6%, or island equivalents)
   - **E**: Exempt
   - **Z**: Zero-rated
   - **AE**: Reverse charge
   - **K**: Intra-community supply
   - **G**: Export
   - **O**: Outside scope of VAT
4. Click **Save**

Light will block invoices that use tax codes without EDIFACT codes when myDATA is enabled on the entity.

## Credit notes and linked invoices

When you create a credit note linked to an original invoice:

- Light automatically references the original invoice's **IAPR MARK** in the credit note submission
- The credit note must be finalized **after** the original invoice has been accepted by AADE
- If you try to finalize a credit note before the linked invoice is accepted, Light will show an error and ask you to try again later

Non-linked credit notes (standalone corrections not tied to a specific invoice) are also supported by myDATA.

## Best practices

- Configure myDATA on your Greek entities before issuing production invoices
- Use a consistent document numbering scheme with clear series prefixes (e.g., "INV-", "CN-")
- Verify all tax codes have correct EDIFACT codes and use approved Greek VAT rates
- For linked credit notes, ensure the original invoice has been finalized and accepted by AADE first
- Consult [AADE's myDATA documentation](https://www.aade.gr/mydata) for official regulatory requirements

## Related articles

- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
- [E-invoicing and Peppol](/articles/02-organization-setup/2-7-e-invoicing-peppol)
- [Tax and VAT Configuration](/articles/02-organization-setup/2-5-tax-vat-configuration)
