# Viewing and Searching Journal Entries

Light provides flexible tools to search, filter, and view journal entries and all accounting documents. This article explains how to find and analyze GL data.

[Open in Light →](https://app.light.inc/ledger-transactions)


## Accessing the General Ledger

To view all accounting documents and transactions:

1. Go to **General Ledger** or **Accounting > Ledger**
2. You see a list of all accounting documents
3. Filter and search to find specific items
4. Click a document to view details

The ledger shows all document types (invoices, payments, journal entries, etc.) in one place.

## Filtering Transactions

Use filters to narrow the ledger view:

**By Document Type:**
- AP (vendor invoices)
- AR (customer invoices)
- Bank Payment
- Journal Entry
- Card Transaction
- etc.

**By Status:**
- Draft, Posted, Partially Cleared, Cleared, Archived

**By Date Range:**
- Posting date (when it posted to GL)
- Document date (when transaction occurred)
- Cleared date (when it was reconciled)

**By Entity:**
- Company entity (if multi-entity)

**By Amount:**
- Equal to specific amount
- Greater than / Less than
- Amount range

Combine filters to find specific transactions quickly.

## Searching Transactions

Search using text or numbers:

**Search fields:**
- Document number (invoice #, reference)
- Description
- Business partner name (vendor, customer)
- GL account name/code
- Custom properties

**Search type:**
- Contains (default)
- Equals exactly
- Starts with
- Ends with

Example: Search "invoice" to find all invoice-related documents.

## Sorting Results

Sort the transaction list by:

- **Posting date** - Most recent first or oldest first
- **Amount** - Largest or smallest first
- **Document type** - Group by type
- **Status** - Posted first or cleared first
- **GL account** - By account code or name

Sort helps identify patterns (e.g., largest transactions, oldest unmatched items).

## Viewing Document Details

Click a document in the list to see full details:

**Header section:**
- Type, status, sequence number
- Document and posting dates
- Business partner (if applicable)
- Currency and amounts

**Lines section:**
- GL account and amount for each line
- Tax information
- Custom properties
- Allocation details

**Related section:**
- Linked documents (original invoice, payment, etc.)
- Approval information
- Clearings/matches

**Activity section:**
- Creation date and user
- Last modification
- Posting details

## Drilling into GL Entries

To see the actual GL transactions created by a document:

1. Open the document
2. Click **View GL Entries** or **Ledger Transactions**
3. See all debit and credit entries posted:
   - GL account, debit/credit amounts
   - Local and group currency amounts
   - FX conversion details
   - Links to source line items

This shows exactly how the document posted to the ledger.

## General Ledger Report

View all GL account balances and transactions:

1. Go to **Reports > General Ledger**
2. Filter by date range and entities
3. See account balances with:
   - Opening balance
   - Period debits and credits
   - Closing balance
   - All transactions that make up the balance

The GL report is your most detailed view of the ledger.

## Trial Balance

See all accounts and their balances:

1. Go to **Reports > Trial Balance**
2. View each GL account with:
   - Debit or credit balance
   - Total debits and total credits (should be equal)
3. Export to CSV or print

Trial balance is useful for reconciliation and audit purposes.

## Account Analysis

Drill into a specific GL account:

1. Go to **General Ledger > GL Accounts**
2. Find the account and click it
3. See:
   - Opening and closing balance
   - All transactions in the account
   - Sub-account balances (if applicable)
   - Filter by date range

This shows you everything affecting a specific account.

## Multi-Level Accounts

For accounts with sub-accounts:

1. Click the parent account
2. See parent balance (sum of children)
3. Click **Expand** to see child accounts and their balances
4. Click a child account for its detailed transactions

This hierarchical view makes it easy to understand account structures.

## Unposted Documents

View documents that haven't posted yet:

1. Go to **Ledger > Unposted Documents** or filter Status = DRAFT
2. See documents waiting to be posted
3. Review before posting or posting in bulk

This helps you manage documents in your pipeline.

## Cleared vs. Uncleared

Filter for clearing status:

**Uncleared:**
- Document posted but not yet matched/reconciled
- Shows as "Unmatched" in reconciliation reports

**Cleared:**
- Document matched to other document
- Shows as "Cleared" or "Matched"

Use this to focus on items needing reconciliation work.

## Journal Entry Specific Features

For journal entries specifically:

1. Go to **General Ledger > Journal Entries**
2. Filter by:
   - Entry type (manual vs. automatic)
   - GL account affected
   - Posted period
   - Description keywords
3. View entries grouped or sorted by your preference

Journal entries are the core manual GL records.

## Multi-Journal Entries

Some journal entries affect multiple accounts. To view and edit:

1. Open the multi-journal entry
2. See all lines with debits and credits
3. Modify amounts if in DRAFT status
4. View how it posted to each account

Multi-journal entries allow complex transactions in one document.

## Custom Properties in GL

Search and filter by custom properties:

1. If documents have custom properties (department, project, etc.)
2. Filter by property value to find related transactions
3. View custom properties in GL listings and reports

This helps with cost allocation and project-based analysis.

## Exporting GL Data

Export journal entries and GL transactions for analysis:

1. Use list **Export** button to export filtered results
2. Choose format:
   - Excel - Full spreadsheet
   - CSV - For import elsewhere
   - PDF - For printing/sharing
3. Specify columns to include
4. Download the file

Use exports for detailed analysis in Excel or consolidation to other systems.

## GL Aging Analysis

For AR and AP accounts, view aging:

1. Go to **Reports > AR Aging** or **AP Aging**
2. See invoices grouped by age:
   - Current (due within 0-30 days)
   - 30-60 days overdue
   - 60-90 days overdue
   - 90+ days overdue

Aging analysis helps identify collection/payment issues.

## Reconciliation Status

From the GL view, see reconciliation status:

1. Each posted document shows status:
   - Unmatched (not reconciled)
   - Partially cleared (some matching)
   - Cleared (fully matched)
2. Click to see what it was matched with

This helps you focus reconciliation efforts.

## Saved Searches and Reports

Save frequently-used searches:

1. Apply filters and sort
2. Click **Save as Report**
3. Name the report
4. Re-use anytime

Example: "AP invoices over 10,000 unmatched" for monthly AP review.

## Performance Tips

When working with large GL databases:

- **Use date filters** - Don't pull all-time data at once
- **Filter by document type** - Narrow to what you need
- **Search before sorting** - Find first, then sort
- **Use reports** - Pre-built reports are optimized
- **Schedule exports** - Large exports run in background

## Best Practices

- **Review GL regularly** - Don't wait for month-end
- **Verify posting** - Check documents posted correctly
- **Investigate anomalies** - Unusual entries need explanation
- **Maintain account list** - Inactive accounts should be archived
- **Use consistent keywords** - Standardize search terms for findability
- **Keep audit trail** - Don't delete GL entries; reverse them instead

## Related Articles

- [Understanding Light's general ledger](/mnt/help-articles/articles/05-general-ledger/5-1-understanding-general-ledger.md)
- [Creating manual journal entries](/mnt/help-articles/articles/05-general-ledger/5-4-manual-journal-entries.md)
- [Immutable ledger and audit trail](/mnt/help-articles/articles/05-general-ledger/5-7-immutable-ledger.md)
