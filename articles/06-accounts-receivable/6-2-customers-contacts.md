# Setting Up Customers and Contacts

This article covers how to create and manage customers in Light's AR module. Customers represent your revenue-generating clients and serve as the foundation for invoicing and payment tracking.

[Open in Light →](https://app.light.inc/customers)

## Understanding Customer Types

Light supports three customer types:

- **Business**: Standard B2B customers such as corporations or partnerships
- **Consumer**: Individual end-users or consumers
- **Government**: Government agencies and public sector organizations

The customer type affects tax calculation and e-invoicing capabilities. You can change the type when editing a customer's profile.

## Creating a Customer

1. Navigate to **Revenue & Invoicing → Customers**
2. Click **+ Create customer**
3. Enter the following required information:
   - **Customer Name**: The company or individual name
   - **Email**: Primary contact email address
   - **Billing Address**: Full address including country, state, city, street, and postal code

4. Add optional information:
   - **Shipping Address**: Different from billing if applicable
   - **VAT Number**: For tax purposes (EU companies)
   - **Business Registration Number**: Company registration ID
   - **Description**: Internal notes about the customer
   - **Customer Type**: Business, Consumer, or Government

5. Click **Create** to save the customer

> Good to know: The billing address is used for tax calculations unless you specify a shipping address. Light uses the shipping address first if both are provided.

## Managing Customer Contacts

Each customer can have multiple contacts for different purposes. To add a contact:

1. Open the customer's profile
2. Scroll to the **Contacts** section
3. Click **Add Contact**
4. Enter:
   - **Contact Name**
   - **Email Address**
   - **Phone Number** (optional)
   - **Role** (e.g., Finance, Operations, Legal)

5. Click **Save**

## Email Preferences

Configure how invoices and payment reminders are sent to each customer:

1. Open the customer's profile
2. Navigate to **Email Preferences**
3. Set the following:
   - **Subject Email**: Email used as the sender
   - **Reply-To Email**: Where customer replies go
   - **Recipient Emails**: Primary recipients for invoices (can be multiple)
   - **CC Emails**: Optional additional recipients

4. Click **Save**

These preferences override default company settings when sending invoices to this customer.

## Custom Properties

Add custom fields to track customer-specific information:

1. Open the customer's profile
2. Scroll to **Custom Properties**
3. Click **Add Property**
4. Select a property group and label
5. Enter the value
6. Click **Save**

Custom properties can be used for filtering, reporting, and CRM integration.

## CRM Integration

Link your customers to external CRM systems:

1. Open the customer's profile
2. Navigate to **External Integrations**
3. Select the CRM system (HubSpot or Salesforce)
4. Enter the **External ID** from your CRM
5. Light will sync basic customer data bidirectionally

> Tip: Enable CRM integration to automatically create Light customers when new accounts are added in your CRM system.

## Archiving Customers

To archive an inactive customer without losing historical data:

1. Open the customer's profile
2. Click **Archive**
3. Confirm the action

Archived customers no longer appear in active customer lists but remain accessible for historical reporting. You can reactivate them at any time by clicking **Activate**.

## Related Articles

- [AR overview](/articles/06-accounts-receivable/6-1-ar-overview.md)
- [Invoice generation and customization](/articles/06-accounts-receivable/6-5-invoice-generation.md)
- [Sending invoices and payment reminders](/articles/06-accounts-receivable/6-7-sending-invoices.md)
- [Multi-entity AR operations](/articles/06-accounts-receivable/6-11-multi-entity-ar.md)
