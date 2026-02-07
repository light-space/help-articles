# Connecting your first bank account

This article walks you through connecting a bank account to Light. Connected accounts enable real-time transaction visibility, automated reconciliation, and streamlined cash management.

[Open in Light →](https://app.light.inc/settings/bank-accounts)

## Before you start

You'll need:
- Administrator or Finance Manager access to Light
- Login credentials for your bank account (or authorized signatory status)
- Information about which company entity the account belongs to

Light supports multiple connection methods depending on your bank and preferences. Most banks can be connected in minutes.

## Connection methods

Light supports three primary connection methods:

**Plaid** - Covers most banks in 12+ countries including US, UK, Europe, and Canada. Fastest setup for consumer and business accounts.

**GoCardless** - Specializes in European banks and provides ACH/SEPA access.

**Stripe** - If you use Stripe for payments, connect your Stripe balance account.

**Manual** - For banks not supported by automated feeds, import bank statements as CSV files (see [Bank Imports](#) for details).

## Connect via Plaid

Plaid connects to thousands of banks worldwide. This is the recommended method for most organizations.

1. Go to **Settings (gear icon) > Bank accounts**
2. Click **+ Connect bank**
3. Select **Plaid** as the connection method
4. Choose your country
5. Search for your bank by name
6. Click your bank from the results
7. You'll be directed to your bank's login page (secure, not through Light)
8. Enter your banking credentials and approve the connection
9. Select which accounts to connect to Light (you can connect multiple)
10. Verify the account details and click **Connect**

Light will now:
- Download 90 days of transaction history immediately
- Automatically fetch new transactions daily
- Show your account balance in real-time

> **Good to know:** Plaid uses your bank's native API when available, so Light never stores your banking credentials. Your login details stay between you and your bank.

## Connect via GoCardless

For European organizations or SEPA-based payments:

1. Go to **Settings (gear icon) > Bank accounts**
2. Click **+ Connect bank**
3. Select **GoCardless** as the connection method
4. Select your country and bank
5. You'll be redirected to GoCardless (secure authentication)
6. Approve the connection and confirm the accounts you want to link
7. Click **Connect**

GoCardless provides the same transaction feed benefits as Plaid and is optimized for European banking relationships.

## Connect via Stripe

If you process payments through Stripe:

1. Go to **Settings (gear icon) > Integrations**
2. Click **Connect** next to Stripe
3. Authenticate with your Stripe account
4. Authorize Light to access your Stripe data
5. Go to **Settings (gear icon) > Bank accounts** and click **+ Connect bank**
6. Select **Stripe** and choose your Stripe account
7. Click **Connect**

Stripe will now appear as a bank account in Light with your available balance and recent transactions.

## Add account details

After connecting, provide additional information for reconciliation:

1. Click the account in **Settings (gear icon) > Bank accounts**
2. Enter:
   - **Account name** - How it appears in Light (e.g., "US Operating Account")
   - **Company entity** - Which entity owns this account
   - **Account type** - Operating, Payroll, Investment, or Other
   - **Currency** - Confirm the account currency
   - **Statements frequency** - How often the bank provides statements (monthly, daily, etc.)

3. Click **Save**

## Verify account connection

After connection, verify the data is flowing correctly:

1. Go to **Settings (gear icon) > Bank accounts > [Your account]**
2. Check:
   - **Latest balance** - Shows current available balance
   - **Last updated** - When Light last fetched transactions
   - **Recent transactions** - Shows 10 most recent transactions

3. Click on any transaction to see full details

If transactions aren't appearing after 24 hours, the bank feed may have failed. See troubleshooting below.

## Map bank accounts to GL

Bank accounts should be linked to a GL account for reconciliation:

1. Go to **Settings (gear icon) > Bank accounts > [Your account]**
2. Click **Map to GL account**
3. Select the asset account from your chart of accounts (typically a bank or cash account)
4. Click **Save**

Now when you reconcile, Light will automatically match bank transactions to GL entries posted to this account.

## Connect multiple accounts

Repeat the connection process for each bank account:

1. Different entities can have accounts at different banks
2. Multiple accounts at the same bank are supported
3. Multi-currency accounts are treated as separate accounts

Light displays all connected accounts in a centralized view, making it easy to manage cash across your organization.

## Troubleshooting connection issues

**Connection failed or timed out**
- Check your internet connection
- Some banks temporarily deny third-party connections for security. Try again in a few minutes.
- Contact your bank to ensure third-party access is enabled
- If the bank requires IP whitelisting, contact Light support for IP addresses

**Transactions aren't appearing**
- Check that the account status shows "Connected" (not "Pending" or "Error")
- Some banks take 24 hours to provide the first transaction feed
- If it's been longer than 24 hours, disconnect and reconnect the account

**Account shows balance but no transactions**
- This is normal during initial setup. Light fetches 90 days of history, which takes a few moments
- If no transactions appear after 2 hours, contact support

**Can't find my bank**
- Try searching by your bank's abbreviation (e.g., "JPM" for JPMorgan)
- Different regions may have separate entries for the same bank
- If your bank isn't listed, use manual CSV import or contact support to request Plaid coverage

**Duplicate account appears**
- If you accidentally connect the same account twice, deactivate one
- Only the most recent connection will receive transaction feeds

## Set up reconciliation

Once your account is connected:

1. Go to **Accounting > Transactions** ([Open in Light →](https://app.light.inc/ledger-transactions)) to see all imported transactions
2. Go to **Accounting > Bank reconciliation** ([Open in Light →](https://app.light.inc/bank-reconciliation)) to start matching transactions to GL entries
3. Light's AI automatically suggests matches based on amount, date, and description

See [Bank reconciliation](/bank-reconciliation) for detailed instructions on the reconciliation process.

## Next steps

With your bank account connected, you can:
- Start reconciling transactions daily
- Create invoices and bills
- Set default accounts for payments
- Monitor cash flow in real-time

## Related articles

- [Bank reconciliation](#)
- [Setting default bank accounts](#)
- [Importing bank statements](#)
- [Managing payments](#)
