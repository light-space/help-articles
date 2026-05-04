# Products and Pricing

The Products module lets you define the goods or services you sell to customers. Products can be reused on contracts and sales invoices, and they carry default accounting settings and pricing.

[Open in Light →](https://app.light.inc/products)

Navigate via **Revenue & Invoicing → Products**.

## Products List

The Products page shows all products with the following columns:

| Column | Description |
|---|---|
| **Product** | Product name |
| **Type** | Pricing model (Fixed / Package) and Recurrence badges |
| **Price** | First pricing amount and currency |

Use the search bar above the table to filter products by name.

## Creating a Product

1. Click **+ Create product** — a side drawer opens
2. Fill in the **Details** section:
   - **Name**: Product name (appears on contracts and invoices)
   - **Pricing model**: Choose **Fixed** or **Package**
   - **Recurrence**: Choose **One time**, **Monthly**, **Quarterly**, **Half yearly**, or **Yearly**
   - **Custom properties** (if any are configured for products)
3. Fill in the **Accounting** section:
   - **Default tax code**: The tax code applied by default. You can also pick **Avatax** to use AvaTax tax determination (a separate dialog opens to enter the AvaTax code).
   - **Default ledger account**: The GL account where revenue posts by default
4. Fill in the **Price** section:
   - Enter the **currency** and **amount** for the default price
   - Click **+ Add more currencies** to add additional prices in other currencies
5. Click **Create**

> Defaults set on a product (tax code, ledger account, prices) flow through to contract and invoice lines. They can still be overridden on each line.

## Editing a Product

1. Click a product row in the list — the edit drawer opens
2. Update any field (Name, Pricing model, Recurrence, tax code, ledger account, prices, custom properties)
3. Click **Save**

If you have unsaved changes and try to close the drawer, Light asks you to confirm before discarding them.

## Multi-Currency Pricing

Multi-currency is built into the product form — there is no separate currency tab.

In the **Price** section of the create/edit drawer:
1. Click **+ Add more currencies**
2. Pick the currency and enter the amount
3. Repeat for each additional currency
4. Use the ✕ button next to any pricing row to remove it

When a contract or invoice is created in a specific currency, Light uses the matching product price for that currency if one exists.

## Pricing Models

Light supports two pricing models, set on each product:

- **Fixed** — A single unit price applied per quantity
- **Package** — A bundled price (used when the product is sold as a package rather than per unit)

## Billing Recurrence

The **Recurrence** field defines how often the product is typically billed when used on a contract:

- **One time** — Billed once
- **Monthly**
- **Quarterly**
- **Half yearly**
- **Yearly**

## Tax Code and Avatax

The **Default tax code** field on a product accepts either:
- A tax code from your tax codes registry (Settings → Tax codes), or
- An **Avatax** code, when AvaTax tax determination is enabled. Selecting Avatax opens a dialog to enter the AvaTax code.

## Products Synced from External Systems

Products imported from external systems show a "Generated from [source]" indicator at the top of the product form, with a button to copy the source ID. Supported sources include:
- **Salesforce**
- **Hubspot**
- **Chargebee**

For these products, some fields may be controlled by the source system.

## Related Articles

- [Creating and managing contracts](/articles/06-accounts-receivable/6-3-contracts.md)
- [Invoice generation and customization](/articles/06-accounts-receivable/6-5-invoice-generation.md)
- [Setting up customers and contacts](/articles/06-accounts-receivable/6-2-customers-contacts.md)
