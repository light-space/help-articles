# Sending Invoices

Light supports sending invoices by email and via e-invoicing in supported countries. Invoices can be sent individually or in bulk.

[Open in Light →](https://app.light.inc/invoice-receivables)

## Sending a Single Invoice

1. Open a draft invoice from [Sales invoices](https://app.light.inc/invoice-receivables)
2. Click the action button at the top right and choose:
   - **Post & send invoice** — posts the invoice and opens the email composer
   - **Post only** — posts the invoice without sending an email

When you choose **Post & send invoice**, the email composer opens.

### Email Composer Fields

| Field | Description |
|---|---|
| **Subject** | Pre-filled from the document template's default email subject |
| **Reply-to** | Pre-filled from the document template; comma-separated addresses |
| **Recipients** | Customer billing email by default; comma-separated |
| **CC** | Pre-filled from the document template's CC list |
| **Custom message** | Pre-filled from the template's default message; max 750 characters |

### E-invoicing Toggle

If your entity is configured for e-invoicing and the customer has the required e-invoice routing (EAS code, e-invoice address, e-invoice network), the composer also exposes an **e-invoicing toggle**. When enabled, the invoice is submitted to the e-invoicing network alongside the email.

The e-invoice goes through these statuses (shown as a separate badge on the invoice):
- **Not submitted**
- **Processing**
- **Delivered**
- **Failed**

## Sending Multiple Invoices in Bulk

1. From the Sales invoices list, select multiple draft invoices using the checkboxes
2. The bulk actions menu appears
3. Choose the bulk post-and-send action
4. The bulk dialog opens, letting you post and send all selected invoices in one go

Failures are reported per-invoice — if some invoices fail (for example, missing required fields), the others can still go through.

## After Sending

Once sent, the invoice transitions to **Open**. The activity log on the invoice records send events.

## Related Articles

- [Invoice generation](/articles/06-accounts-receivable/6-5-invoice-generation.md)
- [Invoice templates](/articles/06-accounts-receivable/6-6-invoice-templates.md)
- [Tracking payments](/articles/06-accounts-receivable/6-8-tracking-payments.md)
