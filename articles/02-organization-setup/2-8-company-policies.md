# Company Policies

This article explains how to create and manage company policies in Light. Policies help communicate your organization's rules and procedures to your team.

[Open in Light →](https://app.light.inc/settings/guardrails/policies)

> **Important:** Company policies aren't just reference documents. The same policy text can be used by Light's AI to automatically check submitted expenses for compliance. See "How policies affect expense approval" below before you rely on a policy for enforcement.

## What are company policies?

Company policies in Light are documents that communicate your organization's rules, procedures, and expectations. Policies can cover expense guidelines, procurement procedures, compliance requirements, and other governance topics. Policies can be assigned to specific entities so different parts of your organization follow the appropriate rules.

## Navigating the Policies page

1. Go to [**Settings (gear icon) → Guardrails → Policies**](https://app.light.inc/settings/guardrails/policies) in the sidebar
2. The page displays all policies with columns for **Title**, **Entities**, **Last edited**, and **Edited by**
3. Use the **+ Create policy** button to add a new policy
4. Use the **Upload** button to upload an existing policy document

## Creating a policy

1. Navigate to [**Settings (gear icon) → Guardrails → Policies**](https://app.light.inc/settings/guardrails/policies)
2. Click **+ Create policy**
3. Fill in the policy details:
   - **Entities**: Select the company entities this policy applies to. This field is optional, but read the note below before leaving it blank
   - **Title**: Enter a descriptive policy title (e.g., "Expense Policy", "Travel Policy")
   - **Content**: Use the rich text editor to write the policy content. The editor supports formatting such as headings, bold, italic, lists, and other standard text formatting options
4. Click **Save**

## Uploading a policy

You can upload an existing policy document instead of creating one from scratch:

1. Navigate to [**Settings (gear icon) → Guardrails → Policies**](https://app.light.inc/settings/guardrails/policies)
2. Click **Upload**
3. Select a **.txt or .pdf** file from your computer
4. Light extracts the text from your document into the policy's Content field. This takes about a minute

## Viewing a policy

1. Click on a policy in the list to open its detail view
2. The detail view shows:
   - The policy title
   - Assigned entities
   - Full policy content
   - **Last edited by** information showing who last modified the policy
3. To make changes, click **Edit** in the bottom-right of the drawer (in the footer)

## Editing a policy

1. Open the policy by clicking on it in the list
2. Click **Edit**
3. Update the policy fields:
   - **Entities**: Change which entities the policy applies to
   - **Title**: Update the policy title
   - **Content**: Modify the policy text using the rich text editor
4. Click **Save**

## Assigning policies to entities

Policies can be scoped to specific entities:

1. When creating or editing a policy, click the **Entities** dropdown
2. Select the entities this policy should apply to
3. Save the policy

This allows different subsidiaries, regions, or divisions to have their own relevant policies.

## How policies affect expense approval

When an employee submits an expense report, Light's AI can check it against your company policies and either approve it or route it to your finance team for manual review — the same compliance check described in Submitting an Expense for Reimbursement. The policy text you write or upload here is exactly what that AI checks against.

Two things to know before you rely on this:

- **Writing a policy here doesn't automatically turn on enforcement.** A policy is only used in expense review once it's connected to your expense approval workflow. If your company hasn't set that up, work with your Light contact to wire your policies into the review step.
- **An unscoped policy (no Entities selected) is silently skipped during review.** It won't apply to everyone by default — it applies to no one. If none of your policies match an employee's entity, that employee's expenses go through with no policy check and no error shown. Always assign at least one entity to any policy you want enforced.

## Best practices

- Use clear, descriptive titles that indicate the policy's purpose
- Assign policies to the correct entities so they stay relevant and are actually applied during expense review
- Write policy content in clear, specific language, since this text is also what Light's AI reads when checking expense compliance
- Review policies periodically to ensure they remain current
- Use the rich text editor's formatting options to make policies easy to read
- Confirm with your Light contact that your policies are wired into the expense approval workflow, since creating a policy alone doesn't enable enforcement

## Related articles

- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
- [Custom Properties (Dimensions)](/articles/02-organization-setup/2-3-custom-properties)
- [Submitting an Expense for Reimbursement](/articles/16-employee/e2-expenses-reimbursements/e2-1-submitting-expense)
