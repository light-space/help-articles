# E-invoicing: Peppol and myDATA

This article explains how to configure e-invoicing details in Light to support electronic invoice exchange via the Peppol and myDATA networks.

[Open in Light →](https://app.light.inc/settings/entities)

## What is e-invoicing?

E-invoicing is the electronic exchange of invoice documents in a standardized format between trading partners. Instead of PDF or paper invoices, e-invoicing uses structured data that can be automatically processed by receiving systems. E-invoicing improves accuracy, reduces processing time, and enhances audit trails.

> Good to know: Many countries now mandate e-invoicing for B2B transactions. Light supports e-invoicing configuration through entity settings and tax code EDIFACT codes.

## Supported networks

Light supports e-invoicing via two networks:

- **Peppol**: Pan-European Public Procurement OnLine network, used across 40+ countries
- **myDATA**: Greece's national e-invoicing system

Each network has different onboarding and configuration requirements (see sections below).

## Peppol network overview

Peppol (Pan-European Public Procurement OnLine) is a free, open network for electronic business document exchange. Key Peppol features:

- **Standardized Formats**: Uses UBL (Universal Business Language) XML format
- **Network Operators**: Routes documents through certified service providers
- **Global Coverage**: Supports 40+ countries and expanding
- **Mandatory in Many Jurisdictions**: EU countries and others require Peppol for B2B invoicing
- **Free to Join**: No licensing fees for network participation

## myDATA network overview

myDATA is Greece's national e-invoicing network, required for businesses operating in Greece. Key myDATA features:

- **Greece-Specific**: Used for Greek tax reporting and compliance
- **Simplified Onboarding**: Does not require a registration workflow or document verification (unlike Peppol)
- **Immediate Availability**: Once configured on your entity, myDATA integration is active

> Note: myDATA onboarding does not require uploading proof-of-ownership documents or waiting for verification. After configuring your entity's e-invoicing details, you can begin sending invoices immediately.

## Configuring e-invoicing on entities

Each company entity can have e-invoicing details configured:

1. Go to [**Settings (gear icon) → Entities**](https://app.light.inc/settings/entities)
2. Click **+ Create entity** (for new entities) or click an existing entity and then **Edit**
3. In the **E-invoicing (optional)** section, fill in:
   - **EAS code**: The Electronic Address Scheme identifier (e.g., 9930 for EU tax ID, 0007 for organization number)
   - **E-invoice address**: The network address for this entity (Peppol identifier or myDATA registration, depending on your network)
4. Click **Create** or **Save**

> Tip: Different entities within your group can have different network registrations based on their jurisdiction.

## EAS codes

The EAS code identifies the type of addressing scheme used for your e-invoicing identifier. Common EAS codes include:

- **0007**: Organization number (used in many EU countries)
- **9930**: Tax identification number
- Other country-specific codes as required by your jurisdiction

Consult your jurisdiction's requirements to determine the correct EAS code.

## EDIFACT codes on tax codes

Tax codes in Light include an optional **EDIFACT** field that supports e-invoicing compliance:

1. Go to [**Accounting → Tax codes**](https://app.light.inc/accounting/ledger-tax-codes)
2. Click **+ Create tax code** or edit an existing tax code
3. Select the appropriate **EDIFACT (optional)** code from the dropdown
4. This EDIFACT code is included in e-invoice documents to classify the tax treatment

## Registering on the Peppol network

To send and receive invoices via Peppol:

1. Register with a Peppol **Service Provider** (authorized network operator)
2. They issue you a **Peppol Identifier** (participant ID)
3. Enter this identifier as the **E-invoice address** on your entity in Light
4. Set the appropriate **EAS code** for your registration type
5. Upload proof-of-ownership documents as required by your service provider

Your Peppol Identifier is unique and identifies your organization on the network (typically formatted as country-code:number-scheme:identifier).

> Note: Peppol onboarding requires document verification. You'll need to upload proof-of-ownership documents and wait for verification before you can send invoices via Peppol.

## Best practices

- Register entities for e-invoicing before mandate deadlines in your jurisdiction
- Verify EAS codes and e-invoice addresses are correct before sending invoices
- Configure e-invoicing details on all entities that will participate in electronic document exchange
- Assign the correct EDIFACT codes to tax codes used in e-invoicing transactions
- For Peppol: maintain current service provider contact information
- For myDATA: ensure your Greek tax registration details are up to date on your entity

## Related articles

- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
- [Tax and VAT Configuration](/articles/02-organization-setup/2-5-tax-vat-configuration)
- [Currency Settings](/articles/02-organization-setup/2-6-currency-settings)
