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

1. Click **+ Create purchase order**
2. Fill in the header:
   - **Vendor**
   - **Entity**
   - **Currency**
   - **PO date** / **expected delivery date**
3. Add **line items**:
   - Description
   - Quantity, unit price
   - GL account
   - Tax code
   - Cost center / custom dimensions
4. Save the PO in draft, or submit it for approval

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
