# Creating Manual Journal Entries

Manual journal entries allow you to record adjustments, accruals, and corrections directly in the GL. This article explains how to create and post journal entries.

[Open in Light →](https://app.light.inc/journal-entries)


## When to Use Journal Entries

Create manual journal entries for:

**Adjustments** - Fix errors in posting or accounts

**Accruals** - Record expenses incurred but not yet billed (e.g., rent accrual)

**Deferrals** - Spread expenses over future periods (e.g., insurance prepayment)

**Corrections** - Reverse and correct prior entries

**Consolidation** - Eliminate intercompany entries

**Custom entries** - Any GL transaction not handled by AP/AR/Payments

## Creating a Simple Journal Entry

To create a basic journal entry:

1. Go to **General Ledger > Journal Entries**
2. Click **Create Journal Entry**
3. Enter details:
   - **Description** - What is this entry for
   - **Posting Date** - When to post to GL
   - **Company Entity** - Which entity (for multi-entity companies)
   - **Currency** - Currency of the entry (if multi-currency)
4. Add lines:
   - Click **Add Line**
   - Select **GL Account**
   - Enter **Debit** or **Credit** amount
   - Add **Description** (optional)
   - Repeat for each account
5. System validates that debits = credits
6. Click **Post**

The entry is now posted to the GL.

## Entry Structure

A journal entry consists of:

**Header:**
- Description (required) - Describes what the entry is for
- Posting date (required) - When it posts
- Company entity (required) - Which entity
- Currency (required)
- Custom properties (optional) - Department, project, etc.

**Lines:**
- GL Account (required)
- Debit amount (optional) - If account is being increased
- Credit amount (optional) - If account is being decreased
- Description (optional)
- Custom properties per line (optional)

Each entry must have at least 2 lines, and debits must equal credits.

## Double-Entry Bookkeeping

All entries use double-entry bookkeeping:

**Example: Accrue rent expense**
- Debit: Rent Expense (5000) - $1,000
- Credit: Accrued Rent Payable (2500) - $1,000

Both sides must balance. This ensures the accounting equation remains true.

## Multi-Line Entries

Create entries with many lines:

1. Add lines one at a time
2. View running total of debits and credits
3. Continue adding until balanced
4. System shows error if not balanced

Example: Month-end allocation of shared expense to departments

```
Debit: Department A Expense 40% - $4,000
Debit: Department B Expense 30% - $3,000
Debit: Department C Expense 30% - $3,000
Credit: Shared Expense Clearing - $10,000
```

## Reversing Entries

Create entries that reverse previous entries:

1. Open the original entry
2. Click **Create Reversal**
3. System automatically:
   - Creates new entry with opposite amounts
   - Links to original for audit trail
   - Shows both entries side by side
4. Choose posting date for reversal
5. Click **Post**

Reversals are used to undo entries while maintaining audit trail.

## Recurring Entries

Set up entries that post automatically each period:

1. Create a journal entry as normal
2. Before posting, click **Make Recurring**
3. Set recurrence:
   - Frequency (monthly, quarterly, annually)
   - Start and end dates
   - Adjustment rules (e.g., increase amount 5% each year)
4. Click **Save**

Recurring entries automatically post on schedule. For monthly rent accrual, create once and it posts every month.

## Multi-Entity Entries

For multi-entity companies:

**Same entity entry:**
- All lines post to the same company entity's GL

**Intercompany entry:**
- Some lines post to entity A, others to entity B
- Creates payable/receivable between entities
- Consolidated reporting eliminates intercompany amounts

To create intercompany entry:
1. Add lines to different entities
2. System tracks which entity each line posts to
3. Consolidation logic handles elimination

## FX and Multi-Currency

For entries in foreign currencies:

1. Select the **currency** (EUR, GBP, JPY, etc.)
2. Enter amounts in that currency
3. Specify **posting date** for FX rate
4. Light converts to local and group currencies
5. Stores all three amounts in GL

When multi-entity, each entity can have different local currencies.

## Tax-Related Entries

Some entries involve tax. For example:

**Sales tax entry:**
- Debit: Sales Tax Expense - $1,000
- Credit: Sales Tax Payable - $1,000

**VAT entry:**
- Debit: VAT Receivable - $5,000
- Credit: VAT Expense - $5,000

GL accounts typically have a tax designation for proper reporting.

## Workflow Approval for Entries

Depending on settings, journal entries may require approval:

1. Entry created in DRAFT status
2. User submits for approval
3. Approver reviews and approves/rejects
4. If approved, user can post
5. If rejected, returns to DRAFT

Large entries or special types may have approval workflows.

## Batch Journal Entries

Create multiple entries at once:

1. Go to **General Ledger > Journal Entries**
2. Click **Import Batch**
3. Upload CSV with entries:
   - Description, Date, Account, Amount, DebitOrCredit
   - One line per row
4. System validates format
5. Creates all entries in DRAFT status
6. Review before posting

Batch import is faster than entering individually.

## Editing Entries

If an entry is still in DRAFT:

1. Open the entry
2. Edit any fields or lines
3. Add or remove lines
4. Click **Save** (not Post yet)

Once posted, you cannot edit directly. Instead:
1. Create a reversing entry
2. Create a new correcting entry
3. Or modify (see document lifecycle article)

## Approving and Posting

Once an entry is ready:

1. If approval is required:
   - Submit for approval
   - Wait for approver
   - Get approval or rejection
2. Click **Post** to finalize
3. Entry posts to GL, becomes immutable

Posting is the point of no return—the entry is now in the permanent GL.

## Common Entry Templates

**Accrual template:**
```
Description: Monthly rent accrual - [Month]
Debit: Rent Expense (5500)
Credit: Accrued Rent (2750)
```

**Depreciation template:**
```
Description: Monthly depreciation - [Asset]
Debit: Depreciation Expense (5600)
Credit: Accumulated Depreciation (1800)
```

**Intercompany allocation:**
```
Description: Allocate headquarters costs
Debit: Entity A Expense (Entity A GL 5700)
Debit: Entity B Expense (Entity B GL 5700)
Credit: HQ Allocation Clearing (HQ GL 9999)
```

Save templates and use them repeatedly.

## Period-End Entries

At period-end, you may create:

**Accrual entries** - Record unbilled expenses or unpaid revenues

**Deferral entries** - Spread prepaid expenses to future periods

**Reclassification entries** - Move balances between accounts

**Tax entries** - Estimate tax liability

Create these after other transactions post but before closing the period.

## Searching Your Entries

Find created entries:

1. Go to **General Ledger > Journal Entries**
2. Filter by:
   - Date range
   - Description keywords
   - GL account affected
   - Posted/Unposted status
   - Custom properties
3. Sort and review

Saved searches help for recurring review tasks.

## Validation Rules

Before posting, entries are validated:

- **Balances** - Debits must equal credits
- **Accounts exist** - All GL accounts must be valid
- **Period open** - Cannot post to closed period
- **Amounts entered** - Cannot have empty debit/credit
- **Required fields** - Description, date, entity required

Validation prevents invalid entries from reaching the ledger.

## Related Articles

- [Understanding Light's general ledger](/mnt/help-articles/articles/05-general-ledger/5-1-understanding-general-ledger.md)
- [Accounting document types and lifecycle](/mnt/help-articles/articles/05-general-ledger/5-2-document-types-lifecycle.md)
- [Deferred entries (accruals and deferrals)](/mnt/help-articles/articles/05-general-ledger/5-5-deferred-entries.md)
- [Immutable ledger and audit trail](/mnt/help-articles/articles/05-general-ledger/5-7-immutable-ledger.md)
