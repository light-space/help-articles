# Stripe Integration

Stripe is the leading online payment processor for e-commerce and SaaS businesses. Light's Stripe integration syncs your Stripe invoices, payments, and credit notes into Light in real time, keeps customers and products aligned across both systems, and can also charge Light sales invoices through Stripe.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

The Stripe integration enables:

- **Invoice sync**: Finalized Stripe invoices are automatically created as sales invoices in Light and opened
- **Payment sync**: When a Stripe invoice is paid, the payment is recorded on the matching Light sales invoice
- **Credit note sync**: Stripe credit notes are created and posted as customer credits in Light
- **Void handling**: Voiding an invoice or credit note in Stripe voids the matching record in Light
- **Customer sync**: Customers are automatically created in Light from Stripe invoice data
- **Product sync**: Stripe products are matched to Light products, or created automatically when missing
- **Document sync**: The original Stripe invoice and credit note PDFs are attached to the Light records
- **Bank feed**: Your Stripe balance can be connected as a bank feed for reconciliation
- **Invoice charging**: Light sales invoices can be charged through Stripe using a saved payment method

## Setting up Stripe integration

To connect Stripe:

1. Navigate to **Settings (gear icon) > Integrations > Stripe**
2. Click **Connect**
3. You're redirected to Stripe to authorize
4. Sign in to your Stripe account
5. Review permissions Light is requesting
6. Click **Authorize**
7. Light confirms connection and enables sync

Once connected, syncing is automatic — Light receives events from Stripe via webhooks, so there is no sync schedule to configure and no manual sync to run.

## How invoice sync works

The integration is event-driven. When something happens in Stripe, Light reacts immediately:

1. **Invoice finalized in Stripe**: Light checks whether the customer already exists (matched by Stripe customer ID). If not, Light creates the customer from the Stripe invoice's customer name, email, and billing country. Light then creates the sales invoice — including lines, quantities, amounts, taxes, and billing periods — and opens it.
2. **Invoice paid in Stripe**: Light records a payment on the matching sales invoice for the amount paid.
3. **Invoice voided in Stripe**: Light voids the matching sales invoice.

Invoices are matched by the Stripe invoice ID, so payments and voids always land on the right record.

> **Note**: When syncing Stripe invoices, Light preserves the original Stripe invoice number as the primary invoice number in Light. This keeps invoice numbers consistent across Stripe and Light for easier reconciliation and customer inquiries. (This applies to new imports; existing invoices retain their current numbers.)

## Product matching

When a synced Stripe invoice references products:

- If a Light product is already linked to the Stripe product, the invoice line uses it
- A Stripe product can be linked explicitly by adding a `light_product_id` entry to the product's metadata in Stripe, pointing at the Light product's ID
- If no linked product exists, Light creates the product automatically with Stripe as its external source
- If the product exists in Light but is priced in a different currency, the invoice currency is added to the product's pricing

> **Note**: When syncing Stripe invoices that include line-level discounts, Light captures the discount amount explicitly on each invoice line. The line amount represents the pre-discount subtotal, and the discount is shown separately, matching how Stripe represents discounted invoices.

## Credit note sync

When a credit note is created in Stripe:

1. Light receives the event in real time
2. Light creates a customer credit for the matching customer, referencing the Stripe credit note
3. Light posts the customer credit
4. The Stripe credit note PDF is attached to the customer credit

Voiding the credit note in Stripe voids the customer credit in Light.

> **Note**: When syncing Stripe credit notes with line-level discounts or taxes, Light preserves the line amount and discount structure exactly as Stripe provides them, ensuring customer credit totals match Stripe's final amounts. This keeps your records consistent with what customers see in Stripe.

## Charging invoices through Stripe

The integration also works in the other direction — Light can collect payment for sales invoices via Stripe:

1. Set the invoice's (or contract's) payment type to **Stripe**
2. The customer saves a payment method through a secure Stripe checkout link
3. Light charges the saved payment method for the invoice's remaining balance
4. The invoice moves to **Payment pending**
5. When the Stripe payout is reconciled against your bank account, the invoice is marked paid

Contracts with the Stripe payment type charge their generated invoices automatically.

## Stripe as a bank feed

Your Stripe balance can act as a bank feed in Light, so Stripe activity flows into bank reconciliation like any other bank account:

1. Connect the Stripe integration first — the bank feed requires it
2. Add Stripe as a bank feed provider
3. Light imports your Stripe balance and balance transactions
4. Reconcile Stripe payouts and charges alongside your other bank accounts

## Disconnecting Stripe

You can disconnect the integration from **Settings (gear icon) > Integrations**, or by removing Light's access from your Stripe dashboard. Either way, Light marks the connection inactive and stops syncing. Records already synced remain in Light.

## Troubleshooting Stripe sync

**Invoices not syncing**: Verify the integration shows as connected. Only finalized Stripe invoices sync — draft invoices in Stripe are not imported.

**Wrong customer assigned**: Customers are matched by Stripe customer ID. Check whether the customer was previously imported under a different Stripe customer.

**Product not linked**: Verify the `light_product_id` metadata on the Stripe product points to a valid Light product ID.

**Connection failed**: Re-authorize the Stripe integration from **Settings (gear icon) > Integrations**.

**Charge failed**: Verify the customer has saved a payment method via the Stripe checkout link and that the invoice's payment type is set to Stripe.

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [Bank integrations overview](11-11-bank-integrations.md)
- [ARR and SaaS metrics](../10-reporting/10-13-arr-saas-metrics.md)
- [Profit and loss](../10-reporting/10-3-profit-loss.md)
