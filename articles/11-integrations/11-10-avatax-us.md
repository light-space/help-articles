# AvaTax Integration (US)

AvaTax is Avalara's automated sales tax service for US operations. Light's AvaTax integration automatically calculates applicable sales tax for your AR documents based on the customer's location. Nexus configuration, tax return filing, and remittance are handled in your Avalara account, using the transactions Light records in AvaTax.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

The AvaTax integration enables:

- **Sales tax calculation**: Automatic calculation for each transaction based on the customer's location
- **Multi-entity support**: Each Light entity is mapped to its own AvaTax company profile
- **Transaction syncing**: Posted invoices and customer credits are committed to AvaTax, so your Avalara account always reflects your tax activity
- **Compliance support**: The transactions Light commits to AvaTax are the basis for filing and remittance through your Avalara account

## Setting up AvaTax integration

The AvaTax connection is provisioned by Light for your company:

1. Contact your Light representative or support to enable AvaTax
2. Provide your Avalara account ID and license key
3. Light connects your company to AvaTax with these credentials
4. Light maps each of your entities to its AvaTax company code and activates the mapping

Light maintains the integration and validates AvaTax connectivity. Once an entity is activated for AvaTax, invoices for US-based customers of that entity automatically use the **AvaTax** tax engine (instead of Light's built-in tax engine).

## Configuring entity mapping

AvaTax requires each Light entity to be mapped to an AvaTax company profile:

1. Light creates the mapping between your entity and the corresponding AvaTax company code during setup
2. Light activates the mapping when the entity is ready to calculate tax with AvaTax
3. To add or change a mapping, contact Light support

Light then uses the correct AvaTax profile when calculating tax for that entity's transactions.

## Configuring nexus

Nexus — the states and jurisdictions where you must collect tax — is configured in your Avalara account, not in Light:

1. Sign in to your Avalara account
2. Add each state where you have nexus, with its effective date
3. AvaTax includes all configured states in the tax calculations it returns to Light
4. As your business grows, add new states as nexus is established

## Assigning AvaTax tax codes

AvaTax classifies transaction items using Avalara tax codes. Configure them in Light:

1. Navigate to [Products](https://app.light.inc/products)
2. For each product, set the **Default AvaTax code** to the appropriate Avalara tax code
3. When a product is added to a line on a document that uses the AvaTax tax engine, the product's default AvaTax code is applied to the line
4. You can override the AvaTax code on individual invoice, contract, or customer credit lines

When a document uses the AvaTax tax engine, only AvaTax tax codes can be used on its lines — Light tax codes apply only to documents using the Light tax engine.

## Transaction processing with AvaTax

When you create an AR invoice:

1. Light sends transaction details to AvaTax:
   - The customer's ship-to address (the customer's shipping address, or billing address if no shipping address is set)
   - Line items (description, quantity, amount, and AvaTax tax code)
2. AvaTax determines:
   - Applicable jurisdictions based on the address
   - Tax rates for those jurisdictions
   - Tax amount for each line
3. Light receives the tax amounts from AvaTax
4. Light displays tax on the invoice
5. You review and click Post to GL

This happens automatically for every invoice.

> Good to know: While an invoice is in draft, Light requests a tax preview from AvaTax without creating a permanent record. When the invoice is posted, Light creates and commits the transaction in AvaTax under the invoice's document number. If a posted invoice is archived, Light voids the corresponding AvaTax transaction.

## Customer exemption certificates

Handle tax-exempt customers:

1. Customer provides a tax exemption certificate
2. Record the exemption against the customer in your Avalara account (Avalara manages exemption certificates)
3. Light sends the customer's code and tax details to AvaTax with every transaction
4. AvaTax applies the exemption automatically to future transactions with this customer
5. No tax is calculated (correct for exempt customers)

Exemption certificates are stored in your Avalara account for audit purposes.

## Handling returns and refunds

When you issue a customer credit for a return or refund:

1. Create a customer credit in Light (linked to the original invoice or standalone)
2. As you add line items, Light automatically calculates tax via AvaTax (just like invoices)
3. When you post the customer credit, Light commits it to AvaTax as a return transaction
4. AvaTax records the tax reversal in its system
5. Your tax liability reduces by the returned amount

If your customer credit is for an AvaTax-enabled entity and customer, tax calculation and syncing happen automatically - you don't need to manually send reversal information to AvaTax.

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

**Marketplace facilitator**: If you sell through a marketplace that collects tax, AvaTax tracks and ensures no double-taxation.

**Sourcing rules**: Different states have different sourcing rules (where tax is calculated from). AvaTax handles state-specific rules.

## Filing and remittance

Filing and remittance are handled in your Avalara account, using the transactions Light commits to AvaTax:

1. When invoices and customer credits are posted in Light, the transactions are committed in AvaTax
2. In your Avalara account, AvaTax calculates total tax owed in each jurisdiction
3. Use Avalara's returns services (such as AvaTax Managed Returns) to prepare and file returns
4. Avalara can also remit tax directly to jurisdictions

Track filing obligations per state (frequency, deadline) and file to each state on its schedule through Avalara.

## Audit documentation and reporting

Your Avalara account maintains the tax audit records: transactions and tax calculations, returns filed, payments made, and exemption certificates on file. Export audit packages from Avalara for tax professionals.

In Light, posted invoices, customer credits, and their ledger entries remain available for reporting. Navigate to **Planning & Reports → Reports** to report on revenue and tax accounts in your ledger.

## E-invoicing

Avalara also powers e-invoicing (including Peppol) for Light in supported countries. This is a separate Avalara capability from AvaTax tax calculation and is provisioned by Light with its own credentials. See [E-invoicing compliance (Peppol)](../09-revenue-compliance/9-6-e-invoicing-compliance.md) for details.

## Troubleshooting AvaTax

**Tax not calculating**: Verify the customer address is complete, check nexus is configured for that state in your Avalara account, ensure AvaTax tax codes are assigned to line items.

**Wrong tax rate**: Verify the ship-to address (the customer's shipping address, or billing address if none), check state nexus in Avalara, confirm the line's AvaTax code is correct.

**Connection failed**: Contact Light support to verify the integration credentials and your AvaTax account status.

**Exemption not applying**: Verify the exemption certificate is current in your Avalara account and recorded against the correct customer.

**Filing errors**: Review the tax return detail in Avalara, correct any customer address or item coding issues, and re-file through Avalara.

## Nexus decision support

Avalara can help evaluate nexus in new states:

1. View transaction data by state in your Avalara account
2. Evaluate sales/transaction count in each state
3. Assess whether the economic nexus threshold is exceeded
4. Make an informed decision about establishing nexus

This supports strategic tax planning.

## Related articles

- [Tax compliance — AvaTax (US)](../09-revenue-compliance/9-8-avatax-us.md)
- [Integrations overview](11-1-integrations-overview.md)
- [E-invoicing compliance (Peppol)](../09-revenue-compliance/9-6-e-invoicing-compliance.md)
