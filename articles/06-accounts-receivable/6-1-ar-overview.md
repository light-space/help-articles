# Accounts Receivable Overview

Accounts Receivable (AR) in Light manages the contract-to-cash process for your organization. This module handles customer creation, invoicing, payment tracking, and revenue management across multiple entities and currencies.

[Open in Light →](https://app.light.inc/invoice-receivables)

## What is Contract-to-Cash?

The contract-to-cash (C2C) process is the end-to-end workflow from establishing a customer contract through to receiving and clearing payment. In Light, this includes:

1. Customer onboarding and setup
2. Contract creation and management
3. Invoice generation and sending
4. Payment tracking and reconciliation
5. Revenue recognition and scheduling
6. Credit note processing

AR integrates with GL and Bank Reconciliation modules to provide complete visibility into your receivables position.

## Key Concepts

**Invoices (AR documents)** are the primary accounting document in this module. They progress through states: DRAFT → OPEN → PARTIALLY_CLEARED → CLEARED → ARCHIVED. Each invoice contains line items with tax, discount, and allocation information.

**Customers** represent your revenue-generating clients. Each customer can have multiple contacts, billing/shipping addresses, email preferences, and custom properties. Customers can be integrated with CRM systems like HubSpot or Salesforce.

**Payment Terms** determine when invoices are due. Light supports net terms (e.g., Net 30) and automatic payment reminders through dunning workflows.

**Revenue Schedules** handle deferred and subscription revenue using ASC 606 recognition rules. Invoices can be mapped to contracts for multi-period revenue tracking.

> Good to know: Light's AR module uses AI-powered email sending and payment reminders. You can customize email templates, set dunning rules, and track customer engagement metrics.

## Multi-Entity and Multi-Currency Support

Light handles complex scenarios across multiple legal entities and currencies:

- Create customers at the company level and assign them to specific entities
- Issue invoices in any supported currency
- Apply FX rates automatically or override them manually
- Consolidate AR reports across entities

## Key Features

- **Automated Invoice Generation**: Create invoices from contracts or manually with full customization
- **Email Templates**: Customize invoice appearance with branded templates
- **Payment Tracking**: Monitor which invoices are paid, partially paid, or outstanding
- **AR Aging Reports**: View overdue invoices by aging bucket (0-30, 31-60, 60+)
- **Credit Notes**: Issue full or partial credits to customers
- **Revenue Recognition**: Schedule revenue across periods using ASC 606 rules
- **E-Invoicing**: Submit invoices to tax authorities in supported countries

## Related Articles

- [Setting up customers and contacts](/articles/06-accounts-receivable/6-2-customers-contacts.md)
- [Creating and managing contracts](/articles/06-accounts-receivable/6-3-contracts.md)
- [Invoice generation and customization](/articles/06-accounts-receivable/6-5-invoice-generation.md)
- [Tracking payments and outstanding balances](/articles/06-accounts-receivable/6-8-tracking-payments.md)
- [Revenue schedules and deferred revenue](/articles/06-accounts-receivable/6-10-revenue-schedules.md)
