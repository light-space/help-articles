# Deferred Entries (Accruals and Deferrals)

Deferred entries allow you to spread costs or revenue over multiple periods using release templates. This article explains how to set up templates and apply them to documents.

[Open in Light →](https://app.light.inc/release-templates)

Navigate to this page via **Settings (gear icon) → Releases templates**.

## Understanding Deferrals

Deferrals spread a transaction across multiple accounting periods:

**Deferral Example** — You prepay for future services:
- You prepay annual insurance ($12,000)
- Expense should spread over 12 months ($1,000/month)
- Apply a release template to the bill to post $1,000 each month

**Accrual Example** — You owe for services received but not yet invoiced:
- You received professional services this month
- Create an accrual entry this month to match expense to the period

Both defer the GL impact across periods for proper matching.

## Release Templates

Release templates define the rules for how an amount is spread across periods. They are reusable and can be applied to AP bills, AR invoices, journal entries, contracts, or fixed assets.

### Template List

Navigate to [**Settings (gear icon) → Releases templates**](https://app.light.inc/release-templates) to see all templates. The table shows:

| Column | Description |
|---|---|
| **Name** | Template name |
| **Method** | Straight line with partial adjustment or Reducing balance |
| **Type** | AP, AR, Journal entry, Revenue contract, or Fixed asset |
| **Contra account** | The balance sheet account used for the deferral |
| **Status** | Active or Archived |

### Creating a Release Template

1. Go to [**Accounting → Release templates**](https://app.light.inc/release-templates)
2. Click **+ New**
3. Fill in the fields:
   - **Name**: Descriptive name (e.g., "12-Month Insurance")
   - **Type**: Select what the template applies to:
     - **Accounts payables** — for AP bills
     - **Accounts receivables** — for AR invoices
     - **Journal entry** — for manual journal entries
     - **Revenue contract** — for contracts
     - **Fixed asset** — for fixed asset depreciation
   - **Method**: Select the amortization method:
     - **Straight line with partial adjustment** — equal amounts each period (available for all types)
     - **Reducing balance** — decreasing amounts over time (available for AP, JE, and Fixed asset)
   - **Contra account**: The balance sheet account (e.g., Prepaid Expenses, Accrued Expenses). For Fixed asset type this is the Depreciations Account.
   - **Contract Asset Account** *(Revenue contract only)*: The contract asset account
   - **Additions Account** *(Fixed asset only)*: The additions account (required)
   - **Initial Amount Percentage** *(Straight line only)*: Percentage for the first period
   - **Residual Amount Percentage** *(Straight line, non-Fixed asset only)*: Percentage kept as residual
   - **Reducing Rate Percentage** *(Reducing balance only)*: The rate applied each period
   - **Default Duration (months)**: Pre-fills the duration when applying the template
   - **Context**: Optional notes
   - **Accumulate past amounts**: Whether to accumulate past period amounts
4. Click **Create**

### Editing a Template

Open a template and click **Edit** to modify its fields. Click **Save** when done.

### Archiving a Template

To deactivate a template, open it, click the three-dot menu (⋯), and select **Archive**. Archived templates can no longer be applied to new documents.

## Applying a Template to a Document

Release templates can be applied per line item on AP bills, AR invoices, and journal entries.

### On an AP Bill Line

1. Open or create an AP bill
2. On a line item, click the amortization field (shown as **Template**)
3. A popover opens with:
   - **Start date** and **End date** date pickers
   - **Template** selector — pick the release template to apply
4. Click **Add amortization** to apply

To update an existing amortization on a line, click the field again and click **Update amortization**.
To remove it, click **Remove**.

### On an AR Invoice Line

1. Open or create an AR invoice
2. On a line item, click the accrual field (shown as **Accrual template**)
3. Set the **Start date**, **End date**, and **Accrual template**
4. Click **Add accrual**

## Viewing Releases

Once a template is applied and the document is posted, Light generates the release entries. Navigate to [**Accounting → Releases**](https://app.light.inc/releases) to view all generated release entries. (This item may be hidden depending on your plan's feature flags.)

## Related Articles

- [Creating manual journal entries](/articles/05-general-ledger/5-4-manual-journal-entries.md)
- [Accounting document types and lifecycle](/articles/05-general-ledger/5-2-document-types-lifecycle.md)
- [Closing periods and month-end close](/articles/05-general-ledger/5-8-closing-periods.md)
