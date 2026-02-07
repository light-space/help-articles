# Products and Pricing

The Products module in Light's AR allows you to define and manage the goods or services you sell to customers. Products are used when creating contracts and invoices.

[Open in Light →](https://app.light.inc/products)

## Understanding Product Structure

Products in Light contain:

- **Name**: Product identifier and display name
- **Description**: Details about what the product is
- **Category**: Product classification (optional)
- **SKU**: Stock keeping unit or internal code
- **Default Unit Price**: Starting price for contracts and invoices
- **Tax Category**: Which tax rate applies
- **GL Account**: Which GL account receives revenue
- **Active Status**: Whether the product can be used in new contracts

## Creating a Product

1. Navigate to **Revenue & Invoicing → Products**
2. Click **+ Create product**
3. Fill in the basic information:
   - **Product Name**: How it appears on invoices
   - **Description**: What the product is or does
   - **SKU**: Internal reference code
   - **Product Category**: Optional classification

4. Set pricing:
   - **Default Unit Price**: Base price in your billing currency
   - **Currency**: Confirm the currency used

5. Configure GL mapping:
   - **Revenue GL Account**: Where sales are posted
   - **Tax Category**: Default tax treatment

6. Click **Create**

> Good to know: You can override the default unit price on each contract or invoice line item.

## Managing Product Pricing

Products support flexible pricing structures:

1. Open a product
2. Click **Pricing**
3. View the **Price History** showing all pricing changes
4. Click **Update Price** to change the default unit price
5. Enter the new price and a reason for the change
6. Click **Save**

Light maintains a complete audit trail of all price changes.

## Multi-Currency Pricing

For companies with global customers:

1. Open the product
2. Navigate to **Currency Pricing**
3. Click **Add Currency Price**
4. Select the currency and set the price
5. Click **Save**

When creating contracts in a specific currency, Light automatically uses the currency-specific price if available, otherwise it uses the default price.

## Product Categories

Organize products using categories:

1. Navigate to **Product Categories**
2. Click **Create Category**
3. Enter the category name and description
4. Click **Create**

Assign categories to products to improve organization and enable category-level reporting.

## Tax Categories

Products can have different tax treatments:

1. Open a product
2. Navigate to **Tax Category**
3. Select from available tax categories configured by your tax administrator
4. Click **Save**

Tax categories determine which tax rates apply to line items containing this product.

## Archiving Products

To retire a product from future use:

1. Open the product
2. Click **Archive**
3. Confirm

Archived products:
- No longer appear in product selection dropdowns
- Remain usable on existing contracts
- Are visible in historical reports
- Can be reactivated by clicking **Activate**

## Product Variants (if applicable)

For products with multiple variants (sizes, colors, editions):

1. Open a product
2. Click **Add Variant**
3. Enter the variant name (e.g., "Professional Edition")
4. Set variant-specific pricing (optional)
5. Click **Add**

Each variant can have its own SKU and pricing while sharing the base product record.

## Related Articles

- [Creating and managing contracts](/articles/06-accounts-receivable/6-3-contracts.md)
- [Invoice generation and customization](/articles/06-accounts-receivable/6-5-invoice-generation.md)
- [Setting up customers and contacts](/articles/06-accounts-receivable/6-2-customers-contacts.md)
