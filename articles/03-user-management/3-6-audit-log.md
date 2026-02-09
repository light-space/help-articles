# Audit Log and Activity History

Light tracks changes to documents through activity timelines and change logs on individual records. This article explains how to view activity history for documents in Light.

[Open in Light →](https://app.light.inc/payables)

## Document Activity Tracking

When you open a document such as a bill, invoice, or expense, Light displays an activity timeline in the **Approval** section at the top of the document detail view. This timeline shows key events in the document's lifecycle, such as when it was created, submitted for approval, approved, or posted.

Each event in the timeline includes:

- **Event type** - What happened (e.g., Bill created, Approved, Posted)
- **Date** - When the event occurred
- **Event count** - A summary showing how many events have been tracked (e.g., "1 events tracked")

Click **See all** to expand the full event timeline if there are multiple events.

## Document Change Log

For a detailed record of every field-level change made to a document, use the **Log** tab:

1. Open a document (bill, invoice, expense, etc.)
2. Scroll down to the section below the approval area
3. Click the **Log** tab (next to **Lines** and **Ledger impact**)

The Log tab displays a table with the following columns:

**Date** - The exact date and time the change was made

**Actor** - The user who made the change

**Action** - The type of change (e.g., Updated)

**Property** - Which field was changed (e.g., Ledger Account Label, Tax Code, Business Partner Name)

**Value** - The new value or the before/after change (e.g., "Inventory → Accounts Payable")

This provides a complete audit trail of every modification to a document, showing who changed what and when.

## Workflow Execution History

To monitor how documents are progressing through approval workflows:

1. Go to **Settings → Workflows**
2. View the list of workflows with their trigger types, published dates, and versions
3. Click a workflow to see its configuration and identify where documents are in the approval process

This helps you track bottlenecks and ensure documents are moving through your approval processes.

## Investigating Common Questions

Between the event timeline, the Log tab, and workflow monitoring, you can investigate common questions:

**Who modified this document?** - Open the document and check the Log tab to see all changes, who made them, and when.

**What changed on this document?** - The Log tab shows every field-level change with before and after values.

**Where is this document in the approval process?** - Check the Approval section on the document to see the event timeline and current approval status.

**How are documents flowing through workflows?** - Use Settings → Workflows to monitor workflow execution and identify delays.

## Best Practices

- **Review document logs** - When investigating discrepancies, check the Log tab on the relevant document for a full change history
- **Monitor approval timelines** - Use the event timeline on documents to ensure approvals are happening on schedule
- **Track workflow execution** - Periodically review workflow execution in Settings to identify bottlenecks

## Related Articles

- [Two-factor authentication and security](/mnt/help-articles/articles/03-user-management/3-5-two-factor-auth.md)
- [User roles and permissions overview](/mnt/help-articles/articles/03-user-management/3-1-roles-permissions-overview.md)
- [Inviting and removing users](/mnt/help-articles/articles/03-user-management/3-2-inviting-removing-users.md)
