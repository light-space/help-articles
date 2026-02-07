# Deferred Entries (Accruals and Deferrals)

Deferred entries allow you to spread costs over multiple periods using amortization schedules. This article explains how to set up and use accruals and deferrals.

[Open in Light →](https://app.light.inc/journal-entries)


## Understanding Deferrals

Deferrals (also called accruals) spread a transaction across multiple accounting periods:

**Accrual Example** - You owe for services received:
- You received professional services this month
- Invoice arrives next month
- Create an accrual entry this month to match revenue to expense
- Reverse or clear the accrual when invoice arrives next month

**Deferral Example** - You prepay for future services:
- You prepay annual insurance ($12,000)
- Expense should spread over 12 months ($1,000/month)
- Create deferral entries to post $1,000 each month

Both defer the GL impact across periods for proper matching.

## Amortization Schedules

Deferrals use **amortization schedules** (also called amortization templates):

**Components:**
- **Name** - e.g., "12-Month Lease"
- **Period type** - Monthly, Quarterly, Annually
- **Number of periods** - How many periods to spread over
- **GL accounts** - Which accounts to debit/credit each period

When an invoice uses an amortization schedule, Light generates entries for each period automatically.

## Creating an Amortization Schedule

To create a reusable amortization template:

1. Go to **General Ledger > Amortization Schedules**
2. Click **Create Schedule**
3. Enter details:
   - **Name** - Descriptive name
   - **Company Entity** - Which entity uses this
   - **Period Type** - Monthly, Quarterly, Annually
   - **Number of Periods** - How many periods
   - **GL Accounts**:
     - **Expense Account** - Debit side
     - **Deferral/Accrual Account** - Credit side (balance sheet account)
4. Click **Save**

The schedule can now be used when creating invoices or manual entries.

## Using Deferrals in Invoices

When creating an AP or AR invoice, enable deferrals:

1. In the invoice, click **Amortize**
2. Select the **Amortization Schedule**
3. Specify the **Start Date** and **End Date**
4. System calculates monthly amounts:
   - First period: From invoice date to end of month
   - Full periods: Same amount each month
   - Last period: From start of month to end date
5. Review the schedule and click **Confirm**

The invoice amount is spread across the selected periods.

## Deferred Entry Generation

When posting an amortized invoice:

1. Initial entry posts to the deferral account (balance sheet)
2. Monthly journal entries automatically generate
3. Each month, system posts:
   - Debit: Expense account
   - Credit: Deferral account
4. Over the period, deferral account balance reaches zero
5. Total expense matches the original invoice

Entries are created automatically on schedule—you don't manually create each month's entry.

## Accrual Examples

**Monthly Rent Accrual:**
- Schedule: 1 month, repeating monthly
- Creates entry each month: Debit Rent Expense, Credit Accrued Rent
- When paid, clear the accrual entry

**Annual Software License:**
- Schedule: 12 months
- Creates 12 monthly entries: Debit Software Expense, Credit Prepaid Software
- After 12 months, balance of prepaid account is zero

**Bonus Accrual:**
- Schedule: 12 months
- Accrues bonus evenly over the year
- Posts total to Accrued Bonus liability by year-end

## Managing Deferred Entries

To view and manage deferred entries:

1. Go to **General Ledger > Deferred Entries**
2. See all active deferral schedules with:
   - Parent document (the invoice)
   - Schedule name and period
   - Remaining balance
   - Generated entries to date
   - Remaining periods
3. Click to edit or view details

From here you can:
- View generated entries for a schedule
- Adjust remaining balance if needed
- Pause or complete a schedule early

## Partial Deferrals

If an invoice is only partially deferred:

1. Invoice total: $5,000
2. Deferred portion: $3,000 (using amortization)
3. Immediate portion: $2,000 (not deferred)
4. Posts as:
   - Immediate: Debit Expense 2,000, Credit AP 2,000
   - Deferred: Debit Deferral Account 3,000, Credit AP 3,000

The AP account shows the full $5,000 owed, split across immediate and deferred.

## Period-Specific Deferrals

Sometimes deferrals align to fiscal periods rather than calendar dates:

**Example:** Prepaid insurance for fiscal year (Jan 1 - Dec 31)
- Schedule: Quarterly (4 periods)
- Start: Jan 1, End: Dec 31
- System generates 4 entries for each quarter

Specify your fiscal period dates when setting up the schedule.

## Early Completion

If a deferral finishes early:

1. Go to **Deferred Entries > [Entry]**
2. Click **Complete Early**
3. Remaining periods are skipped
4. Final entry posts any remaining balance
5. Schedule marked as complete

Use this if you no longer need to defer (e.g., contract cancelled).

## Adjustments to Deferrals

If you need to adjust a deferred amount:

1. Go to **Deferred Entries > [Entry]**
2. Click **Adjust**
3. Enter new amount or new schedule
4. System recalculates remaining entries
5. Future entries adjust to match new total

Adjustments maintain the deferral logic—you just change the total or timing.

## Clearing Deferred Entries

When the underlying transaction occurs, clear the deferral:

1. Original deferral entry posts to balance sheet
2. When paid/invoiced, a reversing entry clears it
3. Manual match or automatic clearing links them
4. Both show as cleared/matched

Example: Accrued rent entry cleared when rent payment posts.

## Monitoring Deferrals

Track deferred balances:

1. Go to **Reports > Balance Sheet**
2. View deferral accounts (Prepaid Expenses, Accrued Expenses)
3. See current balance of all deferrals
4. Compare to prior period to track progress

Deferral accounts should decline over time as they're amortized.

## Multi-Currency Deferrals

For foreign currency invoices:

1. Invoice posted in EUR with amount 5,000
2. Amortization Schedule specifies monthly periods
3. Light converts using posting date rate
4. Monthly entries use period-specific rates
5. FX adjustments calculated for each period

This ensures proper matching in local currency.

## Common Deferral Scenarios

**Rent (Monthly Deferral):**
- 1 month schedule, repeating
- Accrues or defers rent expense each month

**Insurance (Annual Deferral):**
- 12 month schedule
- Prepaid insurance amortized monthly

**Maintenance (Quarterly Deferral):**
- 4 quarter schedule
- Quarterly maintenance contract spread evenly

**Salaries (Weekly Deferral):**
- 52 week schedule (or 26 bi-weekly)
- Salaries accrued as they're earned

## Best Practices

- **Use schedules consistently** - Save reusable schedules to ensure consistency
- **Clear when paid** - Match deferral entries to actual payments
- **Monitor balances** - Watch deferred account balances to catch errors
- **Document purpose** - Use clear names and descriptions
- **Review monthly** - Ensure deferrals are posting correctly
- **Adjust early if needed** - Don't let incorrect deferrals run to completion

## Related Articles

- [Creating manual journal entries](/mnt/help-articles/articles/05-general-ledger/5-4-manual-journal-entries.md)
- [Accounting document types and lifecycle](/mnt/help-articles/articles/05-general-ledger/5-2-document-types-lifecycle.md)
- [Closing periods and month-end close](/mnt/help-articles/articles/05-general-ledger/5-8-closing-periods.md)
