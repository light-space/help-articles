# Company Policies

This article shows you how to create and manage company policies in Light — a quick way to share your organization's rules with your team and, when you want it, to have Light check expense submissions against them automatically.

[Open in Light →](https://app.light.inc/settings/guardrails/policies)

> **Important:** Company policies aren't just reference documents. The same policy text can be used by Light's AI to automatically check submitted expenses for compliance. See "How policies affect expense approval" below before you rely on a policy for enforcement.

**On this page**

- What are company policies?
- Navigating the Policies page
- Creating a policy
- Uploading a policy
- Viewing a policy
- Editing a policy
- Assigning policies to entities
- How policies affect expense approval
- Best practices
- Related articles

## What are company policies?

Company policies in Light are documents that capture your organization's rules, procedures, and expectations. They can cover expense guidelines, procurement procedures, compliance requirements, and other governance topics. Assign a policy to specific entities so each part of your organization follows the rules that apply to it.

## Navigating the Policies page

1. Go to **Settings (gear icon) → Guardrails → Policies** in the sidebar
2. The page lists every policy with columns for **Title**, **Entities**, **Last edited**, and **Edited by**
3. Click **+ Create policy** to add a new policy
4. Click **Upload** to bring in an existing policy document

## Creating a policy

1. Go to **Settings (gear icon) → Guardrails → Policies**
2. Click **+ Create policy**
3. Fill in the policy details:
   - **Entities**: Select the company entities this policy applies to. This field is optional, but read the note below before leaving it blank
   - **Title**: Give the policy a descriptive title (e.g., "Expense Policy", "Travel Policy")
   - **Content**: Write the policy in the rich text editor, which supports headings, bold, italic, lists, and other standard text formatting
4. Click **Save**

## Uploading a policy

Prefer to start from a document you already have? Upload it instead of writing from scratch:

1. Go to **Settings (gear icon) → Guardrails → Policies**
2. Click **Upload**
3. Select a **.txt or .pdf** file from your computer
4. Light extracts the text from your document into the policy's Content field. This takes about a minute

## Viewing a policy

1. Click a policy in the list to open its detail view
2. The detail view shows:
   - The policy title
   - Assigned entities
   - Full policy content
   - **Last edited by** information showing who last modified the policy
3. To make changes, click **Edit** in the bottom-right of the drawer (in the footer)

## Editing a policy

1. Open the policy by clicking it in the list
2. Click **Edit**
3. Update the fields you need:
   - **Entities**: Change which entities the policy applies to
   - **Title**: Update the policy title
   - **Content**: Edit the policy text in the rich text editor
4. Click **Save**

## Assigning policies to entities

Scope a policy to the entities it should cover:

1. When creating or editing a policy, click the **Entities** dropdown
2. Select the entities this policy should apply to
3. Save the policy

This lets different subsidiaries, regions, or divisions carry their own relevant policies.

## How policies affect expense approval

When an employee submits an expense report, Light's AI can check it against your company policies and either approve it or route it to your finance team for manual review — the same compliance check described in Submitting an Expense for Reimbursement. The policy text you write or upload here is exactly what that AI checks against.

Two things to know before you rely on this:

- **Writing a policy here doesn't automatically turn on enforcement.** A policy is only used in expense review once it's connected to your expense approval workflow. If your company hasn't set that up, work with your Light contact to wire your policies into the review step.
- **An unscoped policy (no Entities selected) is silently skipped during review.** It won't apply to everyone by default — it applies to no one. If none of your policies match an employee's entity, that employee's expenses go through with no policy check and no error shown. Always assign at least one entity to any policy you want enforced.

## Best practices

- Use clear, descriptive titles that signal each policy's purpose
- Assign policies to the correct entities so they stay relevant and are actually applied during expense review
- Write policy content in clear, specific language, since this text is also what Light's AI reads when checking expense compliance
- Review policies periodically to keep them current
- Use the rich text editor's formatting options to keep policies easy to read
- Confirm with your Light contact that your policies are wired into the expense approval workflow, since creating a policy alone doesn't enable enforcement

## Related articles

- [Managing Entities](https://light.inc/help/organization-setup/managing-entities)
- [Custom Properties (Dimensions)](https://light.inc/help/organization-setup/custom-properties)
- [Submitting an Expense for Reimbursement](https://light.inc/help/employee-expenses-reimbursements/employee-submitting-expense)
