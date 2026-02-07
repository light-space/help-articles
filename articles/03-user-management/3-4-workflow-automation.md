# Understanding and Managing Workflow Automation

Beyond basic approval workflows, Light supports advanced workflow automation with conditions, branching, mappings, timers, and AI-powered reviews. This article explains how to build complex workflows that handle sophisticated approval scenarios.

[Open in Light →](https://app.light.inc/settings/profile)

## Workflow Components

Advanced workflows in Light are built from several building blocks:

**Trigger Node** - The starting point that initiates the workflow when a document is created or updated

**Condition Nodes** - Branch logic that routes documents to different approval paths based on conditions (amount, document type, custom fields)

**Approval Nodes** - Stop points where users must approve or reject before the workflow continues

**Mapping Nodes** - Transform or enrich document data by copying values between fields or applying functions

**Timer Nodes** - Wait for a set duration or until a specific date before proceeding

**Agent Review Nodes** - Use AI to review documents against policies before human approval

**Custom Nodes** - Execute domain-specific actions like creating invoices or updating entities

## Workflow Variables

Workflows operate on variables that represent document properties and custom data:

**Monetary Amount** - Currency amounts (e.g., invoice total, approval threshold)

**Default Approvers** - List of users from approval tier definitions

**Select** - Dropdown options (e.g., document type, cost center)

**Entity** - References to business objects (customers, vendors, company entities)

**Date** - Specific dates (e.g., invoice date, due date)

**Custom Property** - Company-defined custom fields

**Boolean** - Yes/no flags

**JSON** - Complex structured data for advanced use cases

Variables are populated from the document being processed or supplied by the workflow engine.

## Building Conditional Workflows

Use condition nodes to route documents to different approval paths:

1. **Define conditions** - Specify field name, operator (equals, greater than, contains), and values
2. **Create branches** - Each condition creates a branch for documents matching it
3. **Add default branch** - Documents not matching any condition follow the default (else) path
4. **Connect to approvals** - Connect each branch to appropriate approval nodes

For example: "If invoice amount > 50,000, route to VP approval; otherwise to manager approval."

Conditions can be combined with AND/OR logic for complex routing:

```
(Invoice Amount > 50,000 AND Vendor = Preferred) OR Department = Executive
```

## Approval Node Routing

Approval nodes determine who must approve a document:

**Explicit Users** - Specify exact user by name or ID

**User Groups** - Any member of a group can approve

**Manager Assignment** - Auto-assign to the document requester's manager

**Hierarchical Manager** - Route up the manager chain (each approver's manager approves next)

**Group Hierarchy** - Route through parent/child user group levels

Manager and group assignments are powerful because they adapt automatically as your org changes—you don't need to update workflow rules when someone's manager changes.

## Approval Task Metadata

Each approval can include metadata that provides context to approvers:

- **Title** - What is being approved (e.g., "Vendor Invoice Approval")
- **Description** - Why approval is needed and key facts
- **Task metadata** - Additional structured data displayed in approval UI

This helps approvers make informed decisions without needing to open the full document.

## Mapping Nodes

Mapping nodes transform document data:

**Simple mapping** - Copy a value from one field to another

**Object mapping** - Map complex nested objects with field-level control

**Array mapping** - Map over collections of items, applying transformations to each

Example: Copy invoice amount from source field and round it to nearest currency unit before storing in a custom field for reporting.

## Timer Nodes

Timer nodes introduce delays or scheduling:

**Duration** - Wait a fixed amount of time (e.g., 24 hours) before proceeding

**Scheduled date** - Wait until a specific date in the workflow variable (e.g., invoice due date)

After the timer expires, the workflow automatically proceeds to the next node. This is useful for grace periods or scheduled reviews.

## AI Agent Review

Agent Review nodes use AI to evaluate documents against a set of policies:

1. **Select policies** - Choose which company policies apply
2. **Provide context** - Optionally add custom instructions (e.g., "Focus on contract terms")
3. **Set input** - Specify which document field or variable to review

The AI analyzes the input against policies and returns:

- **Compliance result** - Whether the document is compliant or has violations
- **Reasoning** - Why it is/isn't compliant
- **Evidence** - References to specific policy sections
- **Confidence level** - How certain the AI is about its assessment

Compliant documents proceed one way; non-compliant documents can be routed to a policy expert for manual review.

## Workflow Execution States

As workflows run, they progress through states:

**Pending** - Workflow hasn't started yet (waiting for trigger event)

**In Progress** - Workflow is actively executing

**Paused** - Workflow is waiting for user action (approval)

**Completed** - Workflow finished successfully and document is posted

**Failed** - An error occurred; workflow stopped

**Cancelled** - User manually cancelled the workflow

You can track workflow state and debug issues by viewing execution details.

## Publishing and Versioning

Workflows have versions:

1. **Draft** - Edit freely, doesn't apply to documents
2. **Published** - Active workflow applied to new documents
3. **Historic versions** - Previous published versions available for reference

Only one workflow version can be published at a time. Create a new version to modify a published workflow.

## Monitoring Workflows

Track workflow execution to identify bottlenecks:

1. Go to **Settings (gear icon) > Workflows** to view workflow execution history
2. View all running and completed workflow executions
3. Filter by workflow type, status, date range
4. Click an execution to see detailed node-by-node progress
5. Identify slow nodes and approval bottlenecks

Use this data to optimize your workflows—remove unnecessary approvals, add parallel approvals where possible, etc.

## Best Practices

- **Start simple** - Begin with basic approval flows, add complexity as needed
- **Test thoroughly** - Run test documents through workflows before publishing
- **Use auto-assignment** - Reduces manual configuration and adapts to org changes
- **Monitor execution** - Review workflow analytics to find bottlenecks
- **Document rules** - Add notes explaining why conditions exist for future maintainers
- **Review regularly** - Quarterly check that workflows still match your processes

## Related Articles

- [Setting up approval workflows](/mnt/help-articles/articles/03-user-management/3-3-approval-workflows.md)
- [User roles and permissions overview](/mnt/help-articles/articles/03-user-management/3-1-roles-permissions-overview.md)
