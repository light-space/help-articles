# Immutable Ledger and Audit Trail

Light's ledger is immutable by design—once transactions post, they cannot be changed. This ensures data integrity and creates a complete audit trail. This article explains how immutability works and why it matters.

[Open in Light →](https://app.light.inc/ledger-transactions)


## What Does Immutable Mean?

Immutability means posted transactions cannot be changed or deleted:

- **No editing** - You cannot modify a posted transaction
- **No deletion** - You cannot remove a posted transaction
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

When you post a document:

1. Document status changes from DRAFT to POSTED
2. GL transactions are created in ledger_transaction_line table
3. Transactions are marked as immutable
4. System prevents any modification

If you need to change a posted transaction:

1. You cannot edit it directly
2. Instead, you create a reversing entry (opposite amounts)
3. Then create a correcting entry (if needed)
4. Both reversing and correcting are tracked and posted

## Reversals Instead of Edits

The correct way to fix a posted error:

**Wrong approach:**
- Edit the original posted transaction (not possible)

**Right approach:**
1. Create reversing entry:
   - All debits become credits, all credits become debits
   - Same GL accounts, amounts, and descriptions
   - Marked as reversing entry in system
   - Posts new entry (and system marks original as "reversed")
2. Create correcting entry:
   - New entry with correct amounts
   - Posts to same GL accounts
   - Now correct balance is restored

Example: You posted $1,000 but should have posted $1,200

```
Original entry (Posted):
  Debit: Expense 1000
  Credit: Payable 1000

Reversing entry (Posted):
  Debit: Payable 1000
  Credit: Expense 1000

Correcting entry (Posted):
  Debit: Expense 1200
  Credit: Payable 1200

Result: Net effect is Debit Expense 1200, Credit Payable 1200 (correct)
```

## Modification vs. Reversal

Light offers **modification** for posted documents:

1. Click **Modify** on a posted document
2. System automatically:
   - Reverses the original posting
   - Makes your changes
   - Re-posts with new amounts
3. Behind the scenes: Creates reversing and correcting entries
4. But presents as a single "modification" action

Modification is cleaner than manual reversals—use it when available.

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

When you discover an error:

1. **Identify the error** - Original posting was incorrect
2. **Create reversal** - If still in current period, reverse in same period
3. **Create correction** - Post correct entry
4. **Document the issue** - Add note explaining why correction was made
5. **Verify GL** - Ensure net effect is correct

For prior period errors:
- Don't reverse prior period entries
- Create correcting entry in current period
- Note that it's a prior period correction

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
