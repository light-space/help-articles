# Purchase Orders

Purchase orders (POs) record committed purchases with vendors before bills are received. POs are managed under **Spend management → Purchase orders**.

[Open in Light →](https://app.light.inc/procurement/purchase-orders)

Navigate via **Spend management → Purchase orders**.

## Purchase Order States

| State | Meaning |
|---|---|
| `IN_DRAFT` | Editable draft |
| `APPROVED_ACCOUNTING_ENTRY_PENDING` | Approved; finalising accounting entry |
| `OPEN` | Active and available for matching against bills |
| `CLOSE_PENDING` | Close in progress |
| `CLOSED` | Closed (no further matching) |
| `CANCEL_PENDING` | Cancel in progress |
| `CANCELLED` | Cancelled |
| `RESET_PENDING` | Being reset to a prior state |

## Creating a Purchase Order

1. Navigate to **Purchase Orders**
2. Click **Create PO**
3. Enter PO details:
   - **Vendor**: Select or search
   - **PO Number**: Your internal PO identifier
   - **PO Date**: When PO was created
   - **Required Date**: When goods/services are needed
   - **Delivery Address** (optional)
   - **Company Entity**: Which entity is buying
   - **Currency**: PO currency

4. Click **Next** to add line items

## Adding PO Line Items

1. Click **Add Line Item**
2. Enter:
   - **Description**: What you're ordering
   - **Quantity** and **Unit Price**
   - **GL Account**: Which account to charge
   - **Cost Center** (optional): Department/project
   - **Required Date**: When this line is needed (optional)
   - **Tax Category** (optional)

3. Light calculates line total
4. Click **Add**
5. Repeat for additional items

## PO States and Workflow

POs progress through states:

- **DRAFT**: Created but not sent; no commitment
- **APPROVED**: Approved and sent to vendor
- **RECEIVED**: Goods/services partially or fully received
- **BILLED**: Matched to invoice
- **CLOSED**: Completed and archived

When viewing a PO, the status badge in the header shows the current state.

To change PO state:

1. Open the PO
2. Click **Change Status**
3. Select target state
4. Light validates transition
5. Click **Confirm**

### Sending POs to Vendors

When a PO is approved and syncs to your ERP (moving to APPROVED/OPEN state), Light automatically emails the vendor with the PO PDF attached. The email includes the PO number, issue date, delivery date, and description, plus your contact email for questions.

Note: this only happens if the vendor has an email address on file. If your vendor is missing an email, add it in the vendor record before approving the PO.

## PO Approvals

Enforce approval before orders are committed:

1. Open the PO
2. Click **Send for Approval**
3. PO is routed to configured approvers:
   - **Department Manager**: Approves spending
   - **Finance**: Approves GL account coding
   - **Procurement**: Approves vendor terms

4. Each approver reviews and approves or rejects
5. Rejected POs return to creator for revision
6. Approved POs move to APPROVED state

Configure approval hierarchies in **Settings** > **PO Approvals**.

## Matching to Receipts and Bills

### Receipt Matching

When goods are received:

1. Open the PO
2. Click **Receive Goods**
3. Enter **quantity received** for each line
4. Set **receipt date**
5. Light shows:
   - Ordered quantity vs. received
   - Discrepancies if quantities don't match

6. Click **Record Receipt**

Receipt can be partial (multiple receipts for one PO).

### Three-Way Match

When a bill arrives, Light matches it to PO and receipt:

1. Create bill in AP
2. Link to PO (see Entering Bills article)
3. Light validates:
   - **PO Quantity** vs. **Receipt Quantity**: Match check
   - **PO Price** vs. **Bill Price**: Amount match check
   - **PO Date** vs. **Bill Date**: Timing check

4. If discrepancies:
   - Light flags them
   - Shows variances
   - You document reason and approve or reject

5. Matched bills are ready for approval and payment

When a PO is open or closed, the matched invoices table shows which bills have been linked to the PO, the matched amount, and the remaining unmatched amount.

## Viewing PO Documents

When viewing a PO, use the **Show document** / **Hide document** toggle button to display or hide the PDF preview. This helps focus on the PO details or review the formatted document as needed.

## Controlling Spending with POs

### Spend Limits

Set maximum spending by vendor or category:

1. Open a vendor
2. Navigate to **Spending Limits**
3. Set:
   - **Annual Spending Limit**: Max per year
   - **Monthly Limit**: Max per month
   - **Single Transaction Limit**: Max per PO

4. Light warns when creating POs that approach limits
5. Prevents PO creation if limit exceeded (configurable)

### Budget Allocation

Reserve budget when PO is created:

1. Navigate to **Settings** > **Budget Integration**
2. Enable **Reserve Budget for POs**
3. When PO is approved:
   - Light reserves the PO amount from GL budget
   - Budget is committed (not yet spent)
   - Bill reduces reserved amount

4. This prevents overspending

## Blanket Purchase Orders

For recurring purchases from a vendor:

1. Create a **Blanket PO** with:
   - **Total Contract Value**: Max to spend
   - **Multiple Deliveries**: Over time
   - **No Specific Quantities**: Just total value limit

2. Subsequent purchases against blanket PO draw down the total
3. When amount is exhausted, PO is closed
4. Reduces administrative overhead for routine purchases

## Amendments and Changes

To modify an existing approved PO:

1. Open the PO
2. Click **Amend PO**
3. Make changes to:
   - Quantities
   - Prices
   - Delivery dates
   - Delivery address

4. Light recalculates totals
5. Amendment may require re-approval (depending on change type)
6. Click **Submit Amendment**

Original PO and amendment are linked for audit trail.

## Canceling POs

To cancel a PO:

1. Open the PO
2. Click **Cancel**
3. Provide reason (vendor unavailable, project cancelled, etc.)
4. If goods were already received, you're still liable for payment
5. Click **Confirm Cancel**

Cancelled POs remain in system for historical reference.

## Purchase Order Analytics

### Spend Analysis

1. Navigate to **Reports** > **PO Spend Analysis**
2. View:
   - Total spending by vendor
   - By GL account or cost center
   - By time period
   - By commodity (product category)

Once approved, the PO transitions through `APPROVED_ACCOUNTING_ENTRY_PENDING` to `OPEN` and is available for matching.

## Matching POs to Bills

When entering a bill, you can link it to a PO by setting the **PO number** on the bill. Light then tracks the matched amount against the PO's open quantity.

## Closing a PO

When all bills against a PO have been received (or the PO is no longer needed), close it from the PO detail view. It transitions through `CLOSE_PENDING` to `CLOSED`.

## Purchase Requests (PRs)

Purchase requests are a separate, upstream document used to request approval to buy. PRs live under **Spend management → Purchase requests** and, once approved, can be converted into POs. PRs are an optional workflow — companies that don't need a request layer can use POs directly.

## Related Articles

- [Entering bills](/articles/07-accounts-payable/7-4-entering-bills.md)
- [Bill approval](/articles/07-accounts-payable/7-6-bill-approval.md)
- [Managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md)
