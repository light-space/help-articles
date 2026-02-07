# Tax Compliance — AvaTax (US)

Sales tax in the United States is complex, with over 10,000 taxing jurisdictions (states, counties, cities) each with different rates, rules, and requirements. AvaTax is Avalara's automated tax determination service that calculates sales tax, VAT, and other transaction taxes. Light integrates with AvaTax to automate tax calculation and reporting for US operations.

[Open in Light →](https://app.light.inc/invoice-receivables)

## Understanding US sales tax

US sales tax is a consumption tax applied at the point of sale. Key characteristics:

- **Origin vs. Destination**: Most states use destination-based sales tax (tax rate of buyer's location)
- **Multiple jurisdictions**: Federal, state, county, city taxes combine
- **Variable rates**: Sales tax ranges from 0% (some states) to 10%+ depending on location
- **Nexus requirements**: You must collect/remit sales tax in states where you have economic nexus
- **Exemptions**: Resellers, certain industries, and specific items are exempt from sales tax

Light cannot manually calculate accurate tax for thousands of jurisdictions. AvaTax automatically determines the correct tax treatment.

> Good to know: Economic nexus means you must collect sales tax in any state where you have significant sales, even without a physical presence.

## Setting up AvaTax integration

To enable AvaTax tax calculation:

1. Navigate to **Settings** (gear icon in bottom-left sidebar) > **Integrations**
2. Sign in with your Avalara account or create one
3. Select **Tax Determination Service**
4. Authorize Light to access your AvaTax account
5. Configure your company information:
   - Legal entity name
   - Headquarters address
   - Federal Employer ID (EIN)
6. Identify all states/jurisdictions where you have nexus
7. Save configuration

Light maintains the integration and validates AvaTax connectivity.

## AvaTax transaction processing

When you create an AR (accounts receivable) invoice with AvaTax enabled:

1. Light sends transaction details to AvaTax:
   - Customer location (ship-to address)
   - Item description and type
   - Gross amount
   - Line item details
2. AvaTax determines applicable tax:
   - Looks up jurisdiction for customer location
   - Applies tax rates for that jurisdiction
   - Accounts for any exemptions
3. AvaTax returns the calculated tax
4. Light displays the tax on the invoice and posts to the ledger

This happens automatically without manual intervention.

## Configuring AvaTax entity mapping

AvaTax requires you to map Light entities to AvaTax company profiles:

1. Navigate to **Settings** (gear icon in bottom-left sidebar) > **Entities**
2. For each entity, edit **Tax Configuration**
3. Select **AvaTax Company**: Choose the corresponding AvaTax profile
4. Configure **Default Tax Shipping**: Whether tax is included in price or added
5. Set **Shipping Tax Treatment**: Is shipping taxable?
6. Save mapping

Light then uses the correct AvaTax profile when calculating tax for transactions of that entity.

## Tax codes and item types

AvaTax requires transaction items to be classified by tax treatment. Configure in Light:

1. Navigate to **Settings** (gear icon in bottom-left sidebar) > **Tax codes** or **Tax Tables**
2. For each tax code, select **AvaTax Item Type**:
   - **Taxable goods**: Physical products subject to sales tax
   - **Non-taxable goods**: Items exempt from sales tax
   - **Services**: Professional services (tax treatment varies by state)
   - **Shipping**: Freight charges (tax treatment varies by state)
   - **Digital products**: Software and digital goods (tax treatment varies)

Light applies the correct classification to each invoice line, ensuring AvaTax calculates accurately.

> Tip: Different states have different tax treatments for services and digital products. AvaTax handles these state-specific rules automatically.

## Customer exemption certificates

Resellers and non-profit organizations often hold tax exemption certificates. If a customer claims exemption:

1. Obtain their exemption certificate
2. In Light, navigate to the customer record
3. Upload the exemption certificate: **Documents > Tax Exemption**
4. AvaTax notes the exemption in its system
5. Future transactions with this customer are marked exempt from sales tax

Light maintains a record of all exemption certificates for audit purposes.

## Shipping and delivery

AvaTax considers ship-to address when calculating tax (destination-based sales tax). In Light:

1. When creating an invoice, specify the **Ship-to Address**
2. Light sends this address to AvaTax
3. AvaTax calculates tax for that location
4. If shipping costs are invoiced, AvaTax determines if shipping is taxable (varies by state and destination)

Ensure accurate customer addresses to get correct tax calculations.

## Returns, refunds, and credit notes

When you issue a credit note (CN) for returned goods or services:

1. Create a credit note in Light
2. Reference the original invoice
3. Light automatically tags the document as a return
4. Light sends return information to AvaTax
5. AvaTax records the reversal, reducing your tax liability by the returned amount

This maintains accurate tax accounting and prepares accurate tax return reporting.

## Filing and remittance

Light integrates with AvaTax Managed Returns, which prepares your sales tax returns:

1. Navigate to **Planning & Reports > Reports**
2. Select the period and jurisdiction
3. Light retrieves transactions from AvaTax
4. AvaTax calculates total tax owed in each jurisdiction
5. Generate the official tax return form
6. Submit to the state tax authority

Light can also integrate with AvaTax payment services to remit tax directly to jurisdictions.

> Good to know: Different states have different filing frequencies (monthly, quarterly, annually). AvaTax manages these different schedules and reminds you when each return is due.

## Nexus management

As your business grows, you may establish nexus in new jurisdictions (which requires collecting/remitting sales tax):

1. Navigate to **Settings** (gear icon in bottom-left sidebar) > **Integrations**
2. Add each jurisdiction where you have nexus
3. Light automatically applies that state's tax rates to customers in that state
4. AvaTax includes that jurisdiction in future tax filings and remittances

If you establish nexus in a new state, activate it immediately to ensure accurate tax collection going forward.

## Multi-entity AvaTax configuration

For companies with multiple entities (subsidiaries, branches):

1. Create separate AvaTax company profiles for each entity
2. Map each Light entity to its AvaTax profile
3. Light calculates tax using the correct profile for each transaction
4. Each entity can have different nexus and exemptions

This is useful when subsidiaries operate in different states or have different tax characteristics.

## Audit trail and compliance

Light and AvaTax maintain complete audit trails:

- All transactions and tax calculations
- Tax returns filed with each jurisdiction
- Payments remitted
- Exemption certificates
- Communications with Avalara

Export audit documentation:

1. Navigate to **Planning & Reports > Reports**
2. Select period and jurisdictions
3. Click **Export**
4. Download PDF with all transactions, calculations, and filing records

This documentation supports audit procedures and provides evidence of tax compliance.

## Troubleshooting AvaTax errors

**Tax calculation failed**: Verify the customer address is complete and accurate. Incomplete addresses prevent accurate tax calculation.

**Missing tax code**: Ensure all items on invoices have a tax code configured in Light and mapped to an AvaTax item type.

**Exemption not applied**: Verify the exemption certificate is uploaded and current. Expired certificates won't apply.

**Wrong tax rate**: AvaTax uses shipping address to determine tax. Verify the ship-to address is correct.

> Good to know: Test AvaTax connectivity by creating an invoice with AvaTax enabled. Light immediately sends the transaction to AvaTax and displays the calculated tax.

## Related articles

- [Tax compliance — HMRC (UK) and VAT](9-7-hmrc-vat.md)
- [Audit-ready record keeping](9-9-audit-ready-records.md)
- [AvaTax integration (US)](../11-integrations/11-10-avatax-us.md)
