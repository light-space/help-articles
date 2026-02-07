# Closing Periods and Month-End Close

Accounting periods organize the GL by time. At period-end, you close the period to prevent new postings and prepare for financial reporting. This article explains period management and closing.

[Open in Light →](https://app.light.inc/accounting-periods)


## Accounting Periods

Periods organize the GL by time:

**Period types:**
- Monthly (most common)
- Quarterly
- Annually
- Semi-annually
- Custom periods

**Period structure:**
- Start date and end date
- Status: Open, Closed, or Locked
- Company entity (multi-entity companies have separate periods per entity)

## Period Status

Periods have three statuses:

**Open** - Documents can be posted to this period. Most periods are open while you're working in them.

**Closed** - No new documents can be posted. Used for completed periods (prior months). Prevents accidental postings to old periods.

**Locked** - Completely read-only. No modifications allowed. Used for audited periods.

## Opening Periods

To open a new period:

1. Go to **Company Settings > Accounting Periods**
2. Click **Create Period**
3. Enter:
   - **Period name** (e.g., "January 2024")
   - **Start date**
   - **End date**
   - **Status** (Open)
   - **Company entity** (if multi-entity)
4. Click **Create**

The period is now ready to accept postings.

> Good to know: You typically open periods at the start of the month, before transactions begin posting.

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
2. Enter your authorization/reason
3. Period status changes to Open
4. Post the transaction
5. Click **Close** again to re-close

Reopening is tracked in audit log, showing who reopened and why.

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
2. Go to **Company Settings > Accounting Periods**
3. Find the period and click **Close**
4. System checks:
   - No documents are still in DRAFT
   - All postings are complete
   - Required closing entries are posted
5. If checks pass, period status changes to Closed
6. Audit log records who closed it and when

Once closed, posting to this period requires reopening.

## Locking Periods

After an external audit, lock the period:

1. Go to **Company Settings > Accounting Periods**
2. Find the period and click **Lock**
3. Period becomes completely read-only
4. No modifications or postings allowed
5. Can only be unlocked by administrator

Locked periods demonstrate to auditors that data hasn't been changed post-audit.

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

You can reopen any period:

1. Go to **Company Settings > Accounting Periods**
2. Find the period and click **Reopen**
3. Document your reason
4. Period status returns to Open
5. Can now post and modify documents
6. Re-close when done

Reopening is auditable—you can see in the audit trail when periods were reopened and by whom.

## Best Practices

- **Close promptly** - Don't wait weeks after month-end
- **Follow a checklist** - Use consistent month-end procedures
- **Document assumptions** - Note any judgments made in closing entries
- **Review GL** - Don't just accept reports; verify GL data
- **Get approval** - Have someone review and approve before closing
- **Archive reports** - Keep month-end reports for audit trail
- **Lock audited periods** - After audit, lock to prevent changes
- **Train staff** - Ensure team understands closing procedures

## Related Articles

- [Understanding Light's general ledger](/mnt/help-articles/articles/05-general-ledger/5-1-understanding-general-ledger.md)
- [Creating manual journal entries](/mnt/help-articles/articles/05-general-ledger/5-4-manual-journal-entries.md)
- [Year-end closing entries](/mnt/help-articles/articles/05-general-ledger/5-9-year-end-closing.md)
- [Deferred entries (accruals and deferrals)](/mnt/help-articles/articles/05-general-ledger/5-5-deferred-entries.md)
