# Bank Connection Troubleshooting

This article covers the most common bank connection problems and how to fix them.

[Open in Light →](https://app.light.inc/settings/bank-accounts)

## Overview

Light connects to your bank through secure APIs to automatically sync transactions. When connections fail, Light shows warning icons and explains the issue. This article helps you diagnose and resolve common bank connection problems.

## General Bank Connection Status

### Checking Connection Status

1. Go to **Settings** (gear icon) → **Bank accounts**
2. Look for your account in the list
3. A **green checkmark** means the connection is working
4. A **red warning icon** means there's a problem
5. Click the account to see the detailed status message

### Common Status Messages

- **Linked**: The bank connection is active and syncing normally
- **Expired**: The connection's authorization has expired; renew the connection to resume syncing
- **Active** / **Inactive** (feed status): Light automatically sets a bank feed to Inactive when the provider reports an error for that account

> Note: Only company admins can manage bank connections.

## Issue 1: Authentication Failed

### Symptoms

- Connection status shows "Expired"
- Transactions stopped syncing
- Red error icon on bank account

### Solutions

1. **Renew the Connection**:
   - Click the bank account with the error
   - Click **Renew connection**
   - This opens a secure connection to your bank
2. **Re-enter Bank Credentials**:
   - Log in with your current bank username and password
   - If you've changed your password, use the new one
   - Complete any multi-factor authentication your bank requires
3. **Check Bank Login**:
   - Verify you can log into your bank's website directly
   - If you can't log in at the bank, reset your password there first
   - Then reconnect in Light
4. **Update Contact Information**:
   - Your bank may need current contact info
   - Update phone number or email at your bank
   - Retry the reconnection in Light

> Tip: Your bank password is never stored in Light. Only the authentication token is saved, and it expires regularly requiring re-authentication.

> Note: For Stripe bank connections, if authentication fails with a permission error (e.g., "You don't have the required permission type"), Light automatically marks the connection as "expired" and stops retrying sync attempts. Follow the reconnection flow above to resolve—you may need to regenerate your Stripe API credentials or verify API permissions in your Stripe account settings.

> Note: If any bank feed under a connection shows as Inactive, the **Renew connection** option becomes available right away—you don't have to wait until the connection is near expiry. Completing the renewal flow reactivates the affected feed.

## Issue 2: Connection Keeps Disconnecting

### Symptoms

- Bank account works for a few days then disconnects
- Regularly getting "reconnect required" messages
- Connection status keeps changing

### Solutions

1. **Request Bank Account Upgrade**:
   - Some banks require business accounts for API access
   - Contact your bank and request that your account be enabled for third-party access
   - Specific request: "Enable this account for third-party financial data aggregation"
2. **Verify API Access Is Enabled**:
   - Log into your bank's website
   - Go to **Settings** > **Security** or **Connected Apps**
   - Verify Light is listed and access is enabled
   - Some banks auto-disable access after inactivity
3. **Understand Sync Frequency**:
   - Light syncs bank feeds once or twice a day
   - Sync frequency is managed by Light and is not user-configurable
   - Light's sync cadence will not trigger bank security blocks on its own
4. **Contact Bank Support**:
   - Explain you're using Light (a financial management platform)
   - Ask if your account has any restrictions on third-party access
   - Request they whitelist Light's IP addresses or API integration
5. **Try Manual Import**:
   - If API connection keeps failing, use CSV import
   - Download transactions from your bank as CSV
   - Upload the CSV to the specific bank account in Light

## Issue 3: Transactions Not Syncing

### Symptoms

- Bank account is connected but no new transactions appear
- Transactions appear 1-2 weeks late
- Last sync time is old (more than 24 hours ago)

### Solutions

1. **Wait for Next Sync**:
   - Light syncs bank feeds once or twice a day
   - Allow up to 24 hours for new transactions to appear
   - Don't add transactions manually if waiting for sync
2. **Force Manual Sync**:
   - Click the account with sync issues
   - Click **Sync Now** or **Refresh**
   - Light immediately queries the bank for new transactions
   - Check back in a few minutes
3. **Verify Bank Feed Is Enabled**:
   - Log into your bank's website
   - Go to account settings
   - Verify third-party data sharing is enabled
   - Some banks require checking a consent box
4. **Check Posting Dates**:
   - Bank transactions post at different times
   - Light imports booked (posted) transactions only—pending transactions won't appear until your bank books them
   - Each sync re-checks the last 7 days, so transactions that were pending and later booked are picked up automatically
5. **Check Your Account**:
   - Verify you're connecting the right account
   - Check account number matches your bank statement
   - Ensure it's a transaction account (not savings-only)

## Issue 4: Wrong Transactions Appearing

### Symptoms

- Seeing transactions from a different account
- Seeing transactions from different time period
- Duplicate transactions appearing

### Solutions

1. **Verify Account Connection**:
   - Click the account showing wrong transactions
   - Note the account number and type shown
   - Compare to your actual bank account
   - Reconnect if you're connected to the wrong account
2. **Duplicates Are Handled Automatically**:
   - During bank feed imports, Light detects duplicate transactions and marks them as Excluded automatically
   - You don't need to delete duplicates manually
   - If you spot a duplicate that wasn't excluded, contact Light support
3. **Check Filters**:
   - You may be filtering to wrong account
   - Go to **Bank Accounts** and click the right account
   - Verify you're looking at the account you want
4. **Sync with Recent Statement**:
   - Review your actual bank statement
   - Reconcile against what appears in Light
   - Identify missing or extra transactions
   - Contact Light support with discrepancies

## Issue 5: Bank Credentials Keep Asking for Re-entry

### Symptoms

- Constantly prompted to "reconnect" or re-enter credentials
- Connection works briefly then requires re-authentication
- Error about expired credentials appears frequently

### Solutions

1. **Check Password Expiration**:
   - Your bank may auto-expire passwords
   - Log into your bank directly
   - If prompted for password change, do it
   - Then reconnect in Light
2. **Disable Auto-Logout**:
   - Some banks auto-logout after inactivity
   - In your bank's settings, disable auto-logout if available
   - This allows Light to maintain connection longer
3. **Check for Active Sessions**:
   - You may have multiple active login sessions
   - Log out from all devices except the one using Light
   - Retry connection in Light
4. **Use App-Specific Password** (if available):
   - Some banks support app-specific passwords for third-party access
   - Create an app password for Light instead of using main password
   - Use this app password when reconnecting Light
   - This prevents your main password from being a friction point

> Note: For UK banks connected through open banking, bank authorizations are capped at 90 days by regulation. After 90 days the connection shows as "Expired" and must be renewed—this is expected behavior, not an error.

## Issue 6: Bank Feed Doesn't Cover Entire Date Range

### Symptoms

- Transactions only showing for last 90 days
- History before 3 months ago isn't syncing
- "Transaction history limited" message appears

### Solutions

1. **Understand Bank Limitations**:
   - Most banks limit how far back they provide transaction data
   - Typically 90 days to 2 years back
   - This is a bank limitation, not Light's
2. **Request Extended History**:
   - Contact your bank
   - Ask if they can provide longer transaction history
   - Some business accounts provide longer history
3. **Import Historical Data Manually**:
   - Download historical transactions from bank as CSV
   - Go to **Settings** (gear icon) → **Bank accounts** and select the account
   - Upload the file with older transactions to that account
   - Light imports and reconciles them
4. **Check Account Age**:
   - If account is recently opened, less history may be available
   - New accounts typically don't have historical data available
   - As account ages, banks may provide more history

## Issue 7: Multi-Currency Issues

### Symptoms

- Wrong currency showing for transactions
- Currency conversion rate seems off
- Amounts don't match after currency conversion

### Solutions

1. **Verify Account Currency**:
   - Click the bank account
   - Check what currency is set for the account
   - If wrong, edit and set correct currency
   - Reconnect the account
2. **Check Bank Configuration**:
   - Your bank may provide transactions in one currency but your account is another
   - Review your bank account settings
   - Verify the currency matches what Light shows
3. **Review Conversion Rates**:
   - Light uses current market rates
   - Historical transactions use rates at transaction time
   - If rates seem off, check against currency rate provider
4. **Manual Adjustment**:
   - If conversion is systematically wrong, create adjusting entry
   - Post a journal entry for the currency adjustment
   - Reconcile against the adjusted amount

## Issue 8: Bank Maintenance or Outages

### Symptoms

- Sync fails with message about bank maintenance
- Error message indicates bank is unavailable
- Multiple reconnection attempts fail

### Solutions

1. **Verify Bank Status**:
   - Visit your bank's website
   - Look for service status or maintenance notifications
   - Check the bank's Twitter or status page
2. **Wait for Maintenance Window**:
   - Bank maintenance typically lasts a few hours
   - Light will automatically retry sync
   - No action needed on your part
3. **Temporary Workaround**:
   - If you need transactions urgently
   - Download CSV from bank and import manually
   - This gets transactions into Light immediately
4. **Contact Bank If Prolonged**:
   - If maintenance lasts more than 24 hours, contact bank
   - Ask for estimated time to restoration
   - Request expedited service if possible

## Issue 9: Rate Limiting or API Throttling

### Symptoms

- Sync fails with an error mentioning "too many requests"
- Syncs keep failing with throttling message

### Solutions

1. **Avoid Repeated Manual Syncs**:
   - Light's automatic syncs run only once or twice a day, which stays within provider limits
   - Repeatedly triggering manual syncs can contribute to rate limits
   - Wait for the automatic sync instead of forcing repeated manual syncs
2. **Wait for Automatic Retry**:
   - Light automatically retries at the next scheduled sync
   - Don't manually retry repeatedly (makes it worse)
3. **Contact Bank**:
   - Some banks have tiered rate limits based on account type
   - Ask your bank if business account has higher limits
   - Upgrade account type if needed
4. **Switch to Manual Import**:
   - If API rate limits are blocking sync
   - Use CSV import instead
   - Download a CSV from your bank and import it manually as needed

## Issue 10: Still Having Trouble?

If these solutions don't fix your bank connection:

1. **Gather Information**:
   - Note the exact error message
   - Write down when the problem started
   - Screenshot the connection status page
2. **Contact Your Bank**:
   - Confirm they support third-party integration
   - Ask if there are any blocks or restrictions
   - Verify API access is enabled for your account
3. **Contact Light Support**:
   - See "Contacting Light Support" article
   - Provide bank name and error message
   - Include screenshots of the error

## Related Articles

- Common issues and solutions
- Integration sync issues
- Data import errors
- Contacting Light support