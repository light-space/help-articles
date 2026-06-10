# Contracts

Contracts in Light represent multi-period agreements with customers. They group line items and drive invoicing over the contract period.

[Open in Light →](https://app.light.inc/contracts)

Navigate via **Revenue & Invoicing → Contracts**.

## Contracts List

The Contracts table shows: **Customer**, **Entity**, **Status**, **Description**, **Start date**, **End date**, **Renewal date**, **ARR**, **Activated at**, **Terminated at**.

By default, the page shows only **Active** and **Draft** contracts. To see **Terminated** contracts or other states, adjust or clear the status filter above the table.

## Contract Lifecycle States

| State | UI Label |
|---|---|
| `DRAFT` | **Draft** |
| `CREATED` | **Draft** |
| `ACTIVE` | **Active** |
| `PENDING_TERMINATION` | **Active** (with pending-termination indicator) |
| `TERMINATED` | **Terminated** |

## Creating a Contract

The create-contract dialog collects only a few fields up front; line items, payment terms, and other configuration are added in the contract details view after creation.

1. Click **+ Create contract**
2. Fill in:
   - **Contract period** — start date and end date
   - **Description**
   - **Entity** — the company entity this contract belongs to
   - **Currency** — defaults from the entity's functional currency
3. Click **Create**

> Contracts can also be created from a customer's detail page, which pre-fills the customer.

## Contract Detail Tabs

Open a contract to see these tabs:

- **Lines** — the contract line items (products, quantities, prices, taxes, discounts, amortization)
- **Invoices** — invoices issued against this contract

Line items are added and edited in the **Lines** tab — not in the create dialog.

## Editing Custom Properties After Publishing

Once a contract is published, its line items are locked — except for custom properties. You can add, change, or remove a line item's custom properties (department, cost center, project code, etc.) without voiding and recreating the contract.

1. Open the published contract and go to the **Lines** tab
2. Enter edit mode on the line item you want to update
3. Add, change, or remove its custom properties
4. Confirm the changes when prompted, then save

Amounts, tax codes, descriptions, and other revenue- or ledger-impacting fields remain locked. Every change is recorded in the contract's modification history, and the line item re-locks after saving. See [Custom Properties](/articles/02-organization-setup/2-3-custom-properties.md) for more.

## Terminating a Contract

Open a contract and use the terminate action to end it early. The contract transitions through `PENDING_TERMINATION` to `TERMINATED`, with the terminated date recorded.

## Related Articles

- [Setting up customers](/articles/06-accounts-receivable/6-2-customers-contacts.md)
- [Products and pricing](/articles/06-accounts-receivable/6-4-products-pricing.md)
- [Invoice generation](/articles/06-accounts-receivable/6-5-invoice-generation.md)
- [Revenue schedules](/articles/06-accounts-receivable/6-10-revenue-schedules.md)
