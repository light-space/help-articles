# Adding team members and roles

This article explains how to invite team members to Light, assign roles, and manage permissions across your organization.

[Open in Light →](https://app.light.inc/settings/users)

## Understanding roles

Light comes with predefined roles that cover common scenarios. Each role grants specific permissions for financial operations:

**Finance Admin**
Full access to all features, settings, and data. Manage users, configure integrations, and set policies. Best for finance leaders and controllers.

**Finance Manager**
Create and manage invoices, bills, and expenses. Approve items up to configured limits. Cannot access settings or manage users.

**AP Specialist**
Handle bill processing, vendor management, and payments. Cannot access AR or expense features.

**AR Specialist**
Manage invoices, customers, and revenue. Cannot access AP or expense features.

**Expense Manager**
Configure expense policies and approve expense reports. Cannot manage invoices or bills.

**Employee**
Submit expense reports and request reimbursements. View their own expenses and approvals. Cannot manage company finances.

**Accountant**
Create manual journal entries, review GL accounts, and prepare financial reports. Cannot approve expenses or manage payments.

**Viewer**
Read-only access to all financial data. Useful for stakeholders who need visibility but not approval authority.

> **Tip:** You can create custom roles with specific permissions. This is useful for specialized roles like "Expense Policy Manager" or "Bank Reconciliation Officer."

## Invite team members

1. Go to **Business partners > Users** ([Open in Light →](https://app.light.inc/users)) (or **Settings (gear icon) > Users**)
2. Click **+ Create user**
3. Enter the team member's details:
   - **Email address** - Their work email (they'll receive an invitation at this address)
   - **Full name** - As you want it to appear in Light
   - **Primary role** - Select from predefined or custom roles
   - **Company entities** - Which entities can they access (leave empty for all)
   - **Cost center** (optional) - For expense tracking and approval routing

4. Optionally add additional roles if the team member has multiple responsibilities

5. Click **Send invitation**

Light sends an invitation email to the new member. They'll click the link in the email to accept and set up their account.

## Manage user permissions

### Create custom roles

For specialized permissions:

1. Go to **Settings (gear icon) > Workflows** (to manage approval workflows and role-based permissions)
2. Click **+ Create role**
3. Enter a role name (e.g., "Tax Manager", "Bank Reconciliation Officer")
4. Select the specific permissions you want to grant:
   - **Invoice management** - Create, edit, delete invoices
   - **Bill management** - Create, edit, delete bills
   - **Payment execution** - Execute payments from configured bank accounts
   - **Expense approval** - Approve expense reports (with amount limits)
   - **Journal entries** - Create and review manual GL entries
   - **Bank reconciliation** - Reconcile bank accounts
   - **Reporting** - Generate and export financial reports
   - **User management** - Add and remove users
   - **Settings access** - Modify organization settings

5. Click **Create role**

Assign the custom role to team members during or after invitation.

### Delegate approval authority

Some team members can delegate their approval authority to others:

1. Go to **Settings (gear icon) > Users**
2. Click **Set delegation**
3. Select the approver and their delegate
4. Set the delegation period (e.g., "While I'm on vacation")
5. Click **Create delegation**

The delegate can now approve items on behalf of the original approver.

## Manage team members

### View active team

1. Go to **Settings (gear icon) > Users**
2. See all active users with:
   - Email and name
   - Primary role
   - Last activity
   - Status (Active or Inactive)

### Modify user access

1. Click on a team member's name in the **Users** list
2. Update:
   - **Primary role** - Change their main role
   - **Additional roles** - Add or remove secondary roles
   - **Entity access** - Limit access to specific entities
   - **Cost center** - Update their cost center for expense tracking

3. Click **Save**

### Remove team members

1. Go to **Settings (gear icon) > Users**
2. Click on the team member
3. Click **Deactivate user**
4. Confirm deactivation

Deactivated users:
- Cannot log in or access Light
- Still appear in historical records and approval chains
- Can be reactivated if they rejoin your team later

Their approval authority and delegations are automatically revoked.

### Reactivate users

1. Go to **Settings (gear icon) > Users**
2. Check the **Include inactive users** checkbox
3. Find the deactivated user
4. Click **Reactivate**

## Set approval limits

Control how much team members can approve without escalation:

1. Go to **Settings (gear icon) > Users** to set limits per user or role
2. For each role, set:
   - **Expense approval limit** - Max amount they can approve alone
   - **Invoice approval limit** - Max invoice amount they can approve
   - **Bill approval limit** - Max bill amount they can approve
   - **Payment approval limit** - Max payment they can authorize

When an item exceeds the limit, it automatically escalates to the next approver.

> **Good to know:** Approval limits are per role, so all team members with the "Finance Manager" role have the same limits unless they have a custom role.

## Manage access by entity

Restrict users to specific legal entities:

1. Go to **Settings > Users > [User name]**
2. Under **Entity access**:
   - **All entities** - User can access all company entities
   - **Selected entities** - Choose which entities they can see and work with

3. Click **Save**

This is useful for:
- Regional accountants who only handle specific subsidiaries
- Finance teams distributed across geographies
- Auditors who need limited, read-only access to specific entities

## SSO and authentication

For enterprise organizations using single sign-on (SSO):

1. Contact Light support to enable SSO for your company
2. Light integrates with Auth0, supporting:
   - Google Workspace
   - Microsoft Azure AD / Entra
   - Okta
   - Custom SAML providers

3. Once configured, team members log in using your company's identity provider
4. User provisioning is automated—new hires added to your IdP appear in Light automatically
5. Removing users from your IdP revokes their Light access

## Related articles

- [Setting up your organization](#)
- [Navigating the Light dashboard](#)
- [Creating and sending invoices](#) (for role-specific workflows)
