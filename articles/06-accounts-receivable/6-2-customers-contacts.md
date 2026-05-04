# Setting Up Customers

This article covers how to create and manage customers in Light. Customers are the parties you bill via sales invoices.

[Open in Light →](https://app.light.inc/customers)

Navigate via **Revenue & Invoicing → Customers**.

## Customers List

The Customers table shows: **Customer**, **Billing email**, **Description**, **Domain**, **Created at**, **Country**, **City**, **Address**, **Status**.

Status is either **Active** or **Disabled** (the underlying values are `ACTIVE` / `ARCHIVED`).

## Creating a Customer

1. Click **+ Create customer** — a side drawer opens
2. Fill in the form:
   - **Name** (required)
   - **Billing email**
   - **Domain** (optional)
   - **Description** (optional)
   - **Billing address**: country, state, city, street, zipcode
   - **Shipping address** (optional)
   - **VAT**
   - **Business reg. number**
   - **EAS code**, **E-invoice address**, **E-invoice network** (used when sending e-invoices)
   - **Customer type**: Business, Consumer, or Government
   - **Custom properties** (if your organisation has any configured for customers)
3. Click **Create**

The same drawer is used for editing — click any customer row in the list to open it.

## Customer Status

Each customer has an **Active** toggle in the edit dialog:
- **On** → status is **Active**, the customer appears in pickers and lists
- **Off** → status is **Disabled** (`ARCHIVED`); the customer is hidden from default lists but historical records remain accessible

## Customer Detail Tabs

Open a customer to see the following tabs:

- **Overview** — summary including the customer aging widget (current / 1–30 / 31–60 / 61–90 / 91+ days)
- **Payment history** — payments received from this customer
- **Contracts** — contracts associated with the customer
- **Accounting documents** — invoices, credit notes, and other accounting documents

## Customers Synced from External Systems

If a customer was synced from an external system (e.g., Salesforce, Hubspot), an **External source** indicator appears in the customer detail view, showing the source system. Some fields may be controlled by the source.

## Custom Properties

Custom properties for customers are configured at **Settings (gear icon) → Custom properties**. Once configured, they appear directly inside the customer create/edit form (no separate section).

## Related Articles

- [AR overview](/articles/06-accounts-receivable/6-1-ar-overview.md)
- [Invoice generation](/articles/06-accounts-receivable/6-5-invoice-generation.md)
- [Sending invoices](/articles/06-accounts-receivable/6-7-sending-invoices.md)
- [Tracking payments](/articles/06-accounts-receivable/6-8-tracking-payments.md)
