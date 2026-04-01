# Adding team members and roles

This article explains how to invite team members to Light, assign roles, and manage users across your organisation.

[Open in Light →](https://app.light.inc/users)

## Understanding roles

Light comes with predefined system roles. Each role grants a specific set of permissions:

| Role | Description |
|---|---|
| **Company Admin** | Full access to all features, settings, and data |
| **Controller** | Create journal entries, review GL accounts, and prepare financial reports |
| **Invoice Approver** | Approve invoices up to configured limits |
| **AP Preparation** | Prepare and process bills |
| **AP Clerk** | Handle bill processing, vendor management, and payments |
| **AR Clerk** | Manage invoices, customers, and revenue |
| **Vendor Management** | Manage vendor records and onboarding |
| **Purchase Requester** | Submit purchase requests |
| **Cardholder** | Use a company card and submit card transactions |
| **Reimbursement** | Submit expenses and request reimbursements |
| **Report Viewer** | Read-only access to reports |
| **Auditor** | Read-only access to financial data for audit purposes |

To see the full permission breakdown for each role, go to **Business partners → Users** and open the **Roles** tab.

## Invite a team member

1. Go to **Business partners → Users**
2. Click **+ Create user**
3. Fill in the team member's details:
   - **First name** and **Last name**
   - **Email**
   - **Access role** — select one or more roles
   - **Entity** — which company entity they belong to
   - **Manager** — their direct manager in Light
   - **Communication channel** — how they receive notifications
   - Address fields (Country, City, State, Zip) — optional
   - **Phone number** — optional

4. Click **Create**

Light sends an invitation email to the new member. They click the link to accept and set up their account.

## Manage team members

### View the team

Go to **Business partners → Users** to see all users. The list shows full name, email, notification channel, roles, phone, groups, country, city, and address. Click any row to open the user's details.

### Edit a user

1. Click on a user in the **Users** list
2. Click **Edit**
3. Update their details, roles, entity, or manager
4. Click **Save**

### Archive a user

1. Click on the user in the **Users** list
2. Click **Archive**
3. Confirm

Archived users cannot log in but remain in historical records and approval chains.

## Groups

Groups let you organise users into named teams with a hierarchy level.

### Create a group

1. Go to **Business partners → Users**
2. Open the **Groups** tab
3. Click **+ Create group**
4. Fill in:
   - **Name** (required, max 50 characters)
   - **Description** (optional)
   - **Level** (numeric, 1–99 — used for approval hierarchy)
5. Click **Next**
6. Search and select users to add to the group
7. Click **Create**

### Manage group members

Open any group from the Groups tab to see its members. Use **Add users** to add members or the remove button on any row to remove them.

## Roles tab

Go to **Business partners → Users** and open the **Roles** tab to see a full permission matrix — every role mapped against every available permission. This view is read-only.

## Entity access

Each user is assigned to a specific company entity. To change which entity a user belongs to, open the user's details and update the **Entity** field.

## SSO and authentication

For organisations using single sign-on (SSO), Light integrates with Auth0, supporting:

- Google Workspace
- Microsoft Azure AD / Entra
- Okta
- Custom SAML providers

Contact Light support to enable SSO for your organisation.

## Related articles

- [User management overview](/articles/03-user-management/3-1-user-management-overview.md)
- [Inviting and removing users](/articles/03-user-management/3-2-inviting-removing-users.md)
