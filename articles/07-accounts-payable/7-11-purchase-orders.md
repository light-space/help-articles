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
2. Click **+ Create purchase order**
3. Enter PO details:
   - **Vendor**: Select or search
   - **PO Date**: When PO was created
   - **Delivery Date** (optional): When goods/services are needed
   - **Delivery Address** (optional)
   - **Company Entity**: Which entity is buying
   - **Currency**: PO currency
   - **Description** and **Vendor Notes** (optional)

4. Click **Next** to add line items

The PO number is assigned automatically from your company's PO number sequence when the PO is approved — you don't enter it manually.

## Adding PO Line Items

1. Click **Add Line Item**
2. Enter:
   - **Description**: What you're ordering
   - **Quantity** and **Unit Price**
   - **GL Account**: Which account to charge
   - **Cost Center** (optional): Department/project
   - **Tax Code** (optional)

3. Light calculates line total
4. Click **Add**
5. Repeat for additional items

## PO States and Workflow

POs progress through the states listed above:

- **IN_DRAFT**: Created but not sent; fully editable, no commitment
- **APPROVED_ACCOUNTING_ENTRY_PENDING**: Approved; Light is finalising the accounting entry
- **OPEN**: Active, numbered, sent to the vendor, and available for matching against bills
- **CLOSED**: Completed; no further matching
- **CANCELLED**: Cancelled

When viewing a PO, the status badge in the header shows the current state.

State changes happen through specific actions rather than a free-form status picker: **approve** a draft to open it, and **close**, **cancel**, or **reset** an open PO. Once a PO leaves draft it is locked for editing.

### Sending POs to Vendors

When a PO is approved and syncs to your ERP (moving to APPROVED/OPEN state), Light automatically emails the vendor with the PO PDF attached. The email includes the PO number, issue date, delivery date, and description, plus your contact email for questions.

Note: this only happens if the vendor has an email address on file. If your vendor is missing an email, add it in the vendor record before approving the PO.

## PO Approvals

Light does not route individual POs through their own approval chain. Pre-purchase approval is handled upstream by **purchase requests**: a requester files a purchase request, it is routed to the configured approvers, and an approved request with a purchase order outcome results in a PO.

Configure the routing in **Settings → Workflows** under the purchase request approval workflow. Routing can branch on amount, entity, requester, vendor (including whether the vendor is new), outcome type, and custom properties.

## Matching Bills to POs

Light matches bills (vendor invoices) directly to POs by amount — there is no separate goods-receipt step:

1. Create or receive the bill in AP
2. Link it to a PO (see Entering Bills article)
3. Light records the bill against the PO and tracks the **matched amount** and **remaining amount** in the PO's currency (foreign-currency bills are converted using your company's exchange rates)

Notes:

- A bill can be matched to only one PO at a time; matching it to a different PO moves the match.
- The bill's vendor must match the PO's vendor.
- When a bill arrives with a recognisable PO number (for example, extracted from the invoice document), Light automatically matches it to that vendor's open PO with the same number.

When a PO is open or closed, the matched invoices table shows which bills have been linked to the PO, the matched amount, and the remaining unmatched amount.

## Viewing PO Documents

When viewing a PO, use the **Show document** / **Hide document** toggle button to display or hide the PDF preview. This helps focus on the PO details or review the formatted document as needed.

## Amendments and Changes

Approved and open POs are locked for editing. To modify one:

1. Open the PO
2. Click **Reset** to return it to draft
3. Make your changes
4. Approve the PO again

The PO's activity log keeps a record of updates, state changes, and bill matches for audit purposes.

## Canceling POs

To cancel a PO:

1. Open the PO
2. Click **Cancel**
3. Click **Confirm Cancel**

Draft POs are cancelled immediately; open POs pass through `CANCEL_PENDING` while the cancellation syncs. Cancelled POs remain in the system for historical reference. If goods were already received, you're still liable for payment.

Once approved, the PO transitions through `APPROVED_ACCOUNTING_ENTRY_PENDING` to `OPEN` and is available for matching.

## Matching POs to Bills

When entering a bill, you can link it to a PO by setting the **PO number** on the bill. Light then tracks the matched amount and the remaining unmatched amount on the PO.

## Closing a PO

When all bills against a PO have been received (or the PO is no longer needed), close it from the PO detail view. It transitions through `CLOSE_PENDING` to `CLOSED`.

## Purchase Requests (PRs)

Purchase requests are a separate, upstream document used to request approval to buy. PRs are filed from the [Purchase orders](https://app.light.inc/procurement/purchase-requests) page under **Spend management → Purchase orders**. An approved request's outcome can be a **purchase order** or a **vendor card**; a purchase order outcome creates the PO on approval. PRs are an optional workflow — companies that don't need a request layer can use POs directly.

## Related Articles

- [Entering bills](/articles/07-accounts-payable/7-4-entering-bills.md)
- [Bill approval](/articles/07-accounts-payable/7-6-bill-approval.md)
- [Managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md)
