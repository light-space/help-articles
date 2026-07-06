# Setting Up Bank Feeds

Bank feeds automatically import transactions from your connected bank accounts into Light. This article explains bank feed setup and management.

[Open in Light →](https://app.light.inc/bank-reconciliation)

## What is a Bank Feed?

A bank feed is an automated connection that pulls transaction data from your bank and imports it into Light. Instead of manually downloading transactions and importing them, the feed runs automatically on a schedule and new transactions appear in Light after each sync.

Bank feeds eliminate manual work, reduce errors, and enable faster reconciliation.

## Enabling Bank Feeds

Bank feeds are enabled when you authorize a bank connection:

1. Go to **Settings → Bank accounts**
2. Select a bank account
3. If status shows "Linked", the feed is active
4. Transactions will begin importing on the next sync

Feeds sync daily or twice daily, depending on the sync interval chosen for each account when the feed is set up.

## Transaction Import Frequency

Light syncs transactions at:

**Daily** - Most common. Transactions import once per day

**Twice Daily** - Provides more recent data for active accounts

You can see the sync interval in the account details. You can also manually trigger a sync by clicking **Sync Now** without waiting for the scheduled time.

## First Transaction Date

When setting up a bank feed, specify the **first transaction date**:

- **Recent date** (last 3 months) - Recommended for accounts already reconciled in your prior system
- **Early date** (full history) - Import all available history (up to 2 years for most banks; UK banks are limited to 90 days)

Older transactions available from the bank depend on your account type and bank's retention policy.

## Transaction Reconciliation Status

Imported transactions are marked with reconciliation status:

**Unmatched** - Transaction imported but not yet matched to any accounting entry

**Matched** - Transaction matched to an AP invoice, AR invoice, payment, or other accounting entry

**Excluded** - Transaction intentionally excluded from reconciliation (e.g., bank fees, interest already recorded in GL)

You can manually change status if needed.

## Original Amount and Fees

Where available (for example on Stripe feeds), Light captures:

**Original Amount** - Amount in the transaction's original currency (if different from account currency)

**Fees** - Bank fees associated with the transaction

These are tracked separately from the booked amount and are used when matching transactions.

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

1. Go to **Settings → Bank accounts**
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

**Timeline** - Varies by bank and provider; UK bank connections are limited to 90 days

**What happens** - Feed stops importing when expired

**How to fix** - Go to the account and click **Re-authorize**, follow the authorization flow at your bank

## Handling Feed Issues

**Feed stops importing**
- Check that the connection hasn't expired
- Verify the account hasn't been disabled at the bank
- Check for notifications about the feed status

**Duplicate transactions**
- Sometimes a transaction may appear twice during sync
- Light automatically detects duplicates and marks them as **Excluded**
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

1. The bank converts the amount, and the feed imports the booked amount in the account's currency
2. Where available, the original currency amount is captured as transaction metadata (provided by the feed or extracted from the transaction reference)
3. Both amounts can then be used during reconciliation

When matching to accounting entries, Light uses FX conversion to determine if amounts match despite currency differences.

## Disconnecting a Bank Feed

You can disconnect a bank feed if the account is no longer used:

1. Go to **Settings → Bank accounts**
2. Open the bank connection
3. Remove the linked account from the connection, or delete the connection entirely

Disconnecting stops future imports. Transactions that were already imported remain in Light.

## Reconnecting a Feed

To resume importing for a disconnected account:

1. Go to **Settings → Bank accounts** and find the account
2. Link the account to a bank connection again, re-authorizing the connection if needed
3. The feed resumes importing new transactions

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
