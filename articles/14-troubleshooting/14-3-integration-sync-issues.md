# Integration Sync Issues

This article covers troubleshooting for third-party integrations with CRM systems, Slack, payment processors, and other connected services.

[Open in Light →](https://app.light.inc/dashboard)

## Integration Overview

Light connects with many external systems to automate your workflows. This article helps you troubleshoot when those integrations aren't working properly.

## General Integration Troubleshooting

### Checking Integration Status

1. Go to **Settings** > **Integrations**
2. Review the list of connected apps
3. A **green checkmark** or "Connected" status means it's working
4. A **red icon** or "Error" status indicates a problem
5. Click the integration to view detailed status and logs

### Common Integration States

- **Connected**: Integration is active and syncing
- **Disconnected**: Integration was disconnected; needs reconnection
- **Error**: Last sync failed with an error
- **Pending**: Integration is being set up; initial sync in progress
- **Disabled**: Integration is turned off

## Issue 1: Slack Integration Not Responding

### Symptoms

- @Light bot doesn't respond in Slack
- Messages to Light are ignored
- "Bot not found" error appears

### Solutions

1. **Verify Bot Is in Channel**:
   - Open the Slack channel where you're trying to use Light
   - Click channel name at top
   - Look for Light in the members list
   - If missing, click **Add Members** and add Light
2. **Use Correct Mention**:
   - Type exactly: **@Light** (capital L)
   - Incorrect capitalization or spacing won't work
   - Use single space between @ and Light
3. **Check Bot Permissions**:
   - Go to your Slack workspace settings
   - Click on Light's app
   - Verify it has permission to read and respond in channels
   - Enable missing permissions
4. **Reinstall Slack Integration**:
   - Go to Light > **Settings** > **Integrations** > **Slack**
   - Click **Disconnect**
   - Click **Connect to Slack** again
   - Authorize Light to access your Slack workspace
   - The bot should now respond
5. **Check Slack Workspace**:
   - Verify Light is installed in the right Slack workspace
   - Go to **App Directory** in Slack
   - Search for Light
   - If not there, install it first

> Tip: Direct messages to @Light sometimes work better than channel mentions if channel mentions are failing.

## Issue 2: CRM Sync Not Working

### Symptoms

- Customer or deal data not syncing from CRM
- Light shows old data from days ago
- Salesforce/HubSpot changes don't appear in Light

### Solutions

1. **Verify Sync Is Enabled**:
   - Go to **Settings** > **Integrations** > **[CRM Name]**
   - Check if sync is toggled **On**
   - If off, click to enable
2. **Check Sync Frequency**:
   - Syncs may be scheduled for specific times
   - Review sync settings to see when sync runs
   - If last sync was many days ago, manual sync needed
3. **Manually Trigger Sync**:
   - Click the CRM integration
   - Look for **Sync Now** or **Force Sync** button
   - Click it to immediately sync latest data
   - Wait a few minutes for sync to complete
4. **Verify API Connection**:
   - Click the integration to view connection status
   - If showing error, credentials may have expired
   - Click **Reconnect** to re-authenticate with your CRM
   - Sign in with your CRM account again
5. **Check Permissions**:
   - The CRM integration needs specific permissions
   - Go to your CRM account settings
   - Verify Light's connected app has necessary permissions
   - Grant any missing permissions
6. **Review Sync Logs**:
   - Click the integration to view error logs
   - Logs show specific reasons for sync failures
   - Common issues include permission errors or API limits

## Issue 3: Payment Processor Webhook Not Firing

### Symptoms

- Payments show in processor but not in Light
- Light doesn't get notified of new transactions
- "Webhook error" appears in integration logs

### Solutions

1. **Verify Webhook Is Enabled**:
   - Go to **Settings** > **Integrations** > **[Payment Processor]**
   - Check webhook configuration
   - Ensure webhook URL is correct
   - Webhook should be marked as active
2. **Test Webhook Connection**:
   - Most processors have a "Test Webhook" option
   - Click the test button to verify connection
   - If test fails, check URL and try again
3. **Check Light's Webhook URL**:
   - Copy the webhook URL shown in Light
   - Go to your payment processor settings
   - Verify the URL in processor matches Light's URL exactly
   - URLs are case-sensitive
4. **Verify Webhook Events**:
   - In processor settings, verify which events trigger webhook
   - Ensure payment events are enabled
   - Some processors require specific event selection
5. **Reconnect Integration**:
   - If webhooks keep failing, disconnect and reconnect
   - Go to **Settings** > **Integrations**
   - Click **Disconnect** on the processor
   - Click **Connect** to set up fresh
   - Verify webhook is automatically configured
6. **Check Firewall**:
   - Your company's firewall may block processor webhooks
   - Ask IT to whitelist the payment processor's IP addresses
   - Some processors publish their IP ranges
   - Allow inbound webhooks from processor domain

## Issue 4: Currency or Amount Conversion Issues

### Symptoms

- Amounts appear in wrong currency
- Currency conversion rate looks incorrect
- "Currency mismatch" errors appear

### Solutions

1. **Check Account Currency Settings**:
   - Verify the account/integration currency is correct
   - Go to **Settings** > **Integration** > **Currency**
   - Select the correct currency
   - Save changes and resync
2. **Verify Exchange Rate Source**:
   - Light uses market exchange rates
   - Historical transactions use rates from transaction date
   - Check if conversion rate matches your expectations
   - If consistently off, contact support
3. **Review Transaction Details**:
   - Some transactions are multi-currency
   - Check if amount in original currency is correct
   - Conversion may be from another currency, not your base
4. **Reconcile Manually**:
   - If conversion is wrong, create adjusting journal entry
   - Record currency gain/loss
   - Match against bank balance
5. **Contact Processor**:
   - Verify the processor is reporting amounts in the right currency
   - Some processors have currency settings
   - Ensure processor is set to your company's currency

## Issue 5: Duplicate Entries After Sync

### Symptoms

- Same transaction appears multiple times after sync
- Data duplication increases with each sync
- Can't tell which record is original

### Solutions

1. **Identify Duplicates**:
   - Look at transaction dates and amounts
   - Same transaction usually has similar timestamps
   - Check if amounts, dates, and descriptions match
2. **Delete Obvious Duplicates**:
   - Look at sync logs to identify duplicate
   - Keep the more complete/accurate record
   - Delete the duplicate
   - This prevents future duplication
3. **Check Sync Deduplication**:
   - Some integrations deduplicate automatically
   - Go to **Settings** > **Integration** > **Sync Options**
   - Verify deduplication is enabled
   - Resync to apply deduplication
4. **Review Sync Mapping**:
   - Integration may be mapping fields incorrectly
   - Click integration to check field mapping
   - Ensure key fields (ID, date, amount) map correctly
   - Fix mapping if needed and resync
5. **Reset and Sync**:
   - If duplication is widespread
   - Go to **Settings** > **Integration**
   - Click **Clear History** or **Reset**
   - Reconnect and perform fresh sync
   - This clears duplicates from history

## Issue 6: Data Not Appearing in Light

### Symptoms

- Connected system has data but it's not in Light
- Sync completes but nothing changes
- Records from processor/CRM don't appear

### Solutions

1. **Check Sync Direction**:
   - Some integrations are one-way only
   - Go to **Settings** > **Integration**
   - Verify sync direction includes the data you need
   - If one-way, you may need to import manually
2. **Verify Permissions**:
   - Light may not have permission to access the data
   - Go to your connected system
   - Check Light's app permissions
   - Enable "read" permission for the data type
3. **Check Data Filters**:
   - Integration may be filtering what syncs
   - Go to **Settings** > **Integration** > **Filters**
   - Adjust date range or record type filters
   - Verify you're not filtering out the data
4. **Manual Trigger**:
   - Click integration and select **Sync Now**
   - Wait several minutes for sync to complete
   - If still missing, check integration logs for errors
5. **Check If Data Meets Criteria**:
   - Some integrations only sync certain records
   - Example: Only syncing paid invoices, not open ones
   - Verify your record meets the sync criteria
   - Contact support if criteria are unclear

## Issue 7: Performance Issues After Integration

### Symptoms

- Light is slower after enabling integration
- Reports are taking longer to load
- Interface is sluggish during sync

### Solutions

1. **Check Sync Load**:
   - Large syncs can temporarily slow Light
   - Go to **Settings** > **Integration** > **Sync Schedule**
   - If syncing frequently, try less frequent syncs
   - Off-peak hours: run syncs outside business hours
2. **Reduce Sync Scope**:
   - Syncing lots of historical data is heavy
   - Go to **Settings** > **Integration** > **Filters**
   - Filter to recent data only
   - Exclude unnecessary record types
3. **Split into Multiple Integrations**:
   - If syncing from one source creates bottleneck
   - Create separate connections for different data types
   - Spread syncs across different times
4. **Check Browser Performance**:
   - Clear browser cache
   - Close unnecessary tabs
   - Restart browser
   - Use modern browser (Chrome, Edge)
5. **Contact Support**:
   - If performance issues persist
   - Provide details on what's slow
   - Support can optimize integration settings

## Issue 8: Credentials Expired

### Symptoms

- Integration shows "disconnected" or "auth error"
- "Invalid credentials" message appears
- Integration stopped working after weeks of use

### Solutions

1. **Reconnect Integration**:
   - Go to **Settings** > **Integrations**
   - Find the disconnected integration
   - Click **Reconnect** or **Re-authenticate**
   - Sign in again with your connected system credentials
2. **Update Password**:
   - If you recently changed password at connected system
   - Use new password when reconnecting
   - Don't use old password
3. **Refresh OAuth Token**:
   - For OAuth-based integrations
   - Disconnect and reconnect
   - This refreshes the authorization token
   - Should resolve auth errors
4. **Check App Permissions**:
   - Go to your connected system
   - Review Light's authorized app
   - Permissions may have been revoked
   - Re-authorize Light
5. **Special Handling for Banks**:
   - API credentials for bank connections may expire
   - Review bank's connected app settings
   - Disconnect and reconnect if credentials expired

## Related Articles

- Common issues and solutions
- Bank connection troubleshooting
- Data import errors
- Contacting Light support
