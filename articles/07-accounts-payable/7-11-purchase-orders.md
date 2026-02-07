# Purchase Orders and Procurement

Purchase orders (POs) in Light document your intention to buy goods or services from vendors. They enable three-way matching (PO, receipt, bill) and control spending.

[Open in Light →](https://app.light.inc/procurement/purchase-orders)

## Understanding Purchase Orders

A PO is a contractual commitment to buy from a vendor:

- **Quantity and Price**: What you're buying and at what price
- **Delivery Terms**: When goods/services will be delivered
- **Payment Terms**: When you'll pay
- **GL Accounts**: Which accounts to charge
- **Approvals**: Who must approve the spending

POs are optional in Light AP but recommended for spend control.

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

To change PO state:

1. Open the PO
2. Click **Change Status**
3. Select target state
4. Light validates transition
5. Click **Confirm**

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

3. Identify top vendors
4. Analyze spending patterns
5. Export for analysis

### Vendor Performance

1. Navigate to **Reports** > **Vendor Performance**
2. View:
   - On-time delivery rate
   - Quality of goods/services
   - Price competitiveness
   - Responsiveness

3. Use to negotiate better terms or switch vendors

## Integration with Procurement

For organizations with formal procurement:

1. Light integrates with procurement workflows
2. Procurement team creates POs based on requisitions
3. POs feed into supplier management
4. Contracts track long-term vendor arrangements
5. Volume discounts are tracked and applied

## Related Articles

- [Adding and managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md)
- [Entering and ingesting bills](/articles/07-accounts-payable/7-4-entering-bills.md)
- [Bill approval workflows](/articles/07-accounts-payable/7-6-bill-approval.md)
