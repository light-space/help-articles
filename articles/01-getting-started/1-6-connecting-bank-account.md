# Connecting your first bank account

> **What is this page about:** How to connect your first bank account to Light so you can sync transactions automatically, reconcile faster, and monitor cash in real time. Covers connecting via Plaid, GoCardless, Stripe, Airwallex, and AMC, importing statements manually via CSV, and how to map accounts to your GL for reconciliation.

> **Scope:** This guide covers connecting a bank account so its transactions flow into Light for reconciliation and cash visibility. It sets up a **read-only data feed** — it does **not** enable sending or initiating payments (including host-to-host payment files) from your bank.

## On this page

- Before you start
- Connection methods
  - Connect via Plaid
  - Connect via GoCardless
  - Connect via Stripe
  - Connect via Airwallex
  - Connect via AMC
- Import via CSV
- Manage account details
- Verify account connection
- Map bank accounts to GL
- Connect multiple accounts in Light
- Troubleshooting connection issues
  - Connection failed or timed out
  - Transactions aren't appearing
  - Account shows balance but no transactions
  - Can't find my bank
  - Duplicate account appears
- Set up reconciliation in Light
- Next steps
- Related articles

[Open in Light →](https://app.light.inc/settings/bank-accounts)

This article walks you through connecting a bank account to Light. Once an account is connected, you get real-time transaction visibility, automated reconciliation, and streamlined cash management.

## Before you start

You'll need:
- Administrator access to Light (only company admins can add bank accounts and bank connections; Controllers can view existing connections and upload CSV transactions/files, but cannot add new connections)
- Login credentials for your bank account (or authorized signatory status)
- Information about which company entity the account belongs to

Light supports several connection methods depending on your bank and preferences, and most banks connect in minutes.

**Where to start:** For your *first* live bank connection, start from **Accounting → Bank reconciliation** and click **Connect bank**. Once at least one connection exists, you can also reopen the same flow from **Settings (gear icon) → Integrations → Banks** card. (The **Add account** button under Settings → Bank accounts opens the **Add bank account** drawer — that's the manual entry point, see **Import via CSV** below.)

## Connection methods

Light supports the following bank-feed providers:

| Provider | Best for | Notes |
|---|---|---|
| **Plaid** | Most US banks | Selected via the "American banks" tile in the Connect bank modal |
| **GoCardless** | European banks | Selected via the "European banks" tile; SEPA access |
| **Stripe** | Businesses already using Stripe for payments | Selected via the "Stripe account" tile in the Connect bank modal (after adding your Stripe API key under Integrations) |
| **Airwallex** | Airwallex account holders | Added under Settings → Integrations, not through the Connect bank modal |
| **AMC** (Host-to-host) | Supported banking relationships | Selected via the "Host to Host" tile; requires setup with Light before you can connect. Connecting brings transaction data in — it does not set up outbound payments |

If your bank isn't supported by any of these live feeds, you can still bring transactions into Light manually — see **Import via CSV** below.

## Connect via Plaid

Plaid connects to thousands of banks in the United States, and it's the recommended method for US bank accounts.

**Steps:**

1. Go to **Accounting → Bank reconciliation** and click **Connect bank** (or, if you already have a connection, **Settings (gear icon) → Integrations → Banks** card)
2. In the **Select provider** step, choose the **American banks** tile (subtitle: *via Plaid*)
3. Continue to **Select data set** to search for and select your bank
4. You'll be directed to your bank's login page (secure, not through Light)
5. Enter your banking credentials and approve the connection
6. In **Data mapping**, set the sync start date and sync schedule
7. On the accounts screen that follows, use **Select GL account** to map each account to a GL account, then confirm

Light will now:
- Download 90 days of transaction history by default (you can request up to 2 years)
- Automatically fetch new transactions daily or twice a day, depending on the sync interval set for the feed
- Show your account balance and transactions in **Accounting → Bank reconciliation**

> **Good to know:** Plaid uses your bank's native API when available, so Light never stores your banking credentials. Your login details stay between you and your bank.

## Connect via GoCardless

For European organizations:

**Steps:**

1. Go to **Accounting → Bank reconciliation** and click **Connect bank** (or, if you already have a connection, **Settings (gear icon) → Integrations → Banks** card)
2. In the **Select provider** step, choose the **European banks** tile (subtitle: *via GoCardless*)
3. In **Select data set**, search for your bank using the **Search bank** field and select it
4. You'll be redirected to GoCardless (secure authentication)
5. Approve the connection and confirm the accounts you want to link
6. In **Data mapping**, set the sync start date and sync schedule
7. On the accounts screen that follows, use **Select GL account** to map each account to a GL account, then confirm

GoCardless provides the same transaction feed as Plaid and is optimized for European banking relationships.

## Connect via Stripe

If you process payments through Stripe:

**Steps:**

1. Go to **Settings (gear icon) → Integrations**
2. Click **Add new integration**
3. Choose **Add Stripe API key** and enter your Stripe API key
4. Authorize Light to access your Stripe data
5. Go to **Accounting → Bank reconciliation** and click **Connect bank** (or, if you already have a connection, **Settings (gear icon) → Integrations → Banks** card)
6. In the **Select provider** step, choose the **Stripe account** tile (subtitle: *via Stripe*)
7. Continue through **Select data set** and **Data mapping** (sync start date and schedule)
8. On the accounts screen that follows, use **Select GL account** to map your Stripe account to a GL account, then confirm

Stripe will now appear as a connected account in Light, with balances and transactions visible in **Accounting → Bank reconciliation**.

## Connect via Airwallex

**Steps:**

1. Go to **Settings (gear icon) → Integrations**
2. Click **Add new integration**
3. Choose **Airwallex**
4. Log in and authorize Light to access your Airwallex account

Once authorized, your Airwallex feed appears automatically under **Settings → Bank accounts**. It's shown read-only there — it's managed through the Airwallex integration and can't be edited from Light.

## Connect via AMC

AMC (Host to Host) isn't a self-serve connection. It requires a signed agreement with Light, and Light must enable it for your account before you can connect.

**Note:** Connecting AMC brings your bank's *transaction data into Light* for reconciliation. It does **not** set up outbound payments. Enabling payment initiation is a separate capability configured internally by Light — it is never switched on just by connecting the feed.

**Steps:**

1. Go to **Accounting → Bank reconciliation** and click **Connect bank** (or, once you already have a connection, **Settings (gear icon) → Integrations → Banks** card)
2. In the **Select provider** step, find the **Host to Host** tile (subtitle: *via AMC*)
3. If AMC hasn't been enabled for your company yet, the tile shows a **Contact Light admin** badge — clicking it opens a "Host to Host integration" dialog; reach out to your account team to set this up
4. Once enabled, continue through **Select data set** and **Data mapping** (sync start date and schedule)
5. On the accounts screen that follows, use **Select GL account** to map each account, then confirm

## Import via CSV

For banks not supported by any of the live feed providers above, you can bring in transactions manually as a bulk import rather than a live connection:

**Steps:**

1. Go to **Settings (gear icon) → Bank accounts** and click **Add account**
2. In the **Add bank account** drawer, fill in **Entity**, **Bank country**, **Name**, **Bank provider**, **Currency**, and **Ledger account code** (plus optional BIC, IBAN, or account number), then click **Add**
3. Export a statement from your bank as a CSV file
4. Import the file (see **Importing bank statements** for full details)

Unlike Plaid, GoCardless, Stripe, Airwallex, and AMC, a CSV import is a one-time upload, not an ongoing feed — you'll need to repeat the import to bring in new transactions.

## Manage account details

To review or update an account's details after it's been added:

**Steps:**

1. Click the account row in **Settings (gear icon) → Bank accounts** to open the **Edit bank account** dialog
2. Review or update:
   - **Entity** - Which company entity owns this account
   - **Name** - How it appears in Light
   - **Bank country / Bank provider** - The linked bank feed
   - **Currency** - Confirm the account currency
   - **Ledger account code** - The GL account this bank account posts to
   - Optional: **BIC**, **IBAN**, **account number**
3. Click **Save**

For Airwallex-connected accounts, these fields are read-only — they're managed through the Airwallex integration.

## Verify account connection

After connecting, verify the data is flowing correctly:

**Steps:**

1. Go to **Settings (gear icon) → Bank accounts**
2. Check the row for your account: **Entity**, **Name**, **Bank name**, **Currency**, and **BIC**/**IBAN** should all be populated
3. Confirm **Payment method** shows **Auto** for a live feed (**Manual** means it's a CSV-only account, not a live connection)
4. Make sure there's no red "Inactive: …" or "Account no longer available…" note next to the account — that indicates the feed has failed
5. Balances and transactions appear in **Accounting → Bank reconciliation**, not on this screen

If an account shows as inactive or unavailable, see troubleshooting below.

## Map bank accounts to GL

Bank accounts are linked to a GL account as part of the connect flow, not from a separate settings page:

**Steps:**

1. During **Connect bank**, after **Data mapping**, find your account in the accounts list that follows
2. Use the **Select GL account** dropdown next to each account to choose the asset account from your chart of accounts (typically a bank or cash account)
3. Confirm

Now when you reconcile, Light automatically matches bank transactions to GL entries posted to this account.

## Connect multiple accounts in Light

Repeat the connection process for each bank account:

1. Different entities can have accounts at different banks
2. Multiple accounts at the same bank are supported
3. Multi-currency accounts are treated as separate accounts

Light displays all connected accounts in a centralized view, making it easy to manage cash across your organization.

## Troubleshooting connection issues

**Connection failed or timed out?**

Start by checking your internet connection. Some banks temporarily deny third-party connections for security, so it's worth trying again in a few minutes. If it still won't connect, contact your bank to make sure third-party access is enabled on your account.

---

**Transactions aren't appearing?**

Check whether the account shows a red "Inactive: …" or "Account no longer available…" note in Settings → Bank accounts — that means the feed needs renewing. Some banks also take up to 24 hours to deliver the first transaction feed, so if it's been less than a day, give it a bit more time. If it's been longer, reconnect the feed via **Connect bank**.

---

**Account shows balance but no transactions?**

This is normal during initial setup. Light fetches 90 days of history, which takes a few moments — check **Accounting → Bank reconciliation** for balance and transaction status. Feeds refresh daily or every 12 hours, so allow at least one full sync cycle before contacting support.

---

**Can't find my bank?**

Try searching by your bank's abbreviation (e.g., "JPM" for JPMorgan) — different regions may have separate entries for the same bank. If your bank still isn't listed, use CSV import or contact support to request coverage from an additional provider.

---

**Duplicate account appears?**

If you accidentally connect the same account twice, deactivate one. Only the most recent connection will continue receiving transaction feeds.

## Set up reconciliation in Light

Once your account is connected:

**Steps:**

1. Go to **Accounting → Transactions** to see all imported transactions
2. Go to **Accounting → Bank reconciliation** to start matching transactions to GL entries
3. Light's AI automatically suggests matches based on amount, date, and description

See Bank reconciliation for detailed instructions on the reconciliation process.

## Next steps

With your bank account connected, you can:
- Start reconciling transactions daily
- Create invoices and bills
- Set default accounts for payments
- Monitor cash flow in real-time

## Related articles

- [Bank reconciliation](https://light.inc/help/bank-reconciliation/automated-reconciliation)
- [Setting default bank accounts](https://light.inc/help/bank-reconciliation/connecting-bank-accounts)
