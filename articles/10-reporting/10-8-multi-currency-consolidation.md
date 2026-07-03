# Multi-Currency Reporting

Light stores every transaction in three currency perspectives simultaneously: transaction currency, local (entity) currency, and group currency. When running reports across multiple entities, you choose which perspective to view.

[Open in Light →](https://app.light.inc/ledger-reports)

## Currency options on reports

Every report has a currency selector with two options:

| Option | Label | Description |
|---|---|---|
| **LOCAL** | Entity Crcy | Shows each entity's figures in its own functional currency |
| **GROUP** | Group Crcy | Shows all entities translated to the company's base (group) currency |

> **Note:** Entity Crcy cannot be used when viewing multiple entities that have different functional currencies. If you select it in that case, Light shows a warning: *"Selected entities have different currencies."* Switch to Group Crcy for cross-entity comparisons.

## When to use each option

**Entity Crcy** is useful when:
- Reviewing a single entity's performance in its operating currency
- Running a report where FX translation isn't relevant

**Group Crcy** is useful when:
- Comparing multiple entities side by side
- Running a consolidated report (required for the Subtotal, Eliminations, and Consolidated columns)
- Reporting to group-level stakeholders who work in the base currency

## How Group Crcy translation works

Light does not re-translate balances at report time. The group-currency amount of every line is calculated and stored when the document posts, using the exchange rates in effect at that time. There are no translation rate settings to configure in the report UI — Group Crcy reports simply sum the stored group-currency amounts.

For consolidated reports, all per-entity columns, the Subtotal, and the Consolidated column are shown in the group currency.

## FX revaluations

Unrealized FX gains and losses on open balances (e.g. a foreign currency receivable whose value has changed since it was recorded) are handled through the **FX revaluation** period-close task, which is separate from reporting.

To run an FX revaluation:

1. Navigate to **Accounting → Accounting periods** ([open Accounting periods](https://app.light.inc/accounting/accounting-periods))
2. Open the period you want to close and find the **FX revaluation** task
3. Click **Run revaluations** and select the entities to revalue
4. Click **Post revaluation** — Light revalues open balances at the period-end closing rate, calculates the gain or loss per line, and generates the revaluation document dated at period end

FX revaluation entries post to the ledger as accounting documents and appear in reports once posted.

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Multi-entity consolidation](10-7-multi-entity-consolidation.md)
- [FX revaluations](/articles/05-general-ledger/5-10-fx-revaluations.md)
