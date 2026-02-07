# Common Issues and Solutions

This article covers the top 10 most common issues Light users encounter and provides straightforward solutions for each.

[Open in Light →](https://app.light.inc/dashboard)

## Issue 1: Can't Log In to Light

### Symptoms

- "Invalid credentials" error when logging in
- Password reset email not received
- Locked out after multiple login attempts

### Solutions

1. **Wrong Credentials**: Verify caps lock is off and you're entering your correct email and password
2. **Reset Password**:
   - Click "Forgot Password" on the login page
   - Enter your email address
   - Check your email (including spam folder) for reset link
   - Click the link and create a new password
3. **Account Locked**: Try again in 15 minutes (temporary lockout after 5 failed attempts)
4. **Using SSO**: If your company uses Single Sign-On, click "Sign in with SSO" instead of using password
5. **Browser Cache**: Clear browser cookies and cache, then try again

> Tip: Keep your password reset email in a safe place for future reference.

## Issue 2: Data Not Syncing from Bank

### Symptoms

- Bank transactions missing from Light
- Balance doesn't match your bank
- No new transactions for several days

### Solutions

1. **Check Connection Status**:
   - Go to **Bank Accounts**
   - Look for red warning icons next to account names
   - Click the account to view connection status
2. **Reconnect Bank Account**:
   - Click the account with sync issues
   - Select **Reconnect** or **Reauthenticate**
   - Re-enter bank login credentials through secure connection
   - Complete any multi-factor authentication
3. **Wait for Sync**:
   - Bank feeds can take 4-24 hours to sync
   - Light syncs multiple times per day
   - Don't add transactions manually if waiting for sync
4. **Check Bank Connection Limits**:
   - Some banks limit API connections
   - Contact your bank to verify they allow Light to access accounts
   - Increase connection frequency in Light settings if available
5. **Provider-Specific Issues**: See "Bank Connection Troubleshooting" article

## Issue 3: Invoices Not Extracting Data Correctly

### Symptoms

- AI parsing missed key invoice details
- Amounts extracted incorrectly
- Vendor names not recognized

### Solutions

1. **Improve Image Quality**:
   - Retake photo with better lighting
   - Ensure entire invoice is visible
   - Avoid glare or shadows
   - Keep camera steady
2. **Try Different Upload Method**:
   - If uploading a photo, try uploading a PDF instead
   - Scanned invoices often extract better than phone photos
3. **Verify Invoice Format**:
   - Standard invoice formats extract better than custom formats
   - Ensure text is horizontal (not angled)
   - Handwritten invoices may need manual entry
4. **Manually Correct After Extraction**:
   - Light learns from corrections
   - Edit extracted fields before saving
   - Future invoices from same vendor will be more accurate
5. **Contact Support for Complex Invoices**:
   - Submit sample invoices that consistently fail
   - Light support can configure custom extraction rules

## Issue 4: Expenses Missing Categories

### Symptoms

- Receipts uploaded but no category assigned
- Wrong category auto-assigned to expenses
- "Uncategorized" appears for multiple transactions

### Solutions

1. **Assign Categories Manually**:
   - Go to **Expenses**
   - Find transactions with missing or wrong categories
   - Click the category field
   - Select the correct category from dropdown
   - Save the transaction
2. **Update Merchant Recognition**:
   - Light learns merchant types from your categorizations
   - Manually assigning categories teaches the AI
   - Future purchases from same vendor will be auto-categorized correctly
3. **Check Available Categories**:
   - Your company may have custom categories
   - Ensure you're selecting from your company's defined list
   - Ask your admin if categories need to be added
4. **Bulk Update**:
   - For multiple transactions needing the same category
   - Select multiple transactions
   - Choose **Bulk Update** > **Category**
   - Select the category and apply to all

## Issue 5: Can't Find a Transaction

### Symptoms

- Transaction missing from ledger
- Search doesn't find the transaction
- Transaction appears on bank but not in Light

### Solutions

1. **Check Filters**:
   - Transactions may be filtered by date, account, or status
   - Click **Filters** and verify date range includes the transaction
   - Remove any filters restricting results
2. **Verify Account**:
   - Transaction may be in a different account than expected
   - Check all connected bank accounts
   - Look for similar amounts in different accounts
3. **Search by Reference**:
   - Use search box with invoice number or reference
   - Search by vendor name
   - Search by amount (exact or approximate)
4. **Check If Posted**:
   - Pending transactions may not appear in searches
   - Look in **Pending Transactions** section
   - Review reconciliation status
5. **Multiple Document Posting**:
   - Transaction may be in multiple places (invoice and payment)
   - Search across all document types
   - Consider filtering by document type

## Issue 6: Reconciliation Not Matching Transactions

### Symptoms

- Bank transactions won't match with accounting entries
- AI suggestions are incorrect
- Manual matches won't save

### Solutions

1. **Verify Amounts Match**:
   - Reconciliation requires amounts to balance
   - Add up accounting entries—must equal bank transaction
   - Check for bank fees or currency conversion
2. **Check Dates**:
   - Bank transactions may post after accounting entries
   - Allow 3-5 business day variance
   - Adjust dates if transaction was misdated in accounting
3. **Review Existing Matches**:
   - Transaction may already be matched
   - Search to see if it's in a reconciliation group already
   - Unmatched transactions: delete the old match first
4. **Create Supporting Documents**:
   - For unmatched bank activity, create accounting documents
   - Create journal entries for bank fees
   - Create credit memos for returns
   - Then reconcile the new documents
5. **Check Status**:
   - Verify reconciliation period is open
   - Some statuses prevent new matches
   - Ask admin to unlock reconciliation if needed

## Issue 7: Report Not Showing Expected Data

### Symptoms

- Report is blank or incomplete
- Data doesn't match what you expect
- Report hasn't updated recently

### Solutions

1. **Check Filters and Date Range**:
   - Verify report date range matches what you want
   - Remove any active filters
   - Check if filters are hiding data
2. **Verify Permissions**:
   - You may not have access to all data
   - Ask admin if you need access to restricted entities
   - Confirm you can view the accounts/departments in the report
3. **Refresh the Data**:
   - Click **Refresh** in the report header
   - Wait 30 seconds for data to reload
   - Larger reports take longer to process
4. **Check Data Entry**:
   - Data may not have been entered or posted
   - Verify transactions were posted (not still pending)
   - Confirm posting date matches report date range
5. **Change Report View**:
   - Try a different report type or format
   - Export data to Excel for manual review
   - Contact support if specific reports consistently fail

## Issue 8: Getting "Insufficient Permission" Errors

### Symptoms

- Can't access certain accounts or reports
- "Permission denied" messages
- Unable to approve or post transactions

### Solutions

1. **Verify Your Role**:
   - Click your **Profile** in top right
   - Check your assigned role
   - Certain roles have limited permissions
2. **Request Access**:
   - Contact your Light administrator
   - Ask for the specific permission you need
   - Provide business justification if needed
3. **Check Entity Access**:
   - You may have access to your role but not your entity
   - Verify you're assigned to the company/department you need
   - Ask admin to add you to the right entity
4. **Clear Browser Cache**:
   - Permissions update instantly but may not reflect immediately
   - Clear cookies and refresh page
   - Sign out and back in to pick up new permissions
5. **Temporary Delegation**:
   - Ask someone with permission to complete the action
   - Or ask approver to delegate authority to you temporarily

## Issue 9: Integration Is Not Working

### Symptoms

- Connected app doesn't sync
- Integration shows "disconnected" or "error"
- Data not flowing between systems

### Solutions

1. **Verify Integration Is Active**:
   - Go to **Settings** > **Integrations**
   - Look for your integration in the list
   - Check status indicator (green = connected, red = error)
2. **Check Credentials**:
   - Many integrations require re-authentication
   - Click the integration to view status
   - Select **Reconnect** and re-enter credentials
3. **Review Logs**:
   - Click integration to view error logs
   - Logs show specific reasons for failures
   - Common issues (rate limits, auth failures) are usually clear
4. **Check Third-Party Service**:
   - Verify the connected service is operational
   - Check third-party status page for outages
   - Some integrations require services to be up
5. **Re-enable Integration**:
   - Disable the integration
   - Wait 5 minutes
   - Re-enable it
   - Verify it reconnects properly

## Issue 10: Performance Is Slow

### Symptoms

- Pages take a long time to load
- Scrolling or typing is sluggish
- Reports take many minutes to process

### Solutions

1. **Check Your Internet**:
   - Slow internet causes slow application
   - Test your connection speed
   - Move closer to WiFi or restart modem
2. **Clear Browser Cache**:
   - Accumulated cache can slow browsing
   - Clear cache from browser settings
   - Refresh the page
   - Log out and back in
3. **Use Faster Browser**:
   - Modern browsers (Chrome, Edge, Safari) perform best
   - Avoid older browser versions
   - Update your browser to latest version
4. **Close Extra Tabs**:
   - Multiple Light tabs use more resources
   - Keep only necessary tabs open
   - Close other browser tabs to free memory
5. **Smaller Reports**:
   - Large reports with much data process slowly
   - Filter data to smaller date ranges
   - Run reports during off-peak hours
   - Contact support for persistent slow performance

## Getting More Help

If these solutions don't resolve your issue:

- See "Contacting Light Support" article
- Gather relevant information (error messages, screenshots, transaction IDs)
- Contact support through your preferred channel

## Related Articles

- Bank connection troubleshooting
- Integration sync issues
- Data import errors
- Contacting Light support
