# Intercompany Documents

Intercompany documents record transactions between entities in your corporate group. This article explains how to create and track intercompany entries.

[Open in Light →](https://app.light.inc/ledger-transactions)


## What Are Intercompany Transactions?

Intercompany transactions are financial activities between entities within the same corporate group:

**Examples:**
- Parent company loans cash to subsidiary
- Subsidiary sells products to another subsidiary
- Division A charges Division B for shared services
- Entity A transfers assets to Entity B

These transactions don't go outside the group, so they're eliminated during consolidation.

## Intercompany Document Types

Light supports two types of intercompany documents:

**Intercompany Invoices**
- One entity invoices another for goods/services
- Creates AP for the paying entity
- Creates AR for the selling entity
- Matched and cleared when paid

**Intercompany Journal Entries**
- Posted to multiple entities simultaneously
- Automatically balances across entities
- Creates payable/receivable pair

## Creating Intercompany Invoices

When Entity A sells to Entity B:

1. **Entity A creates AR invoice**:
   - Customer: Entity B
   - Amount: $10,000
   - Post to Entity A's GL
   - Creates: Debit AR, Credit Sales

2. **Entity B creates AP invoice**:
   - Vendor: Entity A
   - Amount: $10,000
   - Post to Entity B's GL
   - Creates: Debit Expense, Credit AP

3. **Link the invoices**:
   - System links them as intercompany pair
   - Shows relationship in both documents

4. **When paid**:
   - Entity B posts payment to Entity A
   - Payment clears both AR and AP
   - Both entities show cleared status

## Creating Intercompany Journal Entries

For non-invoice intercompany transactions:

1. Go to **General Ledger > Journal Entries**
2. Click **Create Journal Entry**
3. Add lines for multiple entities:
   - Line 1: Debit Entity A account (e.g., Asset)
   - Line 2: Credit Entity B account (e.g., Liability)
4. System auto-generates:
   - Entity A's debit entry
   - Entity B's credit entry
   - Maintains balanced pair
5. Click **Post**

Example: Parent loans $100,000 to subsidiary
```
Line 1: Entity A - Debit Intercompany Receivable $100,000
Line 2: Entity B - Credit Intercompany Payable $100,000
```

## Automatic Balancing

Light ensures intercompany entries balance:

**Rule:** Total debits to Entity A = Total credits to Entity B (and vice versa)

If you create:
```
Debit Entity A Asset 100
Credit Entity A Liability 50
Credit Entity B Receivable 50
```

This balances: Entity A net debit 50 = Entity B net credit 50

## Intercompany Accounts

Set up dedicated accounts for intercompany transactions:

**Asset side:**
- Intercompany Receivable (what you're owed by other entities)
- Intercompany Loan (loan to another entity)

**Liability side:**
- Intercompany Payable (what you owe to other entities)
- Intercompany Loan (borrowed from another entity)

These accounts:
- Post transaction on both sides of the pair
- Eliminate during consolidation (payable and receivable offset)
- Show intercompany transactions in GL

## Eliminating Intercompany Entries

During consolidation, eliminate intercompany amounts:

**Consolidation logic:**
- Entity A Intercompany Receivable $100,000
- Entity B Intercompany Payable $100,000
- Consolidation: Both eliminated (net = $0)
- Consolidated GL shows only external transactions

Elimination happens at group level; entity-level GL still shows intercompany accounts.

## Transfer Pricing

For tax purposes, entities may use different prices for intercompany transactions:

**Example:** Parent sells inventory to subsidiary
- Actual cost: $50
- Transfer price: $80 (to allocate profit)
- Subsidiary sells to customers for $100

GL entries:
- Parent: Debit AR $80, Credit Sales $80
- Subsidiary: Debit Inventory $80, Debit AP $80

At consolidation, intercompany profits may be deferred (under arm's-length pricing rules).

## Matching Intercompany Invoices

When invoices are created but not yet paid:

1. Entity A has AR
2. Entity B has AP
3. Both show unmatched status
4. When Entity B pays Entity A:
   - Payment clears both invoices
   - Both show cleared status

For direct intercompany journal entries, matching happens differently.

## Clearing Intercompany Entries

To clear a posted intercompany entry:

1. Create reversing payment or settlement entry
2. Both entities post the settlement
3. Intercompany payable and receivable reduce to zero
4. Both marked as cleared

Example: Subsidiary repays loan
```
Entity B posts payment:
  Debit: Intercompany Payable $50,000
  Credit: Cash $50,000
Entity A posts receipt:
  Debit: Cash $50,000
  Credit: Intercompany Receivable $50,000
```

Both Intercompany accounts now show reduced balance.

## Interest on Intercompany Loans

For intercompany loans, accrue interest:

1. Set up intercompany loan with terms
2. Specify interest rate (e.g., 5% annually)
3. Monthly, create accrual entry:
   - Borrowing entity: Debit Interest Expense, Credit Intercompany Payable
   - Lending entity: Debit Intercompany Receivable, Credit Interest Income
4. When paid, clear both payable and receivable

Interest should be at arm's-length rates (competitive market rates) for tax compliance.

## Multi-Entity Allocations

Allocate shared costs across entities:

1. Parent incurs $100,000 corporate overhead
2. Allocate to 3 entities: A=$50,000, B=$30,000, C=$20,000
3. Create intercompany journal entry:
   - Debit Entity A Allocated Expense $50,000
   - Debit Entity B Allocated Expense $30,000
   - Debit Entity C Allocated Expense $20,000
   - Credit Entity P Clearing Account $100,000

Each entity's GL shows its allocated share; consolidation eliminates clearing account.

## Intercompany Receivables Aging

View aging of intercompany amounts owed:

1. Go to **Reports > Intercompany Receivables Aging**
2. See how long amounts have been outstanding
3. Identify amounts overdue for collection

For intercompany amounts, there's generally no "aging" since these are internal matters, but you can track outstanding balances.

## Consolidation and Elimination

For consolidated statements:

1. Pull entity-level GL
2. Convert all entities to group currency (if multi-currency)
3. **Eliminate intercompany accounts:**
   - Entity A Intercompany Receivable offset by Entity B Intercompany Payable
   - Same for other intercompany accounts
4. Result: Consolidated GL shows only external amounts

Light supports elimination rules for consolidation.

## Regulatory and Tax Treatment

**GAAP/IFRS:**
- Intercompany transactions are eliminated in consolidated statements
- Entity-level statements still show intercompany amounts
- Intercompany profits may be deferred (upstream/downstream sales)

**Tax:**
- Intercompany transactions must be at arm's-length prices
- Documentation required for tax authorities
- Transfer pricing regulations apply to significant intercompany amounts

**Reporting:**
- Consolidated financial statements show only external transactions
- Entity-level statements show intercompany amounts
- Disclosures explain major intercompany balances and transactions

## Best Practices

- **Use consistent accounts** - Standardize intercompany account naming
- **Require approval** - Significant intercompany transactions should require approval
- **Document transfer pricing** - Keep records of how prices are set
- **Reconcile monthly** - Ensure payables match receivables
- **Clear promptly** - Don't let intercompany balances sit outstanding
- **Track interest** - Accrue interest on intercompany loans per terms
- **Plan consolidation** - Ensure elimination rules are set up for reporting
- **Monitor for compliance** - Ensure transfer prices comply with tax rules

## Related Articles

- [Multi-entity ledger management](/mnt/help-articles/articles/05-general-ledger/5-6-multi-entity-ledger.md)
- [Creating manual journal entries](/mnt/help-articles/articles/05-general-ledger/5-4-manual-journal-entries.md)
- [FX revaluations](/mnt/help-articles/articles/05-general-ledger/5-10-fx-revaluations.md)
