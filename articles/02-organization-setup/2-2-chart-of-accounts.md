# Chart of Accounts Setup

This article explains how to prepare and upload your Chart of Accounts in Light, including how to organize accounts by type and establish your accounting structure.

[Open in Light →](https://app.light.inc/accounting/ledger-accounts)

## What is a Chart of Accounts?

Your Chart of Accounts is the complete list of all accounts available for posting transactions in Light. It defines your GL account structure and determines how financial data flows through your general ledger. Light supports multi-entity, multi-currency accounting with a flexible account structure.

## Account types

Light supports standard GL account types used in financial accounting:

- **Assets**: Resources owned by the company (cash, receivables, inventory, equipment)
- **Liabilities**: Obligations owed by the company (payables, loans, accrued expenses)
- **Equity**: Ownership interest and retained earnings
- **Revenue**: Income from sales and services
- **Expenses**: Operating costs and cost of goods sold
- **Clearing**: Temporary accounts used for transaction processing

## Preparing your Chart of Accounts

Before uploading accounts to Light, organize them in a structured format:

1. List all accounts with their:
   - Account number or code (e.g., 1000, 1100, 2000)
   - Account name or description
   - Account type classification
   - Default currency (if multi-currency)
   - Parent account (for hierarchical structures)

2. Structure accounts hierarchically where logical:
   - Parent accounts can have sub-accounts (e.g., 1000 Assets with 1100 Cash, 1200 Receivables)
   - Deep hierarchies improve report organization and detail

3. Consider your reporting needs:
   - Group accounts that should appear together on financial statements
   - Ensure compliance account numbers match your jurisdiction requirements

## Uploading your Chart of Accounts

1. Go to **Accounting → Chart of accounts** ([Open in Light →](https://app.light.inc/accounting/ledger-accounts))
2. Click **Upload** button in the top-right actions
3. Prepare your accounts file in the supported format (CSV or Excel)
4. Click **Select File** and choose your prepared accounts file
5. Light validates the structure and displays any errors
6. Review the preview to confirm accounts will be created correctly
7. Click **Upload** to import all accounts

Light will create account records for each entry and establish hierarchical relationships based on parent account assignments.

> Tip: Start with a clean, validated file to avoid upload errors. Light provides validation feedback to help identify issues before final import.

## Account structure best practices

- Use consistent account numbering across your organization (e.g., all assets starting with 1)
- Limit account code length to 20 characters for manageability
- Create parent accounts to organize into logical groupings
- Avoid duplicate account codes within the same entity
- Use account names that are descriptive and meaningful to users
- Include clearing accounts for inter-company transactions if needed

## Modifying accounts after upload

After upload, you can edit account properties:

1. Go to **Accounting → Chart of accounts**
2. Search for the account you need to modify
3. Click **Edit** to update:
   - Account name or description
   - Default currency settings
   - Parent account relationships
4. Click **Save**

Account numbers cannot be changed after creation. To renumber accounts, you'll need to deactivate the old account and create a new one with the correct number.

## Account activation and deactivation

Accounts can be activated or deactivated to control their availability:

- **Active**: Available for posting new transactions
- **Inactive**: Archived accounts retained for historical reference

To deactivate an account:

1. Find the account in the Chart of Accounts list
2. Click **Edit**
3. Set **Status** to **Inactive**
4. Click **Save**

Inactive accounts retain all historical transaction data but won't appear in transaction posting dropdowns.

## Multi-currency account considerations

For multi-currency operations:

1. Each account can have a primary currency designation
2. Transactions may be posted in alternative currencies with automatic exchange rate conversion
3. Currency pairs determine which rates apply to revaluation adjustments
4. Set up currency configurations in the Currency Settings module

## Validating your Chart of Accounts

After upload, validate completeness:

- Confirm all accounts appear in the account list
- Check that parent-child relationships are correct
- Verify account types are assigned properly
- Review account codes for consistency
- Test posting a sample transaction to verify account availability

## Related articles

- [Currency Settings](/articles/02-organization-setup/2-6-currency-settings)
- [Tax and VAT Configuration](/articles/02-organization-setup/2-5-tax-vat-configuration)
- [Fiscal Year and Accounting Periods](/articles/02-organization-setup/2-4-fiscal-year-periods)
- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
