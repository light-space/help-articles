# Customer Credit Notes

Credit notes (CN) in Light represent partial or full refunds to customers. They reduce customer balance and can originate from returned goods, billing errors, or service adjustments.

[Open in Light →](https://app.light.inc/customer-credits)

## Understanding Credit Notes

Credit notes are negative invoices that:

- Reduce the customer's outstanding balance
- Create GL entries to reverse revenue and tax
- Can be applied to specific invoices
- Can create usable customer credits for future purchases

## Creating a Credit Note

### From an Existing Invoice

1. Open the original invoice
2. Click **Create Credit Note**
3. Light pre-populates customer and original invoice details
4. Review and adjust line items:
   - For full credit: All lines are included
   - For partial credit: Manually remove or adjust line quantities

5. Adjust quantities to reflect what's being credited
6. Tax is automatically recalculated
7. Click **Create**

> Good to know: If the original invoice included discounts, the credit note automatically carries over those discounts on a line-by-line basis, ensuring the ledger reversal matches the original invoice exactly.

### Manual Credit Note Creation

1. Navigate to **Revenue & Invoicing → Customer credits**
2. Click **+ Create customer credit**
3. Select the **Customer**
4. Select or reference the **Original Invoice** (optional)
5. Set the **Credit Date** and **Posting Date**
6. Add line items:
   - Description of what's being credited
   - Quantity
   - Unit Price (usually negative)
   - Tax category

7. Light calculates negative totals
8. Click **Create**

> Good to know: Credit note amounts appear as negative values in accounting. A credit of $100 shows as -$100 in GL entries.

## Assigning Reasons for Credits

Document why the credit was issued:

1. Open the credit note
2. Navigate to **Credit Reason**
3. Select from predefined reasons:
   - Return
   - Billing Correction
   - Discount
   - Damaged Goods
   - Service Adjustment
   - Other

4. Optionally, add detailed **Description**
5. Click **Save**

## Credit Note States

Credit notes follow similar states to invoices:

- **DRAFT**: Created but not finalized
- **POSTED**: Finalized and GL entries created
- **APPLIED**: Assigned to an invoice or customer account
- **CLEARED**: Fully applied or used
- **ARCHIVED**: Retained for historical records

## Editing Posted Credit Notes

Posted credit notes can be edited to update metadata fields without reversing the ledger entry:

1. Open the posted credit note
2. Click **Edit** in the header
3. Update any of these fields:
   - **Description** (header-level)
   - **Document date**
   - **Custom properties** (header-level)
   - **Line descriptions**
   - **Line ledger accounts**
   - **Line tax codes**
   - **Line custom properties**

4. Click **Save** to apply changes, or **Cancel** to discard

These edits update the document's metadata without affecting the ledger posting. The original credit note remains posted throughout the editing process.

> Good to know: You cannot edit line quantities, amounts, or add/remove lines after posting. To make those changes, reset the credit note to draft first.

## Resetting Credit Notes to Draft

If you need to make more substantial changes to a posted credit note, you can reset it back to draft status:

1. Open the posted credit note
2. Click the **⋮** menu in the header
3. Select **Reset to draft**
4. Confirm the reset action

Resetting a credit note:
- Reverses the original ledger entries
- Returns the credit note to **DRAFT** status
- Allows full editing of all fields and line items
- Clears any applications to invoices

After editing, post the credit note again to create new ledger entries.

> Important: Resetting is different from reversing. **Reset** returns the credit note to draft for editing. **Reverse** creates an offsetting credit note to negate the original.

## Applying Credits

### Applying to Specific Invoices

1. Open the posted credit note
2. Click **Apply to Invoice**
3. Select the **target invoice** (must be open or partially cleared)
4. Enter the **application amount** (default is full credit note amount)
5. Click **Apply**

The invoice balance reduces by the applied amount.

### Creating a Customer Credit Balance

If a credit note isn't applied to a specific invoice:

1. Open the posted credit note
2. Click **Create Credit Balance**
3. Light converts the credit to an unapplied balance
4. Customer can use this credit on any future invoice

View and manage customer credits in the **Customer Credits** section.

## Partial Credit Notes

Issue credits for only part of an invoice:

1. Open the invoice
2. Click **Create Credit Note**
3. Reduce line item quantities to reflect partial return
4. Set the correct credit amount
5. Click **Create**

The original invoice remains open; the credit note reduces the outstanding balance.

## Tax Handling in Credits

Light automatically handles tax on credit notes:

- **Full returns**: Tax is fully reversed
- **Partial returns**: Tax is proportionally reversed
- **Damaged goods**: Tax may or may not be reversed depending on your jurisdiction

Customer credits automatically use the tax engine configured for your entity. If your entity is onboarded with Sphere or Avalara, those tax engines will be applied to credits automatically—matching the behavior of invoices.

Contact your tax administrator if you need custom tax treatment.

## E-Invoicing Credit Notes

Credit notes support e-invoicing through integrations like Peppol. When e-invoicing is enabled for your entity, you can track submission status for each credit note.

### E-Invoice Status

The customer credits table displays an **E-invoicing** column showing:

- **Not sent**: Credit note has not been submitted for e-invoicing
- **Sent**: Credit note submitted and processing
- **Delivered**: Credit note successfully delivered to the recipient
- **Failed**: Submission failed (view details in the credit note)

### Filtering by E-Invoice Status

Filter the customer credits table by e-invoice status:

1. Navigate to **Revenue & Invoicing → Customer credits**
2. Click the filter icon
3. Select **E-invoicing** from the filter menu
4. Choose one or more statuses to filter by
5. Apply the filter

### Post Without Sending Email

When posting a credit note, you can choose whether to send an email notification:

1. Open a draft credit note
2. Click **Post & send**
3. Toggle **Email** on or off
   - When **on**: Credit note posts and email is sent to recipients
   - When **off**: Credit note posts without sending email

4. If e-invoicing is enabled, you can also toggle **E-invoice** independently
5. Click **Post & send** (or **Post** if both toggles are off)

This is useful when you need to post a credit note to the ledger but plan to notify the customer through other channels.

## Multi-Currency Credits

Credit notes in a different currency than the original invoice:

1. Open the invoice
2. Click **Create Credit Note**
3. Override the **Currency** if needed
4. Light applies current FX rates
5. You can override the **FX Rate** for a different rate
6. Click **Create**

> Tip: Use FX rate overrides to credit customers at the rate they were originally invoiced if rates have moved significantly.

## Void vs. Credit

- **Credit Note**: Issues a refund or reduces balance
- **Void Invoice**: Cancels an invoice that shouldn't have been created

Use credit notes for legitimate refunds; use void only for administrative errors.

## Receiving Payment on Credits

If a customer asks for cash refund on a credit balance:

1. Open the credit note or customer credit
2. Navigate to **Refund**
3. Click **Record Refund**
4. Enter **Refund Amount**
5. Enter **Refund Date** and **Method**
6. Click **Record**

Light creates GL entries to remove the credit from the customer account and record the cash outflow.

## Reverse/Reverse Credit Notes

To reverse a credit note that was issued in error:

1. Open the credit note
2. Click **Create Reverse**
3. Light generates an offsetting credit note with negative amounts
4. Post the reverse credit note
5. Original credit note is effectively negated

## Related Articles

- [Invoice generation and customization](/articles/06-accounts-receivable/6-5-invoice-generation.md)
- [Tracking payments and outstanding balances](/articles/06-accounts-receivable/6-8-tracking-payments.md)
- [Multi-entity AR operations](/articles/06-accounts-receivable/6-11-multi-entity-ar.md)
