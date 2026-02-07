# Expense Policies and Spending Limits

Expense policies define what employees can spend, on what, and under what conditions. Light enforces policies automatically through the expense submission and approval workflows.

[Open in Light →](https://app.light.inc/settings/guardrails/policies)

## Understanding Expense Policies

An expense policy is a set of rules governing:

- **What's eligible**: Which expense categories are reimbursable
- **How much**: Spending limits per category or per transaction
- **When**: When pre-approval is required
- **How**: What documentation is required
- **Where**: Geographic or merchant restrictions

Policies can be:

- **Company-wide**: Applies to all employees
- **Role-based**: Different policies for executives, employees, contractors
- **Department-based**: Sales might have different policies than Engineering
- **Location-based**: Different limits in different countries

## Creating a Policy

### Step 1: Define Policy Framework

1. Navigate to **Settings** > **Expense Policies**
2. Click **Create Policy**
3. Enter:
   - **Policy Name**: (e.g., "Standard Employee Policy")
   - **Description**: Purpose and scope
   - **Effective Date**: When policy takes effect
   - **Applies To**: Who it applies (all employees, specific role, etc.)

4. Click **Create**

### Step 2: Set Category Limits

1. In policy, click **Add Category Limit**
2. Select **Category** (Travel, Meals, Office Supplies, etc.)
3. Set **Limit Type**:
   - **Per Transaction**: Max per single receipt/purchase
   - **Per Day**: Max per calendar day
   - **Per Month**: Max per month
   - **Annually**: Max per year

4. Enter **Amount**: Spending limit
5. Set **Requires Approval**:
   - Over limit: Flag for manager review
   - Always: Always require approval
   - Never: Auto-approve if within limit

6. Click **Add**

Example:
- **Meals**: $75 per transaction, $100 per day, $1,500 per month
- **Travel - Hotel**: $200 per night, $1,200 per month
- **Travel - Airfare**: $2,000 per transaction, $10,000 per year
- **Office Supplies**: $200 per transaction, $1,000 per month

### Step 3: Set Ineligible Categories

Specify what cannot be reimbursed:

1. Click **Add Ineligible Category**
2. Select categories:
   - **Alcohol** (may be restricted)
   - **Personal Care** (haircuts, grooming)
   - **Entertainment** (movies, entertainment other than client-related)
   - **Gambling** (casinos, betting)
   - **Nightclubs**
   - **Custom**: Add other ineligible categories

3. Light blocks submission of ineligible categories

### Step 4: Set Documentation Requirements

Specify what documentation is needed:

1. Click **Add Documentation Rule**
2. Set **Category**: What category this applies to
3. Set **Requirement**:
   - **Receipt Required**: Receipt image must be provided
   - **Explanation Required**: Employee must provide business purpose
   - **Approval Required**: Manager approval before submission
   - **Custom Approval**: Additional person must approve

4. Example:
   - Meals: Receipt required + explanation
   - Client entertainment: Receipt required + explanation + approver
   - Travel: Receipt required

5. Click **Add**

## Enforcement and Validation

### Real-Time Policy Enforcement

When employee submits expense:

1. Light validates against policy:
   - **Eligible category?**: Is category allowed?
   - **Within limit?**: Does expense exceed limit?
   - **Documented?**: Receipt provided if required?
   - **Explained?**: Business purpose provided if required?

2. Light shows validation results:
   - Green checkmark: Expense complies with policy
   - Yellow warning: Exceeds limit but can be submitted
   - Red error: Cannot submit without correction (ineligible category)

### Flagging for Approval

Expenses that exceed limits:

1. Automatically flag for manager review
2. Employee is notified: "This expense exceeds policy limit"
3. Employee can:
   - **Cancel**: Withdraw and don't submit
   - **Request Variance**: Submit and ask manager to override policy
   - **Resubmit**: Correct and resubmit

4. If submitted despite warning:
   - Goes to manager
   - Manager sees flag: "This exceeds policy limit"
   - Manager can approve or reject with reason

## Policy Exceptions and Overrides

### Requesting Exception

Employee requesting policy exception:

1. Submit expense that violates policy
2. In notes/explanation, request exception:
   - "Need approval for this $350 meal (exceeds $75 limit)"
   - "This is for client entertainment with key client"

3. Submit anyway
4. Manager sees exception request and policy violation
5. Manager can **Approve Exception** with explanation
6. Exception is recorded for audit

### Granting Standing Variance

For predictable exceptions (e.g., employee frequently travels to high-cost areas):

1. Navigate to **Policies** > **Variance Approvals**
2. Click **Add Variance**
3. Set:
   - **Employee**: Who gets variance
   - **Category**: What category (e.g., Meals)
   - **Limit**: New higher limit
   - **Duration**: How long variance lasts
   - **Reason**: Why variance is needed

4. Example: Sales VP traveling to APAC needs $150/meal limit (vs. standard $75)

5. Apply variance
6. Employee's expenses automatically allow higher limit

## Policy Compliance Reporting

### Monitoring Policy Violations

1. Navigate to **Reports** > **Policy Compliance**
2. View:
   - **Total Submissions**: Expenses submitted
   - **Compliant**: Met policy requirements
   - **Violations**: Exceeded limits or ineligible
   - **Violation Rate**: % of submissions violating policy

3. Drill down by:
   - Employee: Who violates most
   - Category: Which categories are problematic
   - Type: Exceeds limit, ineligible category, missing documentation

### Trend Analysis

Track policy compliance over time:

1. View compliance by month
2. Is compliance improving or deteriorating?
3. Are specific employees consistently violating?
4. Are specific categories consistently problematic?

Use data to:
- Identify training needs
- Adjust policy limits (if universally too strict)
- Take action on chronic violators

## Policy Communication

### Publishing Policies

Ensure employees understand policies:

1. Navigate to **Policies** > **Published Policies**
2. Make policy **Public** so employees can review
3. Link in onboarding materials
4. Periodically remind employees

### Policy Training

Help employees learn policies:

1. Create **Policy Guide**: Summary of key limits and rules
2. Include examples: "Here's what's reimbursable and what's not"
3. Distribute to employees
4. Especially important for travel and entertainment categories

## Role-Based Policies

### Creating Different Policies by Role

Different employee types may have different policies:

**Executives** (higher limits):
- Meals: $150 per transaction, $3,000 per month
- Travel: $500 hotel per night
- Air travel: First/Business class pre-approved

**Employees** (standard limits):
- Meals: $75 per transaction, $1,500 per month
- Travel: $150 hotel per night
- Air travel: Economy class only

**Contractors** (limited reimbursement):
- Meals: Not reimbursable except for work events
- Travel: Pre-approval required
- Supplies: Not reimbursable

### Assigning Policies to Employees

1. Navigate to **Employees**
2. Select employee
3. Assign **Policy**: Choose policy that applies
4. Click **Save**

When employee submits, their policy is automatically applied.

## Merchant-Level Restrictions

### Restricting Merchants

Block certain merchants:

1. Click **Add Merchant Restriction**
2. Select merchant (or merchant category)
3. Action: Block or Allow
4. Examples:
   - Block: Nightclubs, casinos, alcohol retailers
   - Allow: Specific airlines or hotel chains

5. When employee tries to submit receipt from blocked merchant:
   - Light flags or blocks submission
   - Requires manager approval to override

## Pre-Approval Workflows

### Large Expenses Requiring Pre-Approval

For planned expenses that require approval before spending:

1. Configure policy: "Travel expenses over $500 require pre-approval"
2. Employee plans trip: $800 airfare
3. Employee submits **Pre-Approval Request**:
   - Date of travel
   - Business purpose
   - Estimated cost
   - Approver

4. Manager approves
5. Pre-approval valid for 30 days
6. Employee books flight
7. When expense submitted, pre-approval noted
8. Approval process is streamlined (already approved)

## Policy Exceptions Log

Track all policy exceptions:

1. Navigate to **Reports** > **Exceptions Log**
2. View all variances and overrides:
   - Who made exception
   - Why
   - When granted
   - Expiration (if applicable)

3. Use to audit policy enforcement
4. Identify if exceptions are being granted too freely
5. Enforce consistency

## Annual Policy Review

### Updating Policies

Policies should be reviewed annually:

1. Review **Policy Performance** data:
   - How many exceptions granted?
   - How many violations?
   - Are limits appropriate?

2. Consider changes:
   - Are limits too restrictive (causing friction)?
   - Are limits too generous (not controlling cost)?
   - Are any categories causing trouble?

3. Update policy limits and rules
4. Communicate changes to employees
5. Set effective date (give notice)

## Related Articles

- [Expense management overview](/articles/08-expense-management/8-1-expense-overview.md)
- [Expense approval workflows](/articles/08-expense-management/8-7-expense-approval.md)
- [Expense reports and analytics](/articles/08-expense-management/8-14-expense-reports.md)
