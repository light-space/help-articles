# AvaTax Integration (US)

AvaTax is Avalara's automated sales tax service for US operations. Light's AvaTax integration automatically calculates applicable sales tax, manages nexus across jurisdictions, and supports filing and remittance to state tax authorities.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

The AvaTax integration enables:

- **Sales tax calculation**: Automatic calculation based on buyer location
- **Nexus management**: Track states where tax must be collected
- **Tax return filing**: Generate and file state tax returns
- **Tax payment**: Optional Avalara remittance services
- **Multi-entity support**: Separate AvaTax profiles per entity
- **Compliance documentation**: Audit-ready records

## Setting up AvaTax integration

To connect AvaTax:

1. Navigate to **Settings (gear icon) > Integrations > AvaTax**
2. Click **Connect**
3. You're redirected to Avalara to authorize
4. Sign in to your Avalara account (or create one)
5. Review permissions Light is requesting
6. Click **Authorize**
7. Light confirms connection is active

Next, configure your company and entities.

## Configuring company and entity information

1. Navigate to **Settings (gear icon) > Integrations > AvaTax > Company Settings**
2. Configure:
   - **Company name**: Legal entity name
   - **Headquarters address**: For AvaTax configuration
   - **Federal ID (EIN)**: For tax identification
   - **Accounting method**: Cash or accrual
3. For multi-entity companies, create an AvaTax company profile for each Light entity and configure nexus per entity

Light uses the correct AvaTax profile when calculating tax for each entity's transactions.

## Configuring nexus

Define which states require tax collection:

1. Navigate to **Settings (gear icon) > Integrations > AvaTax > Nexus**
2. For each state, specify:
   - **State**: Which state you have nexus in
   - **Effective date**: When nexus began
   - **Tax responsibility**: Whether you are responsible for collecting tax
3. As your business grows, add new states as nexus is established

AvaTax automatically includes all configured states in tax calculations.

## Configuring tax calculation

1. Navigate to **Settings (gear icon) > Integrations > AvaTax > Tax Calculation**
2. Configure:
   - **Tax basis**: Which amount to calculate on
   - **Discount handling**: How to treat line item discounts
   - **Shipping**: Whether shipping is taxable
   - **Rounding**: How to handle penny rounding
3. Save configuration

## Transaction processing with AvaTax

When you create an AR invoice:

1. Light sends transaction details to AvaTax (customer address, line items, and shipping)
2. AvaTax determines the applicable jurisdiction, tax rate, and tax amount
3. Light displays tax on the invoice
4. You review and click **Post** to record in the GL

This happens automatically for every invoice.

## Customer exemption certificates

1. Obtain the exemption certificate from your customer
2. In Light, navigate to **Sales invoices → Customers → [Customer]**
3. Upload the certificate file under **Tax Exemption**
4. AvaTax marks the customer as exempt — future invoices apply 0% tax

Light maintains a certificate archive for your audit trail.

## Handling returns and refunds

When you issue a credit note in Light, Light sends the reversal to AvaTax automatically. AvaTax records the tax reversal and reduces your tax liability by the returned amount.

## Filing and remittance

1. Navigate to **Planning & Reports → Reports**
2. Select the period and state
3. Review the tax summary
4. Click **File** to submit directly to the state authority, or export the form to file manually

Avalara payment services can be used for automatic remittance.

## Reporting on tax

Navigate to **Planning & Reports → Reports** to view:

- Sales by state
- Tax by state
- Effective tax rate by state
- Filed returns and exemption certificates

All reports are exportable for audit purposes.

## Multi-state handling

AvaTax handles complex multi-state scenarios:

**Distance selling**: Tax is calculated for the buyer's state when you have nexus there.

**Drop-shipping**: AvaTax calculates based on dropshipper or your location depending on configuration.

**Marketplace facilitator**: AvaTax tracks marketplace-collected tax to avoid double-taxation.

**Sourcing rules**: AvaTax automatically applies state-specific origin or destination sourcing rules.

## E-invoicing integration

AvaTax also supports Peppol-compliant e-invoicing through Avalara's e-invoicing service. See [E-invoicing and Peppol setup](11-20-e-invoicing.md) for details.

## Troubleshooting

**Tax not calculating**: Verify the customer address is complete, check nexus is configured for that state, and ensure tax codes are assigned to line items.

**Wrong tax rate**: Verify the ship-to address, check nexus for that state, and confirm the item's tax code.

**Connection failed**: Re-authorize the AvaTax integration and verify your Avalara account status.

**Exemption not applying**: Verify the exemption certificate is current and uploaded, and that the customer is properly linked.

**Filing errors**: Review the tax return detail, correct any address or item coding issues, and re-file.

## Related articles

- [Tax compliance — AvaTax (US)](../09-revenue-compliance/9-8-avatax-us.md)
- [Integrations overview](11-1-integrations-overview.md)
- [E-invoicing and Peppol setup](11-20-e-invoicing.md)
- [E-invoicing compliance (Peppol)](../09-revenue-compliance/9-6-e-invoicing-compliance.md)
