# Tax and VAT Configuration

This article explains how to configure tax rates, VAT (Value Added Tax) settings by jurisdiction, and VAT number validation in Light. Proper tax configuration ensures accurate tax calculations and compliance reporting.

[Open in Light →](https://app.light.inc/accounting/ledger-tax-codes)

## Tax configuration overview

Light supports complex tax scenarios for multinational operations, including:

- Multiple tax jurisdictions with region-specific tax rates
- VAT/GST configurations for each entity
- Withholding tax and other special tax types
- Reverse charge mechanisms for EU operations
- Tax reporting by jurisdiction

## VAT fundamentals

VAT (Value Added Tax) is a consumption tax applied at each stage of supply. Key VAT concepts in Light:

- **VAT Rate**: The percentage applied to taxable supplies (typically 5-27% depending on jurisdiction)
- **VAT Number**: The entity's VAT identification number by jurisdiction
- **Taxable Amount**: The amount subject to VAT calculation
- **Input VAT**: VAT incurred on purchases (recoverable)
- **Output VAT**: VAT charged on sales (payable to tax authority)
- **Net VAT**: Output VAT minus Input VAT (amount due to/from tax authority)

## Setting up tax rates

1. Navigate to **Accounting → Tax codes** ([Open in Light →](https://app.light.inc/accounting/ledger-tax-codes))
2. Click **+ Create tax code**
3. Enter the **Tax Name** (e.g., "EU VAT 20%", "US Sales Tax")
4. Select the **Tax Type**:
   - VAT/GST
   - Withholding Tax
   - Other
5. Enter the **Rate** as a percentage
6. Select the **Jurisdiction** (country or region where applicable)
7. Set the **Effective From** and **Effective To** dates
8. Click **Create Tax Rate**

Tax rates are applied to accounts and transactions. When posting an invoice or bill, Light automatically applies the correct tax rate based on the account and transaction details.

## Configuring VAT by jurisdiction

Each company entity should have VAT configured for its primary jurisdiction:

1. Go to **Settings (gear icon) → Entities**
2. Select the entity to configure
3. Click **Edit**
4. Scroll to **VAT Configuration**
5. Enter the **VAT Number** (the entity's VAT identification number)
6. Set the **VAT Registration Date** (when VAT registration became effective)
7. Configure **VAT Reporting**:
   - Select reporting frequency (monthly, quarterly, annually)
   - Set submission deadlines
8. Click **Save**

> Good to know: Each entity can have different VAT configurations based on its jurisdiction of operation.

## VAT number validation

Light can validate VAT numbers for European Union entities to ensure accuracy:

1. When entering a VAT number in entity setup, Light validates the format
2. For EU entities, Light performs an VIES (VAT Information Exchange System) check if enabled
3. Invalid VAT numbers are flagged with an error message
4. Correct the VAT number before saving the entity

Valid VAT number formats vary by country. Light recognizes country-specific patterns:
- Germany: DE + 9 digits
- France: FR + 2 characters + 9 digits
- UK: GB + 9 or 12 digits
- Spain: ES + 8 digits + 1 character
- Other countries have their own specific formats

## Multi-currency VAT and reverse charge

When operating in multiple currencies, tax rates apply at transaction level with VAT calculated in transaction currency and amounts converted to group currency for reporting. For B2B EU transactions, reverse charge may apply—VAT Configuration includes this option. When enabled, the supplier doesn't charge VAT; the customer is responsible instead. Mark the Reverse Charge checkbox on transactions to apply it.

## Tax code setup

Tax codes are applied to GL accounts to determine tax treatment. Go to Chart of Accounts, edit an account, assign a Tax Code from the dropdown, and save. Tax codes automate correct tax rate application during transaction posting.

## VAT return preparation

Light tracks VAT amounts for return filing:

1. Navigate to **Planning & Reports → Reports** ([Open in Light →](https://app.light.inc/ledger-reports))
2. Select the reporting period and entity
3. Light calculates:
   - Total Output VAT (sales)
   - Total Input VAT (purchases)
   - Net VAT due or recoverable
4. Export the VAT return data for submission to tax authorities
5. Archive filed returns for audit trail purposes

> Tip: File VAT returns promptly by their deadline dates to avoid penalties. Light allows you to track filing status and deadlines.

## Jurisdiction-specific features

Light supports enhanced features for specific jurisdictions including UK HMRC API integration for VAT obligation tracking, Denmark integration with Danish tax authority, and EU intra-community transaction tracking with VAT recovery support.

## Withholding tax and compliance

Some jurisdictions require withholding tax on vendor invoices. Set up withholding rates by jurisdiction, apply codes to vendor accounts, and Light automatically calculates and tracks withholding. To maintain compliance, regularly review tax configurations, verify VAT numbers, monitor return deadlines, file promptly, and maintain documentation for audits. Best practices include updating rates with regulatory changes, testing configurations before going live, documenting settings, and reviewing quarterly.

## Related articles

- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
- [Chart of Accounts Setup](/articles/02-organization-setup/2-2-chart-of-accounts)
- [E-invoicing and Peppol](/articles/02-organization-setup/2-7-e-invoicing-peppol)
- [Fiscal Year and Accounting Periods](/articles/02-organization-setup/2-4-fiscal-year-periods)
