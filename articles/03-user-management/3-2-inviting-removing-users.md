# Inviting and Removing Users

Add new team members to Light and manage user access as your organization grows. This article covers inviting users, setting their roles, and removing access when needed.

[Open in Light →](https://app.light.inc/users)

## Inviting a New User

New users are invited via email and can be given roles during the invitation process. Follow these steps to invite a user:

1. Navigate to **Business partners → Users** ([Open in Light →](https://app.light.inc/users))
2. Click the **+ Create user** button
3. Enter the user's email address
4. Select their **Company Entity** (where they'll work primarily)
5. Select their **notification channel** (Slack, MS Teams, or Web App)
6. Select **one or more roles** based on their responsibilities
7. Click **Send Invitation**

The user will receive an email with a secure link to activate their account. They'll set their own password and can start using Light immediately after activation.

> Good to know: Email invitations expire after 7 days. If a user doesn't accept within this period, send a new invitation.

## User Information

When inviting users, you can optionally capture additional profile information:

- First name and last name
- Phone number (for contact and SMS notifications)
- Country and state (for localization and region-specific rules)
- Address and city
- Direct manager (for approval workflow routing)

This information helps Light route approvals correctly and personalize the user experience.

## Assigning Multiple Roles

Users can have multiple roles simultaneously. For example, an invoice reviewer might need both **AP Clerk** and **Invoice Approver** roles. When assigning multiple roles:

1. Select the first role checkbox
2. Continue selecting additional role checkboxes as needed
3. The user will have combined permissions from all selected roles

## Changing User Roles

To modify a user's roles after they've been invited:

1. Go to **Business partners → Users**
2. Find the user in the list and click their name
3. Update their **roles** by checking or unchecking role checkboxes
4. Click **Save Changes**

The user's access updates immediately. They don't need to log out and back in for role changes to take effect.

## Deactivating vs. Removing Users

You have two options for removing user access:

**Deactivate User** - The user's account is marked inactive. They cannot log in, but their historical data and permissions remain in the system. Use this when users are temporarily unavailable (leave, transfer).

**Remove User** - The user is permanently removed from the company. They cannot access any company data. Their historical audit trail remains for compliance.

To deactivate or remove a user:

1. Go to **Business partners → Users**
2. Find the user and click the **Actions** menu
3. Select **Deactivate** or **Remove**
4. Confirm your choice

> Important: Removing a user cannot be undone. All their permissions and settings are deleted immediately. Make sure the user no longer needs access to any company resources.

## User Status

Users can have one of three statuses:

**Active** - User can log in and access Light based on their assigned roles

**Deactivated** - User cannot log in. Account is preserved with all historical data intact. Can be reactivated by an admin.

**Pending** - User has been invited but hasn't yet activated their account by setting a password

## User Groups

In addition to roles, users can be added to **user groups** for organized access control and approval routing. Groups can be hierarchical (parent-child relationships) to reflect your organization structure. See [Setting up approval workflows](/mnt/help-articles/articles/03-user-management/3-3-approval-workflows.md) for details on using groups in approvals.

## Best Practices

- **Principle of least privilege**: Assign only the roles users need. Remove roles users no longer need.
- **Review regularly**: Audit user access quarterly as job responsibilities change.
- **Manager assignments**: Keep manager relationships up to date for approval routing.
- **Deactivate instead of remove**: Use deactivation for temporary absences to preserve audit history.

## Related Articles

- [User roles and permissions overview](/mnt/help-articles/articles/03-user-management/3-1-roles-permissions-overview.md)
- [Setting up approval workflows](/mnt/help-articles/articles/03-user-management/3-3-approval-workflows.md)
- [Two-factor authentication and security](/mnt/help-articles/articles/03-user-management/3-5-two-factor-auth.md)
