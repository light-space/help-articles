# Reconciliation History and Reports

Light maintains detailed records of reconciliation activities that you can review and export for analysis, compliance, and audit purposes. This article covers accessing and using reconciliation data.

[Open in Light →](https://app.light.inc/bank-reconciliation)

## Reconciliation History

View past reconciliation activity for each bank account:

1. Go to **Accounting → Bank reconciliation** and click a bank account on the **Accounts** tab
2. Open the **Matched** tab to see all transactions that have already been reconciled
3. Open the **Excluded** tab to see transactions that were intentionally excluded from reconciliation

Each **Auto reconcile** run is tracked as a job with a status (Scheduled, In progress, Completed, or Failed), whether it was triggered manually or by a CSV import or bank feed import, and when it started and finished.

This history provides an audit trail of when and how each account was reconciled.

## Reconciliation Status Overview

View the current reconciliation status across all accounts:

1. Go to **Accounting → Bank reconciliation** to view the **Accounts** tab
2. See each account with:
   - **Entity** - The company entity the account belongs to
   - **Account** - The bank account
   - **Currency** - The account currency
   - **Unmatched transactions** - Count of transactions without matches
   - **Ledger balance** - Balance per the general ledger
   - **Bank balance** - Balance per the bank (anchored to the end-of-day closing balance you enter from your bank statement, with later transactions summed on top)
   - **Balance difference** - The difference between the ledger balance and the bank balance

The Accounts tab gives you a quick overview of reconciliation health. The **Balance difference** is the key figure—it should be zero or explained only by outstanding items.

## Reviewing Unmatched Items

View details of all unmatched bank transactions and ledger entries:

1. Go to **Accounting → Bank reconciliation** and select the account
2. Open the **Unmatched** tab
3. Use the filter bar to narrow by date and apply additional filters, or use the search bar to find specific transactions
4. Review unmatched bank transactions in the left panel and unmatched ledger entries in the right panel

This view helps identify discrepancies and bottlenecks. See [Resolving discrepancies](/mnt/help-articles/articles/04-bank-reconciliation/4-6-resolving-discrepancies.md) for how to investigate and clear them.

## The All Transactions View

To review every bank transaction for an account with its reconciliation status:

1. Go to **Accounting → Bank reconciliation** and select the account
2. Click the **All transactions** tab
3. You'll see every transaction with its status:
   - **Matched** - Transaction reconciled to a GL entry
   - **Unmatched** - Transaction has no corresponding GL entry
   - **Excluded** - Transaction marked as excluded from reconciliation
4. Use the **Period** filter to narrow the date range
5. Use the search bar to find a specific transaction by number or business partner name
6. Review the **Opening balance** (shown at top) and **Closing balance** (shown at bottom) to verify they match your bank statement for that period

This view is useful for audit trails and historical analysis of reconciliation activity.

## Reconciliation Rule Statistics

Track how often your automation rules are used:

1. Go to **Accounting → Bank reconciliation** and open the **Rules** tab
2. View for each rule:
   - **Runs** - How many times the rule has been applied
   - **Last run** - The most recent time the rule was applied

Use this to identify underutilized rules and optimize rule order and conditions.

## Exporting Data

Export reconciliation transaction data for external analysis:

1. Go to **Accounting → Bank reconciliation** and select the account
2. Open the **All transactions** tab (or use the export icon on the transaction panels)
3. Click **Export to CSV**

The export downloads a CSV file (`bank-reconciliation-transactions.csv`) containing the transaction number, transaction date, business partner name, account, amount, currency, status, and created-at timestamp for each transaction. Filters and search terms you have applied are reflected in the export.

## General Financial Reports

Reconciliation-specific reports are not part of the **Reports** section. For general financial reporting (balance sheet, income statement, trial balance, general ledger, and more), go to **Reports** in the sidebar ([Open Reports →](https://app.light.inc/ledger-reports)).

## Archiving Reconciliation Records

Keep historical reconciliation records:

1. At period-end, export reconciliation transaction data to CSV
2. Store exports in a secure location (cloud storage, archive)
3. Keep for audit and compliance (typically 7 years minimum)

Light maintains reconciliation data indefinitely, but exporting provides an independent backup.

## Monthly Reconciliation Checklist

Use these views to complete monthly reconciliation:

- [ ] Run **Auto reconcile** for each account
- [ ] Review unmatched items (investigate and clear)
- [ ] Verify the **Balance difference** on the Accounts tab is zero or explained by outstanding items
- [ ] Verify FX adjustments have been posted (if multi-currency)
- [ ] Export transaction data for archive
- [ ] Report reconciliation status to management

## Best Practices

- **Review regularly** - Check the Accounts tab weekly, not just monthly
- **Archive exports** - Keep independent backup outside Light
- **Monitor unmatched counts** - Track unmatched transaction trends per account
- **Investigate exceptions** - Don't just accept automated matches
- **Document conclusions** - Keep notes on why items were excluded
- **Share with auditors** - Provide CSV exports during audit
- **Use for improvement** - Review rule run counts to improve automation

## Related Articles

- [Automated bank reconciliation](/mnt/help-articles/articles/04-bank-reconciliation/4-4-automated-reconciliation.md)
- [Reconciliation automation rules](/mnt/help-articles/articles/04-bank-reconciliation/4-5-automation-rules.md)
- [Resolving discrepancies](/mnt/help-articles/articles/04-bank-reconciliation/4-6-resolving-discrepancies.md)
