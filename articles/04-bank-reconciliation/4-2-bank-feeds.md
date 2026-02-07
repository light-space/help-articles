# Setting Up Bank Feeds

Bank feeds automatically import transactions from your connected bank accounts into Light. This article explains bank feed setup and management.

[Open in Light →](https://app.light.inc/bank-reconciliation)

## What is a Bank Feed?

A bank feed is an automated connection that pulls transaction data from your bank and imports it into Light. Instead of manually downloading transactions and importing them, the feed runs automatically on a schedule and new transactions appear in Light within minutes.

Bank feeds eliminate manual work, reduce errors, and enable faster reconciliation.

## Enabling Bank Feeds

Bank feeds are enabled when you authorize a bank connection:

1. Go to **Settings > Bank accounts**
2. Select a bank account
3. If status shows "Linked", the feed is active
4. Transactions will begin importing on the next sync

Most banks sync feeds daily. Some premium connections sync twice daily.

## Transaction Import Frequency

Light syncs transactions at:

**Daily** - Most common. Transactions import once per day, typically early morning

**Twice Daily** - For certain banks and account types. Provides more recent data for active accounts

You can see the next scheduled sync time in the account details. You can also manually trigger a sync by clicking **Sync Now** without waiting for the scheduled time.

## First Transaction Date

When setting up a bank feed, specify the **first transaction date**:

- **Recent date** (last 3 months) - Recommended for accounts already reconciled in your prior system
- **Early date** (full history) - Import all available history (typically 2-3 years)

Older transactions available from the bank depend on your account type and bank's retention policy.

## Transaction Reconciliation Status

Imported transactions are marked with reconciliation status:

**Unmatched** - Transaction imported but not yet matched to any accounting entry

**Matched** - Transaction matched to an AP invoice, AR invoice, payment, or other accounting entry

**Excluded** - Transaction intentionally excluded from reconciliation (e.g., bank fees, interest already recorded in GL)

You can manually change status if needed.

## Original Amount and Fees

For multi-currency transactions, Light captures:

**Original Amount** - Amount in the transaction's original currency (if different from account currency)

**Fees** - Bank fees associated with the transaction

These are tracked separately from the converted amount for accurate FX accounting.

## Transaction Metadata

Each imported transaction includes:

**Date** - When the transaction occurred

**Amount** - In the account's base currency

**Name** - Payee or sender name from the bank

**Reference** - Reference number or memo

**Transaction ID** - Unique bank identifier

This metadata helps match transactions to accounting entries.

## Manual Bank Feed Management

If you need to troubleshoot a feed:

1. Go to **Settings > Bank accounts**
2. Find the account and click **Manage Feed**
3. View feed status and history
4. Click **Sync Now** to manually trigger an import
5. View sync logs to see what transactions were imported

Feed logs show:

- **Last sync time** - When the last import ran
- **Transactions imported** - How many new transactions came in
- **Status** - Success or failure details

## Feed Connection Expiration

Bank feed connections may expire:

**Why** - Banks require periodic re-authorization for security

**Timeline** - Usually 6-12 months, varies by bank

**What happens** - Feed stops importing when expired

**How to fix** - Go to the account and click **Re-authorize**, follow the authorization flow at your bank

> Good to know: You'll receive notifications 30 days before expiration so you can re-authorize in advance.

## Handling Feed Issues

**Feed stops importing**
- Check that the connection hasn't expired
- Verify the account hasn't been disabled at the bank
- Check for notifications about the feed status

**Duplicate transactions**
- Sometimes a transaction may appear twice during sync
- Light's matching engine typically deduplicates automatically
- If duplicates remain, mark one as "Excluded"

**Missing transactions**
- Some transactions (e.g., pending, temporary holds) may not appear
- They typically post within 1-2 business days
- If a transaction is missing after 2 days, contact your bank

**Wrong amounts or descriptions**
- Bank feeds import data as-is from the bank
- If the bank shows incorrect data, contact your bank to correct it
- In Light, you can manually adjust the transaction if needed

## Multi-Currency Transaction Handling

When transactions occur in a currency different from the account:

1. Light imports the transaction amount in the original currency
2. The amount is converted to the account's base currency using the daily exchange rate
3. Both amounts are recorded for audit purposes
4. FX gain/loss is calculated if rates changed between transaction date and reconciliation

When matching to accounting entries, Light uses FX conversion to determine if amounts match despite currency differences.

## Archiving Bank Feeds

You can archive a bank feed if the account is no longer used:

1. Go to **Settings > Bank accounts**
2. Find the account and click **Actions**
3. Click **Archive Feed**
4. Confirm

Archived feeds stop importing but remain in the system for historical reference.

## Reactivating a Feed

To reactivate an archived feed:

1. Go to **Settings > Bank accounts** and find the account
2. Click **Reactivate Feed**
3. Re-authorize the bank connection
4. The feed resumes importing new transactions

## Best Practices

- **Check feed status regularly** - Ensure feeds are active and syncing
- **Re-authorize before expiration** - Don't wait until the connection drops
- **Reconcile frequently** - Weekly or daily reconciliation keeps small mismatches manageable
- **Understand your bank's sync schedule** - Know when to expect new transactions
- **Monitor fee transactions** - Some banks charge fees that need GL entries
- **Set realistic expectations** - Feeds typically import within 24 hours; some take 2-3 days

## Related Articles

- [Connecting bank accounts](/mnt/help-articles/articles/04-bank-reconciliation/4-1-connecting-bank-accounts.md)
- [Importing bank transactions](/mnt/help-articles/articles/04-bank-reconciliation/4-3-importing-transactions.md)
- [Automated bank reconciliation](/mnt/help-articles/articles/04-bank-reconciliation/4-4-automated-reconciliation.md)
- [Multi-currency reconciliation](/mnt/help-articles/articles/04-bank-reconciliation/4-7-multi-currency-reconciliation.md)
