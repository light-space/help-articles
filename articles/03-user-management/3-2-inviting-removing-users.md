# Inviting and Removing Users

Add new team members to Light and manage user access as your organization grows. This article covers creating users, setting their roles, and removing access when needed.

[Open in Light →](https://app.light.inc/users)

## Creating a New User

New users are created from the Users page. Follow these steps to add a user:

1. Navigate to **Business partners → Users** ([Open in Light →](https://app.light.inc/users))
2. Click the **+ Create user** button
3. Fill in the user's details:
   - **First name** and **Last name**
   - **Email** address
   - **Address**, **Country**, **State**, **City**, and **Zip / postcode** (optional)
   - **Phone number** (optional)
4. Select their **Entity** (the entity they'll work in primarily)
5. Select their **Access role** (one or more roles based on their responsibilities)
6. Optionally assign a **Manager** (for approval workflow routing)
7. Click **Create**

The user's account is active as soon as it's created — there is no separate invitation to accept or activation step. Depending on your welcome email settings (see below), Light sends the new user a welcome email tailored to their roles, with links to the web app and mobile apps to help them get started.

### Controlling Welcome Emails

When you create a user or update their roles, Light can send them a welcome email with onboarding information. You can control this behavior at two levels:

**Organization-wide default**: Go to **Organization Settings → User emails** and use the **Send emails** toggle to set the default behavior for your entire organization. When enabled, Light automatically sends welcome emails when users are created or when their roles change.

**Per-user override**: When creating or editing a user, you'll see a **Send welcome email** toggle in the user dialog. Use this to override the organization setting for a specific user. For example, if your organization default is enabled but you're making an internal role adjustment you don't want to notify the user about, toggle this off for that specific change.

> Good to know: The per-user toggle always reflects your organization default unless you explicitly change it. If you want to adjust the default for all future users, change the organization setting in Organization Settings.

## Assigning Multiple Roles

Users can have multiple roles simultaneously. For example, an invoice reviewer might need both **AP Clerk** and **Invoice Approver** roles. The **Access role** field in the user form accepts multiple selections — simply select additional roles as needed. The user will have the combined permissions from all selected roles.

## Changing User Details and Roles

To modify a user's roles or information after they've been created:

1. Go to **Business partners → Users**
2. Find the user in the list and click their name
3. Update any fields including their **Access role** by adding or removing roles
4. Click **Save**

The user's access updates immediately. They don't need to log out and back in for role changes to take effect.

## Archiving Users

To remove a user's access, you can archive their account:

1. Go to **Business partners → Users**
2. Find the user and click their name to open their details
3. Click the **Archive** button at the bottom of the dialog
4. Confirm your choice

Archived users cannot log in, but their historical data and audit trail remain in the system for compliance purposes.

> Important: Consider whether you need to reassign any workflows, approvals, or manager relationships before archiving a user.

## User Groups

In addition to roles, users can be organized into **groups** for access control and approval routing. To manage groups:

1. Go to **Business partners → Users**
2. Select the **Groups** tab
3. Click **+ Create group** to create a new group, or click an existing group to manage its members

Groups have a name, description, and member list. You can also assign users to groups directly from their user detail page via the **Groups** field. See [Setting up approval workflows](/mnt/help-articles/articles/03-user-management/3-3-approval-workflows.md) for details on using groups in approvals.

## Best Practices

- **Principle of least privilege**: Assign only the roles users need. Remove roles users no longer need.
- **Review regularly**: Audit user access quarterly as job responsibilities change.
- **Manager assignments**: Keep manager relationships up to date for approval routing.
- **Archive instead of ignoring**: Archive users who no longer need access to maintain a clean user list.

## Related Articles

- [User roles and permissions overview](/mnt/help-articles/articles/03-user-management/3-1-roles-permissions-overview.md)
- [Setting up approval workflows](/mnt/help-articles/articles/03-user-management/3-3-approval-workflows.md)
- [Two-factor authentication and security](/mnt/help-articles/articles/03-user-management/3-5-two-factor-auth.md)
