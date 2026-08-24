# Integration Sync Issues

This article covers troubleshooting for third-party integrations with CRM systems, Slack, payment processors, and other connected services.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration Overview

Light connects with many external systems to automate your workflows. This article helps you troubleshoot when those integrations aren't working properly.

## General Integration Troubleshooting

### Checking Integration Status

1. Go to **Settings (gear icon) → Integrations**
2. Review the list of connected apps
3. Each integration shows its own status label, and the exact wording varies by integration. In general, a status like "Active" means it's working, while a status like "Not connected," "Expired," or "Action required" indicates a problem
4. Click the integration to view detailed status

### Common Integration States

Status labels are specific to each integration rather than a single shared set. For example:

- **Salesforce, Slack, Teams, Gmail**: Active / Not connected
- **HubSpot or Salesforce**: Active / Pending sync / Not connected
- **Bank connections**: Active / Expired
- **Airwallex**: Active / Inactive / Action required
- **Stripe**: renders several states, including Disconnected, depending on the state of the connection
- **HRM (via Finch)**: Active

Check the specific integration's status label in your Light account rather than assuming a universal set of states.

## Issue 1: Slack Integration Not Responding

> Applies to: Slack

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
   - Click the channel name at top
   - Look for Light in the members list
   - If missing, add Light to the channel from Slack's own channel members panel
3. **Mention the Bot**:
   - Type **@Light** to mention the bot
   - If autocomplete doesn't find it, confirm Light is a member of the channel (see step 2)
4. **Check Bot Permissions in Slack** (admin required):
   - Go to your Slack workspace settings
   - Click on Light's app
   - Verify it has permission to read and respond in channels
   - Enable missing permissions
5. **Re-authenticate the Slack Integration in Light** (admin required):
   - Go to **Settings (gear icon) → Integrations → Slack**
   - Click **Re-authenticate**
   - Authorize Light to access your Slack workspace again
   - The bot should now respond
6. **Check Slack Workspace** (admin required):
   - Verify Light is installed in the right Slack workspace
   - Go to **App Directory** in Slack
   - Search for Light
   - If not there, install it first

> Tip: Direct messages to @Light sometimes work better than channel mentions if channel mentions are failing.

## Issue 2: CRM Sync Not Working

> Applies to: Salesforce, HubSpot

### Symptoms

- Customer or deal data not syncing from CRM
- Light shows old data from days ago
- Salesforce/HubSpot changes don't appear in Light

### Solutions

1. **Verify Sync Is Enabled**:
   - Go to **Settings (gear icon) → Integrations → Salesforce** or **HubSpot**
   - Check if sync is toggled **On**
   - If off, click to enable
2. **Know the Sync Schedule**:
   - Sync schedules are managed by Light and are not configurable per company
   - Salesforce syncs run automatically roughly every 20 minutes
   - HubSpot imports run once per hour, and exports to HubSpot run once per hour on a separate schedule
   - If data is older than that, trigger a manual sync or check the connection
3. **Verify API Connection**:
   - Click the integration to view connection status
   - If showing error, credentials may have expired
   - Click **Delete connection**, then reconnect and sign in with your CRM account again — this effectively re-authenticates the integration
4. **Check Permissions**:
   - The CRM integration needs specific permissions
   - Go to your CRM account settings
   - Verify Light's connected app has necessary permissions
   - Grant any missing permissions
5. **Review Workflow Runs**:
   - CRM records are processed through workflows (for example, Salesforce deals are turned into contracts by a workflow)
   - Go to **Settings (gear icon) → Workflows** and open the relevant workflow to review its runs
   - A failed run currently shows only a **Failed** status; the specific reason isn't displayed in that view. Contact support if you need help diagnosing why a record didn't sync

## Issue 3: Payment Processor Webhook Not Firing

> Applies to: Stripe

### Symptoms

- Payments show in processor but not in Light
- Light doesn't get notified of new transactions

### Solutions

1. **Check Connection Status**:
   - Go to **Settings (gear icon) → Integrations → Stripe**
   - Verify the connection shows as active
   - Webhooks are configured automatically by Light when you connect — there is no webhook URL to set up or maintain yourself
2. **Verify the Event Exists in the Processor**:
   - Check the processor's own dashboard to confirm the payment or event actually occurred
   - Light receives events as they happen after the integration is connected; records created before connecting may not appear automatically
3. **Reset the Connection**:
   - If events stop arriving, the connection may need to be refreshed
   - Go to **Settings (gear icon) → Integrations**
   - For Stripe, click **Disconnect** if you connected via Stripe Connect (OAuth), or **Delete connection** if you connected with an API key — then reconnect
   - Reconnecting re-authorizes Light and restarts webhook delivery
4. **Contact Support**:
   - If events are confirmed in the processor but still missing in Light, contact support
   - Include the transaction ID and approximate time so the delivery can be traced

## Issue 4: Duplicate Bank Entries After Sync

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

## Issue 5: Data Not Appearing in Light

> Applies to: HubSpot (import/export direction), Salesforce (manual sync trigger); general steps apply to all integrations

### Symptoms

- Connected system has data but it's not in Light
- Sync completes but nothing changes
- Records from processor/CRM don't appear

### Solutions

1. **Check Sync Direction**:
   - Some integrations sync one way only, or have separate import and export directions (for example, HubSpot)
   - Import and export are set up as part of the integration's workflows rather than as independent on/off toggles, so check the relevant workflow to see which direction is active
   - If one-way, you may need to import manually
2. **Verify Permissions**:
   - Light may not have permission to access the data
   - Go to your connected system
   - Check Light's app permissions
   - Enable "read" permission for the data type
3. **Review Workflow Runs**:
   - Imported records are processed through workflows before they appear in Light
   - Go to **Settings (gear icon) → Workflows** and check the runs for the relevant workflow
   - A failed or skipped run indicates why a record didn't appear, though the workflow list currently shows only a Failed status without a detailed reason. Contact support for more detail if needed
4. **Manual Trigger**:
   - For Salesforce, trigger a manual sync from the integration
   - Wait several minutes for sync to complete
   - If still missing, check the workflow runs for errors
5. **Check If Data Meets Criteria**:
   - Some integrations only sync certain records
   - Example: Only syncing paid invoices, not open ones
   - Verify your record meets the sync criteria
   - Contact support if criteria are unclear

## Issue 6: Performance Issues After Integration

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

## Issue 7: Credentials Expired

> Applies to: all integrations; bank connections have additional handling, see step 5

### Symptoms

- Integration shows "disconnected" or "auth error"
- "Invalid credentials" message appears
- Integration stopped working after weeks of use

### Solutions

1. **Reset the Connection**:
   - Go to **Settings (gear icon) → Integrations**
   - Find the affected integration
   - For Slack, Teams, and HRM (Finch), click **Re-authenticate**
   - For other integrations (Salesforce, HubSpot, Gmail, Stripe, Airwallex, bank feed connections via GoCardless or Plaid), click **Delete connection**, then reconnect
   - Sign in again with your connected system credentials
2. **Update Password**:
   - If you recently changed your password at the connected system, use the new password when reconnecting
3. **Refresh OAuth Token**:
   - For OAuth-based integrations, re-authenticate (Slack, Teams, HRM) or delete and reconnect (other integrations)
   - This refreshes the authorization token and should resolve auth errors
4. **Check App Permissions**:
   - Go to your connected system
   - Review Light's authorized app
   - Permissions may have been revoked — re-authorize Light
5. **Special Handling for Banks**:
   - API credentials for bank connections may expire due to the bank's permissions
   - Review the bank's connected app settings
   - Delete the connection and reconnect if credentials expired

## Issue 8: Sync Stalls or Records Don't Sync, No Error Shown

> Applies to: HubSpot, Salesforce

### Symptoms

- HubSpot sync runs on schedule but no new records appear, and the same old data keeps showing up run after run
- For Salesforce, most records sync fine but a handful never appear in Light, with no visible error message
- The stalled point or the affected records stay consistent across syncs, not random

### Solutions

1. **Contact Support**:
   - A HubSpot sync can occasionally stall on a specific record type, and a Salesforce record with invalid, missing, or unexpected data can sometimes block itself, and occasionally nearby records, from syncing
   - Contact support with the affected integration and the specific records or approximate time it stalled, so it can be checked
2. **Fix the Underlying Record**:
   - If support identifies a specific problem record or field, correct or remove it at the source
   - Trigger a manual sync (Salesforce) or wait for the next scheduled run to confirm the fix took effect

## Issue 9: Deleted Records Still Appear in Light

> Applies to: Salesforce, HubSpot

### Symptoms

- A record was deleted in the CRM but is still visible in Light
- Deleting data at the source doesn't remove it from Light

### Solutions

1. **Understand the Current Behavior**:
   - CRM syncs currently sync based on when a record was last modified, and deletions at the source may not be reflected in Light
   - A deletion in the CRM will not automatically remove the record from Light
2. **Remove the Record Manually**:
   - Delete the record directly in Light if it's no longer needed
   - There's no automatic cleanup for source-side deletions — treat this as an expected limitation rather than a sync error

## Issue 10: Integration Silently Stops Working

> Applies to: bank connections, Stripe, HRM (Finch)

### Symptoms

- An integration (bank, Stripe, HRM/Finch, or similar) was working fine, then data quietly stops appearing
- No error was shown to the user at the time it stopped
- Discovered only when checking Light after several days

### Solutions

1. **Check for an Expired Connection**:
   - Bank connections, Stripe, and HRM (Finch) connections can expire or lapse without a proactive notification to the user
   - Go to **Settings (gear icon) → Integrations** and check the integration's status for an expired, inactive, or action-required state
2. **Reset the Connection**:
   - For HRM (Finch), click **Re-authenticate**
   - For bank connections and Stripe, click **Delete connection**, then reconnect and sign in again — remember to check the cut-off date for when the new bank feed needs to flow from
   - Consider periodically checking integration status for accounts where timely data matters

## Issue 11: Second Slack Workspace Overwrites the First

> Applies to: Slack

### Symptoms

- Connecting Light to a new Slack workspace causes the bot to stop responding in the original workspace
- Only one Slack workspace ever seems to be connected, even after connecting a second

### Solutions

1. **Know the Limitation**:
   - Light currently supports connecting one Slack workspace per company; connecting a second workspace replaces the stored connection for the first
   - This is expected behavior, not an error
2. **Reconnect the Workspace You Need**:
   - If you need to switch back, go to **Settings (gear icon) → Integrations → Slack** and re-authenticate with the workspace you need
   - If you need Light active in multiple Slack workspaces simultaneously, contact support to discuss options

## Issue 12: Syncs or Notifications Fail Under Heavy Load

> Applies to: Salesforce, HubSpot, Slack

### Symptoms

- Syncs or Slack notifications fail intermittently during very large bulk operations
- Errors appear more often during large imports or unusually busy periods

### Solutions

1. **Stagger Large Operations**:
   - Very large bulk imports or exports can occasionally slow down syncing
   - Where possible, stagger large operations rather than running them all at once
2. **Retry Later**:
   - If a sync or notification fails during a high-traffic period, wait and trigger it again once load has decreased
3. **Contact Support**:
   - If failures during normal (non-bulk) usage are frequent, contact support so the affected integration can be reviewed

## Related Articles

- [Common issues and solutions](14-1-common-issues.md)
- [Bank connection troubleshooting](14-2-bank-connection-issues.md)
- [Data import errors](14-4-data-import-errors.md)
- [Contacting Light support](14-5-contacting-support.md)
