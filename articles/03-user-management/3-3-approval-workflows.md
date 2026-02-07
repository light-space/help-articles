# Setting Up Approval Workflows

Approval workflows define how documents like invoices and expenses progress through your organization before being posted to the ledger. This article explains how to configure approval workflows and routing rules.

[Open in Light →](https://app.light.inc/settings/profile)

## Understanding Approval Workflows

Approval workflows are sequential approval processes where documents move through approval stages before final posting. Each stage can require approval from one or more users, based on document attributes like amount, type, or custom criteria.

Workflows prevent unauthorized spending, catch errors early, and create an audit trail of who approved what and when. They're essential for compliance and financial controls.

## Workflow Types

Light supports several built-in workflow types:

**Bill Approval Workflow** - Controls how vendor invoices (bills) move through approval before payment

**Expense Submission Workflow** - Routes employee expense reimbursement requests for approval

**Vendor Approval Workflow** - Routes new or changed vendor master data for approval

**Invoice Receivable Workflow** - Controls AR invoice creation and dunning (payment reminders)

**Card Approval Workflow** - Routes corporate card transactions for review and approval

## Approval Tiers

Approval workflows are organized by tiers (approval levels). Each tier represents an approval stage that a document must pass through:

1. **Tier 1** - First level of approval (e.g., department manager)
2. **Tier 2** - Second level of approval (e.g., finance manager)
3. **Tier 3** - Third level of approval (e.g., CFO)

You can define how many tiers your workflow requires and who approves at each tier.

## Defining Approvers

Approvers can be assigned in three ways:

**Specific Users** - Explicitly select individual users as approvers. Useful for small teams or executive approval.

**User Groups** - Assign a user group as approvers. Any member of the group can approve. Ideal for distributed approval authority.

**Auto-Assignment Rules** - Automatically assign approvers based on document properties:
  - Manager of the requester (person who submitted)
  - Manager of the previous approver (chain approval)
  - Budget owner for the cost center

Auto-assignment is powerful for scaling approvals without hardcoding every approver.

## Approval Conditions

You can set conditions that determine whether a document needs approval:

- **Amount thresholds** - Documents above a certain amount require approval
- **Document type** - Only certain invoice types need approval
- **Custom properties** - Documents with specific custom property values require approval
- **Cost center** - Documents charged to certain cost centers have different approval requirements

This allows you to route documents intelligently based on risk or spend level.

## Approval Rules

Create approval rules to define the approval logic:

1. Navigate to **Settings (gear icon) > Workflows**
2. Select the workflow type (Bill Approval, Expense, etc.)
3. Click **+ Create rule** or edit an existing rule
4. Define the **conditions** (amount, type, etc.) that trigger this rule
5. Specify the **approvers and tiers** for documents matching these conditions
6. Click **Save**

You can have multiple rules that apply to different scenarios. Documents are matched against rules in order, with the first matching rule being applied.

> Tip: Order your rules from most specific to least specific. This ensures documents match the right rule. For example, put your "invoices over 10,000" rule before "all invoices".

## Required vs. Optional Approvals

Approval tiers can be marked as **required** or **optional**:

**Required** - The document cannot progress until approved at this tier. Rejections send documents back to the requester.

**Optional** - If no one from this tier approves within a timeframe, the document can proceed anyway.

## Approval Reminders

Light can automatically send reminders to approvers when documents are waiting for approval:

1. Go to **Settings (gear icon) > Workflows > [Workflow Name]**
2. Enable **Approval Reminders**
3. Set the **reminder frequency** (daily, every 2 days, weekly, etc.)
4. Choose the **notification channel** (Slack, Teams, Email)

Reminders help keep approvals moving and reduce bottlenecks.

## Concurrent vs. Sequential Approvals

**Sequential** - Approvals happen one tier at a time. Tier 1 must approve before Tier 2 sees the document.

**Concurrent** - All approvers in a tier can approve simultaneously. The document moves to the next tier when all approvers at the current tier have approved.

Sequential approvals ensure reviews happen in order. Concurrent approvals speed up the process when multiple people can review in parallel.

## Publishing Workflows

Workflows exist in **draft** and **published** states:

**Draft** - You can edit workflows freely but they don't apply to new documents

**Published** - The workflow is active and applies to new documents. You cannot edit published workflows; create a new version instead.

To publish a workflow:

1. Navigate to the workflow
2. Click **Review & Publish**
3. Verify the rules and approvers
4. Click **Publish**

Only published workflows apply to documents. Keep one version published to avoid confusion.

## Testing Workflows

Before publishing, test your workflow:

1. Create a test document that would match your workflow rules
2. Verify it's assigned to the correct approver
3. Check that approval notifications are sent correctly
4. Submit through the full approval process

Testing catches configuration errors before impacting real documents.

## Best Practices

- **Keep it simple** - Limit approval tiers to 3 or fewer to avoid delays
- **Use auto-assignment** - Reduces manual configuration and scales better
- **Set reasonable timeouts** - Don't let approvals linger indefinitely
- **Monitor exceptions** - Track which rules are applied most to optimize your workflow
- **Review quarterly** - As your organization changes, revisit approval rules to ensure they still fit

## Related Articles

- [Understanding and managing workflow automation](/mnt/help-articles/articles/03-user-management/3-4-workflow-automation.md)
- [User roles and permissions overview](/mnt/help-articles/articles/03-user-management/3-1-roles-permissions-overview.md)
- [Inviting and removing users](/mnt/help-articles/articles/03-user-management/3-2-inviting-removing-users.md)
