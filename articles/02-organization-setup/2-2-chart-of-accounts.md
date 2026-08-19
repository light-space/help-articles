# Chart of Accounts Setup

This article explains how to prepare and upload your Chart of Accounts in Light, including how to create accounts, organize them by group, and manage your accounting structure.

[Open in Light →](https://app.light.inc/accounting/ledger-accounts)

## What is a Chart of Accounts?

Your Chart of Accounts is the complete list of all accounts available for posting transactions in Light. It determines how transactions roll up on your financial statements.

## Navigating the Accounts page

The Accounts page is located at **Settings (gear icon) → Chart of accounts**, under Records. The page has three tabs:

- **Chart of accounts**: View, search, and manage all GL accounts
- **Account defaults**: Assign accounts for system-level postings (rounding, FX gain/loss, bank fees)
- **Intercompany rules**: Configure intercompany transaction handling

Top-right actions on the Chart of accounts tab:

- **+ Create account**
- **+ Add intercompany rule**
- **Upload**
- **⋯** (overflow menu): **Export**, **Build**

## Account fields

Fields appear in this order on the account form:

- **Account number**: A unique 6-digit numeric identifier, enforced by Light
- **Account name**: A descriptive label (e.g., "Cash," "Accounts Receivable")
- **Account status**: Active or Disabled
- **Entities**: Which entities can post to this account
- **Account category**: Standard, Header, or Sum. Standard accounts take postings. Header and Sum accounts give the chart of accounts its structure and roll-up. See **Account categories** below.
- **Aggregation rule**: Required for Sum accounts only, disabled (must be empty) for all other account types. Format is comma-separated numeric ranges, each `startcode:endcode` (6-digit account numbers, start ≤ end) — for example `100000:200000` or `100000:200000,300000:400000`.
- **Account group**: Financial grouping (e.g., Other current asset, Accounts receivable, Cost of Sales, Operating Expense). Required for Standard accounts.
- **Currency**: Appears only when Account group is set to Cash and cash equivalents, and is required there. Bank accounts don't use this field on this form.
- **FX settings**: Two dropdowns — **Entity revaluation settings** (Revalue / Do not revalue) and **Group revaluation settings**. Revaluation applies to Standard accounts.
- **Context** (optional): A note on the account's purpose

## Account categories

Every account is one of three categories, and the category sets what the account does:

- **Standard**: Your working accounts. Documents and journal entries post to these, and these are the accounts that appear when you pick an account anywhere in Light.
- **Header**: A heading that labels a section of the chart of accounts. It carries a zero balance and sits in account-number order.
- **Sum**: Totals the balances of the Standard accounts whose account numbers fall inside its **Aggregation rule** ranges. Light calculates the total when a report runs, so it always reflects current balances.

Category also drives two other fields: **Account group** is required for Standard accounts, and FX revaluation applies to Standard accounts.

## Creating a new account

1. Go to [**Settings (gear icon) → Chart of accounts**](https://app.light.inc/accounting/ledger-accounts)
2. Click **+ Create account**
3. Enter, in order: account number, name, status, entities, category, aggregation rule (if applicable), account group, currency (if applicable), FX settings (if applicable), context (optional)
4. Click **Create account**

## Uploading your Chart of Accounts

To bulk-import accounts:

1. Go to [**Settings (gear icon) → Chart of accounts**](https://app.light.inc/accounting/ledger-accounts)
2. Click **Upload**
3. Use the provided template. File format: **CSV**.
4. Review the preview. This shows exactly what will be created before anything is written to your Chart of Accounts.
5. Confirm to complete the import. All valid rows are created in one batch.

## Editing accounts

1. Go to [**Settings (gear icon) → Chart of accounts**](https://app.light.inc/accounting/ledger-accounts)
2. Search for the account you need to modify
3. Click the account to open its detail view
4. Click **Edit** to update the account fields
5. Make your changes and save

Once an account has posted activity, account number, account group, category, and currency lock. To change a used account's number, deactivate it and create a new one with the correct number.

## Account activation and deactivation

Accounts can be set to Active or Disabled using the **Account status** field:

- **Active**: Available for posting new transactions
- **Disabled**: Archived accounts retained for historical reference

To deactivate an account, open the account, click **Edit**, change Account status to Disabled, and save. Disabled accounts retain all historical transaction data but drop out of posting dropdowns. Accounts deactivated by a connected external ERP can't be reactivated manually in Light — reactivate from the ERP.

## Account defaults

The [**Account defaults**](https://app.light.inc/accounting/ledger-accounts) tab assigns accounts for system-level postings:

- **Rounding**
- **FX loss** / **FX gain**
- **FX unrealized**
- **Sales discount**
- **Bank fees**
- **Bank clearing**
- **Currency translation adjustment**
- **Elimination**

## Exporting your Chart of Accounts

**⋯** menu → **Export**. Exports your full Chart of Accounts, including account number, name, status, entities, category, group, and currency for every account. Use this to:

- back up your account structure before a bulk edit
- share your Chart of Accounts with an auditor or external accountant
- compare against your ERP's chart of accounts when reconciling systems

## Best practices

- Use consistent account numbering across your organization (e.g., all assets starting with 1)
- Assign accounts only to the entities that need them
- Account group determines financial statement classification — set it deliberately
- Configure Account defaults before posting any transactions
- Account numbers are unique company-wide

## Related articles

- [Currency Settings](/articles/02-organization-setup/2-6-currency-settings)
- [Tax and VAT Configuration](/articles/02-organization-setup/2-5-tax-vat-configuration)
- [Fiscal Year and Accounting Periods](/articles/02-organization-setup/2-4-fiscal-year-periods)
- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
