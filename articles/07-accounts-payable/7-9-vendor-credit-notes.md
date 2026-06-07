# Credit Entries (Vendor Credits)

A credit entry represents a credit from a vendor — for returned goods, billing corrections, or refunds. Credit entries are managed under **Credit entries** and can be applied to one or more open vendor bills.

[Open in Light →](https://app.light.inc/credit-entries)

Navigate via **Spend management → Credit entries**.

## Credit Entry States

| State | UI Label |
|---|---|
| `DRAFT` | **Draft** |
| `POSTED` | **Posted** |
| `PARTIALLY_CLEARED` | **Partially cleared** |
| `CLEARED` | **Cleared** |
| `ARCHIVED` | **Archived** |

A credit moves from Posted → Partially cleared → Cleared as it's applied to bills.

## Creating a Credit Entry

1. Click **+ Create credit entry**
2. Fill in the header:
   - **Vendor**
   - **Entity**
   - **Date**
   - **Currency**
   - **Amount**
3. Add **line items** (each with quantity, unit price, GL account, cost center, tax category)
4. Save — the credit opens in **Draft**

## Posting (Publishing) a Credit

From the credit detail header, click **Publish** to post the credit. Once posted, it becomes available to apply against open bills.

## Applying a Credit to a Bill

1. Open a Posted credit entry
2. Click **Apply to bill**
3. The dialog lists open bills for the same vendor in the same currency
4. Pick the target bill and enter the application amount
5. Confirm

The dialog tracks:
- Remaining balance on the credit (credit amount minus already linked bills)
- Total invoice amount of each candidate bill

You can apply a credit across multiple bills in succession; each application reduces the remaining balance. When the credit is fully consumed, its state moves to **Cleared**.

To remove an application, click **Unlink** next to the linked bill in the credit's detail view.

## Other Actions

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

## Approving Credit Notes

If your organization has credit note approvals enabled, credit notes may require approval before posting.

When a credit note is pending approval and you're the assigned approver:

1. Open the credit note
2. **Approve** and **Reject** buttons appear in the credit entry header
3. Click **Approve** to approve (or press **Shift+A**)
4. Click **Reject** to reject (or press **Shift+D**)
   - When rejecting, you can add optional notes explaining why

Once all required approvals are complete, the credit note can be posted.

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

> **API users**: When creating or updating credit notes via `POST /credit-notes` or `PATCH /credit-notes/{id}`, you can pass `localCurrencyFxRateOverride` and `groupCurrencyFxRateOverride` to pin specific FX rates instead of defaulting to ECB rates. These fields work like the bill equivalents.

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

- [Entering bills](/articles/07-accounts-payable/7-4-entering-bills.md)
- [Scheduling payments](/articles/07-accounts-payable/7-7-scheduling-payments.md)
