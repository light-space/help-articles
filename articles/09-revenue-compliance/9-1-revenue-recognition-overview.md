# Revenue Recognition Rules Overview

Revenue recognition is a fundamental accounting principle that determines when to record revenue in your financial statements. Light's revenue recognition framework helps multinational companies comply with accounting standards like IFRS 15 while managing complex multi-entity and multi-currency scenarios.

[Open in Light →](https://app.light.inc/releases)

## What is revenue recognition?

Revenue recognition defines the timing of when you record revenue from the sale of goods or services. Under IFRS 15 and ASC 606, revenue is recognized when (or as) performance obligations to customers are satisfied. This may not always align with the timing of cash receipts.

For multinational companies, revenue recognition becomes more complex when dealing with multiple entities, currencies, and business models. Light simplifies this by providing structured rules that enforce compliance across your entire organization.

## Key revenue recognition scenarios

Light supports four primary revenue recognition scenarios:

**Straight-line recognition** involves spreading revenue evenly across a defined period. This is common for service contracts where performance obligations are satisfied gradually over time.

**Milestone-based recognition** ties revenue recording to specific events or achievements. This applies to project-based work, software development contracts, or SaaS with usage-based components.

**Percentage-of-completion** allows you to recognize revenue as a project progresses based on effort expended or milestones achieved. This is typical for long-term construction or professional services contracts.

**Point-in-time recognition** records revenue immediately when control of goods or services transfers to the customer, such as product sales.

## Configuring revenue recognition rules

You configure revenue recognition rules by setting up accounting release templates for each revenue scenario. These templates define the start date, end date, duration, and release pattern. Once configured, you apply them to individual invoice lines when creating invoices.

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
