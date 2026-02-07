# Accruals, Prepayments, Deferred Revenue, and Depreciation

Understanding the distinction between accruals, prepayments, deferred revenue, and depreciation is essential for accurate financial reporting. These accounting mechanisms ensure that transactions are recorded in the period they economically occur, not just when cash changes hands.

[Open in Light →](https://app.light.inc/releases)

## Accruals explained

An accrual records revenue or expense in the period earned or incurred, regardless of cash timing. Accruals follow the matching principle: expenses are matched with the revenue they generate, and revenue is recognized when earned.

Common accrual examples include:

**Accrued expenses**: You receive a utility bill in January for December services. Create an accrual in December to record the expense in the correct period.

**Accrued revenue**: You complete a service contract in December but invoice the customer in January. Create an accrual in December to recognize the revenue when earned.

In Light, accruals are typically created as journal entries (JE) or deferred entries (DE) that reverse automatically in the following period. This prevents double-counting when you record the official invoice or expense document.

## Prepayments in detail

Prepayments occur when you pay for goods or services that will be delivered or consumed in future periods. Unlike accruals, prepayments represent actual cash outflows before the benefit is received.

**Examples of prepayments:**

- Annual software subscriptions paid upfront
- Insurance premiums for the next 12 months
- Rent paid in advance
- Training courses paid before attendance

Prepayments create an asset on your balance sheet. As you consume the benefit, you expense the prepaid amount through a release schedule. This is where accounting release templates become essential.

For example, if you prepay EUR 12,000 for annual insurance in January, create a prepayment release template that spreads this amount equally across 12 months. Light automatically records EUR 1,000 in insurance expense each month while reducing the prepaid asset.

> Tip: Prepayment releases are essential for companies with significant upfront payments. They prevent balance sheet distortion and ensure monthly expenses accurately reflect consumption.

## Deferred revenue fundamentals

Deferred revenue (unearned revenue) is the opposite of prepayments. You receive payment before delivering goods or services, creating a liability on your balance sheet.

**Common deferred revenue scenarios:**

- Annual SaaS subscriptions paid upfront but delivered monthly
- Advance customer deposits for future shipments
- Service contracts with quarterly billing in advance
- Extended warranties sold with product purchases

Deferred revenue creates a liability because you owe the customer a service or good. As you deliver the performance obligation, you recognize revenue through a release schedule.

For instance, a customer pays USD 2,400 upfront for a 12-month SaaS service in January. Your deferred revenue template spreads this across 12 months, recognizing USD 200 in revenue each month while reducing the deferred revenue liability.

> Good to know: Deferred revenue timing is critical for compliance with IFRS 15. Over-recognizing revenue or recognizing it too early can trigger audit adjustments and regulatory issues.

## Depreciation overview

Depreciation allocates the cost of a fixed asset over its useful life. Unlike accruals or prepayments that relate to revenue and expenses, depreciation specifically addresses the systematic decline in asset value.

**Depreciation methods supported by Light:**

**Straight-line depreciation**: The asset cost is divided equally across the useful life. A machine costing GBP 50,000 with a 10-year life depreciates GBP 5,000 annually.

**Declining balance depreciation**: A fixed percentage is applied to the remaining book value each period, resulting in higher depreciation early and lower depreciation later. This matches how many assets (vehicles, equipment) lose value faster initially.

**Units of production depreciation**: Asset depreciation is based on actual usage. An asset depreciates in proportion to units produced, kilometers driven, or operating hours.

When setting up depreciation, Light requires:

- Asset cost (capitalized amount)
- Useful life (in years or production units)
- Salvage value (if any)
- Depreciation method
- Fixed asset account and accumulated depreciation account
- Depreciation expense account

Depreciation templates automatically post entries on a monthly or quarterly schedule, eliminating manual calculations.

## Deferred entries for complex scenarios

For revenue recognition scenarios that don't fit standard prepayment or deferred revenue templates, Light provides deferred entries (DE). These are transactional documents that record the full accounting treatment of complex scenarios.

Deferred entries can link to parent documents (like AP invoices) and create child accounting entries automatically. This enables sophisticated revenue recognition arrangements that require multi-account mappings or conditional logic.

## Interaction with financial reporting

Each of these mechanisms appears differently in your financial statements:

- **Accruals** increase expenses or revenues in the current period and reverse in the next
- **Prepayments** appear as assets on the balance sheet and become expenses over time
- **Deferred revenue** appears as a liability and becomes revenue as delivered
- **Depreciation** reduces fixed asset values and increases expense account balances

Light's reporting engine automatically handles these distinctions, ensuring your trial balance, balance sheet, and P&L correctly reflect your accounting policies.

## Multi-currency considerations

For international operations, all release-based mechanisms (prepayments, deferred revenue, depreciation) automatically handle currency translation. You can override default FX rates to match your internal policies, and Light maintains separate reporting for transaction, local, and group currencies.

## Related articles

- [Revenue recognition rules overview](9-1-revenue-recognition-overview.md)
- [Configuring releases: depreciation, prepayments, deferred revenue](9-2-configuring-releases.md)
- [Multi-currency revenue recognition](9-4-multi-currency-revenue.md)
- [Trial balance](../10-reporting/10-5-trial-balance.md)
