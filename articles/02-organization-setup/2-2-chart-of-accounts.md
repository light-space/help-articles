# Chart of Accounts Setup

This article explains how to prepare and upload your Chart of Accounts in Light, including how to create accounts, organize them by group, and manage your accounting structure.

[Open in Light →](https://app.light.inc/accounting/ledger-accounts)

## What is a Chart of Accounts?

Your Chart of Accounts is the complete list of all accounts available for posting transactions in Light. It defines your GL account structure and determines how financial data flows through your general ledger. Light supports multi-entity, multi-currency accounting with a flexible account structure.

## Navigating the Accounts page

The Accounts page is located at [**Accounting → Chart of accounts**](https://app.light.inc/accounting/ledger-accounts) in the sidebar. The page has three tabs:

- **Chart of accounts**: View, search, and manage all GL accounts
- **Account defaults**: Configure system account mappings (e.g., Rounding, FX loss, FX gain, Bank fees)
- **Intercompany rules**: Set up rules for intercompany transactions

The top-right actions include **Build**, **Upload**, and **Export** buttons, along with **+ Create account** and **+ Add intercompany rule**.

## Account fields

Each account in Light has the following properties:

- **Account number**: A unique numeric identifier (e.g., 100100, 200100)
- **Account name**: A descriptive name (e.g., "Cash", "Accounts Receivable")
- **Account status**: Active or Inactive
- **Entities**: Which company entities this account is available in
- **Account category**: The category classification (e.g., Standard)
- **Aggregation rule**: Optional rule for how the account aggregates in reporting
- **Account group**: The financial grouping (e.g., Other current asset, Accounts receivable, Intangible asset)
- **Revalue open balance for foreign currency transactions**: Checkbox to enable FX revaluation for this account
- **Context** (optional): A description of the account's purpose

## Creating a new account

1. Go to [**Accounting → Chart of accounts**](https://app.light.inc/accounting/ledger-accounts)
2. Click **+ Create account**
3. Fill in the account details:
   - **Account number**: Enter a unique account number
   - **Account name**: Enter a descriptive name
   - **Account status**: Select Active or Inactive
   - **Entities**: Choose which entities this account applies to
   - **Account category**: Select the appropriate category
   - **Aggregation rule**: Optionally enter an aggregation rule
   - **Account group**: Select the account group (e.g., Other current asset, Revenue, Expense)
   - **Revalue open balance for foreign currency transactions**: Check if this account should be revalued
   - **Context** (optional): Add a description of the account's purpose
4. Click **Create account**

## Uploading your Chart of Accounts

To bulk-import accounts:

1. Go to [**Accounting → Chart of accounts**](https://app.light.inc/accounting/ledger-accounts)
2. Click the **Upload** button in the top-right actions
3. Prepare your accounts file in the supported format (CSV or Excel)
4. Upload your prepared file
5. Light validates the structure and displays any errors
6. Review the preview to confirm accounts will be created correctly
7. Complete the upload to import all accounts

> Tip: Start with a clean, validated file to avoid upload errors. Light provides validation feedback to help identify issues before final import.

## Editing accounts

1. Go to [**Accounting → Chart of accounts**](https://app.light.inc/accounting/ledger-accounts)
2. Search for the account you need to modify
3. Click the account to open its detail view
4. Click **Edit** to update the account fields
5. Make your changes and save

Account numbers cannot be changed after creation. To renumber accounts, you'll need to deactivate the old account and create a new one with the correct number.

## Account activation and deactivation

Accounts can be set to Active or Inactive using the **Account status** field:

- **Active**: Available for posting new transactions
- **Inactive**: Archived accounts retained for historical reference

To deactivate an account, open the account, click Edit, change Account status to Inactive, and save. Inactive accounts retain all historical transaction data but won't appear in transaction posting dropdowns.

## Account defaults

The [**Account defaults**](https://app.light.inc/accounting/ledger-accounts) tab configures which accounts are used for system-level postings:

- **Rounding**: Account for rounding gain/loss
- **FX loss** / **FX gain**: Accounts for realized foreign exchange gains and losses
- **FX unrealized**: Account for unrealized FX gains and losses
- **Sales discount**: Account for sales discounts
- **Bank fees**: Account for bank charges
- **Bank clearing**: Clearing account for bank transactions
- **Currency translation adjustment**: Account for currency translation differences
- **Elimination**: System elimination account for consolidation

## Exporting your Chart of Accounts

Click the **Export** button in the top-right actions on the Chart of accounts tab to download your complete account list.

## Best practices

- Use consistent account numbering across your organization (e.g., all assets starting with 1)
- Create meaningful account names that are clear to users
- Assign accounts to the correct entities to control where they appear
- Choose appropriate account groups for accurate financial statement classification
- Use the Context field to document the purpose of each account
- Configure account defaults before posting transactions
- Avoid duplicate account numbers within the same entity

## Related articles

- [Currency Settings](/articles/02-organization-setup/2-6-currency-settings)
- [Tax and VAT Configuration](/articles/02-organization-setup/2-5-tax-vat-configuration)
- [Fiscal Year and Accounting Periods](/articles/02-organization-setup/2-4-fiscal-year-periods)
- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
