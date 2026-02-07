# Accounting Document Types and Lifecycle

All financial transactions in Light flow through a unified accounting document system. This article explains the document types and their lifecycle from creation to archival.

[Open in Light →](https://app.light.inc/accounting-documents)


## Accounting Document Concept

An "accounting document" is any financial transaction that posts to the ledger:

- Invoice Payables (vendor bills)
- Invoice Receivables (customer invoices)
- Bank Payments (payment instructions)
- Journal Entries (manual GL entries)
- Card Transactions (corporate card charges)
- Deferred Entries (accruals and deferrals)
- FX Revaluations (currency adjustments)
- Year-End Closing Entries (period close entries)
- Credit Notes (AP and AR credits)

Each document type has domain-specific fields but follows the same posting lifecycle.

## Document Structure

All documents share a common structure:

**Header:**
- Unique ID and sequence number
- Document type and status
- Company entity (which entity it belongs to)
- Posting date (when it posts to GL)
- Document date (when the transaction occurred)
- Currency and amount
- Business partner (if applicable: vendor, customer)

**Lines:**
- GL account and amount for each line
- Tax information if applicable
- Allocation to cost centers or projects
- Custom properties

**Relationships:**
- Linked to source documents (purchase order, contract)
- Linked to cleared/matched documents
- Linked to workflow approvals

## Document Types

**Accounts Payable (AP)**
- Type: Invoice Payable
- Purpose: Vendor invoices for goods/services received
- Lifecycle: Created, approved, posted, paid, cleared
- Key fields: Vendor, invoice number, due date, payment terms

**Accounts Receivable (AR)**
- Type: Invoice Receivable
- Purpose: Customer invoices for goods/services sold
- Lifecycle: Created, sent, posted, payment received, cleared
- Key fields: Customer, contract, billing period, payment terms

**Bank Payments**
- Type: Bank Payment
- Purpose: Payment instructions sent to the bank
- Lifecycle: Created, approved, posted, executed, cleared
- Key fields: Bank account, payment method, payee, amount

**Journal Entries**
- Type: Journal Entry
- Purpose: Manual GL entries for adjustments, accruals, etc.
- Lifecycle: Created, posted, cleared (if matched to transactions)
- Key fields: GL accounts, debit/credit amounts, description

**Deferred Entries**
- Type: Deferred Entry
- Purpose: Accruals, deferrals, and spreading costs over time
- Lifecycle: Template created, entries generated, posted
- Key fields: Amortization schedule, cost center, period allocation

**Card Transactions**
- Type: Card Transaction
- Purpose: Corporate card charges
- Lifecycle: Imported, categorized, posted, cleared
- Key fields: Cardholder, merchant, category, amount

**Credit Notes**
- Type: Credit Note (AP) or Customer Credit (AR)
- Purpose: Offset original invoices (refunds, adjustments)
- Lifecycle: Created, posted, matched to invoice
- Key fields: Original invoice reference, credit reason, amount

**FX Revaluations**
- Type: FX Revaluation
- Purpose: Currency adjustment entries
- Lifecycle: Generated, posted, cleared
- Key fields: Asset accounts, exchange rates, currency pairs

**Year-End Closing**
- Type: Year Closing Entry
- Purpose: Transfer net income to retained earnings
- Lifecycle: Generated at year-end, posted, never reversed
- Key fields: Earnings accounts, retained earnings account

## Document Lifecycle

All documents follow this state machine:

```
DRAFT → POSTED → (PARTIALLY_CLEARED) → CLEARED → ARCHIVED
```

**DRAFT State:**
- Document is being created or edited
- Can be modified freely (amounts, lines, etc.)
- Has not posted to the ledger yet
- Not visible in financial reports

**POSTED State:**
- Document has posted to the ledger
- GL transactions created and immutable
- Can still be modified (via reversal + re-posting)
- Visible in financial reports
- Can be cleared as transactions are matched

**PARTIALLY_CLEARED State:**
- Document has been partially matched/cleared
- Some GL transactions matched to other documents
- Can still be modified (reversals are uncleared first)
- Shows in aged item reports

**CLEARED State:**
- Document fully matched to other documents
- All amounts have been reconciled
- Can still be modified if needed
- Typically no longer needs attention

**ARCHIVED State:**
- Document marked as closed/inactive
- Removed from active document lists
- Remains in system for historical/audit purposes
- Can be reactivated if needed

## Posting Process

When a document posts to the ledger:

1. **Validation** - System validates all required fields and amounts
2. **Sequence number assignment** - Unique document sequence ID generated
3. **Line expansion** - Multi-line documents expanded into individual GL entries
4. **Tax calculation** - Tax amounts calculated and posted to tax accounts
5. **FX conversion** - Multi-currency amounts converted to local/group currencies
6. **GL posting** - All entries posted to ledger_transaction_line table
7. **Status change** - Document status changes from DRAFT to POSTED

Posting is atomic—either all transactions post or none do. Partial posts are not possible.

> Good to know: Posting typically takes 1-5 seconds. For bulk operations, timing may vary.

## Modifying Posted Documents

To modify a document that's already posted:

1. Document status must be POSTED, PARTIALLY_CLEARED, or CLEARED
2. Click **Modify**
3. System automatically:
   - Reverses all clearings and matched entries
   - Reverses the original posting (sets status to DRAFT)
   - Applies your modifications
   - Re-posts with new amounts
   - Reapplies clearings
4. Document is now modified with updated GL transactions

Modifying is safer than manual reversals because it's atomic—all steps succeed or all fail.

## Reversing Documents

To completely undo a posting:

1. Open the document
2. Click **Reverse**
3. System creates a new document with opposite amounts:
   - All debits become credits, all credits become debits
   - Same GL accounts, amounts, and descriptions
   - Linked to the original for audit trail
4. Original document remains in the ledger; reversing entry offsets it

Reversals are used when you want to document that an error occurred (for audit trail).

## Clearing and Matching

Documents can be "cleared" when matched to other documents:

**Bank reconciliation:**
- Bank transaction matched to GL payment entry
- Both marked as cleared/matched

**Invoice payment:**
- AP invoice matched to payment
- Both show cleared status

**Cross-entity settlements:**
- Intercompany payable matched to intercompany receivable
- Both cleared

Clearing links documents but doesn't modify either—they remain as posted.

## Workflow Integration

Many documents require approval before posting:

1. Document created in DRAFT status
2. Submitted for approval (workflow starts)
3. Approval workflow completes (approved or rejected)
4. If approved, user posts the document
5. If rejected, document returns to DRAFT for modification

Approval workflows control who can post what documents.

## Bulk Operations

Light supports bulk posting of documents:

1. Create multiple documents in draft
2. Select them and click **Post All**
3. Each document validates and posts
4. Progress shown, with success/failure breakdown
5. Failed documents remain in DRAFT for correction

Bulk posting is faster than posting individually but should be done carefully.

## Archival

Documents can be archived when no longer needed:

1. Click **Archive** on a cleared or old document
2. Document is hidden from active lists
3. Remains in GL for reporting/audit
4. Can be retrieved if needed

Archive old periods' documents to keep active lists clean.

## Document Sequence

Each document type has a sequence:

- **Format:** DOCTYPE/ENTITY/NUMBER (e.g., AP/001/12345)
- **Guarantees uniqueness** - No two documents have the same number
- **Immutable** - Sequence number assigned at posting, never changes
- **Supports reporting** - Easy reference to specific documents

The sequence is company-wide (all APs share one sequence, all JEs share another).

## Multi-Line Documents

Documents can have multiple line items:

**Invoice example:**
- Header: Invoice, total amount, vendor
- Line 1: Materials, GL account, amount, tax
- Line 2: Labor, GL account, amount, tax
- Line 3: Shipping, GL account, amount, tax

When posted, each line posts to its GL account, creating multiple ledger transactions.

## Custom Properties

Documents can be tagged with custom properties:

- Department, project, cost center
- Program, activity, fund
- Custom fields you define

Custom properties are posted with each GL transaction for reporting/analysis.

## Document Validation

Before posting, documents are validated:

- **Required fields** - All required fields must be filled
- **Amount balance** - Debits must equal credits
- **GL accounts exist** - All accounts must be valid
- **Period is open** - Posting date's period must not be closed
- **Approval complete** - If applicable, approval workflow must be done
- **Business rules** - Document-type-specific rules

Validation prevents invalid data from reaching the ledger.

## Related Articles

- [Understanding Light's general ledger](/mnt/help-articles/articles/05-general-ledger/5-1-understanding-general-ledger.md)
- [Viewing and searching journal entries](/mnt/help-articles/articles/05-general-ledger/5-3-viewing-journal-entries.md)
- [Creating manual journal entries](/mnt/help-articles/articles/05-general-ledger/5-4-manual-journal-entries.md)
- [Immutable ledger and audit trail](/mnt/help-articles/articles/05-general-ledger/5-7-immutable-ledger.md)
