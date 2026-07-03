# Integration Sync Issues

This article covers troubleshooting for third-party integrations with CRM systems, Slack, payment processors, and other connected services.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration Overview

Light connects with many external systems to automate your workflows. This article helps you troubleshoot when those integrations aren't working properly.

## General Integration Troubleshooting

### Checking Integration Status

1. Go to **Settings** > **Integrations**
2. Review the list of connected apps
3. A **green checkmark** or "Connected" status means it's working
4. A **red icon** or "Error" status indicates a problem
5. Click the integration to view detailed status

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

1. **Verify Your Email Matches**:
   - Light identifies you by matching your Slack account's email address to your Light user email
   - If the email on your Slack profile differs from the email you use to sign in to Light, the bot cannot resolve your user and won't respond
   - Update one of the emails so they match, or ask your admin to check
2. **Verify Bot Is in Channel**:
   - Open the Slack channel where you're trying to use Light
   - Click channel name at top
   - Look for Light in the members list
   - If missing, click **Add Members** and add Light
3. **Use Correct Mention**:
   - Type exactly: **@Light** (capital L)
   - Incorrect capitalization or spacing won't work
   - Use single space between @ and Light
4. **Check Bot Permissions**:
   - Go to your Slack workspace settings
   - Click on Light's app
   - Verify it has permission to read and respond in channels
   - Enable missing permissions
5. **Reinstall Slack Integration**:
   - Go to Light > **Settings** > **Integrations** > **Slack**
   - Click **Disconnect**
   - Click **Connect to Slack** again
   - Authorize Light to access your Slack workspace
   - The bot should now respond
6. **Check Slack Workspace**:
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
2. **Know the Sync Schedule**:
   - Sync schedules are managed by Light and are not configurable per company
   - Salesforce syncs run automatically roughly every 20 minutes
   - HubSpot imports run once per hour, and exports to HubSpot run once per hour on a separate schedule
   - If data is older than that, trigger a manual sync or check the connection
3. **Manually Trigger Sync**:
   - For Salesforce, open the integration and trigger a manual sync to immediately import the latest data
   - For HubSpot, manual syncs can only be run by Light — contact support if you need one
   - Wait a few minutes for the sync to complete
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
6. **Review Workflow Runs**:
   - CRM records are processed through workflows (for example, Salesforce deals are turned into contracts by a workflow)
   - Go to **Settings** > **Workflows** and open the relevant workflow to review its runs
   - Failed runs show the specific reason a record didn't sync, such as permission errors or API limits

## Issue 3: Payment Processor Webhook Not Firing

### Symptoms

- Payments show in processor but not in Light
- Light doesn't get notified of new transactions

### Solutions

1. **Check Connection Status**:
   - Go to **Settings** > **Integrations** > **[Payment Processor]**
   - Verify the connection shows as active
   - Webhooks are configured automatically by Light when you connect — there is no webhook URL to set up or maintain yourself
2. **Verify the Event Exists in the Processor**:
   - Check the processor's own dashboard to confirm the payment or event actually occurred
   - Light receives events as they happen after the integration is connected; records created before connecting may not appear automatically
3. **Reconnect Integration**:
   - If events stop arriving, disconnect and reconnect
   - Go to **Settings** > **Integrations**
   - Click **Disconnect** on the processor
   - Click **Connect** to set up fresh and re-authorize Light
4. **Contact Support**:
   - If events are confirmed in the processor but still missing in Light, contact support
   - Include the transaction ID and approximate time so the delivery can be traced

## Issue 4: Currency or Amount Conversion Issues

### Symptoms

- Amounts appear in wrong currency
- Currency conversion rate looks incorrect
- "Currency mismatch" errors appear

### Solutions

1. **Check Entity Currency Settings**:
   - Verify your entity's base currency is correct under **Settings** > **Entities**
   - Amounts from integrations are recorded in their original currency and converted to your base currency
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
   - Keep the more complete/accurate record
   - Delete the duplicate
3. **Contact Support**:
   - Light's integrations match records against their ID in the source system, so duplicates should not normally occur
   - If duplication is widespread or keeps recurring after cleanup, contact support with example records

## Issue 6: Data Not Appearing in Light

### Symptoms

- Connected system has data but it's not in Light
- Sync completes but nothing changes
- Records from processor/CRM don't appear

### Solutions

1. **Check Sync Direction**:
   - Some integrations sync one way only, or have separate import and export directions (for example, HubSpot)
   - Verify the direction you need is enabled on the integration
   - If one-way, you may need to import manually
2. **Verify Permissions**:
   - Light may not have permission to access the data
   - Go to your connected system
   - Check Light's app permissions
   - Enable "read" permission for the data type
3. **Review Workflow Runs**:
   - Imported records are processed through workflows before they appear in Light
   - Go to **Settings** > **Workflows** and check the runs for the relevant workflow
   - A failed or skipped run explains why a record didn't appear
4. **Manual Trigger**:
   - For Salesforce, trigger a manual sync from the integration
   - Wait several minutes for sync to complete
   - If still missing, check the workflow runs for errors
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

1. **Allow Initial Syncs to Finish**:
   - Syncs run in the background on Light's servers on fixed schedules
   - A large initial import can take a while to process; data appears progressively
   - Sync schedules and scope are managed by Light and are not configurable per company
2. **Check Browser Performance**:
   - Clear browser cache
   - Close unnecessary tabs
   - Restart browser
   - Use modern browser (Chrome, Edge)
3. **Contact Support**:
   - If performance issues persist
   - Provide details on what's slow

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
