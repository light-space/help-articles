# Multi-Entity AP Operations

Light's AP module handles complex multi-entity payables common in global organizations. This article covers vendor management, bill entry, and payments across multiple legal entities.

[Open in Light →](https://app.light.inc/payables)

## Multi-Entity AP Concepts

In multi-entity AP:

- **Company**: Your top-level organization
- **Entities**: Legal entities or subsidiaries (e.g., Light US Inc, Light Europe GmbH)
- **Vendors**: Managed at company level but bills are by entity
- **GL**: Each entity has its own GL account structure

Each entity has independent AP (separate vendors, bills, payments) while sharing a vendor master database.

## Setting Up Multi-Entity Vendors

### Creating Vendors for Specific Entities

1. Create vendor at company level (visible to all entities)
2. Open the vendor
3. Navigate to **Entity Assignment**
4. Click **Assign to Entity**
5. Select one or more entities
6. Optionally, set **Entity-Specific Details**:
   - Different billing address
   - Different contact person
   - Entity-specific payment terms
   - Entity-specific GL account defaults

7. Click **Assign**

Vendors can be assigned to one entity (local vendor) or multiple entities (shared vendor).

### Shared Vendors Across Entities

Some vendors serve multiple entities:

- **Global Vendors**: Same company has branches in multiple countries (use shared vendor)
- **Regional Vendors**: Multiple entities use same supplier

For shared vendors:

1. Assign vendor to all relevant entities
2. Set entity-specific banking/payment details if each entity has separate account
3. Set entity-specific contacts if different people handle orders
4. Bill and payment routing automatically goes to correct entity GL

## Entering Bills in Multi-Entity Environment

### Selecting Entity When Creating Bill

1. Click **Create Bill**
2. Select **Vendor** (vendor list shows only those available to your entity)
3. If vendor serves multiple entities, select your **Entity**
4. Light defaults GL accounts to the selected entity's chart of accounts
5. Continue creating bill

The bill is posted to the selected entity's GL, not to other entities.

### Cross-Entity Transactions (Intercompany Bills)

When one entity buys from another entity (internal transfer):

1. Create bill normally
2. In bill details, mark **Intercompany Transaction**
3. Select the **Selling Entity** (which entity is selling to you)
4. Light creates:
   - AP bill in buying entity's GL
   - AR invoice in selling entity's GL
   - Both are linked for consolidation/elimination

5. Post and pay the bill normally
6. GL entries include intercompany accounts for consolidation

## Multi-Entity Payment Execution

### Entity-Specific Payment Batches

Payments are created and executed per entity:

1. Navigate to **Payments**
2. Filter to show bills from your **entity only**
3. Create payment batch with your entity's bills
4. Payment executes from your entity's bank account
5. GL entries post to your entity

Bills from other entities appear in their payment queues.

### Intercompany Settlement

When one entity owes another (from intercompany transaction):

1. At period end, intercompany balances are calculated
2. Buying entity's payable = Selling entity's receivable
3. Option to settle:
   - **Actual payment**: One entity actually transfers cash to other
   - **Offset**: Accounts are netted at consolidation (only consolidated P&L affected)

4. Light tracks which intercompany invoices are settled vs. pending

## Multi-Currency in Multi-Entity

### Entity-Specific Currencies

Each entity has:

- **Functional Currency**: Entity's local currency
- **Reporting Currency**: Company currency (for consolidation)

When entering bills:

1. Bill currency defaults to entity's functional currency
2. You can override to other currency
3. Payment in non-functional currency triggers FX processing
4. GL records in both functional and reporting currencies

### Multi-Entity Consolidation

Consolidation software or Light's consolidation module:

1. Pulls GL from each entity (in local currency)
2. Eliminates intercompany transactions
3. Converts to reporting currency
4. Produces consolidated financial statements

Light's AP module supplies GL data for this process.

## Centralized vs. Decentralized Payables

Light supports both:

### Centralized Model

**One central AP team** processes all payables:

1. All vendors in single list
2. Central team enters and approves all bills
3. Central team processes all payments
4. Each entity's AP is managed centrally
5. Benefits: Better control, fewer vendors, better negotiation

Configuration:
- Give central AP team access to all entities
- Individual users have entity-restricted access
- Central team users see all bills across entities

### Decentralized Model

**Each entity manages own payables**:

1. Separate AP teams per entity
2. Entity-specific vendors
3. Entity-specific processes
4. Central team consolidates for reporting
5. Benefits: Local autonomy, faster local decisions

Configuration:
- Give each entity's AP team access to only their entity
- Vendors assigned to specific entities
- Central reporting team has read-only consolidation access

## Shared Services Center (SSC)

For large organizations, use Light's SSC features:

1. Create a **Shared Services Center** entity
2. Assign service duties (payroll, AP, AR) to SSC
3. Operating entities send work to SSC via intercompany
4. SSC processes and returns results
5. GL entries properly allocated to operating entities

Benefits: Efficiency, standardization, cost reduction.

## Multi-Entity Reporting and Consolidation

### AP Aging by Entity

1. Navigate to **Reports** > **AP Aging**
2. Select **View**: Single Entity or Consolidated
3. For consolidated:
   - View total AP across all entities
   - See breakdown by entity
   - View in reporting currency

4. Filter reports by entity or show multi-entity comparison

### Consolidated AP Metrics

1. Navigate to **Dashboard** > **AP Summary**
2. Consolidation option shows:
   - Total payables (all entities combined)
   - Total by vendor (consolidated across entities)
   - Payment schedule (all entities)
   - Currency breakdown (all entity currencies)

3. Drill down into specific entities for detail

### Intercompany Reconciliation

Monitor intercompany transactions:

1. Navigate to **Reports** > **Intercompany Transactions**
2. Filter to **AP type** (payables from entity to entity)
3. View matched pairs:
   - Selling entity's AR
   - Buying entity's AP
   - Reconciliation status

4. Identify unmatched or disputed transactions
5. Investigate discrepancies

## Entity Consolidation for Close

At period close, use consolidation features:

1. Navigate to **Close Process** > **Consolidation**
2. Light identifies all intercompany transactions
3. For each:
   - Verify amounts match
   - Confirm both sides posted
   - Mark as consolidated or review if discrepancies

4. Light eliminates intercompany entries from consolidated view
5. Produces consolidated AP aging and metrics

## Related Articles

- [Adding and managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md)
- [Entering and ingesting bills](/articles/07-accounts-payable/7-4-entering-bills.md)
- [Scheduling and executing payments](/articles/07-accounts-payable/7-7-scheduling-payments.md)
