# Multi-Entity AR Operations

Light's AR module supports complex multi-entity structures common in global enterprises. This article covers managing customers, invoices, and payments across multiple legal entities and currencies.

[Open in Light →](https://app.light.inc/invoice-receivables)

## Multi-Entity Concepts

In a multi-entity setup:

- **Company**: Your top-level organization
- **Entities**: Legal entities or subsidiaries (e.g., Light US Inc, Light Europe GmbH)
- **Ledger**: GL account structure specific to each entity
- **Currency**: Each entity can have a different functional currency

Customers exist at the company level but are assigned to specific entities for invoicing.

## Setting Up Multi-Entity Customers

### Creating Customers for Specific Entities

1. Create the customer at the company level (visible to all entities)
2. Open the customer record
3. Navigate to **Entity Assignment**
4. Click **Assign to Entity**
5. Select the entity
6. Optionally, set **Entity-Specific Details**:
   - Different billing address per entity
   - Entity-specific contact
   - Entity-specific payment terms

7. Click **Assign**

Customers can be assigned to multiple entities if they do business with each.

### Entity-Specific Customer Information

Some details can vary by entity:

- **Default Currency**: Each entity has its own functional currency
- **Payment Terms**: Entity-specific terms
- **Billing Address**: Can differ if entity has different mailing address
- **GL Accounts**: Revenue accounts specific to each entity

Set entity-specific overrides when assigning customers.

## Invoicing Across Entities

### Selecting the Correct Entity

When creating an invoice:

1. Click **Create Invoice**
2. Select the **Customer**
3. Light shows available entities (only those the customer is assigned to)
4. Select the **Company Entity**
5. The invoice currency defaults to the entity's functional currency
6. Continue creating the invoice

If a customer is assigned to only one entity, the entity is pre-selected.

### Inter-company Invoicing

When one entity sells to another (internal transfer):

1. Create the invoice normally to the internal customer
2. In the invoice, mark **Intercompany Transaction**
3. Light creates offsetting entries in both entities' GL
4. Buying entity sees an AP record; selling entity sees an AR record
5. Both are linked for reconciliation

Intercompany transactions help consolidate and eliminate during period close.

## Multi-Currency Transactions

### Invoicing in Foreign Currency

1. Open or create an invoice
2. Select **Customer** and **Entity**
3. Light defaults to entity's functional currency
4. Click **Currency** to override
5. Select a foreign currency
6. Light calculates the FX rate:
   - Default: Current mid-market rate from data provider
   - Override: Enter a specific rate for this invoice

7. Amounts in the foreign currency are displayed
8. GL entries record both local and foreign amounts

### FX Rate Overrides

Override default FX rates:

1. When creating or editing an invoice, find **FX Rate**
2. Click **Override Rate**
3. Enter the **FX Rate** (units of local currency per foreign currency unit)
4. Optionally, select the **Source** (e.g., customer quote, internal policy)
5. Click **Apply**

Use overrides to match customer's local exchange rate or historical rates.

### Foreign Exchange Adjustments

As FX rates move, realized/unrealized gains/losses occur:

1. Navigate to **FX Adjustments** in AR
2. Light identifies invoices with FX exposure
3. Review calculated adjustments
4. For invoices you're about to settle:
   - Lock in current FX rate by recording payment at actual settlement rate
   - Light automatically calculates gain/loss

5. Click **Post FX Adjustment**
6. GL entries record realized gain/loss to FX GL accounts

## Consolidation and Reporting

### Consolidated AR Views

View combined AR across all entities:

1. Navigate to **Reports** > **AR Summary**
2. Click **Consolidation**
3. Select scope:
   - **Company**: All entities combined
   - **Specific Entities**: Multi-select
   - **Currency**: View in company currency or each entity's local currency

4. Light shows:
   - Total outstanding by aging bucket
   - Largest customers (consolidated)
   - Outstanding by currency
   - Entity-by-entity breakdown

5. Export to Excel for further analysis

### Intercompany Elimination

View and manage intercompany AR:

1. Navigate to **Intercompany Transactions**
2. Filter to **AR type** (invoices from one entity to another)
3. View matched pairs showing:
   - Selling entity's AR
   - Buying entity's AP
   - Status (matched, unmatched, in dispute)

4. Click into a pair to view GL entries in both entities

## Customer Credit Management Across Entities

A customer with credit from one entity may be invoiced by another:

1. Open the customer
2. Navigate to **Credit Balance**
3. View credits by **issuing entity**
4. When creating a new invoice in a different entity:
   - Light shows available credits from other entities
   - You can apply cross-entity credits manually
   - GL records credit movement between entities

5. Approve cross-entity credit applications if required by your policies

## Tax Compliance in Multi-Entity

Different entities have different tax requirements:

1. Navigate to **AR Settings** > **Tax Configuration**
2. For each entity, set:
   - **Primary Tax Engine** (for calculating invoice tax)
   - **Tax IDs** (VAT number, etc.)
   - **E-Invoicing Networks** (if applicable)

3. When invoicing, Light applies the correct entity's tax rules
4. E-invoice submissions are made on behalf of the correct entity

## Related Articles

- [AR overview](/articles/06-accounts-receivable/6-1-ar-overview.md)
- [Setting up customers and contacts](/articles/06-accounts-receivable/6-2-customers-contacts.md)
- [Invoice generation and customization](/articles/06-accounts-receivable/6-5-invoice-generation.md)
- [Tracking payments and outstanding balances](/articles/06-accounts-receivable/6-8-tracking-payments.md)
