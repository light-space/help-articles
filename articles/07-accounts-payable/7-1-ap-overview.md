# Accounts Payable Overview

Accounts Payable (AP) in Light manages the invoice-to-payment process for vendor bills. This module handles vendor management, bill entry, approval workflows, payment execution, and spend analytics across multiple entities and currencies.

[Open in Light →](https://app.light.inc/payables)

## What is Invoice-to-Payment?

The invoice-to-payment (I2P) process is the complete workflow from receiving a vendor bill through to payment and reconciliation. In Light, this includes:

1. Vendor onboarding and setup
2. Bill receipt (manual or automated from vendors)
3. Three-way match (PO, receipt, bill)
4. Approval workflows and sign-offs
5. Payment scheduling and execution
6. Reconciliation and close-out

AP integrates with GL, Bank Reconciliation, and Expense modules to provide complete visibility into payables.

## Key Concepts

**Bills (AP documents)** are accounting documents representing vendor invoices. They progress through states: DRAFT → POSTED → PARTIALLY_CLEARED → CLEARED → ARCHIVED. Each bill contains line items mapped to GL accounts and cost centers.

**Vendors** represent suppliers and service providers. Vendor records contain contact information, banking details, tax IDs, and payment preferences. Vendors can range from small freelancers to major suppliers.

**Approval Workflows** ensure bills are reviewed by appropriate stakeholders (manager, finance, executive) before payment. Light supports multi-level approvals and conditional rules.

**Payments** settle vendor bills through various methods: bank transfer, checks, ACH, credit card, or virtual payments.

> Good to know: Light's AP module uses AI to extract data from vendor invoices automatically, reducing manual data entry by 90%.

## Multi-Entity and Multi-Currency Support

Light handles complex AP scenarios:

- Manage vendors at company or entity level
- Issue payments in any supported currency
- Apply FX rates automatically or override manually
- Consolidate AP reports across entities
- Support local payment methods per country/region

## Key Features

- **Invoice Data Extraction**: AI-powered OCR to capture invoice data from PDFs, images, or emails
- **Vendor Portal**: Magic links allowing vendors to submit invoices directly
- **Three-Way Match**: Automatic validation that PO, receipt, and bill match
- **Approval Workflows**: Configurable workflows with escalation rules
- **Payment Scheduling**: Manage cash flow with payment batches and schedules
- **Multi-Currency Payments**: Automatic FX conversion or supplier-specified rates
- **Vendor Credit Notes**: Track credits and apply to future invoices
- **AP Aging Reports**: Monitor vendor payables and aging
- **Employee Reimbursements**: Process expense reimbursements through AP

## Vendor Management

Vendors can be:

- **External Vendors**: Third-party suppliers (contractors, service providers, equipment vendors)
- **User Vendors**: Employees receiving reimbursement for expenses or advances

Each vendor has:

- Contact information and banking details
- Payment terms and preferred payment methods
- Currency and tax information
- Approval rules and spending limits
- Portal access for direct invoice submission

## The Approval Workflow

Most organizations require bill approvals before payment:

1. Bill received and matched to PO
2. Bill routed for approval (manager reviews)
3. Manager approves or rejects
4. If rejected, returned to vendor with explanation
5. If approved, moves to payment queue
6. Finance/treasurer executes payment

Light automates routing and tracks approval status.

## Related Articles

- [Adding and managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md)
- [Entering and ingesting bills](/articles/07-accounts-payable/7-4-entering-bills.md)
- [AI-driven invoice data extraction](/articles/07-accounts-payable/7-5-ai-invoice-extraction.md)
- [Bill approval workflows](/articles/07-accounts-payable/7-6-bill-approval.md)
- [Scheduling and executing payments](/articles/07-accounts-payable/7-7-scheduling-payments.md)
