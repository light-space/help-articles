# ARR Tracking with Contracts

Light tracks ARR through the **Contracts** module, where each contract carries an estimated contract value alongside its billing schedule and invoice history.

[Open in Light →](https://app.light.inc/contracts)

## What the Contracts module tracks

Each contract stores the following financial data:

| Field | Description |
|---|---|
| **Est. contract value** | The contract value, used as the ARR figure |
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

## Contract statuses

| Status | Description |
|---|---|
| **Draft** | Contract created but not yet published |
| **Active** | Contract is live and generating invoices |
| **Terminated** | Contract has been ended |

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Exporting reports](10-11-exporting-reports.md)
- [ARR tracking and reporting](../09-revenue-compliance/9-5-arr-tracking.md)
