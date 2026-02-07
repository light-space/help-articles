# Notification Preferences

This article explains how to configure alerts, set up notification channels, and manage email preferences in Light. Proper notification setup ensures you stay informed about important business events without information overload.

[Open in Light →](https://app.light.inc/settings/profile)

## Understanding notifications in Light

Light sends alerts for important events and updates across your accounting operations:

- **Transaction Approvals**: When documents await your approval
- **Period Closing**: Reminders for accounting period close tasks
- **Policy Updates**: New policies requiring acknowledgment
- **System Events**: Important system notifications and maintenance alerts
- **Compliance Alerts**: Deadline reminders for VAT returns, tax filings
- **Exception Notifications**: Unusual transactions or errors requiring attention

Notifications help you stay on top of critical business events without constantly monitoring the system.

## Notification channels

Light supports multiple notification delivery methods:

- **Email**: Traditional inbox delivery for offline awareness
- **Slack**: Real-time alerts in your Slack workspace
- **Microsoft Teams**: Notifications in your Teams channel
- **Web App**: In-app notifications visible in Light dashboard

You can enable multiple channels simultaneously and choose which notification types use which channels.

## Configuring personal notification preferences

1. Navigate to **Settings (gear icon) → Profile** ([Open in Light →](https://app.light.inc/settings/profile)) to manage notification preferences
2. You'll see sections for each notification type
3. For each notification, select:
   - **Enabled/Disabled**: Whether to receive this notification
   - **Channel**: Which delivery method (email, Slack, Teams, web app)
   - **Frequency**: When to receive (immediately, daily digest, weekly digest)
4. Click **Save Preferences**

Your preferences apply to notifications sent specifically to you based on your role and responsibilities.

## Setting up email notifications

In Notification Preferences, set Primary Email and optional Alternate Email. Select notification types to receive via email and set frequency (Immediate for urgent, Daily Digest for daily summaries, or Weekly Digest). Different notification types can have different frequencies.

## Slack integration setup

Go to Notification Preferences, click Connect Slack Workspace, and authorize Light's access. Select the default Slack channel and click Authorize. Once connected, return to preferences, select notification types for Slack, choose channels for each type (you can customize per notification type), and click Save.

## Microsoft Teams integration setup

Go to Notification Preferences, click Connect Teams, and authorize Light's access. Select the Team and Channel for notifications and click Authorize. Return to preferences, select notification types for Teams, choose the channel, set delivery frequency, and click Save. Administrators can route team members' notifications to a shared channel.

## Web app (in-app) notifications

Light also displays notifications directly in the application:

1. In **Notification Preferences**, enable **Web App Notifications**
2. You'll see notification icons and messages in the Light interface
3. Unread notifications appear as badges on relevant modules
4. Click the **Notifications** icon (bell) in the top navigation
5. View the notification list and mark as read
6. Click a notification to navigate to the relevant item

Web app notifications are always enabled by default and provide real-time awareness while using Light.

## Company-level notification settings

Organization administrators can configure default notification settings for their company:

1. Navigate to **Settings (gear icon) → Profile** to configure company-level notification settings
2. Set **Default Notification Preferences** for new users
3. Choose default channels and frequencies
4. Select which notification types are enabled by default
5. Click **Save**

New team members inherit these defaults when accounts are created. They can customize further in their personal preferences.

## Managing notification frequency

To avoid notification fatigue, customize frequency for each type: Immediate for critical alerts, twice daily for important alerts, daily digest for regular updates, weekly digest for non-urgent information, or Never to disable. This tiered approach ensures urgent items reach you immediately while reducing interruptions.

## Role-based notifications

Different roles receive notifications based on responsibilities: Finance Controllers get approvals and period closings, AP Clerks get bill updates, AR Clerks get invoices and receipts, and Admins get system alerts. Check Assigned Roles in settings to see what notifications apply to your role.

## Notification rules and unsubscribing

Create custom rules in Notification Preferences → Custom Rules to set triggers, criteria, and actions (e.g., "Alert me immediately in Slack when invoices over $50,000 are created"). To stop receiving notifications, toggle Enabled to Off in Notification Preferences. Rather than disabling, try adjusting frequency to weekly digest to reduce interruptions.

## Troubleshooting and best practices

Common issues: check email address and spam filters for email delivery, verify Slack workspace authorization for Slack notifications, confirm Teams channel access. Best practices include enabling immediate notifications only for urgent items, using daily digests for routine updates, choosing channels that match your workflow, testing after setup, reviewing preferences quarterly, using notification rules to route complex scenarios, and documenting team responsibility assignments.

## Related articles

- [Company Policies](/articles/02-organization-setup/2-8-company-policies)
- [Fiscal Year and Accounting Periods](/articles/02-organization-setup/2-4-fiscal-year-periods)
- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
