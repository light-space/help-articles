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

The AvaTax connection is provisioned by Light for your company:

1. Contact your Light representative or support to enable AvaTax
2. Provide your Avalara account ID and license key
3. Light connects your company to AvaTax with these credentials
4. Light maps each of your entities to its AvaTax company code and activates the mapping
5. Configure your nexus (the states/jurisdictions where you must collect tax) in your Avalara account

Light maintains the integration and validates AvaTax connectivity.

Once an entity is activated for AvaTax, invoices for US-based customers of that entity automatically use the **AvaTax** tax engine (instead of Light's built-in tax engine).

## AvaTax transaction processing

When you create an AR (accounts receivable) invoice with AvaTax enabled:

1. Light sends transaction details to AvaTax:
   - Customer location (the customer's shipping address, or billing address if no shipping address is set)
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

> Good to know: While an invoice is in draft, Light requests a tax preview from AvaTax without creating a permanent record. When the invoice is posted, Light creates and commits the transaction in AvaTax under the invoice's document number. If a posted invoice is archived, Light voids the corresponding AvaTax transaction.

## Configuring AvaTax entity mapping

AvaTax requires each Light entity to be mapped to an AvaTax company profile:

1. Light creates the mapping between your entity and the corresponding AvaTax company code during setup
2. Light activates the mapping when the entity is ready to calculate tax with AvaTax
3. To add or change a mapping, contact Light support

Light then uses the correct AvaTax profile when calculating tax for transactions of that entity.

## Tax codes and item types

AvaTax classifies transaction items using Avalara tax codes. Configure them in Light:

1. Navigate to [Products](https://app.light.inc/products)
2. For each product, set the **Default AvaTax code** to the appropriate Avalara tax code
3. When a product is added to a line on a document that uses the AvaTax tax engine, the product's default AvaTax code is applied to the line
4. You can override the AvaTax code on individual invoice, contract, or customer credit lines

When a document uses the AvaTax tax engine, only AvaTax tax codes can be used on its lines — Light tax codes apply only to documents using the Light tax engine.

> Tip: Different states have different tax treatments for services and digital products. AvaTax handles these state-specific rules automatically.

## Customer exemption certificates

Resellers and non-profit organizations often hold tax exemption certificates. If a customer claims exemption:

1. Obtain their exemption certificate
2. Record the exemption against the customer in your Avalara account (Avalara manages exemption certificates)
3. Light sends the customer's code and tax details to AvaTax with every transaction
4. AvaTax applies the exemption automatically to future transactions with this customer

Exemption certificates are stored in your Avalara account for audit purposes.

## Shipping and delivery

AvaTax considers ship-to address when calculating tax (destination-based sales tax). In Light:

1. Set the customer's **Shipping address** on the customer record (if no shipping address is set, the billing address is used)
2. Light sends this address to AvaTax as the ship-to location
3. AvaTax calculates tax for that location
4. If shipping costs are invoiced, AvaTax determines if shipping is taxable (varies by state and destination)

Ensure accurate customer addresses to get correct tax calculations.

## Returns, refunds, and credit notes

When you issue a customer credit for returned goods or services:

1. Create a customer credit in Light
2. Reference the original invoice
3. Light automatically treats the document as a return
4. When the customer credit is posted, Light sends it to AvaTax as a return transaction
5. AvaTax records the reversal, reducing your tax liability by the returned amount

This maintains accurate tax accounting and prepares accurate tax return reporting.

## Filing and remittance

Filing and remittance are handled in your Avalara account, using the transactions Light commits to AvaTax:

1. When invoices are posted in Light, the transactions are committed in AvaTax
2. In your Avalara account, AvaTax calculates total tax owed in each jurisdiction
3. Use Avalara's returns services (such as AvaTax Managed Returns) to prepare and file the returns
4. Avalara can also remit tax directly to jurisdictions

Light itself does not prepare or file tax returns — its role is to keep AvaTax supplied with accurate, committed transactions.

> Good to know: Different states have different filing frequencies (monthly, quarterly, annually). AvaTax manages these different schedules and reminds you when each return is due.

## Nexus management

As your business grows, you may establish nexus in new jurisdictions (which requires collecting/remitting sales tax):

1. Register the new jurisdiction in your Avalara account (nexus is managed in AvaTax, not in Light)
2. AvaTax automatically applies that state's tax rates to customers in that state
3. AvaTax includes that jurisdiction in future tax filings and remittances

If you establish nexus in a new state, activate it immediately to ensure accurate tax collection going forward.

## Multi-entity AvaTax configuration

For companies with multiple entities (subsidiaries, branches):

1. Create separate AvaTax company profiles for each entity
2. Light maps each of your entities to its AvaTax profile
3. Light calculates tax using the correct profile for each transaction
4. Each entity can have different nexus and exemptions

This is useful when subsidiaries operate in different states or have different tax characteristics.

## Audit trail and compliance

Light and AvaTax maintain complete audit trails:

- All transactions and tax calculations
- Tax returns filed with each jurisdiction
- Payments remitted
- Exemption certificates (stored in your Avalara account)
- Communications with Avalara

Export audit documentation:

1. Navigate to **Planning & Reports > Reports**
2. Select period and jurisdictions
3. Click **Export**
4. Download PDF with all transactions, calculations, and filing records

This documentation supports audit procedures and provides evidence of tax compliance.

## Troubleshooting AvaTax errors

**Tax calculation failed**: Verify a customer and currency are set on the invoice, and that the customer's shipping or billing address is complete and accurate. Incomplete addresses prevent accurate tax calculation.

**Missing tax code**: Ensure the products on the invoice have a **Default AvaTax code** configured, or set the AvaTax code directly on the invoice lines.

**Exemption not applied**: Verify the exemption is recorded in your Avalara account for the customer and is current. Expired certificates won't apply.

**Wrong tax rate**: AvaTax uses shipping address to determine tax. Verify the ship-to address is correct.

> Good to know: Test AvaTax connectivity by creating an invoice with AvaTax enabled. Light immediately sends the transaction to AvaTax and displays the calculated tax.

## Related articles

- [Tax compliance — HMRC (UK) and VAT](9-7-hmrc-vat.md)
- [Audit-ready record keeping](9-9-audit-ready-records.md)
- [AvaTax integration (US)](../11-integrations/11-10-avatax-us.md)
