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
| **Pending termination** | Termination is scheduled for a future date; it can be cancelled (returning the contract to Active) or completed |
| **Terminated** | Contract has been ended |

## SaaS Metrics dashboard

The SaaS Metrics dashboard provides visualizations and summaries of your contract performance, ARR trends, and other subscription metrics. MRR and ARR on this dashboard are calculated from the recurring lines of published contracts — recurring amounts are normalized to a monthly value after discounts, and ARR is MRR × 12 — rather than from the manually entered estimated contract value. One-time lines are excluded. You can add charts, stats, and AI-generated summaries to create a personalized view of your metrics.

### Adding AI summary widgets

When you switch the dashboard to edit mode, you can add an AI summary widget that generates natural language summaries of your selected charts and stats.

To add and configure an AI summary:

1. Click **Edit** in the top-right corner of the dashboard.
2. In the action bar that appears at the bottom of the screen, click **AI summary** (sparkles icon).
3. An empty summary widget is added to your dashboard. Click the **Configure widget** button inside it.
4. Click any chart or stat card on the dashboard to add it to the summary. Selected items show a checkmark badge; you can select up to a certain number of charts and stats per summary.
5. Choose a summary length from the dropdown in the summary widget header:
   - **Auto** — Light picks the length based on your selected inputs (currently defaults to Balanced)
   - **Brief** — short, high-level overview
   - **Balanced** — moderate detail
   - **Detailed** — comprehensive summary
6. Click **Apply** to generate the summary.
7. Click **Save** in the top-right corner to save your dashboard changes.

Once configured, the AI summary widget displays a natural language summary of your selected metrics. Summaries are cached for 24 hours and personalized to your dashboard layout—if you and a colleague select different charts, you'll see different summaries.

To regenerate a summary at any time, hover over the summary widget and click the **Regenerate summary** icon (circular arrow). This bypasses the cache and generates a fresh summary based on the current data and filters.

You can configure multiple AI summary widgets on the same dashboard if you want separate summaries for different areas of your metrics.

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Exporting reports](10-11-exporting-reports.md)
- [ARR tracking and reporting](../09-revenue-compliance/9-5-arr-tracking.md)
