# Configuring Releases: Depreciation, Prepayments, Deferred Revenue

Accounting releases control how and when transactions are recognized in your ledger. Light provides a flexible release framework for managing depreciation, prepayments, deferred revenue, and other amortized items across your organization.

[Open in Light →](https://app.light.inc/releases)

## Understanding accounting releases

An accounting release is a rule that breaks down a single transaction into multiple ledger entries across time. Rather than recording an amount entirely in one period, releases spread recognition according to a defined schedule.

Release templates define the pattern. When you apply a template to an invoice line, Light automatically generates the corresponding ledger entries across the specified period, posting them on their scheduled dates.

## Release template components

Each release template includes:

**Duration and period**: The length of time over which the release occurs and how frequently entries post. A 12-month template with monthly releases creates 12 individual ledger entries.

**Release pattern**: How the amount is distributed. Light supports straight-line (equal portions each period), declining balance, and custom allocation patterns.

**Account mappings**: Which ledger accounts are used for the initial booking and the periodic releases. For deferred revenue, you specify the deferred revenue liability account and the revenue recognition account.

**Currency handling**: Specify whether releases use the transaction currency, local entity currency, or group currency for each posting.

## Setting up deferred revenue releases

Deferred revenue (also called unearned revenue) occurs when you receive payment before delivering goods or services. Create a release template by:

1. Navigate to **Accounting > Releases** (in Platform section)
2. Click **Create New Template**
3. Enter a template name (e.g., "12-Month Deferred Revenue")
4. Set **Release Type** to **Deferred Revenue**
5. Define the duration (12 months for annual contracts)
6. Select **Straight-line** for monthly recognition
7. Map the deferred revenue liability account and revenue recognition account
8. Save the template

> Tip: Use descriptive template names that include the duration and purpose, such as "24-Month SaaS Deferred Revenue" or "3-Year Prepaid Maintenance".

## Setting up prepayment releases

Prepayments are amounts paid for future goods or services not yet delivered. Create a prepayment release template similarly:

1. Navigate to **Accounting > Releases** (in Platform section)
2. Click **Create New Template**
3. Enter a template name (e.g., "Annual Prepaid Expenses")
4. Set **Release Type** to **Prepayment**
5. Define the recognition period
6. Map the prepaid asset account to the corresponding expense account
7. Save the template

## Setting up depreciation releases

Fixed assets lose value over time through use and obsolescence. Depreciation templates allocate this loss systematically:

1. Navigate to **Accounting > Releases** (in Platform section)
2. Click **Create New Template**
3. Enter a template name (e.g., "5-Year Straight-Line Depreciation")
4. Set **Release Type** to **Depreciation**
5. Define the useful life (5 years = 60 months)
6. Select depreciation method:
   - **Straight-line**: Equal depreciation each period
   - **Declining balance**: Higher depreciation early, lower later
   - **Units of production**: Based on usage
7. Map the fixed asset account to the accumulated depreciation and depreciation expense accounts
8. Save the template

## Applying releases to transactions

Once templates are configured, apply them when entering transactions:

1. Create a new AP, AR, or JE document
2. On each line, select the appropriate release template
3. Specify the start and end dates for the release
4. Light automatically calculates and posts entries according to the template schedule

The system prevents accidentally posting transactions that should follow a release template, ensuring consistent application of accounting policies.

## Monitoring and adjusting releases

View active releases in the **Accounting > Releases** dashboard (in Platform section). This shows all pending and completed releases, their progress, and book values. You can:

- View the release schedule and book value chart
- Adjust the end date or amount (adjustments create new release entries)
- Monitor progress as a percentage of the total release period
- Print release schedules for audit documentation

> Good to know: Once a release has posted entries, you cannot delete it. Instead, create an adjustment release to correct errors or changes.

## Multi-entity release management

For multinational organizations, release templates are defined at the company level but can be customized per entity. This allows:

- Consistent release policies across all subsidiaries
- Entity-specific depreciation methods required by local regulations
- Centralized template governance with local flexibility

## Related articles

- [Revenue recognition rules overview](9-1-revenue-recognition-overview.md)
- [Accruals, prepayments, deferred revenue, and depreciation](9-3-accruals-prepayments.md)
- [Multi-currency revenue recognition](9-4-multi-currency-revenue.md)
