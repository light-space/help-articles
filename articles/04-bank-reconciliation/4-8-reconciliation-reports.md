# Reconciliation History and Reports

Light maintains detailed records of reconciliation activities and generates reports for analysis, compliance, and audit purposes. This article covers accessing and using reconciliation reports.

[Open in Light →](https://app.light.inc/ledger-reports)

## Reconciliation History

View the complete history of reconciliation activities for each bank account:

1. Go to **Settings > Bank accounts**
2. Find an account and click **View History**
3. See all past reconciliation runs:
   - Date and time of reconciliation
   - Who ran it (manual) or "Automatic"
   - Number of transactions processed
   - Number of matches found
   - Success or failure status

This history provides an audit trail of when and how each account was reconciled.

## Reconciliation Status Dashboard

View the current reconciliation status across all accounts:

1. Go to **Accounting > Bank reconciliation** to view reconciliation dashboard
2. See each account with:
   - **Total transactions** - Bank transactions in the period
   - **Matched** - Successfully matched to GL entries
   - **Unmatched** - Transactions without matches
   - **Reconciliation %** - Matched / Total percentage
   - **Last reconciliation** - When it was last done
   - **Status** - Complete, In Progress, or Failed

The dashboard gives you a quick overview of reconciliation health.

> Tip: Accounts with less than 95% reconciliation need investigation.

## Unmatched Items Report

View details of all unmatched transactions and GL entries:

1. Go to **Accounting → Bank reconciliation → Reports > Unmatched Items**
2. Filter by:
   - **Account** - Specific bank account
   - **Date range** - Period to report on
   - **Type** - Bank transactions, GL entries, or both
   - **Age** - How long unmatched
3. View the list showing:
   - Transaction/entry date
   - Amount
   - Description
   - Days unmatched
   - Status (investigate, exclude, or clear)

This report helps identify discrepancies and bottlenecks.

## Outstanding Items Report

View items expected to reconcile in the future:

1. Go to **Accounting → Bank reconciliation → Reports > Outstanding Items**
2. See:
   - **Outstanding checks** - Checks written but not cashed
   - **Deposits in transit** - Deposits received but not cleared
   - **Pending bank transactions** - Transactions not yet finalized by the bank
   - **Expected GL entries** - Entries that should post but haven't yet

This helps you forecast reconciliation—you expect these items to disappear.

## Aged Analysis Report

Understand how long items have been unmatched:

1. Go to **Accounting → Bank reconciliation → Reports > Aged Analysis**
2. View buckets:
   - **0-7 days** - Recent, likely timing differences
   - **7-30 days** - Should be investigated
   - **30-60 days** - Likely errors, needs action
   - **60+ days** - Significant issue, escalate

Items older than 60 days typically indicate data errors or missing GL entries.

## Reconciliation Summary Report

High-level reconciliation metrics:

1. Go to **Accounting → Bank reconciliation → Reports > Summary**
2. See:
   - **Total bank transactions** by account
   - **Total matches** and **match rate %**
   - **Total outstanding items** and dollar amount
   - **Total FX adjustments** (for multi-currency accounts)
   - **Reconciliation variance** (bank balance vs. GL balance)

Use this for monthly reporting to management.

## Cleared Transactions Report

View all transactions that have been reconciled:

1. Go to **Accounting → Bank reconciliation → Reports > Cleared Transactions**
2. Filter by:
   - **Account** - Specific account
   - **Date range** - Period to report on
   - **Cleared date** - When the match occurred
3. See for each cleared pair:
   - Bank transaction details
   - Matched GL entry
   - Matching rule used
   - Date matched
   - User who cleared it (if manual)

This report is useful for:
- Audit trail (who matched what)
- Debugging matching (which rule was used)
- Historical analysis (trends in matching patterns)

## FX Impact Report

For multi-currency accounts, see FX gains and losses:

1. Go to **Accounting → Bank reconciliation → Reports > FX Impact**
2. View:
   - **By currency** - FX gain/loss per currency pair
   - **By transaction** - FX gain/loss per individual transaction
   - **Summary** - Total FX impact for the period
   - **Trend** - FX impact over time

This helps understand how currency volatility affected results.

## Reconciliation Rule Statistics

Track the effectiveness of your automation rules:

1. Go to **Accounting → Bank reconciliation → Reports > Rule Statistics**
2. View for each rule:
   - **Times applied** - How many transactions matched this rule
   - **Match accuracy** - Were the matches correct
   - **Success rate** - % of transactions correctly matched
   - **Most recent use** - Last time the rule applied

Use this to:
- Identify underutilized or ineffective rules
- Find rules that frequently produce incorrect matches
- Optimize rule order and conditions

## Exception Report

View transactions that required manual intervention:

1. Go to **Accounting → Bank reconciliation → Reports > Exceptions**
2. See:
   - Transactions auto-matched but then manually cleared (different match)
   - Transactions marked as excluded
   - Transactions with warnings or notes
   - Transactions requiring investigation

This helps you understand where automation isn't working.

## Variance Report

Identify differences between bank balance and GL balance:

1. Go to **Accounting → Bank reconciliation → Reports > Variance**
2. View:
   - **Bank balance** - Per bank statement
   - **GL balance** - Per general ledger
   - **Variance amount** - Difference
   - **Outstanding items** - Items that explain the variance
   - **Remaining variance** - Unexplained difference

This is the most important report—it should show zero or only outstanding items.

## Generating Custom Reports

Create custom reports for specific analysis:

1. Go to **Accounting → Bank reconciliation → Reports > Custom**
2. Click **Create Report**
3. Select data to include:
   - Account(s)
   - Date range
   - Transaction types (debits, credits, etc.)
   - Matching status
   - Currencies
   - Custom filters
4. Choose output format (PDF, Excel, CSV)
5. Click **Generate**

Save custom report templates for regular use (e.g., monthly reports).

## Exporting Data

Export reconciliation data for external analysis:

1. Open any reconciliation report
2. Click **Export**
3. Choose format:
   - **Excel** - Full spreadsheet with multiple sheets
   - **CSV** - Comma-separated values for import elsewhere
   - **PDF** - Formatted report for printing/sharing
4. Specify rows to export:
   - All results
   - Currently viewed/filtered results
   - Selected rows only

## Archiving Reconciliation Records

Keep historical reconciliation records:

1. At period-end, export all reconciliation reports
2. Store exports in secure location (cloud storage, archive)
3. Keep for audit and compliance (typically 7 years minimum)

Light maintains reconciliation data indefinitely, but exporting provides independent backup.

## Reconciliation Sign-Off

Formally close out reconciliation:

1. Once all items are matched or explained:
   - Go to **Accounting → Bank reconciliation → [Account]**
   - Click **Sign Off**
   - Add notes explaining any exceptions
2. System records who signed off and when
3. Account is marked as "Reconciled" for the period

Sign-off creates an audit trail showing management approved the reconciliation.

## Monthly Reconciliation Checklist

Use reports to complete monthly reconciliation:

- [ ] Run automated reconciliation (see dashboard)
- [ ] Review unmatched items (investigate and clear)
- [ ] Check aged analysis (follow up on items over 30 days)
- [ ] Verify FX adjustments have been posted (if multi-currency)
- [ ] Generate variance report (confirm zero variance or only outstanding)
- [ ] Export all reports for archive
- [ ] Sign off on reconciliation
- [ ] Report reconciliation status to management

## Best Practices

- **Review reports weekly** - Not just monthly
- **Archive exports** - Keep independent backup outside Light
- **Monitor metrics** - Track reconciliation % trends
- **Investigate exceptions** - Don't just accept automated matches
- **Document conclusions** - Keep notes on why items were excluded
- **Share with auditors** - Provide reports during audit
- **Use for improvement** - Analyze rule statistics to improve automation
- **Sign off formally** - Create audit trail of management approval

## Related Articles

- [Automated bank reconciliation](/mnt/help-articles/articles/04-bank-reconciliation/4-4-automated-reconciliation.md)
- [Reconciliation automation rules](/mnt/help-articles/articles/04-bank-reconciliation/4-5-automation-rules.md)
- [Resolving discrepancies](/mnt/help-articles/articles/04-bank-reconciliation/4-6-resolving-discrepancies.md)
