# E-invoicing and Peppol

This article explains how to set up e-invoicing, configure Peppol network connectivity, and ensure compliance with electronic invoicing requirements in Light.

[Open in Light →](https://app.light.inc/accounting/invoicing)

## What is e-invoicing?

E-invoicing is the electronic exchange of invoice documents in a standardized format between trading partners. Instead of PDF or paper invoices, e-invoicing uses structured data that can be automatically processed by receiving systems. E-invoicing improves accuracy, reduces processing time, and enhances audit trails.

> Good to know: Many countries now mandate e-invoicing for B2B transactions. Light supports the Peppol network and other e-invoicing standards.

## Peppol network overview

Peppol (Pan-European Public Procurement OnLine) is a free, open network for electronic business document exchange. Key Peppol features:

- **Standardized Formats**: Uses UBL (Universal Business Language) XML format
- **Network Operators**: Routes documents through certified service providers
- **Global Coverage**: Supports 40+ countries and expanding
- **Mandatory in Many Jurisdictions**: EU countries and others require Peppol for B2B invoicing
- **Free to Join**: No licensing fees for network participation

## Enabling e-invoicing in Light

1. Navigate to **Settings (gear icon) → E-invoicing** (or **Settings (gear icon) → Integrations**)
2. Click **Enable E-invoicing**
3. Choose your **E-invoicing Network**:
   - **Peppol**: For EU and global B2B invoicing
   - **Other Standards**: Alternative networks by jurisdiction
4. Click **Next** to proceed with configuration

## Registering on the Peppol network

To send and receive invoices via Peppol:

1. Register with a Peppol **Service Provider** (authorized network operator)
2. Light provides a list of certified service providers by country
3. Register your company with your chosen provider
4. They issue you a **Peppol Identifier** (Peppol participant ID)
5. Provide the Peppol Identifier to Light

Your Peppol Identifier is unique and identifies your organization on the network (typically formatted as country-code:number-scheme:identifier).

## Configuring entity e-invoicing details

Each company entity can have e-invoicing enabled:

1. Go to **Settings (gear icon) → Entities**
2. Select the entity
3. Click **Edit**
4. Scroll to **E-invoicing Configuration**
5. Enter the **Peppol Identifier** for this entity
6. Enter the **EAS Code** (Electronic Address Scheme):
   - For most EU companies: 9930 (TAXID) or 0007 (Organization number)
   - Consult your jurisdiction's requirements
7. Enter the **E-invoice Address**: The complete Peppol address
8. Set **E-invoicing Status** to **Active**
9. Click **Save**

> Tip: Different entities within your group can have different Peppol registrations based on their jurisdiction.

## E-invoicing compliance requirements

Different jurisdictions have specific requirements. The EU mandates UBL XML via Peppol for B2B invoices above minimum thresholds with VAT validation required. Denmark requires all B2B invoices via specific service providers. Some countries have national systems instead of Peppol. To verify compliance, go to **Settings (gear icon) → E-invoicing** and click **Compliance Check** to validate VAT numbers, Peppol identifiers, and EAS codes.

## Sending and receiving e-invoices

When creating an invoice for a Peppol customer, mark Send via Peppol and Light converts to UBL format and transmits automatically. For non-Peppol customers, use email delivery. When vendors send Peppol invoices, they arrive in your inbox and Light automatically retrieves them. Invoices appear in Accounts Payable with pre-populated details extracted from UBL format. Peppol invoices capture complete audit trail information automatically.

## VAT number validation in Peppol

Peppol transactions validate VAT numbers:

1. When sending an invoice, Light validates your VAT number
2. When receiving an invoice, Light validates the vendor's VAT number
3. For EU entities, Light can perform VIES (VAT Information Exchange System) checks
4. Invalid VAT numbers trigger warnings but don't block transmission
5. Correct VAT numbers before final sending to ensure compliance

> Good to know: Peppol's built-in validation helps prevent incorrect VAT registration numbers from being transmitted.

## Peppol identifier management

Manage your Peppol identifiers in one place:

1. Go to **Settings (gear icon) → E-invoicing**
2. Click **Manage Peppol Identifiers**
3. View all registered identifiers for your entities
4. Update identifiers if service providers change
5. Track validation status for each identifier
6. Generate Peppol connection test reports

## E-invoicing monitoring and best practices

In **Planning & Reports → Reports** or **E-invoicing Dashboard**, track sent/received invoices, failed transmissions, and validation errors filtered by entity or date. Register entities before mandate deadlines, verify identifiers are current, validate VAT numbers before sending, and test with sample invoices. Monitor the dashboard regularly, archive logs for compliance, train your team, and maintain service provider contact information.

## Related articles

- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
- [Tax and VAT Configuration](/articles/02-organization-setup/2-5-tax-vat-configuration)
- [Currency Settings](/articles/02-organization-setup/2-6-currency-settings)
