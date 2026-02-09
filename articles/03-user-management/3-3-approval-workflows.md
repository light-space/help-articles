# Setting Up Approval Workflows

Approval workflows define how documents like invoices and expenses progress through your organization before being posted to the ledger. This article explains how to configure approval workflows and routing rules.

[Open in Light →](https://app.light.inc/settings/workflows)

## Understanding Approval Workflows

Approval workflows are sequential approval processes where documents move through approval stages before final posting. Each stage can require approval from one or more users, based on document attributes like amount, type, or custom criteria.

Workflows prevent unauthorized spending, catch errors early, and create an audit trail of who approved what and when. They're essential for compliance and financial controls.

## Workflow Types

Light includes the following built-in workflow types:

**Bill Payment** - Controls how vendor invoices (bills) move through approval before payment. Triggered when bill data changes.

**Invoice-to-Cash** - Controls AR invoice creation and collection processes. Triggered when an invoice is posted.

**Vendor Card Request** - Routes corporate card requests for review and approval. Triggered when a card request is created.

**Expense Reimbursement** - Routes employee expense reimbursement requests for approval. Triggered when an expense report is submitted.

**Vendor Onboarding** - Routes new or changed vendor master data for approval. Triggered when a vendor is created or bank data changes.

Additional workflow types may be available depending on your integrations, such as sync workflows for HubSpot, Salesforce, or HRM systems.

## Workflow Editor

Light uses a visual flow editor to define workflows. Each workflow is built by connecting nodes on a canvas:

1. Navigate to **Settings → Workflows** ([Open in Light →](https://app.light.inc/settings/workflows))
2. Click on a workflow to open its visual editor
3. Use the toolbar at the bottom to add **Action** or **Condition** nodes
4. Connect nodes to define the approval flow

The visual editor lets you see the entire approval path at a glance and makes it easy to add branching logic.

## Condition Nodes

Condition nodes route documents to different approval paths based on criteria:

- **Amount thresholds** - Documents above a certain amount follow a different path
- **Document type** - Route based on invoice type, bill type, or other classifications
- **Vendor** - Route based on specific vendors
- **Cost center** - Documents charged to certain cost centers have different approval requirements
- **Custom properties** - Route based on any custom field values

Each condition creates branches (including an "else" default path) that connect to different downstream nodes.

## Approval Nodes

Approval nodes are stop points where designated users must approve or reject a document before the workflow continues. Each approval node shows two paths:

- **If approved** - The document proceeds to the next step
- **If rejected** - The document is sent back or routed to an alternative path

## Publishing Workflows

Workflows exist in **draft** and **published** states:

**Draft** - You can edit the workflow freely in the visual editor, but it doesn't apply to new documents.

**Published** - The workflow is active and applies to new documents. Each workflow tracks its version number and who published it.

To publish a workflow:

1. Navigate to the workflow in the visual editor
2. Click **Publish** in the top-right corner
3. The workflow becomes active immediately

The Workflows list shows the published date, who published it, and the current version number for each workflow.

## Best Practices

- **Keep it simple** - Limit approval paths to avoid delays
- **Use conditions wisely** - Route documents based on risk and spend level
- **Test before publishing** - Run test documents through workflows before publishing
- **Monitor versions** - Track which version is published and review changes
- **Review quarterly** - As your organization changes, revisit approval rules to ensure they still fit

## Related Articles

- [Understanding and managing workflow automation](/mnt/help-articles/articles/03-user-management/3-4-workflow-automation.md)
- [User roles and permissions overview](/mnt/help-articles/articles/03-user-management/3-1-roles-permissions-overview.md)
- [Inviting and removing users](/mnt/help-articles/articles/03-user-management/3-2-inviting-removing-users.md)
