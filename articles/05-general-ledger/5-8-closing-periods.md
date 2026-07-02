# Closing Periods and Month-End Close

Accounting periods organize the GL by time. At period-end, you close the period to prevent new postings and prepare for financial reporting. This article explains period management and closing.

[Open in Light →](https://app.light.inc/accounting/accounting-periods)


## Accounting Periods

Periods organize the GL by time:

**Period types:**
- Monthly (most common)
- Quarterly
- Yearly

The period interval is set in your company's accounting period configuration.

**Period structure:**
- Start date and end date (periods are always month-aligned)
- Status: Open or Closed
- Closing tasks, tracked per company entity (multi-entity companies share the same periods, but each closing task is completed per entity)

## Period Status

Periods have two statuses:

**Open** - Documents can be posted to this period. Most periods are open while you're working in them.

**Closed** - No new documents can be posted. Used for completed periods (prior months). Prevents accidental postings to old periods.

Within an open period, you can also lock individual document types (AP, AR, journal entries) by completing the period's closing tasks—see **Locking Document Types** below.

## Opening Periods

Periods are generated in bulk for an accounting year rather than created one at a time:

1. Go to **Accounting → Accounting periods**
2. Generate periods by entering a **start date** and (optionally) an **end date**
3. The system creates the periods based on your configured interval (monthly, quarterly, or yearly)

Generated periods are created as Open and are ready to accept postings.

> Good to know: The date range must be month-aligned (start on the first day of a month and end on the last day of a month) and cannot exceed 12 months. Each new accounting year must start the day after the previous year ends.

## Posting Date and Period

When posting a document, the posting date must fall within an open period:

- **Posting date** = January 15, 2024
- **System checks** = Is January 2024 period open?
- **If open** = Post allowed; transaction posts to January period
- **If closed** = Post fails with error; must re-date or open the period

The posting date determines which period a transaction belongs to.

## Prior Period Postings

Sometimes you need to post to a prior (closed) period:

1. Go to the period and click **Reopen**
2. Period status changes to Open—any later periods are reopened as well
3. Post the transaction
4. Click **Close** again to re-close

Completed closing tasks are preserved when you reopen, so re-closing is quick. The system records who reopened the period and when.

> Important: Closing a period prevents accidental postings, but you can always reopen for adjustments.

## Month-End Close Checklist

A typical month-end close process:

1. **Ensure all transactions posted**
   - Check bank reconciliation is 100%
   - Verify all invoices posted
   - Confirm all payments processed
2. **Create accrual entries**
   - Accrue unpaid expenses
   - Accrue unbilled revenue
   - Post manual adjustments
3. **Post allocation entries**
   - Allocate shared costs
   - Spread period-specific expenses
4. **Review GL accounts**
   - Check for unusual balances
   - Verify all accounts reconcile
5. **Generate reports**
   - Trial balance
   - GL report
   - Income statement and balance sheet
6. **Review and approve**
   - Finance manager or controller reviews
   - Approves period as closed
7. **Close period**
   - Close period to prevent new postings
   - Archive reports and documentation

## Closing Procedures

To close a period:

1. Ensure all activity is complete
2. Go to **Accounting → Accounting periods**
3. Complete the period's closing tasks:
   - **Lock AP** - locks accounts payable documents
   - **Lock AR** - locks accounts receivable documents
   - **Lock JE** - locks journal entries
   - **FX revaluation** - requires the three lock tasks to be completed first
4. Find the period and click **Close**
5. System checks:
   - All closing tasks are completed
   - All previous periods are closed (periods must be closed in chronological order)
6. If checks pass, period status changes to Closed, and the system records who closed it and when

Closing tasks can be completed per company entity or for all entities at once. Only company admins and controllers can complete closing tasks and close or reopen periods.

Once closed, posting to this period requires reopening.

## Locking Document Types

While a period is still open, you can lock individual document types by completing the period's lock tasks:

1. Go to **Accounting → Accounting periods**
2. Open the period and complete a lock task (**Lock AP**, **Lock AR**, or **Lock JE**)
3. Once a lock task is completed, documents of that type can no longer be posted to the period, even though the period itself is still open

This lets you lock down parts of the ledger progressively during the close. Undoing a lock task removes the lock—and also reopens the FX revaluation task for that period and all later periods, since FX revaluation depends on locked balances.

## Closing Entries

At period-end, create closing entries:

**Month-end closing entries:**
- Accrual entries (accrue expenses)
- Deferral entries (spread costs)
- Allocation entries (distribute costs)
- Adjustment entries (correct errors)

**Year-end closing entries:**
- Transfer net income to retained earnings
- Close revenue and expense accounts to zero
- Reset income statement for new year

Closing entries are just regular journal entries, created and posted like any other entry.

## Prior Period Adjustments

If you discover an error in a closed period:

1. Don't reopen and modify (unless required for audit)
2. Instead, create a correcting entry in the current period
3. Entry explains it's a prior period correction
4. GL still shows complete history

This preserves the prior period's record while correcting the error.

> Good to know: For major errors, you may need to reopen, correct, and re-close. Document your action for audit.

## Reconciliation and Period Closing

Before closing, reconcile:

1. **Bank reconciliation** - 100% matched
2. **AP aging** - All invoices matched to payments or marked as outstanding
3. **AR aging** - All invoices matched to collections or aged appropriately
4. **GL accounts** - Each account reconciled to source documents

Unreconciled items don't prevent closing, but they should be resolved before closing.

## Reports at Period-End

Generate reports for the period:

1. **Trial Balance** - Check debits = credits
2. **GL Report** - Detail of all transactions
3. **Income Statement** - Revenue and expenses
4. **Balance Sheet** - Assets, liabilities, equity
5. **Cash Flow** - If applicable
6. **AR/AP aging** - Outstanding items

These reports are your proof the period is complete and accurate.

## Financial Statement Sign-Off

After generating reports, get sign-off:

1. Finance manager or controller reviews reports
2. Confirms accuracy and completeness
3. Signs off (electronically or with note)
4. Provides approval to close period
5. Audit trail records who signed off and when

Sign-off demonstrates management approval.

## Period-End Adjustments

Common adjustments posted at period-end:

**Revenue adjustments:**
- Recognize revenue earned but not yet invoiced
- Write off uncollectible accounts

**Expense adjustments:**
- Accrue unpaid expenses
- Depreciate assets
- Amortize intangible assets

**Other adjustments:**
- Inventory adjustments
- Currency adjustments
- Valuation adjustments

Create these as journal entries and post them in the period.

## Quarterly and Year-End Closing

For quarters and year-end:

1. **Close all months first** - Each month must be closed before closing the quarter
2. **Create special entries** - Quarterly or annual adjustments
3. **Generate comparative reports** - Compare to prior periods
4. **Review trends** - Analyze changes from prior periods
5. **Document assumptions** - Any estimates or judgments made
6. **Get approval** - CEO, CFO, or board approval if required

Quarterly and year-end closes are more rigorous than monthly closes.

## Reopening Old Periods

You can reopen any closed period:

1. Go to **Accounting → Accounting periods**
2. Find the period and click **Reopen**
3. Period status returns to Open—all periods after it (and their accounting years) are reopened as well, keeping the timeline consistent
4. Can now post and modify documents
5. Re-close when done (completed closing tasks are preserved, so re-closing is quick)

The system records when periods were reopened and by whom.

## Best Practices

- **Close promptly** - Don't wait weeks after month-end
- **Follow a checklist** - Use consistent month-end procedures
- **Document assumptions** - Note any judgments made in closing entries
- **Review GL** - Don't just accept reports; verify GL data
- **Get approval** - Have someone review and approve before closing
- **Archive reports** - Keep month-end reports for audit trail
- **Keep audited periods closed** - Reopen only when strictly necessary
- **Train staff** - Ensure team understands closing procedures

## Related Articles

- [Understanding Light's general ledger](/mnt/help-articles/articles/05-general-ledger/5-1-understanding-general-ledger.md)
- [Creating manual journal entries](/mnt/help-articles/articles/05-general-ledger/5-4-manual-journal-entries.md)
- [Year-end closing entries](/mnt/help-articles/articles/05-general-ledger/5-9-year-end-closing.md)
- [Deferred entries (accruals and deferrals)](/mnt/help-articles/articles/05-general-ledger/5-5-deferred-entries.md)
