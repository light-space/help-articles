# Year-End Closing Entries

Year-end close is the annual accounting process that closes all revenue and expense accounts and transfers net income to retained earnings. This article explains the year-end closing process.

[Open in Light →](https://app.light.inc/accounting-periods)


## What is Year-End Closing?

Year-end closing consists of journal entries that:

1. **Close revenue accounts** - Transfer year's revenue to closing entry
2. **Close expense accounts** - Transfer year's expenses to closing entry
3. **Close other temporary accounts** - Gains, losses, transfers
4. **Transfer net income** - Move year's profit to retained earnings
5. **Reset for new year** - Revenue and expenses now zero for new year

After closing, your balance sheet shows the year's earnings in retained earnings, and income statement is zero and ready for the new year.

## Why Close the Books?

Closing entries serve several purposes:

**Prepare new year** - Reset revenue/expense accounts to zero to track next year's activity separately

**Finalize results** - Lock in the year's performance before reports are finalized

**Transfer earnings** - Move net income to retained earnings (equity) for balance sheet

**Compliance** - Financial statement and tax preparation require closing entries

**Clarity** - Separate each year's results clearly

## Closing Entry Process

The standard closing process uses 4-5 closing entries:

**Entry 1: Close Revenue**
- Debit: All revenue accounts (sum of the year)
- Credit: Income Summary (temporary account)

**Entry 2: Close Expenses**
- Debit: Income Summary
- Credit: All expense accounts (sum of the year)

**Entry 3: Close Other Temporary Accounts**
- Debit/Credit: Gains, losses, other temporary accounts
- To/From: Income Summary

**Entry 4: Close Income Summary to Retained Earnings**
- Debit/Credit: Income Summary (net income or loss)
- Credit/Debit: Retained Earnings

**Entry 5 (Optional): Dividends**
- Debit: Retained Earnings
- Credit: Dividends Paid
- (Close out dividends paid during year)

After these entries:
- All revenue and expense accounts = zero
- All temporary accounts = zero
- Retained earnings increased by year's net income
- Ready for new year

## Creating Closing Entries in Light

Light provides automated closing entry generation:

1. Go to **General Ledger > Year-End Closing**
2. Click **Generate Closing Entries**
3. Select the **fiscal year** to close
4. System automatically:
   - Identifies all revenue and expense accounts
   - Calculates their year-to-date balances
   - Generates closing journal entries
   - Creates income summary entry
   - Transfers to retained earnings
5. Review the generated entries
6. Click **Post** to post all closing entries

## Manual Closing Entries

If you prefer manual control:

1. Create journal entries manually
2. Entry 1: Close revenues
3. Entry 2: Close expenses
4. Entry 3: Close other accounts
5. Entry 4: Transfer to retained earnings
6. Post each entry

Manual approach gives more control but is more tedious.

## Income Summary Account

Most closing processes use an Income Summary account:

**Purpose:** Temporary holding account to collect all revenue and expenses before final transfer

**Balance:** After entries 1-3, Income Summary balance = year's net income/loss

**Closed:** Transferred to Retained Earnings in entry 4

**Not needed:** Some companies skip Income Summary and close directly to Retained Earnings

Check your accounting policy—some companies require Income Summary, others don't.

## Pre-Closing Adjustments

Before closing, ensure all period-end adjustments are posted:

1. **Accruals** - Unbilled revenue, unpaid expenses
2. **Deferrals** - Spread prepaid expenses, deferred revenue
3. **Depreciation** - Annual depreciation
4. **Amortization** - Annual amortization of intangibles
5. **Valuations** - Inventory reserves, bad debt reserves
6. **FX adjustments** - Currency revaluation

These must all post before closing, or results will be incorrect.

## Closing Sequence for Multi-Entity

For multi-entity companies:

1. **Close each entity separately**
   - Create closing entries for Entity A, Entity B, etc.
   - Each entity's own Income Summary and Retained Earnings
2. **At group level**
   - Consolidation process combines entities
   - Eliminates intercompany amounts
   - Shows consolidated retained earnings

Or, if using consolidated chart:
1. Create single closing entry for consolidated GL
2. Allocates results back to individual entities if needed

## Retained Earnings

Retained earnings is where closed net income goes:

**Components:**
- Beginning retained earnings (from prior year)
- Plus: Year's net income
- Less: Dividends paid
- Equals: Ending retained earnings (balance sheet amount)

The closing entry increases Retained Earnings by the year's profit (or decreases if loss).

## Dividends and Distributions

If your company paid dividends:

1. **During the year** - Dividend payments are debited to Dividends Paid account
2. **At year-end** - Create entry to close Dividends Paid to Retained Earnings:
   - Debit: Retained Earnings
   - Credit: Dividends Paid
3. Result: Retained Earnings reduced by dividends paid

This shows that some earnings were distributed, not retained.

## Temporary vs. Permanent Accounts

**Temporary accounts** (closed at year-end):
- Revenue accounts
- Expense accounts
- Gains and losses
- Dividends paid
- Income summary

**Permanent accounts** (NOT closed):
- Assets
- Liabilities
- Equity accounts (except Income Summary)
- Retained Earnings

Permanent accounts carry forward; temporary accounts start fresh each year.

## Reversing Entries

Some accountants create reversing entries on the first day of the new year:

**Purpose:** Simplify subsequent period accounting

**Example:** If you accrued $10,000 salary at year-end:
- Year-end: Debit Salary Expense, Credit Accrued Salary
- Next day: Debit Accrued Salary, Credit Salary Expense (reverses)
- When actual payment: Debit Salary Expense, Credit Cash

Reversals are optional—your accounting policy determines whether you use them.

## Testing the Close

Before finalizing, verify your closing entries are correct:

1. **Trial Balance before closing** - All accounts with balances
2. **Post closing entries**
3. **Trial Balance after closing** - Only permanent accounts should have balances
4. **Review Retained Earnings** - Should equal prior year + net income - dividends

If post-closing trial balance shows only balance sheet accounts, the close was done correctly.

## Audit Considerations

External auditors will review:

1. **Accuracy of closing entries** - Amounts match GL balances
2. **Completeness** - All revenue and expense accounts closed
3. **Proper accounts used** - Income Summary used correctly
4. **Documentation** - Entries documented and supported
5. **Timing** - Closed within reasonable time after year-end

Prepare a closing entry workpaper for auditors showing:
- Pre-closing trial balance
- Each closing entry
- Post-closing trial balance
- Reconciliation of Retained Earnings

## Fiscal Year Differences

If your fiscal year doesn't match the calendar year:

1. **Fiscal year** = June 1 - May 31
2. **Close on May 31** - Not December 31
3. **New fiscal year** begins June 1
4. Same closing process, just different calendar date

Light supports any fiscal year; just set period dates accordingly.

## Multi-Currency Closing

For companies with foreign entities:

1. **Each entity closes in local currency** - EUR, GBP, JPY, etc.
2. **Consolidated close** - Converts all to group currency
3. **FX adjustments** - Any consolidated translation adjustments post
4. **CTA account** - Cumulative translation adjustment account captures FX
5. **Eliminate intercompany** - Between-entity amounts eliminated

Multi-currency closing is more complex; consider hiring specialist if needed.

## Year-End Reporting Timeline

Typical year-end close timeline:

**January 1-3:** Close December period, post final accruals
**January 4-5:** Generate closing entries, post to GL
**January 6-7:** Generate financial statements
**January 8-10:** Review with management, resolve issues
**January 11-14:** Finalize statements, get approval
**January 15+:** Deliver to auditors, external parties

Adjust based on your company's complexity and deadlines.

## Common Issues and Solutions

**Issue:** Closing entries don't balance
- **Solution:** Ensure all revenue and expense accounts included; check for missing accounts

**Issue:** Retained Earnings doesn't match prior year + NI
- **Solution:** Check that all items affecting equity were included; verify dividends

**Issue:** Post-closing trial balance not zero
- **Solution:** Review trial balance; ensure only permanent accounts have balances

## Best Practices

- **Start early** - Don't wait until the last day
- **Follow your accounting policy** - Be consistent year over year
- **Document thoroughly** - Keep notes on adjustments and estimates
- **Get approval** - Have CFO or board approve closing
- **Test before posting** - Verify on trial balance before posting actual entries
- **Archive documentation** - Keep workpapers for audit and future reference
- **Train staff** - Ensure team understands year-end close requirements

## Related Articles

- [Creating manual journal entries](/mnt/help-articles/articles/05-general-ledger/5-4-manual-journal-entries.md)
- [Closing periods and month-end close](/mnt/help-articles/articles/05-general-ledger/5-8-closing-periods.md)
- [Deferred entries (accruals and deferrals)](/mnt/help-articles/articles/05-general-ledger/5-5-deferred-entries.md)
