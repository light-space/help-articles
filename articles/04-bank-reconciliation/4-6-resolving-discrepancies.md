# Resolving Discrepancies

Bank reconciliation discrepancies occur when bank transactions don't match accounting entries. This article explains how to investigate and resolve common discrepancies.

[Open in Light →](https://app.light.inc/bank-reconciliation)

## Types of Discrepancies

**Unmatched Bank Transactions** - Transactions on the bank statement with no corresponding GL entry

**Unmatched GL Entries** - Accounting entries with no corresponding bank transaction

**Amount Mismatches** - Same transaction appears in both but with different amounts

**Timing Differences** - Same transaction but on different dates (most common and easiest to fix)

**Duplicate Transactions** - Same transaction appears twice in bank feed or GL

## Timing Differences

The most common discrepancy is timing—when the bank posts a transaction before or after your GL:

**Scenario 1: Bank posts first**
- You initiated a payment (wire, ACH) several days ago
- Bank has already deducted the amount
- Your GL entry posts later (when you send the instruction, not when the bank processes it)
- **Fix:** Wait for GL entry to post, then reconcile

**Scenario 2: GL posts first**
- You created and posted an invoice to a customer
- Customer hasn't paid yet
- **Fix:** Wait for payment, then reconcile when the deposit appears

Timing differences resolve naturally as transactions flow through the system. They don't require manual intervention.

## Outstanding Items

Items that legitimately won't reconcile on a given date:

**Outstanding Checks** - Checks you've written but recipients haven't cashed yet

**Deposits in Transit** - Customer payments received but not yet cleared by the bank

**Pending Transactions** - Bank shows as "pending" and not yet posted

These items will reconcile eventually when the bank processes them. Include them in your reconciliation reserve calculation.

## Data Entry Errors

Sometimes discrepancies result from mistakes:

**Wrong Amount** - GL entry amount doesn't match bank transaction

**Wrong Account** - Entry was posted to the wrong GL account

**Wrong Date** - Entry dated differently than transaction date

To fix:

1. Identify the incorrect entry
2. Either correct it or delete and re-create correctly
3. Re-attempt reconciliation

> Important: Only correct errors during the current period. For prior periods, post correcting journal entries instead of modifying posted entries.

## Missing GL Entries

A bank transaction exists but has no corresponding GL entry:

**Example:** Bank fee charged by the bank; no GL entry created

**To fix:**
1. Go to the unmatched bank transaction
2. Click **Create GL Entry**
3. Enter the transaction details:
   - **Account:** Which GL account (usually Expense for fees)
   - **Amount:** The transaction amount
   - **Description:** What the transaction was for
   - **Date:** Match the bank transaction date
4. Click **Post**
5. Reconciliation engine automatically matches the new entry to the transaction

This is common for:
- Bank fees and interest
- Automatic transfers between accounts
- Government-mandated withholding
- Third-party collections

## Missing Bank Transactions

A GL entry exists but doesn't appear on the bank statement:

**Example:** You initiated a payment that won't settle for several days; GL entry is posted but transaction isn't on the bank yet.

**To fix:**
1. Identify when the transaction should appear (settlement date)
2. Wait for the bank to process it
3. When it appears, reconcile normally

If a transaction doesn't appear after expected settlement time:
1. Check the GL entry for accuracy
2. Contact your bank to verify they have the instruction
3. If the payment was lost, initiate a stop-payment and re-issue

## Duplicate Transactions

If the same transaction appears twice:

**In bank feed:**
- The bank or feed provider may have imported it twice
- Check the transaction ID—if identical, it's a true duplicate
- Mark one as "Excluded" in reconciliation

**In GL:**
- A user may have manually entered a transaction that already came from a feed
- Compare dates and amounts
- Delete the duplicate GL entry and keep the original
- Reconcile the transaction to the feed

**Across systems:**
- Same transaction recorded in both bank and GL
- Mark as reconciled (correctly matched)
- If truly a duplicate, delete one side and reconcile

## Amount Mismatches

When amounts differ, investigate the cause:

**Rounding Difference** (e.g., $100.005 becomes $100.01)
- Acceptable; reconcile with notation of the rounding difference

**Bank Fees** (e.g., Invoice for $1,000 but you received $999.50)
- Bank deducted $0.50 fee
- Create a GL entry for the fee and link the bank transaction to both the invoice and fee

**FX Conversion** (multi-currency)
- Amount in original currency differs when converted
- This is expected; use FX adjustment GL entries

**Calculation Error**
- Someone miscalculated; correct the GL entry
- Re-attempt reconciliation

## Investigating Aged Items

Items unmatched for more than 30 days need investigation:

1. Go to **Accounting → Bank reconciliation → Aged Unmatched**
2. View items by age (0-30 days, 30-60, 60+ days)
3. Click an item to see details
4. Investigate:
   - Is this a timing difference that will resolve?
   - Is there a data error that needs fixing?
   - Should this be excluded from reconciliation?
5. Take appropriate action

The longer an item remains unmatched, the more likely it's an error.

## Month-End Reconciliation Adjustments

If you can't fully reconcile by month-end:

1. Identify all unmatched items
2. For items you're confident will reconcile:
   - Create a **reserve account** entry
   - Debit/credit "Unreconciled Items" temporarily
   - When items reconcile next period, reverse the entry
3. For items you believe are errors:
   - Create journal entry to correct the discrepancy
   - Document the correction for audit purposes
4. Complete month-end with a note explaining adjustments

This approach allows you to close the period while tracking discrepancies.

## Reconciliation Discrepancy Report

Generate a report of all unmatched items:

1. Go to **Accounting → Bank reconciliation → Reports**
2. Click **Discrepancy Report**
3. View:
   - Unmatched bank transactions
   - Unmatched GL entries
   - Items by age
   - Total unreconciled amount
4. Export to CSV for investigation

Use this report in your reconciliation documentation.

## Multi-Account Reconciliation

When reconciling multiple accounts, check:

- **Interdepartmental transfers** - Transfers between your own accounts should appear as balanced pairs
- **Netting** - Some transactions may net across accounts
- **Consolidated view** - Total of all accounts should match consolidated GL

If one account shows a credit and another doesn't show the debit, investigate the inter-account transfer.

## Escalation Process

For discrepancies you can't resolve:

1. Document what you've found
2. Ask for help from your finance manager or controller
3. They may contact the bank to investigate
4. The bank can provide detailed transaction information
5. Work with them to resolve the discrepancy

Never ignore unmatched items; eventually they'll cause problems.

## Preventing Discrepancies

- **Match frequently** - Daily or weekly prevents large accumulations
- **Post accurately** - Ensure GL entries match supporting documents exactly
- **Monitor feeds** - Check that bank feeds are importing correctly
- **Use references** - Include invoice/check numbers in bank transactions when possible
- **Document manually** - For manual entries, note the source document
- **Review monthly** - Catch discrepancies early before they cascade

## Related Articles

- [Automated bank reconciliation](/mnt/help-articles/articles/04-bank-reconciliation/4-4-automated-reconciliation.md)
- [Reconciliation automation rules](/mnt/help-articles/articles/04-bank-reconciliation/4-5-automation-rules.md)
- [Multi-currency reconciliation](/mnt/help-articles/articles/04-bank-reconciliation/4-7-multi-currency-reconciliation.md)
- [Reconciliation history and reports](/mnt/help-articles/articles/04-bank-reconciliation/4-8-reconciliation-reports.md)
