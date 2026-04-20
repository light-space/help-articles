# AvaTax - Light Customer Onboarding

## AvaTax Integration (US)

AvaTax is Avalara's automated sales tax service for US operations. Light's AvaTax integration automatically calculates applicable sales tax, manages nexus across jurisdictions, and supports filing/remittance to state authorities.

[Open in Light →](#)

### Integration capabilities

The AvaTax integration enables:

- **Sales tax calculation**: Automatic calculation based on buyer location
- **Nexus management**: Track states where tax must be collected
- **Tax return filing**: Generate and file state tax returns
- **Tax payment**: Optional Avalara remittance services
- **Multi-entity support**: Separate profiles per entity
- **Compliance documentation**: Audit-ready records

## Commercial & onboarding flow

### New AvaTax customers

If the customer is new to AvaTax:

1. Light engages Avalara via **Vini da Silva (Senior Strategic Alliance Manager)**
2. Customer introduction is made via email: **vini.dasilva@avalara.com**
3. Avalara sales team conducts:
   - Discovery sessions
   - Product demo
4. Avalara provides commercial proposal (software & services)
5. If Light implements:
   - Light shares implementation services proposal
6. Customer signs agreements with Avalara (and Light if applicable)
7. AvaTax provisioning begins

### Existing AvaTax customers

If the customer already uses AvaTax:

### Step 1: Provide API credentials (Customer)

1. Log in to Avalara tenant
2. Navigate to **Settings → API Keys**
3. Generate:
   - **Client ID**
   - **Client Secret**
4. Share securely with Light (e.g. via 1Password)

### Step 2: Light setup (Backend)

Light will:

- Store credentials securely (AWS Secrets Manager)
- Enable system-to-system communication with AvaTax
- Configure company entity mappings

## Mapping Avalara to Light

To calculate tax correctly, Light maps internal objects to Avalara:

| Light Object | Avalara Mapping |
|---|---|
| Company Entity | Avalara Company Code |

- These mappings are stored internally
- Avalara "codes" are required for accurate filing

**Note:**

- Tax calculation can work with default (`DEFAULT`) codes
- However, incorrect mappings may affect tax filing later

## Customer requirements

Customers must provide:

- **Client ID & Client Secret**
- **Company Entity Codes** (optional, defaults can be used)
- **Preferred GL account for tax posting**

## Verifying connection

Light admin can verify integration:

```
GET /v1/avatax/ping?companyId={COMPANY_ID}
```

**Expected result:**

- Successful response includes `avataxUsername`

## Setting up AvaTax integration (UI)

To connect AvaTax in Light:

1. Navigate to **Settings > Integrations > AvaTax**
2. Click **Connect**
3. Authorize via Avalara login
4. Light confirms connection

## Configuring company and entities

1. Navigate to **Company Settings**
2. Configure:
   - Legal entity name
   - Headquarters address
   - Federal ID (EIN)
   - Accounting method
3. For multi-entity setups:
   - Create profiles per entity
   - Configure nexus per entity

## Configuring nexus

1. Navigate to **Nexus settings**
2. Define:
   - State
   - Effective date
   - Tax responsibility

AvaTax will automatically apply correct tax rules.

## Configuring tax calculation

Set:

- Tax basis
- Discount handling
- Shipping taxability
- Rounding rules

## Transaction flow

When creating an invoice:

1. Light sends transaction data to AvaTax
2. AvaTax determines:
   - Jurisdiction
   - Tax rate
   - Tax amount
3. Tax is returned to Light
4. Tax appears on invoice
5. User posts to GL

## Customer exemptions

1. Upload exemption certificate in Light
2. AvaTax marks customer as exempt
3. Future invoices apply 0% tax

## Returns & refunds

- Credit notes trigger tax reversals
- AvaTax adjusts tax liability accordingly

## Filing & remittance

1. Navigate to **Reports**
2. Select state & period
3. Review tax summary
4. File directly or export

Optional: Use Avalara for automatic remittance

## Audit & reporting

Available reports:

- Sales by state
- Tax by state
- Filed returns
- Exemption certificates

Exportable for audit purposes

## Multi-state handling

AvaTax supports:

- Cross-state sales
- Drop-shipping
- Marketplace scenarios
- State-specific sourcing rules

## E-invoicing integration

AvaTax also supports:

- Peppol-compliant invoices
- E-invoice submission via Avalara

## Troubleshooting

- **No tax calculated** → Check address, nexus, tax codes
- **Incorrect tax** → Verify ship-to location
- **Connection issues** → Re-authorize integration
- **Exemption issues** → Validate certificate
- **Filing errors** → Review transaction data

## Summary

- AvaTax handles **end-to-end US sales tax compliance**
- Light manages **integration, mapping, and automation**
- Customers provide **credentials and entity setup**
- System ensures **accurate calculation, reporting, and filing**

## Related articles

## Related articles

- [Tax compliance — AvaTax (US)](../09-revenue-compliance/9-8-avatax-us.md)
- [Integrations overview](11-1-integrations-overview.md)
- [E-invoicing compliance (Peppol)](../09-revenue-compliance/9-6-e-invoicing-compliance.md)
