# Audit Log and Activity History

Light maintains detailed audit logs of all significant actions for compliance, troubleshooting, and security monitoring. This article explains how to access and use audit logs.

[Open in Light →](https://app.light.inc/settings/profile)

## What is the Audit Log?

The audit log is a permanent, immutable record of:

- **User authentication** - Who logged in and when
- **Document actions** - Creating, editing, posting, clearing documents
- **Permission changes** - User role assignments and modifications
- **System settings** - Configuration changes to workflows, accounts, etc.
- **API access** - Calls made by service accounts and external systems
- **Data exports** - When reports are downloaded or data is exported

Every action includes:

- **Who** performed the action (user or service account)
- **What** action was taken (created, posted, approved, etc.)
- **When** it happened (timestamp)
- **Where** from (IP address, device)
- **Original and new values** (before/after data for changes)

## Accessing the Audit Log

To view audit logs:

1. Navigate to **Settings (gear icon) > Audit Logs** to view audit logs
2. View the activity stream showing recent actions
3. Use filters to narrow results by:
   - **Date range** - When the action occurred
   - **User** - Who performed the action
   - **Action type** - What was done (created, posted, deleted, etc.)
   - **Document type** - Which entities were affected (invoices, journal entries, etc.)
4. Click a log entry to see full details including before/after data

> Good to know: Audit logs are retained for 7 years per standard regulatory requirements. You cannot delete or modify audit logs.

## Document Activity History

For individual documents, view an activity timeline:

1. Open a document (invoice, journal entry, etc.)
2. Click the **Activity** or **History** tab
3. View all changes to that document in chronological order
4. Click an entry to see what changed and who made the change

This is useful for understanding how a document evolved from creation through posting to clearing.

## Using Filters Effectively

Apply multiple filters to find specific events:

**By Date** - Filter to a specific period (last 7 days, last month, custom range)

**By User** - Find all actions by a specific person

**By Document Type** - Show only invoices, journal entries, payments, etc.

**By Action** - Find specific action types:
  - **Posted** - Documents moved from draft to posted
  - **Modified** - Changes to existing documents
  - **Cleared** - Payments and clearings
  - **Approved/Rejected** - Workflow approvals

Combining filters helps you investigate specific scenarios quickly.

## Common Investigations

Use the audit log to investigate common questions:

**Who modified this invoice?**
- Filter by document ID, see all changes and who made them

**When was this payment posted?**
- Filter by payment ID, find the post action and timestamp

**Why is an invoice in this status?**
- View activity history, see the sequence of state changes

**Did someone delete a document?**
- Filter by document and look for "archived" or "deleted" actions

**Which service account made this API call?**
- Filter by API access, see what each service account did

## Understanding Log Entries

Each audit log entry shows:

**Timestamp** - Exact date and time of the action

**User/Service Account** - Who performed the action

**Action** - What was done (created, posted, approved, cleared, etc.)

**Entity** - What was affected (specific invoice, user, workflow, etc.)

**IP Address** - Where the action originated from

**Before/After** - Original and new values for changes

**Status** - Success or failure with error details if applicable

Clicking the entry shows the full detail view with complete before/after data.

## Export Audit Logs

Export audit logs for external analysis or long-term storage:

1. Go to **Settings (gear icon) > Audit Logs**
2. Apply filters for the data you want to export
3. Click **Export to CSV**
4. Open the downloaded file in your spreadsheet application

CSV exports include all columns and can be analyzed with Excel, Google Sheets, or other tools.

## Retention and Compliance

Light's audit logging supports compliance with regulations:

- **SOX (Sarbanes-Oxley)** - Complete audit trail of financial transactions
- **GDPR** - Record of who accessed personal data
- **HIPAA** - Activity logs for healthcare industry compliance
- **Internal policies** - Custom audit requirements

Audit logs are immutable (cannot be changed or deleted) and retained for 7 years minimum.

> Important: Export and archive audit logs periodically if you need longer retention than 7 years for compliance.

## Monitoring for Security

Use audit logs to monitor for suspicious activity:

- **Failed login attempts** - Multiple failures may indicate account compromise attempts
- **Unusual access times** - Access outside normal business hours
- **Permission escalation** - Users suddenly given higher-privilege roles
- **Bulk data access** - Users or service accounts exporting large amounts of data
- **After-hours modifications** - Changes made by users outside their normal schedule

Review audit logs regularly as part of your security program.

## API Activity

For integrations and automations, audit logs show:

- **Service account** that made the call
- **API endpoint** that was called
- **Request parameters** and data sent
- **Response status** (success or error)
- **Timestamp** when the call occurred

This helps debug integration issues and audit external system access.

## Alerts and Notifications

Set up alerts for critical audit events:

1. Go to **Settings (gear icon) > Audit Logs** to configure audit alerts
2. Click **+ Create alert rule**
3. Select which actions trigger alerts (user added, payment posted, etc.)
4. Choose notification method (email, Slack, Teams)
5. Configure recipients

Alerts notify you immediately when important events occur, rather than waiting to review logs manually.

## Best Practices

- **Review regularly** - Check audit logs weekly for unusual activity
- **Archive exports** - Periodically export logs for long-term storage
- **Set up alerts** - Get notified of critical events immediately
- **Investigate anomalies** - Follow up on suspicious patterns
- **Retain records** - Never delete or modify audit logs
- **Share with auditors** - Provide audit log exports to external auditors when requested

## Related Articles

- [Two-factor authentication and security](/mnt/help-articles/articles/03-user-management/3-5-two-factor-auth.md)
- [User roles and permissions overview](/mnt/help-articles/articles/03-user-management/3-1-roles-permissions-overview.md)
- [Inviting and removing users](/mnt/help-articles/articles/03-user-management/3-2-inviting-removing-users.md)
