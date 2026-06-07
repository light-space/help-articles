# Multi-Entity AP

Light's AP supports multiple legal entities. Each bill is associated with one entity, and vendors can be assigned to one or more entities with entity-specific accounting defaults.

## Vendors Across Entities

A single vendor record can be used across multiple entities:

- In the vendor's **Accounting** step, pick one or more **Entities** the vendor is approved for
- Designate a **default entity** to unlock entity-specific defaults (GL account, tax code, From account) that pre-fill bills
- Approvers can be assigned per vendor

See [Managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md) for the full setup.

## Entity on Bills

When entering a bill:
- The **Entity** field is required
- The vendor list filters to vendors assigned to the selected entity
- The bill's currency defaults from the entity's functional currency but can be changed
- GL account, tax code, and From account defaults flow in from the vendor's entity-specific defaults (when set)

## Filtering Bills by Entity

The Bills list filter bar exposes an **Entity** filter so each entity's finance team can work from a filtered view.

## Payments Across Entities

Each entity has its own bank accounts. The **From account** on a bill is restricted to bank accounts belonging to the bill's entity, so payment batches naturally stay within an entity's banking.

## Related Articles

- [Managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md)
- [Multi-currency payments](/articles/07-accounts-payable/7-8-multi-currency-payments.md)
- [Multi-entity reporting / consolidation](/articles/10-reporting/10-7-multi-entity-consolidation.md)
