# Invoice Templates

Document templates configure the layout and email defaults for sales invoices and other accounting documents. Templates are managed under Settings.

[Open in Light →](https://app.light.inc/settings/templates)

Navigate via **Settings (gear icon) → Templates**.

## What a Template Controls

A document template defines:

- **Name** — internal name for the template
- **Description** — optional notes
- **Type** — document type the template applies to
- **Company entities** — which entities can use this template
- **Invoice pattern** — number/format pattern for the document number
- **Background color** — color used on the rendered document
- **Reply-to email** — default reply-to when this template is used to send a document
- **CC emails** — default CC recipients
- **Default email subject** — subject line used when sending
- **Default email message** — body text used when sending (max 750 characters)
- **Additional text** — extra text rendered on the document
- **Show contract period** — whether to display the contract period on the rendered document

## Creating a Template

1. Go to **Settings (gear icon) → Templates**
2. Click **+ Create template**
3. Fill in the fields above
4. Save

## Editing a Template

Open a template to update its fields. Changes apply to future documents that use the template.

## Assigning a Template to an Invoice

When creating or editing a sales invoice, pick a **Document template** in the invoice header. The template controls the document layout and the email defaults when sending.

## Payment Details on Invoices

Invoices display the payment details from the bank account on the document so your customers know where to send payment. Depending on the bank account's country and configuration, this can include:

- **BIC / IBAN** — for international and SEPA payments
- **Account number** — for domestic transfers
- **Bankgiro** — for Swedish entities (see below)

### Showing a Bankgiro Number (Swedish Entities)

Bankgiro is the primary payment method for Swedish business-to-business transactions, and Swedish customers expect to see it on their invoices. If your Swedish entity has a Bankgiro number set on its bank account, you can display it on invoices alongside (or instead of) the BIC/IBAN and account number fields.

1. Make sure the **Bankgiro** number is entered on the bank account — set the bank country to Sweden in **Settings > Bank accounts** to reveal the field. See [Connecting bank accounts](/articles/04-bank-reconciliation/4-1-connecting-bank-accounts.md).
2. Update your invoice template to show the Bankgiro number in the payment details
3. Save the template — future invoices that use it will display the Bankgiro number

## Related Articles

- [Invoice generation](/articles/06-accounts-receivable/6-5-invoice-generation.md)
- [Sending invoices](/articles/06-accounts-receivable/6-7-sending-invoices.md)
- [Connecting bank accounts](/articles/04-bank-reconciliation/4-1-connecting-bank-accounts.md)
