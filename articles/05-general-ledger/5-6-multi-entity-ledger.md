# Multi-Entity Ledger Management

For companies with multiple entities (subsidiaries, branches, operating divisions), Light maintains separate ledgers per entity. This article explains multi-entity GL management and consolidation.

[Open in Light →](https://app.light.inc/ledger-transactions)


## Multi-Entity Overview

A multi-entity company has multiple operating units:

- **Subsidiaries** - Separate legal entities (each with own tax ID)
- **Branches** - Operating units of the same legal entity
- **Divisions** - Internal business units

Each entity:
- Has its own company entity record
- Maintains its own ledger and chart of accounts
- Posts transactions independently
- Reports separately and consolidated

## Entity Structure

Set up entities in **Company Settings > Company Entities**:

1. Each entity has:
   - **Name** - Legal or operating name
   - **Code** - Short identifier (e.g., "US-01", "EU-02")
   - **Currency** - Local currency (USD, EUR, GBP, etc.)
   - **Address** - Legal address
   - **Parent entity** - If part of a hierarchy
   - **Status** - Active, Inactive, Hidden

2. Entities can be hierarchical:
   - Parent entity rolls up child balances
   - Useful for regional or functional groupings

## Chart of Accounts per Entity

Each entity can have:

**Shared chart of accounts:**
- All entities use the same GL account codes
- Simplifies consolidation and reporting
- Standard practice for multinational companies

**Entity-specific accounts:**
- Entities have unique accounts (unusual)
- Useful for entity-specific GL accounts (intercompany receivable)
- More complex to consolidate

Most companies use a shared chart across entities.

## Posting to Entities

When creating documents, specify the company entity:

1. Invoice Payable:
   - Specify vendor's entity (which entity receives the bill)
   - Posts to that entity's GL
2. Invoice Receivable:
   - Specify customer's entity
   - Posts to that entity's GL
3. Journal Entry:
   - Can post lines to different entities (intercompany)
   - Each line shows its entity

Documents are always posted to an entity's GL, not to a shared general ledger.

## Intercompany Transactions

When entities transact with each other:

**Example: Parent lends cash to subsidiary**
- Parent entity: Debit Intercompany Receivable, Credit Cash
- Subsidiary entity: Debit Cash, Credit Intercompany Payable

Both entities post the transaction, creating a payable/receivable pair.

## Creating Intercompany Entries

For intercompany transactions, create journal entries spanning entities:

1. Go to **General Ledger > Journal Entries**
2. Create entry with lines for multiple entities
3. Each line specifies:
   - GL account
   - Debit/credit amount
   - **Company entity**
4. Entry posts to each entity's GL separately

System tracks which lines are intercompany for consolidation elimination.

## Entity-Level Reporting

Report on individual entity GL:

1. Go to **Reports > [Report Type]**
2. Filter by **Entity**
3. View that entity's GL, balance sheet, income statement, etc.
4. Report contains only that entity's transactions

Entity-level reports are useful for:
- Individual P&L reviews
- Regulatory filings for subsidiaries
- Performance evaluation

## Consolidated Reporting

Report across all entities:

1. Go to **Reports > [Report Type]**
2. Leave **Entity** filter blank (or select "All")
3. Select **Consolidation Method**:
   - Sum (total across all entities, keep intercompany)
   - Eliminate (total minus intercompany eliminations)
4. View consolidated GL, balance sheet, income statement

Consolidated reports typically use elimination to show true group results.

## Intercompany Elimination

When consolidating, eliminate intercompany transactions:

**Example:**
- Entity A loaned $100,000 to Entity B
- Entity A GL: Intercompany Receivable $100,000
- Entity B GL: Intercompany Payable $100,000
- Consolidated (without elimination): Shows $100,000 both ways (cancels out)
- Consolidated (with elimination): Shows $0 (properly eliminated)

Elimination removes intercompany amounts to show group transactions with external parties only.

## Multi-Currency Considerations

For multi-entity companies with different currencies:

1. Each entity has a local currency (EUR, GBP, JPY, etc.)
2. Transactions post in local currency to entity GL
3. Group level converts all to group currency
4. FX differences arise from consolidation conversion

When consolidating, all entities are converted to group currency using consolidation date rates.

## Entity Hierarchy in Reports

If entities are hierarchical:

```
Parent Entity
  ├─ Child Entity A
  └─ Child Entity B
```

Reports can show:
- Parent and all children combined
- Only parent or specific child
- Hierarchy view (rolling up balances)

## Transfer Pricing

For entities in different countries, use transfer pricing:

1. Create journal entries between entities with specific rates
2. Document transfer price for tax purposes
3. Report separately for each entity (at transfer price)
4. Consolidation can show fair value

Light doesn't enforce transfer pricing rules but allows you to implement them via intercompany entries.

## Allocations Between Entities

Allocate shared costs across entities:

1. Parent incurs $100,000 corporate overhead
2. Allocate 60% to Entity A ($60,000), 40% to Entity B ($40,000)
3. Create journal entry:
   - Debit: Entity A Expense, Credit: Parent Clearing
   - Debit: Entity B Expense, Credit: Parent Clearing
   - Debit: Entity A Intercompany Payable
   - Debit: Entity B Intercompany Payable
4. Posts allocation to each entity's GL

Use this for cost allocation, management accounting, or regulatory requirements.

## Minority Interests

For partial subsidiaries or joint ventures:

1. Parent owns 70%, Outside party owns 30%
2. Subsidiary posts full GL transactions
3. Consolidation calculates minority interest:
   - Parent share: 70% of subsidiary results
   - Minority share: 30% of subsidiary results
4. Income statement shows minority interest as separate line

Light supports minority interest calculations in consolidated statements.

## Equity Accounting

For significant investments in other entities:

1. Investor company uses equity method
2. Records initial investment
3. Posts annual:
   - Share of investee's income
   - Less any dividends received
4. Increases or decreases investment balance each period

Manual journal entries implement equity accounting; Light provides GL structure.

## Segment Reporting

For management reporting by segment (entity, geography, product):

1. Set up custom properties for segment codes
2. Post all transactions with segment property
3. Report filtered by segment
4. Analyze performance by segment

Entities can be segments, or use custom properties for finer-grained segmentation.

## Best Practices

- **Use consistent entity codes** - Standardize naming and coding
- **Maintain entity hierarchy** - Reflect organizational structure in GL
- **Document allocations** - Keep notes on why allocations are made
- **Reconcile intercompany** - Ensure payables match receivables
- **Monitor elimination** - Verify intercompany accounts eliminate properly
- **Report both views** - Show entity-level and consolidated results
- **Archive old entities** - Mark inactive entities as such

## Related Articles

- [Understanding Light's general ledger](/mnt/help-articles/articles/05-general-ledger/5-1-understanding-general-ledger.md)
- [Creating manual journal entries](/mnt/help-articles/articles/05-general-ledger/5-4-manual-journal-entries.md)
- [Intercompany documents](/mnt/help-articles/articles/05-general-ledger/5-11-intercompany-documents.md)
