# Connecting Bank Accounts

Connect your company's bank accounts to Light to enable automatic transaction feeds and reconciliation. This article covers bank account setup and the connection process.

[Open in Light →](https://app.light.inc/bank-reconciliation)

## Why Connect Bank Accounts?

Connecting bank accounts enables:

- **Automatic transaction feeds** - Bank transactions automatically import instead of manual entry
- **Bank reconciliation** - Match transactions to accounting entries
- **Real-time visibility** - See current bank balances and recent activity
- **Payment scheduling** - Use Light to initiate payments directly from your bank

Light supports connections to major banks in US, Europe, and Asia through providers like Plaid, GoCardless, Stripe and Host-to-Host (AMC) integrations.

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
   - For Swedish accounts: IBAN, BIC, and optionally **Bankgiro** (7-8 digits) - set the bank country to Sweden to reveal this field (see [Bankgiro for Swedish entities](#bankgiro-for-swedish-entities) below)
   - Bank country and currency
8. Click **Add**

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

**Plaid** (United States) - Connects to thousands of banks in the United States

**GoCardless** (Europe, UK) - Covers European and UK banks including Revolut, Wise, Starling, and traditional banks

**Stripe** (Payment Processing) - For Stripe payment accounts

**AMC** (Host-to-Host) - For banks not covered via Plaid and GoCardless - note your bank may charge you a fee for setting this up. Timeline is often 2-3 months depending on the bank. 

Not all banks support all providers e.g. J.P. Morgan and HSBC is not supported via Plaid in the US while Gocardless do not support J.P. Morgan in the UK. If your bank isn't available via your preferred provider, you can always upload the bank feed manually or inquire Light about options for Host-to-Host integration support.

## Bankgiro for Swedish Entities

Bankgiro is the primary payment method for Swedish business-to-business transactions. Swedish customers expect to see a Bankgiro number on their invoices to process payment, so adding it to your bank account lets Light display it on the documents you send.

To add a Bankgiro number:

1. Go to **Settings > Bank accounts**
2. Open the bank account you want to edit (or add a new one)
3. Set the **bank country** to Sweden — this reveals the optional **Bankgiro** field
4. Enter your **Bankgiro** number
5. Click **Save**

Once saved, update your invoice template to display the Bankgiro number on invoices. See [Invoice templates](/articles/06-accounts-receivable/6-6-invoice-templates.md) for details.

> **Note:** The Bankgiro field is optional and appears only when the bank country is set to Sweden. If you invoice internationally using BIC/IBAN only, no action is needed.

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

> Good to know: Each bank account must be mapped to its own unique ledger account code — Light will reject a ledger account code that is already in use by another bank account. Use a consistent numbering scheme (e.g., 1010, 1011, 1012 for accounts at the same bank) to keep reconciliation and reporting easy to follow.

## Account Status

Bank accounts can be:

**Active** - Enabled and visible for transactions

**Inactive** - Disabled and hidden from most screens

**Expired** - Bank feed connection has expired (re-authorize required)

If a connection expires (your bank requires periodic re-authorization), you'll see a notification to re-authorize.

## Editing Bank Account Names

To change the display name of a bank account in Light:

1. Go to **Settings > Bank accounts**
2. Open the bank account you want to rename
3. Update the **Name** field
4. Click **Save**

The updated name will appear in bank reconciliation and throughout Light.

> Note: The bank account name is separate from the label of its linked ledger account. Renaming the ledger account in **Chart of accounts** changes how it appears in your financial records, but the bank account name shown in bank reconciliation is managed in Settings > Bank accounts.

## Re-authorizing Bank Feeds

Bank feed authorizations may expire after a period set by your bank (for example, UK banks limit access to a maximum of 90 days per authorization):

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

**"Connection succeeded but no transactions appear"** - Bank feeds sync on a schedule (daily or twice a day depending on the feed), so it can take up to a day for the first transactions to appear. If it takes longer, check that your account has recent activity and the connection status shows "Linked".

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
