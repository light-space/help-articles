# Revenue Recognition Rules Overview

Revenue recognition is a fundamental accounting principle that determines when to record revenue in your financial statements. Light's revenue recognition framework helps multinational companies comply with accounting standards like IFRS 15 while managing complex multi-entity and multi-currency scenarios.

[Open in Light →](https://app.light.inc/releases)

## What is revenue recognition?

Revenue recognition defines the timing of when you record revenue from the sale of goods or services. Under IFRS 15 and ASC 606, revenue is recognized when (or as) performance obligations to customers are satisfied. This may not always align with the timing of cash receipts.

For multinational companies, revenue recognition becomes more complex when dealing with multiple entities, currencies, and business models. Light simplifies this by providing structured rules that enforce compliance across your entire organization.

## Key revenue recognition scenarios

Light supports two primary revenue recognition scenarios:

**Straight-line recognition** spreads revenue evenly across a defined period, with a partial adjustment for the first and last months when the period does not start or end exactly on month boundaries. This is common for service contracts and subscriptions where performance obligations are satisfied gradually over time. You set this up by applying a release template to the relevant line, together with a recognition start and end date. When the document is posted, Light generates the full monthly release schedule as deferred entries (DE documents).

**Point-in-time recognition** records revenue immediately when the invoice is posted, such as for product sales. This is the default behavior for any invoice line without a release template.

## Configuring revenue recognition rules

You configure revenue recognition rules by setting up accounting release templates under **Settings → Releases templates** ([Releases templates](https://app.light.inc/release-templates)). Each template defines the release type (sales invoice or contract), the recognition method, the deferred revenue account, and an optional default duration. Contract templates additionally require a contract asset account. Once configured, you apply a template to individual invoice or contract lines, setting the recognition start and end dates on each line. You can track the resulting release schedules under **Accounting → Releases** ([Releases](https://app.light.inc/releases)).

> Good to know: Revenue recognition rules are applied at the document line level, giving you granular control over which invoice items follow specific recognition patterns.

## Multi-currency considerations

For companies operating in multiple currencies, Light automatically handles exchange rate fluctuations when recognizing revenue. You can override default FX rates to match your internal rate locking policies, ensuring consistency across financial periods.

## Audit trail and compliance

All revenue recognition activities are logged with complete audit trails. Light maintains a historical record of every transaction, adjustment, and release, making it easy to demonstrate compliance during external audits or regulatory reviews.

## Related articles

- [Configuring releases: depreciation, prepayments, deferred revenue](9-2-configuring-releases.md)
- [Accruals, prepayments, deferred revenue, and depreciation](9-3-accruals-prepayments.md)
- [Multi-currency revenue recognition](9-4-multi-currency-revenue.md)
- [ARR tracking and reporting](9-5-arr-tracking.md)
