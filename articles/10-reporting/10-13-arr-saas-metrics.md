# ARR Tracking with Contracts

Light does not have a dedicated SaaS metrics dashboard. ARR tracking in Light is done through the **Contracts** module, where each contract carries an estimated contract value (displayed as ARR) alongside its billing schedule and invoice history.

[Open in Light →](https://app.light.inc/contracts)

## What the Contracts module tracks

Each contract in Light stores the following financial data:

| Field | Description |
|---|---|
| **Est. contract value** | Manually entered contract value, used as the ARR figure |
| **Currency** | Contract currency |
| **Start date / End date** | Contract period |
| **First invoice date** | When billing begins |
| **Renewal date** | Upcoming renewal |
| **Net terms** | Payment terms |
| **Payment type** | Direct, Stripe, etc. |

The contract value is entered manually on each contract.

## Contract stats

Opening any active contract shows three summary stats:

- **Contract ARR** — the estimated contract value, labelled as "Annualised contract value"
- **Total contract value** — total billed amount, split into collected (green) and residual (orange)
- **Next invoice** — date and amount of the next scheduled invoice

## Contracts list

Navigate to **Revenue & Invoicing → Contracts** to see all contracts. The list includes an **ARR** column showing the estimated contract value per contract, sortable alongside customer, entity, status, start/end date, renewal date, and activation/termination dates.

There is no aggregate ARR total or MRR summary shown in the list view.

## Contract statuses

| Status | Description |
|---|---|
| **Draft** | Contract created but not yet published |
| **Active** | Contract is live and generating invoices |
| **Terminated** | Contract has been ended |

## What Light does not currently provide

The following SaaS metrics are **not calculated or displayed** in Light:

- Monthly Recurring Revenue (MRR)
- Net Revenue Retention (NRR)
- Churn rate
- Cohort retention analysis
- Customer Acquisition Cost (CAC) / LTV / LTV:CAC ratio
- Magic Number / Rule of 40

For these metrics, export contract and invoice data via the reporting CSV export and calculate them externally in a spreadsheet or BI tool.

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Exporting reports](10-11-exporting-reports.md)
- [ARR tracking and reporting](../09-revenue-compliance/9-5-arr-tracking.md)
