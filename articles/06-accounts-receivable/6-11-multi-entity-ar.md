# Multi-Entity AR

Light's AR works across multiple legal entities. Each sales invoice and contract is associated with one entity, and the AR list and reports can be filtered by entity.

## Entity Selection on Documents

**Sales invoices**: When creating an invoice, an **Entity** selector is shown alongside the customer. The currency defaults from the entity's functional currency.

**Contracts**: The contract creation dialog also requires an **Entity** to be picked. Currency defaults from the entity.

**Customers**: Customers are stored at the company level — not pre-assigned to a specific entity. The entity is chosen at document creation time, which means the same customer can be invoiced from multiple entities.

## Filtering by Entity

The Sales invoices list filters can narrow results to one or more entities. The same applies to Contracts and Customer credits.

## Currency

Each invoice or contract carries its own currency, which defaults from the selected entity but can be changed. Multi-currency reporting is handled at the report level (see the Reports module).

## Customer Aging Across Entities

The customer aging widget on a customer record aggregates open balances across the entities the customer has been invoiced from.

## Related Articles

- [AR overview](/articles/06-accounts-receivable/6-1-ar-overview.md)
- [Multi-entity consolidation in reporting](/articles/10-reporting/10-7-multi-entity-consolidation.md)
- [Multi-currency consolidation](/articles/10-reporting/10-8-multi-currency-consolidation.md)
