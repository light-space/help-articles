# Connecting Bank Accounts

Connect your company's bank accounts to Light to enable automatic transaction feeds and reconciliation. This article covers bank account setup and the connection process.

[Open in Light →](https://app.light.inc/bank-reconciliation)

## Why Connect Bank Accounts?

Connecting bank accounts enables:

- **Automatic transaction feeds** - Bank transactions automatically import instead of manual entry
- **Bank reconciliation** - Match transactions to accounting entries
- **Real-time visibility** - See current bank balances and recent activity
- **Payment scheduling** - Use Light to initiate payments directly from your bank

Light supports connections to major banks in US, Europe, and Asia through providers like Plaid, GoCardless, and Airwallex.

## Before You Start

Ensure you have:

- Access to the bank account online or mobile banking login
- Authority to set up third-party connections at your bank
- The bank routing number or IBAN (International Bank Account Number)
- Currency and country information for the account

## Adding a Bank Account

To add a new bank account to Light:

1. Go to **Settings > Bank accounts**
2. Click **Add Bank Account**
3. Select your **bank provider** from the list (Chase, HSBC, Deutsche Bank, etc.)
4. Choose your **company entity** (which entity owns this account)
5. Enter the **account name** (for internal reference, e.g., "US Operating Account")
6. Select the **account type** (Physical or Virtual)
7. Enter account details:
   - For IBAN accounts: IBAN and BIC
   - For US accounts: Routing number and account number
   - Bank country and currency
8. Click **Connect**

## Bank Feed Authorization

To enable automatic transaction imports, authorize Light to access your bank account:

1. After adding the account, click **Authorize Feed**
2. You're directed to your bank's secure login page
3. Log in with your online banking credentials
4. Approve Light's access request
5. You're redirected back to Light—connection is complete

> Important: Light never stores your banking password. You authenticate directly with your bank each time. Your bank shares only transaction information with Light, not passwords or credentials.

## Supported Bank Feeds

Light supports transaction feeds from:

**Plaid** (North America, Europe) - Connects to thousands of banks in US, Canada, UK, Europe

**GoCardless** (Europe, UK) - Covers European and UK banks including revolut, Wise, Starling, and traditional banks

**Stripe** (Payment Processing) - For Stripe payment accounts

**AMC** (SWIFT-based) - For banks using SWIFT payments infrastructure

Not all banks support all providers. If your bank isn't available via your preferred provider, try a different provider.

## Multi-Currency Accounts

If your account holds multiple currencies, specify the **base currency** for reporting:

1. When adding the account, select the **currency** (USD, EUR, GBP, etc.)
2. All transactions in other currencies will be converted using daily exchange rates
3. FX gains and losses are automatically calculated

The bank account is associated with one currency, but Light can match it with invoices in different currencies using FX conversion.

## Default Bank Account

For each company entity and currency, set a **default bank account** for payments:

1. Go to **Settings > Bank accounts**
2. Find an account and click **Set as Default**
3. When creating payments, this account is pre-selected

You can override the default for individual payments if needed.

## Ledger Account Mapping

Each bank account is mapped to a **ledger account** for posting to your general ledger:

1. When adding the account, specify the **ledger account** (Cash, Bank Account 1000, etc.)
2. When transactions post, they debit/credit this ledger account
3. Ensure the ledger account is a balance sheet account (Cash or Bank type)

The mapping is checked when posting—if the account doesn't exist, posting will fail.

> Good to know: Use the same ledger account for multiple bank accounts at the same bank (e.g., all Chase accounts use Checking 1010). This simplifies reconciliation and reporting.

## Account Status

Bank accounts can be:

**Active** - Enabled and visible for transactions

**Inactive** - Disabled and hidden from most screens

**Expired** - Bank feed connection has expired (re-authorize required)

If a connection expires (your bank requires periodic re-authorization), you'll see a notification to re-authorize.

## Re-authorizing Bank Feeds

Bank feed authorizations may expire after a period (6-12 months depending on the bank):

1. Go to **Settings > Bank accounts**
2. Find the account with status "Expired"
3. Click **Re-authorize**
4. Follow the authorization flow at your bank
5. Once complete, transactions will resume importing

## Disconnect a Bank Account

To stop importing from a bank account:

1. Go to **Settings > Bank accounts**
2. Find the account and click **Actions**
3. Click **Disconnect Feed**
4. Confirm—the account remains but new transactions won't import

You can re-authorize later if you change your mind.

## Troubleshooting Connection Issues

**"Cannot find my bank"** - Check that you selected the correct country and bank name. Try a different provider (Plaid vs. GoCardless).

**"Login fails at the bank"** - Ensure you're using correct credentials. Some banks require special app passwords for third-party access.

**"Connection times out"** - Try again later. Your bank's servers may be temporarily unavailable.

**"Connection succeeded but no transactions appear"** - Transactions typically appear within 1 hour. If longer, check that your account has recent activity and the connection status shows "Linked".

## Bank Account Validation

Light validates bank account details:

- **IBAN format** - Checks country code and check digits
- **Routing number** - Validates US ABA routing numbers
- **Account number length** - Ensures reasonable length for the country

Invalid account details prevent adding the account. Double-check the IBAN or routing number if validation fails.

## Best Practices

- **Connect all accounts** - Don't exclude accounts; full visibility helps reconciliation
- **Test with small amount** - If unsure about the account details, make a small test transfer first
- **Keep authorizations current** - Re-authorize before connections expire
- **Use consistent naming** - Name accounts consistently for easy identification
- **Map to correct GL accounts** - Verify ledger accounts before large transactions start flowing

## Related Articles

- [Setting up bank feeds](/mnt/help-articles/articles/04-bank-reconciliation/4-2-bank-feeds.md)
- [Importing bank transactions](/mnt/help-articles/articles/04-bank-reconciliation/4-3-importing-transactions.md)
- [Automated bank reconciliation](/mnt/help-articles/articles/04-bank-reconciliation/4-4-automated-reconciliation.md)
