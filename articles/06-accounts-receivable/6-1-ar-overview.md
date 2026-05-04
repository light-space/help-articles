# Accounts Receivable Overview

Accounts Receivable (AR) in Light covers the customer-to-cash workflow: creating customers, drafting and sending sales invoices, tracking payments, and recognising revenue across multiple entities and currencies.

[Open in Light →](https://app.light.inc/invoice-receivables)

## Key Modules

| Module | Path | Description |
|---|---|---|
| **Sales invoices** | [/invoice-receivables](https://app.light.inc/invoice-receivables) | Create, post, and send AR invoices |
| **Customer credits** | [/customer-credits](https://app.light.inc/customer-credits) | Issue credit notes and apply them to invoices |
| **Contracts** | [/contracts](https://app.light.inc/contracts) | Multi-period customer agreements with line items |
| **Products** | [/products](https://app.light.inc/products) | Reusable product catalog with default pricing and accounting |
| **Customers** | [/customers](https://app.light.inc/customers) | Customer records with billing details and history |

All five appear under **Revenue & Invoicing** in the sidebar.

## Sales Invoice Lifecycle

A sales invoice (AR document) progresses through these states:

| State | UI Label | Description |
|---|---|---|
| `DRAFT` | **Draft** | Created but not yet posted |
| `OPEN_IN_PROGRESS` | **Open pending** | Posting in progress |
| `OPEN` | **Open** | Posted; awaiting payment |
| `PAYMENT_PENDING` | **Payment pending** | Payment initiated but not yet cleared |
| `PARTIALLY_PAID` | **Partially paid** | Some payments received |
| `PAID` | **Paid** | Fully paid |
| `ARCHIVED` | **Void** | Voided / archived |

Each invoice also tracks an **e-invoice status** (when e-invoicing is enabled for the entity), shown as a separate badge.

## Key Concepts

**Customers** represent the parties you bill. Each customer record stores name, billing email, addresses, VAT, business registration number, e-invoice routing fields, and customer type (Business / Consumer / Government).

**Contracts** define multi-period agreements with a contract period, entity, currency, and lines. They can drive recurring invoicing and revenue recognition over time.

**Products** are reusable catalog items with default pricing (multi-currency), default tax code, default ledger account, and a recurrence (One time / Monthly / Quarterly / Half yearly / Yearly).

**Customer credits** are credit notes issued to customers. They progress through Draft → Posted → Partially cleared → Cleared, and can be applied to one or more open invoices.

## Multi-Entity and Multi-Currency

Light supports multi-entity AR:
- An entity is selected on each invoice and contract
- Currency on the document defaults from the entity's functional currency
- The Sales invoices list filters by entity
- Customers can be used across entities

## Key Features

- **Sales invoice creation** with line items, products, taxes, discounts, and document templates
- **Document templates** (Settings → Templates) for invoice layout and email defaults
- **Posting and sending** — post-only or post & send by email, with optional e-invoicing
- **Bulk actions** for posting and sending multiple invoices at once
- **Customer credits** to issue refunds and apply to invoices
- **Customer aging widget** on each customer's record showing 0–30 / 31–60 / 61–90 / 91+ days
- **Activity log** on each invoice
- **Bank reconciliation** for matching incoming payments to open invoices

## Related Articles

- [Setting up customers and contacts](/articles/06-accounts-receivable/6-2-customers-contacts.md)
- [Creating and managing contracts](/articles/06-accounts-receivable/6-3-contracts.md)
- [Products and pricing](/articles/06-accounts-receivable/6-4-products-pricing.md)
- [Invoice generation](/articles/06-accounts-receivable/6-5-invoice-generation.md)
- [Sending invoices](/articles/06-accounts-receivable/6-7-sending-invoices.md)
- [Tracking payments](/articles/06-accounts-receivable/6-8-tracking-payments.md)
