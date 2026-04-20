# Sphere Integration (US)

Sphere is a tax calculation engine that Light uses to compute sales tax for accounts receivable transactions. Once enabled per entity, Light routes all AR tax calculation requests to Sphere automatically, applying the correct tax to every invoice.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

The Sphere integration enables:

- **Tax calculation**: Automatic tax calculation via Sphere for AR transactions
- **Entity-level configuration**: Enable or disable Sphere per company entity
- **Mapping-based processing**: Uses customer and product identifiers shared between Light and Sphere
- **Flexible activation**: Can be activated and deactivated per entity as needed

## How Sphere differs from AvaTax

Both Sphere and AvaTax calculate US sales tax for AR transactions, but they differ in setup:

- **AvaTax** connects via OAuth through Light's integrations settings
- **Sphere** is configured manually and requires coordination between your team and Sphere to share the correct identifiers before activation

## Setting up Sphere

Setting up Sphere requires coordination with the Sphere team and your Light implementation manager.

### Step 1: Share identifiers with Sphere

Provide your Sphere account team with the following identifiers from Light:

- **Customer Light IDs**: For each customer that will have tax calculated
- **Product Light IDs**: For each product or service included on invoices

Sphere uses these IDs to match entities and apply the correct tax rules.

### Step 2: Obtain your Sphere company code

Request your **Sphere company code** from the Sphere team. This code links your Light entity to your Sphere account. If a specific code is not available, Light uses a default value.

### Step 3: Activate Sphere for your entity

Contact your Light implementation manager to activate Sphere for the relevant entity. Once active, all AR tax calculations for that entity are routed to Sphere.

## Transaction processing with Sphere

When you create an AR invoice:

1. Light sends the transaction details to Sphere (customer, products, and amounts)
2. Sphere matches the IDs, calculates the applicable tax, and returns the result
3. Light applies the tax to the invoice and displays it to you
4. You review and click **Post** to record in the GL

## Disabling Sphere

To disable Sphere for an entity, contact your Light implementation manager. Once disabled, new transactions will no longer use Sphere for tax calculation.

> Good to know: Existing draft invoices created while Sphere was active may still reference Sphere. Contact Light support if you need assistance transitioning existing drafts.

## Troubleshooting

**Tax not calculated**: Verify that your customer and product Light IDs have been shared with Sphere and that mappings are correctly configured in Sphere.

**Wrong tax result**: Check the accuracy of the customer and product mappings provided to Sphere.

**Sphere not triggered**: Confirm with your Light implementation manager that Sphere is active for your entity.

## Related articles

- [AvaTax integration (US)](11-10-avatax-us.md)
- [Integrations overview](11-1-integrations-overview.md)
- [Tax compliance — AvaTax (US)](../09-revenue-compliance/9-8-avatax-us.md)
- [E-invoicing and Peppol setup](11-20-e-invoicing.md)
