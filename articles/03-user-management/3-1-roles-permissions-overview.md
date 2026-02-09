# User Roles and Permissions Overview

Light uses a role-based access control system to manage what actions users can perform in your company. This article explains the available roles and their permissions.

[Open in Light →](https://app.light.inc/users?tab=roles)

## Understanding Roles

Roles define a set of permissions that determine what users can do in Light. Each user is assigned one or more roles, and their access is based on the combination of all assigned roles. Roles are company-wide, meaning they apply across all entities in your company.

## Available Roles

Light includes the following predefined roles:

**Admin** - Full system access with complete control over all features, configurations, and user management. Only assign this to administrators who need unrestricted access.

**Controller** - Access to financial reports, ledger management, and accounting period closing. Ideal for your finance controller or accounting manager.

**AP Clerk** - Access to accounts payable functions including invoice entry, approval workflows, and payment management. Can view AP-specific data only.

**AP Preparation** - Limited AP access for data entry and document preparation without approval authority. Useful for administrative staff preparing invoices.

**Invoice Approver** - Authority to approve invoices and payments within configured thresholds. Works with approval workflows to control document progression.

**AR Clerk** - Access to accounts receivable functions including invoice creation, customer management, and payment registration.

**Cardholder** - Access to corporate card features and transaction history. Users can view and dispute card transactions, report fraud. This role does not grant access to expense reimbursement features — users who also need reimbursement must be assigned the **Reimbursement** role separately.

**Vendor Management** - Authority to create, edit, and approve vendor master data changes. Manages vendor information and payment details.

**Reimbursement** - Access to employee expense reimbursement features. Users can submit expenses and view reimbursement status. This role does not grant access to corporate card features — users who also need card access must be assigned the **Cardholder** role separately.

**Report Viewer** - Read-only access to financial reports and dashboards. Ideal for stakeholders who need visibility without transaction access.

**Purchase Requester** - Access to create and manage purchase orders. Limited to procurement workflows.

> **Important:** The **Cardholder** and **Reimbursement** roles are independent. A user with only the Cardholder role cannot access reimbursement features, and a user with only the Reimbursement role cannot access card features. If a user needs both, assign both roles.

## How Permissions Work

You can view the full permissions matrix by navigating to **Business partners → Users** and selecting the **Access roles** tab. This shows every permission grouped by feature area (e.g., Accounting Documents, Accounting Periods, AI Config, API Keys) and which roles have access to each.

Permissions are cumulative, meaning a user with multiple roles has the combined permissions of all their roles. If a role doesn't explicitly grant a permission, the user cannot perform that action.

## Entities and Permissions

Permissions can also be scoped by entity. A user may have full access in one entity but limited or no access in another. This is useful for multi-entity companies where you want to restrict certain users to specific operating units.

## Assigning and Modifying Roles

Roles are assigned by users with the Admin role. When assigning roles, consider the principle of least privilege: give users only the roles they need to perform their job.

> Tip: Review user roles quarterly. Periodically audit who has which roles to ensure access is still appropriate as job responsibilities change.

## Related Articles

- [Inviting and removing users](/mnt/help-articles/articles/03-user-management/3-2-inviting-removing-users.md)
- [Understanding and managing workflow automation](/mnt/help-articles/articles/03-user-management/3-4-workflow-automation.md)
- [Setting up approval workflows](/mnt/help-articles/articles/03-user-management/3-3-approval-workflows.md)
- [Two-factor authentication and security](/mnt/help-articles/articles/03-user-management/3-5-two-factor-auth.md)
