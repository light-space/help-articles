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
- Maintains its own ledger, with GL accounts assigned from the company chart of accounts
- Posts transactions independently
- Reports separately and consolidated

## Entity Structure

Set up entities in [**Settings (gear icon) → Entities**](https://app.light.inc/settings/entities):

1. Each entity has:
   - **Name** - Legal or operating name
   - **Code** - Automatically assigned entity code (e.g., "001", "002"), used in document numbers
   - **Local currency** - The entity's operating currency (USD, EUR, GBP, etc.); cannot be changed after creation
   - **Address** - Legal address
   - **Parent entity** - If part of a hierarchy
   - **Status** - Active, Inactive, Hidden

2. Entities can be hierarchical:
   - Assign a parent entity to reflect your group structure
   - Useful for regional or functional groupings

## Chart of Accounts per Entity

Light maintains one chart of accounts per company, and each GL account is assigned to one or more entities:

**Shared accounts:**
- Assign accounts to all entities so they use the same GL account codes
- Simplifies consolidation and reporting
- Standard practice for multinational companies

**Entity-specific accounts:**
- Assign an account to selected entities only (unusual)
- Useful for entity-specific GL accounts (intercompany receivable)
- More complex to consolidate

Most companies share the chart of accounts across entities.

## Posting to Entities

When creating documents, specify the company entity:

1. Invoice Payable:
   - Specify vendor's entity (which entity receives the bill)
   - Posts to that entity's GL
2. Invoice Receivable:
   - Specify customer's entity
   - Posts to that entity's GL
3. Journal Entry:
   - Posts to a single entity's GL
   - Use an intercompany journal entry to span entities (each line specifies its entity)

Documents are always posted to an entity's GL, not to a shared general ledger. Document numbers include the entity code in the format DOCTYPE/ENTITY/NUMBER (e.g., AP/001/000000123), and number sequences run separately per entity and document type.

## Intercompany Transactions

When entities transact with each other:

**Example: Parent lends cash to subsidiary**
- Parent entity: Debit Intercompany Receivable, Credit Cash
- Subsidiary entity: Debit Cash, Credit Intercompany Payable

Both entities post the transaction, creating a payable/receivable pair.

## Creating Intercompany Entries

For intercompany transactions, create journal entries spanning entities:

1. Go to **Accounting → Journal entries**
2. Click **+ Create journal entry** and select the intercompany type
3. Each line specifies:
   - **Company entity**
   - GL account
   - Debit/credit amount
   - **Eliminate** - whether the line is eliminated at consolidation
4. Entry posts to each entity's GL separately, and Light automatically adds the intercompany receivable/payable offset lines based on your intercompany account configuration

Lines flagged for elimination post to the Elimination ledger, which feeds the eliminations column in consolidated reports.

## Entity-Level Reporting

Report on individual entity GL:

1. Go to **Planning & Reports → Reports** and open a report
2. In the **Entity** filter, select a single entity
3. View that entity's GL, balance sheet, income statement, etc.
4. Report contains only that entity's transactions

Entity-level reports are useful for:
- Individual P&L reviews
- Regulatory filings for subsidiaries
- Performance evaluation

## Consolidated Reporting

Report across all entities:

1. Go to **Planning & Reports → Reports** and open a report
2. In the entity selector, click **Consolidated** and select the entities to include
3. The report shows a column per entity, a **Subtotal** column, an **Eliminations** column (intercompany offsets), and a **Total** column
4. Use **Group Crcy** to view all entities translated to the group currency

The Total column is the Subtotal minus Eliminations - the true group result.

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
2. Every transaction posts with three amounts: the document (transaction) currency, the entity's local currency, and the company's group currency
3. Local and group amounts are converted at posting time using the valuation date rate (official ECB rates, or a custom rate override)
4. Translation differences are handled via FX revaluation and the currency translation adjustment (CTA) system account

Consolidated reports read the group currency amounts stored on each transaction, so no separate consolidation-date conversion is applied.

## Entity Hierarchy in Reports

If entities are hierarchical:

```
Parent Entity
  ├─ Child Entity A
  └─ Child Entity B
```

Reports let you choose which entities to include:
- Parent and all children combined (select them together in consolidated view)
- Only the parent or a specific child

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
3. Create an intercompany journal entry:
   - FROM line: Credit the parent's overhead (or clearing) account $100,000
   - TO lines: Debit Entity A Expense $60,000 and Entity B Expense $40,000
   - Light automatically adds the intercompany receivable/payable offset lines
4. Posts the allocation to each entity's GL

Use this for cost allocation, management accounting, or regulatory requirements.

## Minority Interests

For partial subsidiaries or joint ventures:

1. Parent owns 70%, outside party owns 30%
2. Subsidiary posts full GL transactions
3. Consolidated reports combine 100% of the subsidiary's results
4. Record the minority (non-controlling) interest share via manual journal entries if required

Light does not calculate minority interest automatically; implement it with manual journal entries.

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

- **Use consistent entity names** - Entity codes are assigned automatically; standardize display names
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
