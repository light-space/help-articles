# AvaTax Integration (US)

AvaTax is Avalara's automated sales tax service for US operations. Light's AvaTax integration automatically calculates applicable sales tax, handles nexus across all US jurisdictions, and files/remits tax returns to state authorities.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

The AvaTax integration enables:

- **Sales tax calculation**: Automatic calculation for each transaction based on buyer location
- **Nexus management**: Tracking which states require tax collection/remittance
- **Tax return filing**: Automated generation of state tax returns
- **Tax payment**: Optional integration with Avalara payment services for remittance
- **Multi-entity support**: Separate AvaTax profiles per entity
- **Compliance documentation**: Audit-ready tax records

This automates US sales tax entirely.

## Setting up AvaTax integration

To connect AvaTax:

1. Navigate to **Settings (gear icon) > Integrations > AvaTax**
2. Click **Connect**
3. You're redirected to Avalara to authorize
4. Sign in to your Avalara account (or create one)
5. Review permissions Light is requesting
6. Click **Authorize**
7. Light confirms connection is active

Next, configure your company and entities in AvaTax.

## Configuring company and entity information

Provide AvaTax with your company details:

1. Navigate to **Settings > Integrations > AvaTax > Company Settings**
2. Configure:
   - **Company name**: Legal entity name
   - **Headquarters address**: For AvaTax configuration
   - **Federal ID (EIN)**: For tax identification
   - **Accounting method**: Cash or accrual
3. For multi-entity companies:
   - Create AvaTax company profile for each Light entity
   - Configure nexus per entity (states where you have nexus)
4. Save configuration

Light then uses the correct AvaTax profile when calculating tax for transactions.

## Configuring nexus

Define which states require tax collection:

1. Navigate to **Settings > Integrations > AvaTax > Nexus**
2. For each state, specify:
   - **State**: Which state(s) you have nexus
   - **Effective date**: When nexus began
   - **Tax responsibility**: Are you responsible for collecting tax?
3. Light uses this to determine which states' tax to calculate
4. As your business grows, add new states as nexus is established

AvaTax automatically includes all configured states in tax calculations.

## Configuring tax calculation

Set up how AvaTax determines tax:

1. Navigate to **Settings > Integrations > AvaTax > Tax Calculation**
2. Configure:
   - **Tax basis**: Calculate on which amount (line item, invoice total, tax before discount)
   - **Discount handling**: How to treat line item discounts
   - **Shipping**: Is shipping taxable?
   - **Rounding**: How to handle penny rounding
3. Save configuration

These settings match AvaTax behavior to your business model.

## Transaction processing with AvaTax

When you create an AR invoice:

1. Light sends transaction details to AvaTax:
   - Customer ship-to address
   - Line items (description and amount)
   - Shipping amount (if any)
   - Invoice total
2. AvaTax determines:
   - Applicable jurisdiction based on address
   - Tax rate for that jurisdiction
   - Tax amount for each line and shipping (if applicable)
   - Total invoice tax
3. Light receives tax amount from AvaTax
4. Light displays tax on invoice
5. You review and click Post to GL

This happens automatically for every invoice.

## Customer exemption certificates

Handle tax-exempt customers:

1. Customer provides tax exemption certificate
2. In Light, upload to customer record: **Settings > Customers > [Customer] > Tax Exemption**
3. Upload certificate file
4. AvaTax notes exemption in its system
5. Future transactions with this customer are marked exempt
6. No tax calculated (correct for exempt customers)

Light maintains certificate archive for audit trail.

## Handling returns and refunds

When customers return goods or you issue credit:

1. Create a credit note in Light
2. Light marks it as a return/refund
3. Light sends reversal information to AvaTax
4. AvaTax records the tax reversal
5. Your tax liability reduces by the returned amount

This correctly tracks returns in tax accounting.

## Tax rate automation

AvaTax automatically handles:

- Tax rate changes (states change rates quarterly)
- Special jurisdictions (local taxes, special districts)
- Tax code exceptions (items that are tax-treated differently by state)
- Holiday periods (states with varying holiday sales tax rules)

You don't need to track rate changes; AvaTax stays current.

## Multi-state complexity handling

AvaTax handles complex multi-state scenarios:

**Distance selling**: If you ship to a customer in another state where you have nexus, AvaTax calculates that state's tax.

**Drop-shipping**: If third party ships for you, AvaTax calculates based on dropshipper location or your location (depends on your configuration).

**Marketplace facilitator**: If you sell through a marketplace that collects tax, AvaTax tracks and ensures no double-taxation.

**Sourcing rules**: Different states have different sourcing rules (where tax is calculated from). AvaTax handles state-specific rules.

## Filing and remittance

AvaTax prepares your tax returns:

1. Navigate to **Planning & Reports → Reports**
2. Select period and state
3. Light retrieves transactions from AvaTax
4. AvaTax calculates total tax owed
5. Light displays tax return form (ready to file)
6. Click **File** to submit to state
7. Or export form to file manually

Light can optionally remit tax directly (if using Avalara payment services).

## Audit documentation

AvaTax maintains complete audit records:

1. Navigate to **Planning & Reports → Reports**
2. View all:
   - Transactions and tax calculations
   - Tax returns filed
   - Tax payments made
   - Exemption certificates on file
3. Export audit package for tax professionals

This provides everything auditors need.

## Reporting on tax

Generate tax reports:

1. Navigate to **Planning & Reports → Reports**
2. View:
   - Sales by state
   - Tax by state
   - Effective tax rate by state
   - Comparison to budget
3. Export for analysis

This helps understand tax burden and optimize pricing.

## Managing multiple nexus states

As you expand to new states:

1. Add each new state to AvaTax Nexus configuration
2. AvaTax begins calculating tax for that state immediately
3. Track filing obligations per state (frequency, deadline)
4. File and remit to each state on its schedule

Light helps manage multi-state tax complexity.

## E-invoicing integration

Light's AvaTax integration includes Avalara E-Invoicing:

1. Invoices are Peppol-compliant automatically (AvaTax ensures compliance)
2. Submit invoices to Peppol network for e-invoice transmission
3. AvaTax handles e-invoice formatting and submission

This combines tax calculation with e-invoicing compliance.

## Troubleshooting AvaTax

**Tax not calculating**: Verify customer address is complete, check nexus is configured for that state, ensure tax codes are assigned to line items.

**Wrong tax rate**: Verify ship-to address (not ship-from), check state nexus, confirm item tax code matches.

**Connection failed**: Re-authorize AvaTax integration, verify your AvaTax account status.

**Exemption not applying**: Verify exemption certificate is current and uploaded, check customer is properly linked.

**Filing errors**: Review tax return detail, correct any customer address or item coding issues, re-file.

## Nexus decision support

AvaTax can help evaluate nexus in new states:

1. View transaction data by state (from AvaTax)
2. Evaluate sales/transaction count in each state
3. Assess whether economic nexus threshold is exceeded
4. Make informed decision about establishing nexus

This supports strategic tax planning.

## Related articles

- [Tax compliance — AvaTax (US)](../09-revenue-compliance/9-8-avatax-us.md)
- [Integrations overview](11-1-integrations-overview.md)
- [E-invoicing compliance (Peppol)](../09-revenue-compliance/9-6-e-invoicing-compliance.md)
