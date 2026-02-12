# Immutable Ledger and Audit Trail

Light's ledger is immutable by design—once transactions post, they cannot be changed. This ensures data integrity and creates a complete audit trail. This article explains how immutability works, the distinction between accounting documents and transactions, and why it matters.

[Open in Light →](https://app.light.inc/ledger-transactions)


## Accounting Documents vs. Transactions

In Light, it's important to understand the distinction between accounting documents and transactions:

**Accounting documents** (such as bills, sales invoices, and journal entries) are **mutable** records that can be edited. A single accounting document can generate one or several transactions on the general ledger.

**Transactions** are the individual debit and credit entries posted to the general ledger. Once posted, transactions are **immutable**—they cannot be changed or deleted.

When you edit an accounting document that has already been posted, the accounting document engine automatically handles the reversal of existing transactions on the general ledger and creates new transactions reflecting your changes. You don't need to manually create reversing entries.

## What Does Immutable Mean?

Immutability applies specifically to posted transactions on the general ledger:

- **No editing** - You cannot modify a posted transaction directly
- **No deletion** - You cannot remove a posted transaction from the ledger
- **Permanent record** - All transactions remain forever
- **Complete trail** - Every change is logged and traceable

This design prevents fraud, maintains compliance, and ensures financial data is trustworthy.

## Why Immutability Matters

**Prevents fraud** - Someone cannot change a past transaction to cover up theft or embezzlement

**Ensures compliance** - Auditors and regulators can trust the GL is complete and unchanged

**Maintains integrity** - Financial reports are based on data that hasn't been tampered with

**Accountability** - You can always see who posted what and when

**Historical accuracy** - You have a complete record of how balances evolved over time

## How Immutability Works

When you post an accounting document:

1. Document status changes from Draft to Posted
2. GL transactions are created on the general ledger
3. Transactions are marked as immutable
4. System prevents any direct modification of those transactions

If you need to change something after posting:

1. **Edit the accounting document** - You can modify the accounting document itself
2. **Automatic reversal** - The accounting document engine automatically reverses the existing transactions
3. **New transactions created** - New transactions reflecting your changes are posted
4. **Full audit trail** - Both the original and new transactions remain visible for audit purposes

## How Automatic Reversals Work

When you edit a posted accounting document, the system automatically creates reversals behind the scenes. Here's what happens:

1. **Original transactions are reversed** - All debits become credits, all credits become debits
2. **New transactions are created** - Reflecting your updated accounting document
3. **Both remain on the ledger** - The original, reversal, and new transactions are all preserved

Example: You posted a bill for $1,000 but should have posted $1,200

```
Original transactions (from initial posting):
  Debit: Expense 1000
  Credit: Payable 1000

Automatic reversal (when you edit the document):
  Debit: Payable 1000
  Credit: Expense 1000

New transactions (from your corrected document):
  Debit: Expense 1200
  Credit: Payable 1200

Result: Net effect is Debit Expense 1200, Credit Payable 1200 (correct)
```

All of this happens automatically when you save your changes to the accounting document—you only need to edit the document itself.

## Editing Accounting Documents

Light allows you to edit accounting documents even after they've been posted:

1. Open the posted accounting document
2. Make your changes (e.g., correct a cost center, update an amount, change a GL account)
3. Save your changes
4. The accounting document engine automatically:
   - Reverses the original transactions on the general ledger
   - Creates new transactions reflecting your changes
   - Maintains full audit trail of both sets of transactions

This approach preserves the immutability of the ledger while giving you flexibility to correct errors in accounting documents. You don't need to manually create reversing entries—the system handles this automatically.

## Audit Trail

Every transaction and change is logged:

**What's tracked:**
- Who created the document
- When it was created
- What the document contained
- Who posted it
- When it was posted
- Any modifications (reversals + corrections)
- Who cleared/matched it
- When it was cleared

**Access audit trail:**
1. Open any document or transaction
2. Click **Activity** or **Audit Trail**
3. See complete history of changes

## Document-Level Audit

For each document, view:

1. **Creation** - Who created, when, what fields
2. **Modifications** - All changes while in DRAFT
3. **Posting** - Who posted, when, GL impact
4. **Clearing** - When/if it was matched to other documents
5. **Reversal** - If reversed, linked entry shown

Example: Invoice Payable audit trail
```
2024-01-15 10:30 - Sarah Created invoice AP-001-10000 for $5,000
2024-01-15 11:45 - Sarah Modified amount to $5,100
2024-01-15 14:00 - Mike Approved invoice
2024-01-16 09:00 - Sarah Posted invoice
2024-02-01 15:30 - System Matched to payment, cleared
```

## Transaction-Level Detail

For posted GL transactions:

1. View debit/credit amounts
2. See linked accounting document
3. View source document (invoice, etc.)
4. See FX conversion details (if multi-currency)
5. View custom properties
6. See cleared status

Every GL entry shows its complete lineage.

## User Accountability

The audit trail shows accountability:

- **Who posted this transaction?** - User name in audit trail
- **Did they have authority?** - Role-based permissions in system
- **When was it posted?** - Timestamp in audit trail
- **Has it been changed?** - Immutability ensures it hasn't

This creates accountability for all financial entries.

## Compliance and Regulatory

Immutability supports compliance:

**SOX Compliance (Sarbanes-Oxley):**
- Requires complete GL audit trail
- Light's immutability + audit trail provides this

**GDPR:**
- Requires proof of what data you have/had
- Immutable GL shows historical state

**Tax Audits:**
- Revenue agencies want to verify transactions
- Immutable ledger provides complete, unchangeable record

**Internal Audits:**
- Auditors verify GL hasn't been tampered with
- Immutability provides confidence

## Correcting Errors

When you discover an error in a posted accounting document:

1. **Open the accounting document** - Find the document with the error
2. **Edit the document** - Make your corrections (update amounts, GL accounts, cost centers, etc.)
3. **Save** - The system automatically reverses the original transactions and creates corrected ones
4. **Verify** - Check that the GL now reflects the correct entries

The accounting document engine handles all the reversal logic automatically, so you don't need to manually create reversing journal entries.

For prior period errors:
- Consider whether you need to correct in the original period or the current period
- Consult your accounting policies for prior period adjustments
- The system maintains full audit trail regardless of when corrections are made

## Preventing Errors in the First Place

Since errors must be reversed and corrected:

- **Validate before posting** - Check amounts and accounts carefully
- **Have someone review** - Use approval workflows
- **Test with small amount** - For new transaction types
- **Maintain good records** - Keep supporting documentation
- **Post promptly** - Don't batch old transactions; post as they occur

Prevention is better than correction.

## Clearing as a Form of Matching

Cleared transactions are still immutable:

- **Clearing** links transactions but doesn't modify them
- **Both sides remain unchanged** - Only clearing status changes
- **Clearing can be undone** - Un-clear to break the link
- **Clearing is tracked** - Audit trail shows when/who cleared

## Data Retention

Light retains all GL data:

- **Forever** - No automatic deletion of old GL data
- **Archived** - Old periods can be archived to slower storage
- **Backed up** - Regular backups ensure data isn't lost
- **Exported** - You can export GL data for external backup

Data never disappears from Light's GL.

## Best Practices for Immutable Ledgers

- **Review before posting** - Most important—prevent errors before posting
- **Use workflows** - Approval workflows catch errors before posting
- **Document corrections** - When correcting, explain why in notes
- **Reconcile frequently** - Catch errors early when easier to correct
- **Train staff** - Ensure users understand posting is permanent
- **Archive exports** - Keep offline backup of GL data
- **Review audit trail** - Periodically check for suspicious activity

## Related Articles

- [Accounting document types and lifecycle](/mnt/help-articles/articles/05-general-ledger/5-2-document-types-lifecycle.md)
- [Viewing and searching journal entries](/mnt/help-articles/articles/05-general-ledger/5-3-viewing-journal-entries.md)
- [Audit log and activity history](/mnt/help-articles/articles/03-user-management/3-6-audit-log.md)
