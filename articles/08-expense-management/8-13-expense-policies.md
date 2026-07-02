# Expense Policies

Expense policies document what employees can spend, on what, and under what conditions. Light's AI reviews submitted expense reports against your policies as part of the expense submission workflow.

[Open in Light →](https://app.light.inc/settings/guardrails/policies)

## Understanding Expense Policies

In Light, a policy is a written document — not a set of structured rules or limits configured in the app. Each policy has:

- **Title**: A descriptive name (e.g., "Expense Policy", "Travel Policy")
- **Content**: The full policy text, written in the rich text editor
- **Entities**: The company entities the policy applies to

Because policies are free text, you can express any rules your organization needs — spending guidance, eligible and ineligible expense types, documentation expectations, pre-approval requirements — in plain language. Light's AI reads the policy content when reviewing expense reports, so clearly written policies lead to better automated reviews.

Policies are managed on the same page as other company policies. See [Company policies setup](/articles/02-organization-setup/2-8-company-policies.md) for full details on creating, editing, and managing policies.

## Creating an Expense Policy

1. Navigate to [**Settings (gear icon) → Guardrails → Policies**](https://app.light.inc/settings/guardrails/policies)
2. Click **+ Create policy**
3. Fill in the policy details:
   - **Entities**: Select the company entities this policy applies to
   - **Title**: Enter a descriptive title (e.g., "Expense Policy")
   - **Content**: Write the policy rules using the rich text editor
4. Click **Save**

### Uploading an Existing Policy

If you already have a policy document:

1. Navigate to [**Settings (gear icon) → Guardrails → Policies**](https://app.light.inc/settings/guardrails/policies)
2. Click **Upload**
3. Select the document from your computer
4. Light's AI parses the uploaded document into a policy

## Writing Effective Expense Policies

Since the AI interprets your policy text when reviewing expenses, be specific and concrete. For example, your policy content might state:

- "Meals are reimbursable up to $75 per person per meal"
- "Hotel stays should not exceed $200 per night in standard locations"
- "Alcohol, entertainment, and personal care expenses are not reimbursable"
- "All expenses require an itemized receipt and a business purpose"
- "Air travel should be booked in economy class"

Clear, unambiguous rules like these give the AI reviewer a solid basis for judging whether a submitted expense report complies.

### Scoping Policies by Entity

Policies are assigned to company entities, so different subsidiaries, regions, or divisions can have their own expense rules. When creating or editing a policy, use the **Entities** field to control where it applies.

## How Policies Are Enforced

Expense policies are enforced through the expense submission workflow:

1. An employee submits an expense report
2. The workflow's AI review step (**Review expense report**) checks the report against the policies selected on that step
3. Based on the outcome:
   - **Compliant**: The expense is approved automatically
   - **Non-compliant**: The expense is sent to the inbox for manual review

To configure this, open [**Settings (gear icon) → Workflows**](https://app.light.inc/settings/workflows), edit the expense submission workflow, and select which policies the AI review step should check against.

Reviewers see the AI's assessment and can approve or reject the expense — a non-compliant flag routes the expense to a person rather than blocking it outright.

## Asking About Policies

Employees can ask Light's AI assistant questions about company policies (e.g., "What's the meal limit for business travel?"). The assistant answers based on the policy documents you've created.

## Expense Categories

Reimbursement categories are managed separately from policies. Each category has a label, GL account, tax code, optional context for the AI, and entity assignments. Configure them at **Settings (gear icon) → Records → Reimbursement category** ([open in Light](https://app.light.inc/settings/reimbursement-categories)).

## Reviewing and Updating Policies

Policies should be reviewed periodically:

1. Check how often expenses are flagged as non-compliant and why
2. Consider whether your written rules are too restrictive, too generous, or unclear
3. Update the policy content in the editor
4. Communicate changes to employees

## Related Articles

- [Company policies setup](/articles/02-organization-setup/2-8-company-policies.md)
- [Expense management overview](/articles/08-expense-management/8-1-expense-overview.md)
- [Expense approval workflows](/articles/08-expense-management/8-7-expense-approval.md)
- [Expense reports and analytics](/articles/08-expense-management/8-14-expense-reports.md)
