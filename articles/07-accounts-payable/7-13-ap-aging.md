# AP Aging

To monitor what you owe by how overdue it is, use the **Aged Accounts Payable** report together with the Bills list filters.

[Open in Light →](https://app.light.inc/ledger-reports)

## Tracking Open Bills

The Bills list shows the current state of every bill:
- **Inbox / Approving** — bills not yet ready for payment
- **Scheduled** — bills approved and awaiting / undergoing payment
- **Paid** — fully paid bills
- **Discarded** — cancelled or declined

Filter by entity, vendor, due date, and state to focus on a specific aging slice (for example, bills due in the next 30 days, or bills overdue).

## Aging Buckets

The Aged Accounts Payable report groups open amounts into the following columns, based on due date relative to the as-of date:

| Bucket | Range |
|---|---|
| **Current** | Not yet due |
| **1–30 Days** | 1–30 days past due |
| **31–60 Days** | 31–60 days past due |
| **Older than 60 Days** | More than 60 days past due |
| **Total** | Total open amount |
| **Total (Transaction Currency)** | Total open amount in the vendor's billing currency |

## Reporting

For period-end AP aging analysis, run the **Aged Accounts Payable** report from the **Reports** page ([Planning & Reports → Reports](https://app.light.inc/ledger-reports)). The report:

- Runs per entity, as of a date you choose (defaults to today)
- Can be shown in the entity's local currency or the group currency
- Groups open amounts by vendor across the aging buckets above
- Supports drilling down into the underlying documents, viewing invoice-level detail, and exporting the detail as CSV

See [Reporting overview](/articles/10-reporting/10-1-reporting-overview.md).

## Related Articles

- [Scheduling payments](/articles/07-accounts-payable/7-7-scheduling-payments.md)
- [Reporting overview](/articles/10-reporting/10-1-reporting-overview.md)
- [Multi-entity AP](/articles/07-accounts-payable/7-12-multi-entity-ap.md)
