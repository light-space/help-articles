# Tax and VAT Configuration

This article explains how to configure tax codes and VAT settings in Light. Proper tax configuration ensures accurate tax calculations and compliance reporting.

[Open in Light →](https://app.light.inc/accounting/ledger-tax-codes)

## Tax configuration overview

Light supports tax configurations for multinational operations, including multiple tax jurisdictions with region-specific tax rates, VAT configurations for each entity, and tax reporting by country.

## Navigating the Tax codes page

1. Go to **Accounting → Tax codes** in the sidebar
2. The page displays all tax codes with columns for **Name**, **Context**, **Type**, **Rate**, and **Country**
3. By default, the list is filtered to show only **Active** tax codes
4. Use the **Search** bar to find specific tax codes
5. Click **Export** to download your tax code list

## Creating a tax code

1. Navigate to **Accounting → Tax codes**
2. Click **+ Create tax code**
3. Fill in the **General** section:
   - **Active** toggle: Enable or disable the tax code
   - **Label**: A short identifier for the tax code (e.g., "P-DK-STD-25-DOM")
   - **Name**: A descriptive name (e.g., "Purchase VAT (input VAT 25%)")
   - **Type**: Select **Sales** or **Purchase**
   - **EDIFACT** (optional): Select an EDIFACT code if applicable for e-invoicing
   - **Rate**: The tax rate as a percentage
   - **Effective rate**: The effective tax rate if different from the nominal rate
   - **Country**: Select the country where this tax code applies
   - **Base report tag**: Select the reporting tag for tax return classification
   - **Entities**: Choose which entities this tax code applies to
   - **Context** (optional): Add a description of this tax code's purpose
4. Configure **Posting rules**:
   - Click **+ Add posting rule** to add a rule
   - Set the **Percentage of tax**, **Account**, and **Report tag** for each rule
   - Posting rules determine which GL accounts receive the tax amounts
5. Click **Create tax code**

## Tax code structure

Tax codes in Light use a structured naming convention. For example, "P-DK-STD-25-DOM" indicates a Purchase tax code for Denmark at the standard 25% domestic rate. This naming pattern helps organize codes by type, country, rate, and scenario.

## Configuring VAT on entities

Each company entity can have VAT details configured:

1. Go to **Settings (gear icon) → Entities**
2. Select the entity to configure
3. Click **Edit**
4. Enter the **VAT** number for the entity
5. Click **Save**

> Good to know: Each entity can have different VAT numbers based on its jurisdiction of operation.

## Editing tax codes

1. Go to **Accounting → Tax codes**
2. Click on the tax code you want to modify
3. Click **Edit** to update the tax code fields
4. Make your changes and save

## Deactivating tax codes

To deactivate a tax code that is no longer needed:

1. Open the tax code
2. Toggle the **Active** switch to off
3. Save the changes

Inactive tax codes are hidden from the default list view but can be found by clearing the Status filter.

## Best practices

- Use consistent naming conventions for tax codes (e.g., type-country-rate-scenario)
- Create separate tax codes for Sales and Purchase transactions
- Assign tax codes to the correct entities and countries
- Configure posting rules to route tax amounts to the appropriate GL accounts
- Use the Context field to document when and how each tax code should be used
- Review tax codes regularly to ensure rates match current regulations
- Test tax codes on sample transactions before going live

## Related articles

- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
- [Chart of Accounts Setup](/articles/02-organization-setup/2-2-chart-of-accounts)
- [E-invoicing and Peppol](/articles/02-organization-setup/2-7-e-invoicing-peppol)
- [Fiscal Year and Accounting Periods](/articles/02-organization-setup/2-4-fiscal-year-periods)
