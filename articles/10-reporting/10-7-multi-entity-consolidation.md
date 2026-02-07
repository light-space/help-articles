# Multi-Entity Consolidation

When your organization includes multiple legal entities (subsidiaries, branches, divisions), consolidation combines their financial results into a single set of group financial statements. Light automates consolidation, eliminating inter-company transactions and combining financial positions to present your organization as a single entity.

[Open in Light →](https://app.light.inc/ledger-reports)

## Consolidation overview

Consolidation is the process of combining financial statements of a parent company and its subsidiaries. The result is a consolidated balance sheet, P&L, and cash flow statement showing the combined financial position and performance.

Key consolidation requirements:

- **Identify the group structure**: Parent and subsidiary relationships
- **Eliminate inter-company transactions**: Remove transactions between group members
- **Combine balances**: Sum corresponding accounts across entities
- **Document adjustments**: Record consolidation entries and their rationale

Light automates most of this process.

## Defining the entity structure

Configure your multi-entity structure in Light:

1. Navigate to **Settings (gear icon) > Entities**
2. Define parent company (top of hierarchy)
3. For each entity, specify:
   - Entity type: Parent, subsidiary, division, branch
   - Parent entity (if applicable)
   - Ownership percentage (for partial subsidiaries)
   - Reporting relationship
4. Save the structure

Light then knows which entities to consolidate.

> Good to know: You can have multiple parents (decentralized reporting) or a single parent (centralized hierarchy). Define the structure based on your organization.

## Inter-company transaction identification

Inter-company transactions occur when one entity sells to or buys from another entity in the same group. Common examples:

- Subsidiary buys inventory or materials from parent
- Parent provides management fees to subsidiary
- Subsidiary pays interest to parent on inter-company loans
- Subsidiary pays royalties to parent for use of intellectual property

These transactions are legitimate between entities but must be eliminated in consolidated statements to prevent double-counting.

Light identifies inter-company transactions:

1. When creating a transaction, mark it as **Inter-company**
2. Link the transaction to its corresponding mirror entry in the other entity
3. Light tracks the pairing

Light then eliminates both the inter-company transaction and its mirror when consolidating.

## Consolidation mechanics

When you generate a consolidated report:

1. Light pulls trial balance for each entity
2. Light identifies inter-company transactions
3. Light eliminates inter-company balances (for balance sheet):
   - Receivable in one entity paired with payable in another
   - Investment in subsidiary paired with subsidiary equity
4. Light eliminates inter-company transactions (for P&L):
   - Sale in one entity paired with purchase in another
   - Profit on inter-company transactions reversed
5. Light sums remaining balances across entities
6. Result: Consolidated financial statements

## Consolidation adjustments

Beyond eliminating inter-company transactions, adjustments may be needed:

**Goodwill and fair value**: If a subsidiary was acquired for more than net asset value, goodwill records the difference.

**Elimination of intercompany profit**: If one entity sells to another at a markup, the profit is eliminated until sold to external parties.

**Equity translation**: When translating foreign subsidiary financial statements, translation differences are recorded.

**Deferred tax**: Tax impacts of consolidation adjustments may require deferred tax recording.

Configure these adjustments in consolidation templates.

## Generating consolidated financial statements

To generate a consolidated report:

1. Navigate to **Planning & Reports → Reports**
2. Select consolidation scope:
   - Parent company
   - All subsidiaries
   - Specific subset of entities
3. Select report type:
   - Balance sheet
   - Income statement
   - Cash flow statement
   - Trial balance
4. Select as-of date or period
5. Click **Generate**

Light displays consolidated results with elimination detail.

## Consolidation at different ownership levels

If you own less than 100% of a subsidiary:

**Full consolidation** (parent-subsidiary): You control the subsidiary even with <50% ownership (e.g., voting agreements give control).

Light includes 100% of subsidiary assets, liabilities, revenue, and expenses in consolidation.

Record **non-controlling interest** (minority interest) on the balance sheet and P&L:
- Balance sheet liability representing the portion owned by non-controlling shareholders
- P&L line showing profit attributable to non-controlling interests

**Equity method** (investments in associates): You have significant influence (typically 20-50% ownership).

Record investment as single line item on balance sheet at equity value. Record investment income from share of subsidiary profits on P&L.

**Cost method** (investments in other companies): You don't have control or significant influence.

Record investment as asset on balance sheet. Record dividend income as P&L line.

Configure the consolidation method per entity.

> Tip: Review your ownership percentages and control relationships. Consolidation requirements depend on control, not just ownership percentage.

## Inter-company receivable and payable elimination

Inter-company receivables and payables must be eliminated on the consolidated balance sheet:

1. Subsidiary A invoices subsidiary B for goods: Subsidiary A records receivable, Subsidiary B records payable
2. In consolidation, eliminate both the receivable and payable
3. Net effect: No balance sheet impact from inter-company transactions

If receivables and payables don't match exactly, document the timing difference and reconcile.

## Downstream and upstream inter-company profit elimination

If one entity sells goods to another at a markup, the profit is eliminated until sold to external parties.

**Downstream sale** (parent to subsidiary):
- Profit is eliminated from parent's P&L
- Subsidiary's inventory is written down
- Elimination affects parent's retained earnings

**Upstream sale** (subsidiary to parent):
- Profit is eliminated from subsidiary's P&L
- Parent's inventory is written down
- Elimination affects subsidiary's retained earnings

Light identifies these situations and calculates the elimination.

## Consolidation of foreign subsidiaries

Foreign subsidiaries operate in different currencies. When consolidating:

1. Translate foreign subsidiary's statements to group currency
2. Use average exchange rates for P&L accounts (income, expense)
3. Use period-end rates for balance sheet accounts (assets, liabilities)
4. Differences from prior period's rate create translation gain/loss
5. Record translation gains/losses in other comprehensive income (OCI)

Light automatically handles currency translation in consolidation.

## Statutory vs. management reporting consolidation

You may prepare two sets of consolidated statements:

**Statutory consolidation**: For external audit and regulatory filing. Follows IFRS or GAAP rules strictly. May include footnotes and tax positions.

**Management consolidation**: For internal decision-making. May include adjustments for inter-company profits, management fees, and other items.

Light supports both by allowing flexible consolidation templates.

## Consolidation working papers

Maintain comprehensive consolidation documentation:

**Consolidation schedule**: Lists all entities consolidated, ownership percentages, and reporting dates.

**Inter-company transaction schedules**: Documents all inter-company transactions eliminated.

**Consolidation adjustment schedules**: Documents non-elimination adjustments (goodwill, FX translation, etc.).

**Elimination entries**: Journal entries recording consolidation adjustments.

**Reconciliation of equity**: Shows how consolidated equity equals sum of entity equities plus goodwill and adjustments.

Light can generate all these supporting schedules.

## Consolidation review and approval

Establish a review procedure:

1. Prepare preliminary consolidated statements
2. Review by finance team for completeness and accuracy
3. Identify and investigate variances or unusual items
4. Adjust if needed
5. Review by CFO or audit committee
6. Approve and finalize

Light maintains an audit trail of who reviewed and approved each consolidation.

## Segment reporting

If you report different business segments, provide separate P&L by segment:

1. Navigate to **Planning & Reports → Reports**
2. Define segments: Geography, product line, or business unit
3. Light aggregates revenue and expense by segment
4. Report each segment's profitability

This is useful for investors understanding profitability by business line.

## Consolidation date and timing

All entities must consolidate as of the same date:

- For most companies: Quarter-end or year-end (Jan 31, Apr 30, etc.)
- For companies with different fiscal years: Use the group's fiscal year-end

If a subsidiary has a different fiscal year:
1. Prepare subsidiary financial statements as of the group consolidation date
2. Make adjustments for inter-company transactions between subsidiary and group fiscal year-end

Light helps coordinate consolidation timing across all entities.

## Consolidated cash flow statement

The consolidated cash flow statement shows group-wide cash flows:

1. Combine operating, investing, financing cash flows from all entities
2. Eliminate inter-company cash flows (not relevant to consolidated group)
3. Consolidate cash balance sheet impact
4. Result shows external cash flows only

Light automatically handles consolidation mechanics.

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Multi-currency consolidation](10-8-multi-currency-consolidation.md)
- [Balance sheet](10-2-balance-sheet.md)
- [Profit and loss](10-3-profit-loss.md)
- [Custom reports and filters](10-9-custom-reports.md)
