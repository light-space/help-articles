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

Contact your tax administrator if you need custom tax treatment.

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
