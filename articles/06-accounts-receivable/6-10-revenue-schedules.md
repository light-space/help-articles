# Revenue Schedules and Deferred Revenue

Light spreads revenue across multiple periods using **release templates** (also called amortization templates). For deferred revenue, you apply a release template to a sales invoice line or to a contract line, with a start and end date. Light then generates the periodic recognition entries automatically.

## How Deferred Revenue Works in Light

Deferred revenue is driven by release templates of type **AR** (sales invoices) or **CONTRACT** (revenue contracts):

1. Set up a release template once (defines method, contra account, default duration)
2. Apply it to a sales invoice line or a contract line, with a start and end date
3. As the period progresses, Light generates the recognition entries automatically

There is no separate "Revenue schedules" page — the configuration lives on the document line.

## Setting Up a Release Template

Navigate via **Settings (gear icon) → Releases templates**, then create a template with:
- **Type**: **Accounts receivables** (for AR invoices) or **Revenue contract** (for contracts)
- **Method**: **Straight line with partial adjustment** (the only method available for AR/Contract types)
- **Contra account**: the deferred revenue balance sheet account
- **Contract Asset Account** (Revenue contract only)
- **Default Duration (months)**: pre-fills the duration when applied
- **Context** and **Accumulate past amounts** as needed

See [Deferred entries](/articles/05-general-ledger/5-5-deferred-entries.md) for full template details.

## Applying a Schedule on a Sales Invoice

On a sales invoice line, click the **Accrual template** field. A popover opens with:
- **Start date** and **End date** date pickers
- **Accrual template** selector

Click **Add accrual** to apply, or **Update accrual** to modify an existing schedule. **Remove** removes the accrual entirely.

## Applying a Schedule on a Contract

Open a contract and apply the release template on each line in the **Lines** tab using the same start/end + template flow.

## Viewing Generated Releases

Once the document is posted and the schedule is active, generated entries appear under [**Accounting → Releases**](https://app.light.inc/releases) (when the Releases module is enabled for your plan).

## Related Articles

- [Deferred entries (Accruals and Deferrals)](/articles/05-general-ledger/5-5-deferred-entries.md)
- [Contracts](/articles/06-accounts-receivable/6-3-contracts.md)
- [Invoice generation](/articles/06-accounts-receivable/6-5-invoice-generation.md)
