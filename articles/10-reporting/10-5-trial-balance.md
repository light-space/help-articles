# Trial Balance

The Trial Balance is a worksheet listing all general ledger accounts and their debit or credit balances. It's a fundamental internal control used to verify that double-entry bookkeeping is accurate: total debits must equal total credits. The trial balance is the source for preparing the balance sheet, P&L, and cash flow statement.

[Open in Light →](https://app.light.inc/ledger-reports)

## Trial balance structure

The trial balance lists:

- **Account number and name**: Each GL account
- **Debit balance**: If the account has a debit balance (assets, expenses, dividends)
- **Credit balance**: If the account has a credit balance (liabilities, equity, revenue)

Total debits must equal total credits. If they don't, errors in posting exist that must be corrected.

Example structure:

| Account | Debit | Credit |
|---------|-------|--------|
| Cash | 50,000 | |
| Accounts Receivable | 25,000 | |
| Accounts Payable | | 10,000 |
| Revenue | | 100,000 |
| **Totals** | **75,000** | **110,000** |

In this example, debits (75,000) don't equal credits (110,000), indicating errors requiring investigation.

> Good to know: A balanced trial balance doesn't guarantee accuracy. Errors like duplicate postings or posting to the wrong account won't be caught.

## Accessing the trial balance in Light

Generate your trial balance:

1. Navigate to **Planning & Reports → Reports**
2. Open the **Trial Balance** report
3. Select the as-of date
4. Select entities to include (single entity or consolidated)
5. Select currency: **Entity Crcy** (local) or **Group Crcy** (group)

Light displays the trial balance with all GL accounts and balances. The Trial Balance is a built-in system report — it cannot be edited or deleted.

## Accounts with zero balances

By default, Light hides accounts with zero balances to reduce clutter. Toggle **Show Zero Balances** to see all accounts including those with no activity.

This is useful when:
- Confirming accounts are correctly configured
- Identifying departments with no activity
- Ensuring all required accounts are in the chart of accounts

## Finding trial balance errors

If your trial balance doesn't balance:

1. Check that all transactions have been posted (some may be pending)
2. Review recent transactions for duplicates or reversals
3. Check for unmatched inter-company transactions
4. Verify that all month-end accruals have been recorded
5. Look for unmatched bank reconciliations

## Trial balance by subsidiary

For multi-entity organizations:

1. Open the trial balance
2. Select the entities to include, or switch to **Consolidated** view
3. In consolidated view, Light shows a column per entity plus **Subtotal**, **Elimination**, and **Total** columns
4. Each subsidiary's trial balance should balance

This helps identify which entity (if any) has posting errors.

## Trial balance by currency

View trial balance in different currencies:

1. Navigate to **Planning & Reports → Reports**
2. Select **Currency**: **Entity Crcy** (local) or **Group Crcy** (group)
3. Light displays accounts in your selected currency

> Note: Entity currency cannot be used when the selected entities have different local currencies.

This is useful for:
- Verifying currency conversion accuracy
- Checking consolidated trial balance in group currency
- Analyzing foreign subsidiary results before consolidation

## Permanent accounts vs. temporary accounts

Trial balances distinguish between two types of accounts:

**Permanent accounts** (balance sheet accounts):
- Assets, liabilities, equity
- Balances carry forward to next period
- Appear on the balance sheet

**Temporary accounts** (income statement accounts):
- Revenue, expenses
- Balances reset at year-end
- Close to retained earnings

The trial balance includes both. At year-end, temporary accounts are closed to zero, and permanent accounts' balances carry forward to the next year.

## Preliminary vs. post-closing trial balance

Two versions exist:

**Preliminary trial balance** (unadjusted):
- Before month-end or year-end adjustments
- Includes both permanent and temporary accounts
- Used to identify needed adjustments

**Post-closing trial balance** (after closing):
- After temporary accounts are closed
- Includes only permanent (balance sheet) accounts
- Starting point for next period

## Trial balance and account reconciliation

Use the trial balance to plan account reconciliations:

1. Generate trial balance
2. For each material account, reconcile:
   - Trial balance amount
   - Supporting subledger (AP aging, AR aging, fixed assets)
   - Bank statements (for cash accounts)
3. Investigate reconciling items
4. Prepare reconciliation schedules

This ensures your trial balance is supported by detailed reconciliations.

## Trial balance and financial statement preparation

The trial balance is the foundation for preparing financial statements:

1. Generate trial balance
2. Classify accounts as balance sheet or P&L
3. Prepare balance sheet using permanent account balances
4. Prepare P&L using temporary account balances
5. Verify balance sheet and P&L totals

Light does this automatically, but understanding the connection is important.

## Trial balance trend analysis

Compare trial balances across periods:

1. Navigate to **Planning & Reports → Reports**
2. Add a **Comparison** period: 1, 3, 6, 9, or 12 months back, or 1, 2, or 3 years back
3. Light displays account balances side-by-side
4. Shows period-over-period changes
5. Highlights accounts with significant changes

Investigate large movements to understand business activity and identify errors.

## Account-level detail from trial balance

Drill into any trial balance account:

1. Click any account on the trial balance
2. Light shows all transactions posted to that account
3. Filter by posting date, currency, amount, document type, or entity
4. Export transaction detail as CSV

This enables rapid error-finding and substantiation.

## Journal entry details

Verify that all trial balance accounts have corresponding journal entries:

1. Generate trial balance
2. For each account, review supporting journal entries
3. Verify amounts, dates, and descriptions match expected transactions
4. Identify if any entries are missing or duplicated

Light maintains a complete journal entry log, which feeds into the trial balance.

## Month-end and year-end procedures

At month and year-end, complete these procedures:

1. **Post all transactions**: Ensure no pending items exist
2. **Bank reconciliation**: Reconcile all bank accounts
3. **Account reconciliation**: Reconcile subledgers to GL
4. **Accruals and reversals**: Record month-end accruals, reverse prior-month accruals
5. **Generate trial balance**: Verify debits equal credits
6. **Prepare financial statements**: Balance sheet, P&L, cash flow
7. **Review significant items**: Document significant or unusual transactions
8. **Sign off**: Document that financial close is complete

Light supports all these procedures with built-in workflows.

## Trial balance export and analysis

Export trial balance for external auditors or further analysis:

1. Open the trial balance
2. Click the export button
3. Light downloads a CSV file with all accounts and balances

You can open the CSV in Excel or Google Sheets for further analysis.

External auditors typically request the trial balance to start their audit procedures.

> Tip: Document your trial balance timing and reconciliation procedures in a month-end close checklist. This demonstrates strong financial controls.

## Related articles

- [Reporting overview](10-1-reporting-overview.md)
- [Balance sheet](10-2-balance-sheet.md)
- [Profit and loss](10-3-profit-loss.md)
- [Custom reports and filters](10-9-custom-reports.md)
- [Audit-ready record keeping](../09-revenue-compliance/9-9-audit-ready-records.md)
