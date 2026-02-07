# Understanding Light's General Ledger

Light's general ledger is the central accounting system where all financial transactions are recorded. This article explains the ledger structure, how documents flow through it, and its relationship to other modules.

[Open in Light →](https://app.light.inc/ledger-transactions)

## What is a General Ledger?

The general ledger (GL) is the master record of all financial transactions:

- Every debit and credit is recorded
- All transactions are linked to ledger accounts (chart of accounts)
- It's the source of truth for financial reporting and compliance
- All transactions are immutable once posted

The GL is where AP invoices, AR invoices, payments, journal entries, and other documents ultimately post as transactions.

## Ledger Accounts (Chart of Accounts)

The ledger organizes transactions by account type:

**Asset Accounts** - What you own (1000-1999)
- Cash, Bank Accounts, Accounts Receivable, Inventory

**Liability Accounts** - What you owe (2000-2999)
- Accounts Payable, Loans, Accrued Expenses

**Equity Accounts** - Owner's stake (3000-3999)
- Common Stock, Retained Earnings, Contributed Capital

**Revenue Accounts** - Money earned (4000-4999)
- Product Revenue, Service Revenue, Other Income

**Expense Accounts** - Money spent (5000-5999)
- Salaries, Rent, Cost of Goods Sold, Utilities

The chart of accounts is your company's GL structure. All posting flows through these accounts.

## Account Hierarchy

Ledger accounts can be organized hierarchically:

**Parent accounts** - Summary level (e.g., "Expenses")

**Sub-accounts** - Detail level (e.g., "Salaries", "Rent", "Utilities")

Reporting rolls up from sub-accounts to parents, allowing both detailed and summary views.

## Ledger Transactions

Transactions in the ledger record the actual debit and credit:

**Components:**
- **Account** - Which GL account (e.g., Cash 1010)
- **Debit amount** - If this account is being increased (assets, expenses)
- **Credit amount** - If this account is being decreased (liabilities, revenue)
- **Date** - When the transaction occurred
- **Reference** - Link to the source document (invoice, payment, etc.)

Transactions follow the fundamental equation: **Debits = Credits** (double-entry bookkeeping)

## Document Flow to Ledger

Financial documents flow through Light and post to the ledger:

1. **Domain modules** create documents:
   - AP creates Invoice Payable (bills)
   - AR creates Invoice Receivable (customer invoices)
   - Payments module creates bank payments
   - Users create manual Journal Entries

2. **Documents are drafted** - Created in DRAFT status, can be edited freely

3. **Documents are posted** - Status changes to POSTED, generates GL transactions

4. **Transactions become immutable** - Once in the ledger, they cannot be changed (only reversed)

5. **Reporting pulls from ledger** - Reports query GL transactions for financial data

## Multi-Currency Posting

When posting a document in a foreign currency:

**Original amount** - The transaction's original currency (e.g., 1,000 EUR)

**Local amount** - Converted to company entity's local currency using daily rates

**Group amount** - Converted to corporate group currency for consolidated reporting

Light stores all three amounts, allowing reporting in any currency.

## Tax Handling

Tax calculations occur during posting:

- **Line-level taxes** - Each invoice line may have different tax rates
- **Tax amounts** - Separated into tax GL accounts (liability)
- **Net vs. gross** - Lines can be specified as net (tax calculated and added) or gross (tax already included)

Tax is automatically calculated during posting and posted to dedicated tax accounts.

## Ledger Accounts Features

Advanced ledger account capabilities:

**Account types** - Asset, Liability, Equity, Revenue, Expense, etc.

**Account categories** - For reporting (Operating Expenses, COGS, etc.)

**Reconciliation accounts** - For clearing (Accounts Payable offset, Accounts Receivable clearing)

**Parent-child relationships** - For hierarchy and roll-up reporting

**Active/Inactive** - Archive accounts no longer in use

**Reporting codes** - For regulatory reporting (GAAP, IFRS, tax codes)

## Posting Rules

When documents post, several rules apply:

**Period must be open** - Cannot post to a closed accounting period

**Required fields** - All document fields must be complete before posting

**GL accounts must exist** - All accounts referenced must be in the chart of accounts

**Amounts must balance** - Total debits must equal total credits

**Document type rules** - Certain document types have specific posting requirements

If any rule is violated, posting fails with an error message.

## Document Status and Ledger Impact

Document status affects GL interaction:

**DRAFT** - No GL impact. Can be freely edited.

**POSTED** - GL transactions created. Immutable. Cannot edit directly.

**PARTIALLY_CLEARED** - Some GL entries have been cleared/matched. Cannot modify without reversing first.

**CLEARED** - All GL entries have been cleared/matched.

**ARCHIVED** - Removed from active lists but remains in GL.

## Immutability and Audit Trail

The ledger is immutable by design:

- **Posted transactions cannot be changed** - Ever
- **Reversals instead of edits** - If you need to undo a posting, create a reversing entry
- **Audit trail** - Every change to a document is logged
- **Accountability** - You can always see who posted what and when

This prevents fraud and ensures financial data integrity.

## Clearing and Reconciliation

Transactions in the ledger can be "cleared" as part of reconciliation:

- **Bank reconciliation** - Bank transactions cleared against GL entries
- **Payment clearing** - Invoices cleared when paid
- **Customer clearance** - AR invoices cleared when collected

Clearing links transactions but doesn't modify them—they remain as posted.

## Ledger Reporting

Financial reports pull directly from the ledger:

- **Balance sheet** - Balances of asset, liability, equity accounts
- **Income statement** - Balances of revenue and expense accounts
- **Trial balance** - All accounts with their balances
- **General ledger report** - Transaction-level detail

Reports are always current and reflect the latest posted transactions.

## Company Entities and Ledgers

Each company entity has its own ledger:

- **Entity-level accounts** - Each entity has its own chart of accounts (or shared)
- **Entity-level transactions** - Transactions are always posted to a specific entity
- **Consolidation** - Corporate pulls together entity-level GL for group reporting

Reports can be generated at entity level or consolidated across the group.

## Accounting Periods

The ledger is organized into accounting periods:

- **Period status** - Open (accepting posts), Closed (no new posts)
- **Period dates** - Start and end date of the period
- **Year-end** - Special processing at year-end for closing entries

Periods control when transactions can be posted and when closing entries are created.

## Key Features

Light's ledger includes:

- **Real-time posting** - Documents post immediately, GL updates instantly
- **Multi-currency support** - Automatically converts and tracks FX
- **Tax integration** - Automated tax calculation and posting
- **Workflow integration** - Documents can't post until approved
- **Audit trail** - Complete history of all changes
- **Customization** - Custom GL accounts and properties
- **Reporting** - Flexible GL-based reporting

## Best Practices

- **Use consistent account coding** - Train staff on proper GL account selection
- **Validate before posting** - Review document details before posting
- **Post promptly** - Don't delay posting; timely data is critical
- **Review GL regularly** - Look for unusual or suspicious transactions
- **Archive old periods** - Keep recent GL data online, archive older data
- **Maintain chart of accounts** - Keep GL structure aligned with reporting needs

## Related Articles

- [Accounting document types and lifecycle](/mnt/help-articles/articles/05-general-ledger/5-2-document-types-lifecycle.md)
- [Viewing and searching journal entries](/mnt/help-articles/articles/05-general-ledger/5-3-viewing-journal-entries.md)
- [Creating manual journal entries](/mnt/help-articles/articles/05-general-ledger/5-4-manual-journal-entries.md)
- [Immutable ledger and audit trail](/mnt/help-articles/articles/05-general-ledger/5-7-immutable-ledger.md)
