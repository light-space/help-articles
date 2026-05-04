# Greek myDATA e-invoicing

This article explains how to configure Greek myDATA e-invoicing details in Light to support electronic invoice submission to AADE (the Greek tax authority) via Invopop.

[Open in Light →](https://app.light.inc/settings/entities)

## What is myDATA?

myDATA (μyΔΑΤΑ) is Greece's mandatory e-invoicing and digital reporting system operated by AADE (Independent Authority for Public Revenue). All businesses in Greece must electronically submit transaction data to IAPR (the myDATA submission portal) in real-time or near-real-time.

> Good to know: myDATA applies to all B2B and B2C transactions in Greece. Light supports myDATA e-invoicing through Invopop, which handles document validation and submission to IAPR.

## myDATA network overview

Key features of Greek myDATA:

- **Domestic Network**: Used for transactions involving Greek entities
- **Real-Time Submission**: Invoices are submitted to IAPR immediately after issuance
- **IAPR MARK**: Each accepted document receives a unique identifier from IAPR
- **Structured Data**: Uses standardized formats to ensure compliance and automatic processing
- **Credit Note Linking**: Associated credit notes reference the original invoice's IAPR MARK

## Configuring e-invoicing on entities

Each Greek company entity can have e-invoicing details configured:

1. Go to [**Settings (gear icon) → Entities**](https://app.light.inc/settings/entities)
2. Click **+ Create entity** (for new entities) or click an existing entity and then **Edit**
3. In the **E-invoicing (optional)** section, fill in:
   - **E-invoice network**: Select **myDATA** from the dropdown
   - **EAS code**: The Electronic Address Scheme identifier (e.g., 9930 for Greek tax ID)
   - **E-invoice address**: Your Greek VAT number or tax registration identifier
4. Click **Create** or **Save**

> Tip: Only entities with a Greek address can use the myDATA network. Invopop validates and submits documents to IAPR on your behalf.

## Document numbering requirements

Greek myDATA requires invoices to follow a specific numbering format:

- **Alphanumeric series**: A prefix containing letters and/or digits (e.g., "INV2024")
- **Numeric serial number**: A sequence of digits at the end (e.g., "001")

### How Light handles document numbers

Light automatically splits your document number into series and serial components:

- Document number **INV2024-001** becomes series **INV2024** and code **001**
- Document number **A1-2024-123** becomes series **A12024** and code **123**
- Non-alphanumeric characters in the prefix are stripped (hyphens, spaces, etc.)

> Important: Your document numbers must contain at least one letter or digit before the final numeric sequence, and must end with at least one digit. Examples: "INV-001" ✓, "2024-001" ✓, "001" ✗

## Supported VAT rates

Greek myDATA recognizes specific VAT rates depending on the region:

### Mainland rates

- **24%** – Standard rate
- **13%** – Reduced rate
- **6%** – Super-reduced rate

### Island rates

Certain Greek islands (Leros, Lesbos, Kos, Samos, Chios) have reduced rates:

- **17%** – Island standard rate (30% reduction from 24%)
- **9%** – Island reduced rate (30% reduction from 13%)
- **4%** – Island super-reduced rate (30% reduction from 6%)

Configure the appropriate rate on your tax codes based on your entity's location and transaction details.

> Tip: Light automatically maps your configured tax rate to the correct myDATA tax category. Other VAT rates will be rejected by IAPR during submission.

## Credit note types

Greek myDATA distinguishes between two types of credit notes:

### Associated credit notes (Type 5.1)

Credit notes linked to a specific original invoice:

- Reference the original invoice's IAPR MARK
- Include the original invoice's series, code, and issue date
- Used for corrections, returns, or discounts related to a specific invoice

In Light, create an associated credit note by linking it to the original invoice when you create the credit note.

### Non-associated credit notes (Type 5.2)

Credit notes issued without reference to a specific invoice:

- No preceding invoice reference
- Used for general credits, promotional discounts, or adjustments not tied to a single invoice
- Submitted with document type code 5.2

In Light, create a non-associated credit note by leaving the invoice reference empty.

> Good to know: Associated credit notes require the original invoice to have been successfully submitted to IAPR first. Light automatically retrieves the IAPR MARK when linking credit notes.

## EDIFACT codes on tax codes

Tax codes in Light require an **EDIFACT** code for myDATA compliance:

1. Go to [**Accounting → Tax codes**](https://app.light.inc/accounting/ledger-tax-codes)
2. Click **+ Create tax code** or edit an existing tax code
3. Select the appropriate **EDIFACT (optional)** code from the dropdown:
   - **S** – Standard rate (use with 24%, 13%, 6%, 17%, 9%, or 4%)
   - **E** – Exempt (domestic exemption)
   - **Z** – Zero rate
   - **AE** – Reverse charge
   - **K** – Intra-community supply
   - **G** – Export outside EU
   - **O** – Outside scope of VAT
4. Enter the VAT **Rate** percentage (if applicable)
5. Click **Create** or **Save**

> Important: All tax codes used on myDATA invoices must have an EDIFACT code configured. Transactions without EDIFACT codes will fail validation during submission.

## Best practices

- Ensure your entity is configured with the myDATA network before issuing invoices to Greek customers
- Use consistent document number formats that include both a series prefix and numeric serial
- Configure EDIFACT codes on all tax codes used in Greek transactions
- For associated credit notes, verify the original invoice was successfully submitted before creating the credit note
- Select the correct VAT rate (mainland or island) based on your entity's registration and the transaction location
- Monitor submission status to confirm IAPR has accepted your documents

## Related articles

- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
- [E-invoicing and Peppol](/articles/02-organization-setup/2-7-e-invoicing-peppol)
- [Tax and VAT Configuration](/articles/02-organization-setup/2-5-tax-vat-configuration)
