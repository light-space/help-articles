# Configuring Releases: Depreciation, Prepayments, Deferred Revenue

Accounting releases control how and when transactions are recognized in your ledger. Light provides a flexible release framework for managing depreciation, prepayments, deferred revenue, and other amortized items across your organization.

[Open in Light →](https://app.light.inc/releases)

## Understanding accounting releases

An accounting release is a rule that breaks down a single transaction into multiple ledger entries across time. Rather than recording an amount entirely in one period, releases spread recognition according to a defined schedule.

Release templates define the pattern. When you apply a template to an invoice line, Light generates the full release schedule at the moment the document is posted — a set of ledger entries dated monthly across the specified period.

## Release template components

Each release template includes:

**Default duration**: The length of time over which the release occurs. Entries post monthly, so a 12-month release creates 12 individual ledger entries. When applying a template to a line, the start and end dates you set determine the actual period.

**Release method**: How the amount is distributed. Light supports **straight-line** (equal portions each month, with partial adjustment for partial first and last months) and **reducing balance** (declining balance — higher amounts early, lower later). The reducing balance method is only available for **Fixed asset**, **AP**, and **JE** template types.

**Balance sheet account (Contra account)**: The release template requires a **balance sheet account** — this is where the full amount is initially parked. For prepayments, this would be a prepaid asset account; for depreciation, a fixed asset account; for deferred revenue, a deferred revenue liability account. When you apply the template to a transaction line, Light automatically moves the entire amount to this balance sheet account and releases it to the expense/revenue account over time.

**Currency handling**: Release amounts are calculated automatically in the transaction currency, local entity currency, and group currency for each posting — no configuration is required.

## Setting up deferred revenue releases

Deferred revenue (also called unearned revenue) occurs when you receive payment before delivering goods or services. Create a release template by:

1. Navigate to **Settings (gear icon) → Records → Releases templates**
2. Click **+ Create template**
3. Enter a template name (e.g., "12-Month Deferred Revenue")
4. Set the template **Type** to **AR** (sales invoices)
5. Define the default duration (12 months for annual contracts)
6. Select **Straight-line** for monthly recognition
7. Set the **Contra account** to your deferred revenue liability account — the revenue recognition account is selected on the invoice line when you apply the template
8. Save the template

> Tip: Use descriptive template names that include the duration and purpose, such as "24-Month SaaS Deferred Revenue" or "3-Year Prepaid Maintenance".

## Setting up prepayment releases

Prepayments are amounts paid for future goods or services not yet delivered. Create a prepayment release template similarly:

1. Navigate to **Settings (gear icon) → Records → Releases templates**
2. Click **+ Create template**
3. Enter a template name (e.g., "Annual Prepaid Expenses")
4. Set the template **Type** to **AP** (bills)
5. Define the default duration
6. Set the **Contra account** to your prepaid asset account — the expense account is selected on the bill line when you apply the template
7. Save the template

## Setting up depreciation releases

Fixed assets lose value over time through use and obsolescence. In Light, fixed assets are entered by applying a **Fixed Asset** release template to a journal entry, bill, or sales invoice line — there is no separate fixed asset import. The resulting fixed asset register lives at [**Accounting → Releases**](https://app.light.inc/releases): filter the page by **Fixed asset** type to view only fixed assets.

Depreciation templates allocate the asset cost systematically:

1. Navigate to **Settings (gear icon) → Records → Releases templates**
2. Click **+ Create template**
3. Enter a template name (e.g., "5-Year Straight-Line Depreciation")
4. Set the template **Type** to **Fixed asset**
5. Define the default duration to match the useful life (5 years = 60 months)
6. Select the release method:
   - **Straight-line**: Equal depreciation each period
   - **Reducing balance** (declining balance): Higher depreciation early, lower later — requires a reducing rate or residual amount
7. Set the **Contra account** to your accumulated depreciation account — the depreciation expense account is selected on the line when you apply the template
8. Save the template

## Applying releases to transactions

Once templates are configured, apply them when entering transactions:

1. Create a new AP, AR, or JE document
2. On each line, select the **expense account** (or revenue account) as the GL account — this is where the amount will ultimately be recognized
3. Select the appropriate release template
4. Specify the start and end dates for the release

**How it works:** When you post the transaction, Light automatically moves the entire amount to the **balance sheet account** configured in the template. The release engine then systematically releases the amount from the balance sheet account to your selected expense/revenue account according to the template schedule.

> Important: You do not need to manually book to the balance sheet account. Pick the expense account on the line, assign the template, and Light handles the rest.

## Example: Depreciating office furniture

This example shows how to record a $12,000 office furniture purchase with a 5-year useful life and no salvage value.

**Step 1: Ensure your release template exists**

Your organization should have a release template called "Furniture" configured with:
- **Release Type**: Accounts Payables
- **Duration**: 60 months (5 years)
- **Pattern**: Straight-line
- **Balance sheet account**: 800800 - Furniture and Assets (this is where the full amount is parked before being released)

**Step 2: Enter the bill**

Navigate to **Spend management → Bills** and click **+ Create bill**. On the bill line item:

| Field | Value |
|-------|-------|
| Description | Office furniture |
| Amount | $12,000 |
| GL Account | 500500 - Office Furniture (expense account) |
| Release Template | Furniture |

**What happens when you post this bill:**

1. Light creates the accounts payable liability for $12,000
2. The release template immediately capitalizes the expense to the asset account (800800 - Furniture and Assets)
3. Each month, Light automatically posts $200 in depreciation expense (12,000 ÷ 60 months)
4. After 60 months, the asset is fully depreciated with a book value of $0

**The accounting entries:**

*Initial posting (when bill is posted):*
- Debit: 800800 - Furniture and Assets $12,000 (asset)
- Credit: Accounts Payable $12,000 (liability)

*Monthly release (repeated 60 times):*
- Debit: 500500 - Office Furniture $200 (expense)
- Credit: 800800 - Furniture and Assets $200 (contra asset)

> Key concept: On the bill line, you select the **expense account** (500500) as the GL account. The release template's **balance sheet account** (800800) is where Light automatically parks the full amount. The engine then releases from the balance sheet account to your expense account over the 60-month period — you don't need to manually book to the asset account.

## Monitoring and adjusting releases

View active releases in the [**Accounting → Releases**](https://app.light.inc/releases) dashboard. This is also the **fixed asset register** — filter the page by **Fixed asset** type to see only fixed assets and their depreciation schedules. The dashboard shows all pending and completed releases, their progress, and book values. You can:

- View the release schedule and book value chart
- Adjust the end date or amount (adjustments create new release entries)
- Monitor progress as a percentage of the total release period
- Print release schedules for audit documentation

> Good to know: Once a release has posted entries, you cannot delete it. Instead, create an adjustment release to correct errors or changes.

## Multi-entity release management

For multinational organizations, release templates are defined at the company level and shared across all entities. This allows:

- Consistent release policies across all subsidiaries
- Centralized template governance

## Related articles

- [Revenue recognition rules overview](9-1-revenue-recognition-overview.md)
- [Accruals, prepayments, deferred revenue, and depreciation](9-3-accruals-prepayments.md)
- [Fixed asset register](../15-fixed-assets/15-1-fixed-assets.md)
- [Multi-currency revenue recognition](9-4-multi-currency-revenue.md)
