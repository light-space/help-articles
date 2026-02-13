# Vendor Credit Notes

Vendor credit notes (credit memos) represent refunds or credits from vendors. They reduce payables and can be applied to future vendor invoices or refunded to cash.

[Open in Light →](https://app.light.inc/credit-entries)

## Understanding Vendor Credit Notes

A vendor credit note is a negative bill representing:

- **Return of goods**: Merchandise returned for refund
- **Billing error**: Vendor overcharged or double-billed
- **Service adjustment**: Partial refund for unsatisfactory service
- **Promotional credit**: Volume discount or promotional allowance
- **Discount taken**: Early payment discount or other adjustment

Credit notes reduce your AP balance and can be applied to future vendor invoices.

## Creating a Vendor Credit Note

### From an Existing Bill

1. Open the original vendor bill
2. Click **Create Credit Note**
3. Light pre-populates vendor and original bill details
4. For full credit: All line items are included
5. For partial credit: Adjust or remove line items
6. Review amounts:
   - Quantities reduced as needed
   - Tax automatically recalculated
   - Total shows negative amount (e.g., -$500)

7. Click **Create**

The credit note is created in DRAFT state.

### From the Bill Inbox

You can forward vendor credit notes to the same email address used for bills. Light will process them automatically:

1. Forward the credit note document to your bill inbox email address
2. Light analyzes the document:
   - **If recognized as a credit note**: Light automatically creates a credit entry
   - **If classified as a bill**: The document appears in your inbox as a bill
3. To manually convert a bill to a credit note in the inbox:
   - Open the document in the inbox
   - Click **Convert to Credit Note**
   - Light converts the bill to a credit entry with the same details

This is useful when vendors send credit notes as PDF attachments that need to be ingested into Light.

### Manual Credit Note Creation

1. Navigate to **Spend management → Credit entries**
2. Click **+ Create credit entry**
3. Enter details:
   - **Vendor**: Select or search
   - **Credit Memo Number**: Vendor's credit memo number
   - **Credit Date**: When credit was issued
   - **Original Bill** (optional): Reference the bill being credited
   - **Company Entity**: Where credit is received
   - **Currency**: Credit currency

4. Add line items:
   - Description of what's being credited
   - Quantity and unit price (usually negative)
   - GL account and cost center
   - Tax category

5. Light calculates negative totals
6. Click **Create**

## Credit Note States and Lifecycle

Credit notes follow similar states to bills:

- **DRAFT**: Created but not finalized; no GL entries
- **POSTED**: Finalized and GL entries created
- **APPLIED**: Assigned to a vendor bill or vendor credit balance
- **CLEARED**: Fully applied or refunded
- **ARCHIVED**: Historical record

To post a credit note:

1. Open the credit note
2. Click **Post**
3. Light creates GL entries:
   - Debit to expense/asset GL account (reverses original charge)
   - Credit to accounts payable (reduces what you owe)

4. Click **Confirm**

## Applying Credits to Future Invoices

### Applying to Specific Bills

1. Open a posted credit note
2. Click **Apply to Bill**
3. Search for and select the **target bill**
4. Enter the **application amount** (default is full credit)
5. Light validates:
   - Same vendor
   - Credit currency matches bill currency
   - Amount doesn't exceed remaining credit

6. Click **Apply**

The bill's balance is reduced by the applied amount.

### Partial Application

If credit is larger than one bill:

1. Click **Apply to Bill**
2. Select first bill and apply partial credit
3. Remaining credit balance is shown
4. Continue applying to additional bills
5. Click **Apply** for each

A single credit note can be split across multiple bills.

## Creating Vendor Credit Balance

If a credit isn't applied to a specific bill:

1. Open the posted credit note
2. Click **Create Credit Balance**
3. Light converts credit note to usable credit balance
4. Status becomes CLEARED
5. Credit balance appears in vendor record

The vendor can use this credit on any future invoice.

### Tracking Credit Balances

1. Open the vendor
2. Navigate to **Credit Balance**
3. View:
   - Total available credit
   - Date credit was issued
   - Original credit note reference
   - Aging of credit

4. Click on credit to see application history

## Tax Treatment in Credits

Light automatically handles tax on credit notes:

- **Full return**: Tax is fully reversed
- **Partial return**: Tax is proportionally reversed
- **Allowance**: May or may not reverse tax depending on nature

Review the tax GL entries created to ensure compliance with your jurisdiction's rules.

## Multi-Currency Credits

Credit notes in different currency than original bill:

1. Create credit note
2. Override the **Currency** if different from bill
3. Light applies current FX rate
4. You can override the **FX Rate** (e.g., to match original rate)
5. GL entries record both original and adjusted amounts

Use to credit customers at their original invoice rate if currencies have moved significantly.

## Reverse/Reversing Credit Notes

To reverse a credit note issued in error:

1. Open the credit note
2. Click **Reverse**
3. Light creates an offsetting credit note with opposite amounts
4. New reverse credit note is created
5. Original credit note remains posted but is effectively neutralized
6. Post the reverse credit note

Original GL entries are reversed; new GL entries offset them.

## Refunding Credits

If a vendor requests cash refund instead of credit:

1. Open the credit note or vendor credit balance
2. Click **Request Refund**
3. Enter:
   - **Refund Amount**
   - **Refund Date**
   - **Payment Method** (bank transfer, check, etc.)

4. Light routes refund for approval
5. Once approved, creates payment record
6. Payment is executed to vendor
7. GL records cash outflow and credit clearance

## Vendor Agreements and Standing Credits

Some vendors provide standing credit balances (blanket allowances):

1. Navigate to **Vendor Settings**
2. Click **Standing Credits**
3. Add:
   - **Credit Amount**
   - **Effective Date**
   - **Expiration Date** (optional)
   - **Description** (reason for credit)

4. Light tracks standing credit usage
5. Auto-applies to bills if configured
6. Alerts when credit is about to expire

## Credit Note Reporting

### Credit Note Dashboard

1. Navigate to **Dashboard** > **Vendor Credits**
2. View:
   - Total outstanding credits
   - Credits by vendor
   - Aging of credits (how long unused)
   - Applied vs. unused credits

### Reconciliation to Vendor Statements

1. Open vendor
2. Navigate to **Credit Reconciliation**
3. Compare Light's credits to vendor's statement
4. Investigate discrepancies:
   - Different amounts or dates
   - Credits not appearing on statement
   - Credits applied differently

5. Contact vendor to resolve

## Related Articles

- [Adding and managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md)
- [Entering and ingesting bills](/articles/07-accounts-payable/7-4-entering-bills.md)
- [Scheduling and executing payments](/articles/07-accounts-payable/7-7-scheduling-payments.md)
