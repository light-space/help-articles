# Understanding and Managing Workflow Automation

Beyond basic approval workflows, Light supports advanced workflow automation with conditions, branching, and approval routing. This article explains how to build complex workflows using the visual workflow editor that handle sophisticated approval scenarios.

[Open in Light →](https://app.light.inc/settings/workflows)

## Workflow Components

Workflows in Light are built using a visual flow editor with the following building blocks:

**Condition Nodes** - Branch logic that routes documents to different approval paths based on conditions (amount, document type, vendor, cost center, custom fields). Each condition node can have multiple branches plus an "else" default path.

**Approval Nodes** - Stop points where users must approve or reject before the workflow continues. Each approval node shows two outgoing paths: "if approved" and "if rejected."

**Action Nodes** - Execute specific operations like creating records, sending notifications, or updating document fields.

You add nodes to your workflow using the **Action** and **Condition** buttons in the toolbar at the bottom of the visual editor.

## Building Conditional Workflows

Use condition nodes to route documents to different approval paths:

1. Open a workflow from **Settings → Workflows**
2. Click **Condition** in the bottom toolbar to add a condition node
3. Define conditions — specify field name, operator (equals, greater than, contains), and values
4. Each condition creates a branch for documents matching it, plus an "else" path for everything else
5. Connect each branch to appropriate approval or action nodes

For example, the Bill Payment workflow might route based on: amount thresholds (e.g., Amount < GBP 20,000), vendor name, bill type (e.g., Reimbursement), cost center (e.g., Finance & Ops), or line item classifications (e.g., External subcontracting).

Conditions can be combined for complex routing scenarios with multiple branches from a single condition node.

## Approval Node Routing

Approval nodes determine who must approve a document. When a document reaches an approval node, the assigned approver receives a notification and must take action. The workflow then follows the "if approved" or "if rejected" path accordingly.

Approvers can be assigned based on:

- **Specific users** - Explicitly select individual users
- **User groups** - Any member of a group can approve
- **Manager assignment** - Auto-assign to the document requester's manager
- **Hierarchical routing** - Route up the manager chain

Manager and group assignments are powerful because they adapt automatically as your organization changes — you don't need to update workflow rules when someone's manager changes.

## Workflow Versioning

Workflows have versions that track changes over time:

1. **Draft** - Edit freely in the visual editor; doesn't apply to documents
2. **Published** - Active workflow applied to new documents
3. **Previous versions** - Earlier published versions available for reference

Only one workflow version can be published at a time. The Workflows list shows the current version number, published date, and who published it for each workflow.

To publish, click the **Publish** button in the top-right corner of the workflow editor.

## Monitoring Workflows

Track workflow execution from the Workflows list:

1. Go to **Settings → Workflows** to view all workflows
2. See which workflows are published (with dates and version numbers)
3. Identify which workflows have been recently updated
4. Click a workflow to view and edit its flow in the visual editor

## Best Practices

- **Start simple** - Begin with basic condition and approval flows, add complexity as needed
- **Test thoroughly** - Run test documents through workflows before publishing
- **Use auto-assignment** - Reduces manual configuration and adapts to org changes
- **Monitor versions** - Keep track of published versions and who changed them
- **Document conditions** - Add clear condition labels so future editors understand the routing logic
- **Review regularly** - Quarterly check that workflows still match your processes

## Related Articles

- [Setting up approval workflows](/mnt/help-articles/articles/03-user-management/3-3-approval-workflows.md)
- [User roles and permissions overview](/mnt/help-articles/articles/03-user-management/3-1-roles-permissions-overview.md)
