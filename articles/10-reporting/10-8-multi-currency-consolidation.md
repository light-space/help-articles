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

Translation from local to group currency happens server-side automatically using the exchange rates stored against each transaction. There are no translation rate settings to configure in the report UI — the translated amounts are calculated from the rates recorded at posting time.

For consolidated reports, all per-entity columns, the Subtotal, and the Consolidated column are shown in the group currency.

## FX revaluations

Unrealized FX gains and losses on open balances (e.g. a foreign currency receivable whose value has changed since it was recorded) are handled through the **FX Revaluation** module, which is separate from reporting.

To create an FX revaluation:

1. Navigate to **Accounting → Transactions**
2. Open the FX revaluation section
3. Set the **Valuation date** — Light uses the exchange rate on this date to revalue open balances
4. Set the **Posting date** and optionally a description
5. Light calculates the gain or loss per account line and generates the revaluation document

FX revaluation entries post to the ledger as accounting documents and appear in reports once posted.

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Multi-entity consolidation](10-7-multi-entity-consolidation.md)
- [FX revaluations](/articles/05-general-ledger/5-10-fx-revaluations.md)
