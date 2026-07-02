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
3. Add **line items** (each with a description, amount, GL account, cost center, tax code)
4. Save — the credit opens in **Draft**

## Posting (Publishing) a Credit

From the credit detail header, click **Publish** to post the credit. If a credit note approval workflow is published (**Settings → Workflows**), publishing submits the credit for approval instead, and it's posted once approved. Once posted, it becomes available to apply against open bills.

## Applying a Credit to a Bill

1. Open a Posted credit entry
2. Click **Apply to bill**
3. The dialog lists open bills for the same vendor and entity in the same currency
4. Pick the target bill and enter the application amount
5. Confirm

The dialog tracks:
- Remaining balance on the credit (credit amount minus already linked bills)
- Total invoice amount of each candidate bill

You can apply a credit across multiple bills in succession; each application reduces the remaining balance. When the credit is fully consumed, its state moves to **Cleared**.

To remove an application, click **Unlink** next to the linked bill in the credit's detail view.

## Other Actions

From the credit detail header:
- **Archive** — archive the credit (available in Draft and Posted; a Posted credit with linked bills must be unlinked first)
- **Mark as paid** — record a vendor refund of the credit as a bank payment; pick the payment date, bank account, and amount

## Related Articles

- [Entering bills](/articles/07-accounts-payable/7-4-entering-bills.md)
- [Scheduling payments](/articles/07-accounts-payable/7-7-scheduling-payments.md)
