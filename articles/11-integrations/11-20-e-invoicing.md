# E-Invoicing and Peppol Setup

E-invoicing is the structured, digital exchange of invoice data between buyers and suppliers in a machine-readable format recognized by tax authorities. Light supports e-invoicing through Avalara, enabling businesses to send and receive legally compliant electronic invoices across multiple international networks.

[Open in Light →](https://app.light.inc/settings/integrations)

## What is e-invoicing?

Unlike PDF invoices, e-invoices are structured XML documents transmitted through certified networks. Light supports the following networks:

- **Peppol**: The primary network, used across 40+ countries including the EU, Australia, Japan, and the UK
- **Nemhandel**: Denmark's national e-invoicing network
- **SDI**: Italy's mandatory clearance network

Many countries now mandate e-invoicing for B2B and B2G (business-to-government) transactions. Light validates all invoices against the relevant network's rules before transmission.

## Country coverage

| Country | Network | Supported by Light | Mandate Scope | Mandate Status |
|---|---|---|---|---|
| Australia | Peppol (PINT A-NZ) | Yes | B2G | Active |
| Austria | Peppol | Yes | B2G | Active |
| Belgium | Peppol | Yes | B2G | Active |
| Croatia | Peppol | Yes | B2G | Active |
| Czechia | Peppol | Yes | B2G | Active |
| Denmark | Peppol, Nemhandel | Yes | B2G | Active |
| Estonia | Peppol | Yes | B2G | Active |
| Finland | Peppol | Yes | B2G | Active |
| France | Peppol | Yes | B2G (B2B upcoming) | B2G Active |
| Germany | Peppol | Yes | B2G (B2B upcoming) | B2G Active |
| Greece | Peppol | Yes | B2G, B2B, B2C | Active |
| Ireland | Peppol | Yes | B2G | Active |
| Italy | SDI | Yes | B2G, B2B, B2C | Active |
| Japan | Peppol JP PINT | Yes | B2G | Active |
| Luxembourg | Peppol | Yes | B2G | Active |
| Malta | Peppol | Yes | B2G | Active |
| Netherlands | Peppol | Yes | B2G | Active |
| New Zealand | Peppol (PINT A-NZ) | Yes | B2G | Active |
| Norway | Peppol | Yes | B2G | Active |
| Poland | Peppol | Yes | B2G | Active |
| Portugal | Peppol | Yes | B2G, B2B, B2C | Active |
| Singapore | Peppol | Yes | B2B | Upcoming |
| Spain | Peppol | Yes | B2G | Active |
| Sweden | Peppol | Yes | B2G | Active |
| Switzerland | Peppol | Yes | B2G | Active |
| UK | Peppol | Yes | B2G | Active |

## Enabling e-invoicing in Light

To activate e-invoicing:

1. Navigate to **Settings (gear icon) > Integrations**
2. Click **Add Integration** and select **Avalara**
3. Complete the initial setup form
4. Avalara sends a confirmation email to your account — this typically takes a few minutes

## Configuring entities for e-invoicing

Each entity that will send or receive e-invoices must be configured with its network identifier. After completing the Avalara setup, the legal representative of each entity will receive an email from Avalara containing the entity's assigned identifier.

To configure each entity:

1. Navigate to **Settings (gear icon) > Entities**
2. Click an existing entity and select **Edit**
3. In the **E-invoicing** section, enter:
   - **EAS Code**: The identifier scheme code (e.g. `9930` for German VAT, `0192` for Norwegian Org No)
   - **E-Invoice Address**: The actual identifier value for this entity on the network
   - **VAT Number** and **Business Registration Number**
4. Save

> Good to know: If the Avalara confirmation email has not arrived after 24 hours, verify that the legal representative email is correct. The identifier can also be found directly in the Avalara platform under the entity's profile.

## Configuring customers for e-invoicing

For each customer you will send e-invoices to, add their e-invoicing details:

1. Navigate to **Sales invoices → Customers**
2. Open the customer record and click **Edit**
3. Fill in:
   - **EAS Code**: The customer's identifier scheme code
   - **E-Invoice Address**: The customer's network identifier
   - **E-Invoice Network**: The network the customer is registered on (Peppol, Nemhandel, or SDI)
   - **Customer Type**: B2B, B2G, or B2C
4. Save

> Tip: Use the [Peppol directory](https://directory.peppol.eu/public/locale-en_US/menuitem-search) or [Nemhandel registry](https://registration.nemhandel.dk/NemHandelRegisterWeb/public/participant/info) to look up a customer's identifier if they don't have it to hand. For Italy (SDI), the Codice Destinatario must be obtained directly from the customer.

## Peppol identifier format

A Peppol ID always follows the format `<ICD Code>:<Identifier Value>`. The ICD code is a 4-digit number that identifies the type of business identifier.

**Examples:**
- `0007:5566778899` — Swedish organisation number
- `9930:DE123456789` — German VAT number
- `0192:999888777` — Norwegian organisation number
- `0088:1234567890123` — Global Location Number (GLN)

Common ICD codes by country:

| Country | Identifier Type | ICD Code | Example |
|---|---|---|---|
| Australia | ABN | 0151 | `0151:51824753556` |
| Austria | VAT | 9914 | `9914:ATU12345678` |
| Belgium | Enterprise No | 0208 | `0208:0123456789` |
| Denmark | CVR | 0184 | `0184:12345678` |
| France | SIRET | 0009 | `0009:12345678901234` |
| Germany | VAT | 9930 | `9930:DE123456789` |
| Ireland | VAT | 9935 | `9935:IE1234567A` |
| Italy (Peppol) | VAT | 9906 | `9906:IT12345678901` |
| Netherlands | KvK | 0106 | `0106:12345678` |
| Norway | Org No | 0192 | `0192:999888777` |
| Spain | VAT | 9920 | `9920:ESB12345678` |
| Sweden | Org No | 0007 | `0007:5566778899` |
| UK | VAT | 9932 | `9932:GB123456789` |
| Global | GLN | 0088 | `0088:1234567890123` |

> Good to know: GLN (`0088`) and DUNS (`0060`) are global schemes accepted across all Peppol countries — useful when a company uses one of these instead of a country-specific identifier.

Peppol ID validation rules:

| Rule | Check |
|---|---|
| Format | Must be `NNNN:value` — 4-digit ICD code, colon, then the identifier |
| No spaces | No spaces anywhere in the ID |
| Separator | Always `:` not `-` |
| Country prefix | VAT schemes (9xxx) include the country prefix; Org No schemes (0xxx) typically do not |

## Configuring EDIFACT codes on tax codes

Tax codes used on e-invoices must have an EDIFACT code assigned to classify the tax treatment within the outgoing XML. This is required for invoices to be accepted by certain tax authorities and recipients.

1. Navigate to **Accounting → Tax codes**
2. Click **+ Create tax code**, or open an existing tax code and click **Edit**
3. Select the appropriate **EDIFACT** code from the dropdown
4. Save

> Good to know: Missing EDIFACT codes are a common cause of invoice rejection. Assign EDIFACT codes to every tax code used on e-invoice transactions.

## Sending e-invoices

Once your entities and customers are configured:

1. Create an AR invoice as normal in **Sales invoices**
2. Verify all required fields are complete
3. Click **Post** to record in the GL
4. Click **Send via Peppol** (or the relevant network) to transmit

Light converts the invoice to the correct XML format and submits it. Invoice status updates automatically:

- **Submitted**: Sent to the network, awaiting confirmation
- **Delivered**: Confirmed received by the buyer's access point
- **Accepted**: Buyer's system processed the invoice
- **Rejected**: Buyer's system could not process the invoice (error details provided)

> Tip: Pre-validate invoices before posting by clicking **Validate**. This identifies compliance issues early without affecting your ledger.

## Receiving e-invoices

If you are registered to receive e-invoices, Light automatically monitors your network inbox. Received invoices appear in **Accounting → Accounting documents**, where you can match them to purchase orders and create AP invoices with auto-populated fields from the transmitted document.

## Troubleshooting

**Validation errors**: Check the error messages — typically a missing VAT number, incorrect tax code, or missing EDIFACT code. Fix and resubmit.

**Transmission failures**: Ensure the Avalara integration is active and connected. Contact Light support if the issue persists.

**Invoice rejected by buyer**: Light provides rejection codes. Common causes include an invalid buyer identifier, amount mismatch, or unsupported invoice type. Correct the issue and resubmit — resubmission does not duplicate ledger entries.

**Status stuck at Submitted**: If an invoice remains "Submitted" for more than 24 hours, contact Light support. Network delays can occasionally occur.

**Identifier email not received**: Verify the legal representative email is correct in the Avalara setup. The identifier can also be found directly in the Avalara platform under the entity's profile.

## Related articles

- [E-invoicing compliance (Peppol)](../09-revenue-compliance/9-6-e-invoicing-compliance.md)
- [E-invoicing and Peppol setup](../02-organization-setup/2-7-e-invoicing-peppol.md)
- [AvaTax integration (US)](11-10-avatax-us.md)
- [Sphere integration (US)](11-19-sphere-us.md)
- [Integrations overview](11-1-integrations-overview.md)
- [Tax and VAT configuration](../02-organization-setup/2-5-tax-vat-configuration.md)
