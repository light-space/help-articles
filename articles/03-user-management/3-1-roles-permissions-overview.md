# User Roles and Permissions Overview

Light uses a role-based access control system to manage what actions users can perform in your company. This article explains the available roles and their permissions.

[Open in Light →](https://app.light.inc/users?tab=roles)

## Understanding Roles

Roles define a set of permissions that determine what users can do in Light. Each user is assigned one or more roles, and their access is based on the combination of all assigned roles. Roles are company-wide, meaning they apply across all entities in your company.

## Available Roles

Light includes the following predefined roles:

**Admin** - Full system access with complete control over all features, configurations, and user management. Only assign this to administrators who need unrestricted access.

**Controller** - Access to financial reports, ledger management, and accounting period closing. Ideal for your finance controller or accounting manager.

**AP Clerk** - Covers day-to-day accounts payable work, including entering, editing, and submitting invoices, and managing payments. Also grants access to view financial reports and to view and post card transactions. Does not include invoice approval — that's handled by whoever is assigned as the Invoice Approver on a given document.

**AP Preparation** - Limited AP access for data entry and document preparation without approval authority. Useful for administrative staff preparing invoices.

**Invoice Approver** - Authority to approve invoices and payments within configured thresholds. Works with approval workflows to control document progression.

**AR Clerk** - Access to accounts receivable functions including invoice creation, customer management, and payment registration.

**Cardholder** - Access to corporate card features in Light. Includes viewing and disputing your own card transactions. Scoped to the cardholder's own activity, not company-wide card usage. This role does not grant access to expense reimbursement features — users who also need reimbursement must be assigned the **Reimbursement** role separately.

**Vendor Management** - Authority to create, edit, and approve vendor master data changes. Manages vendor information and payment details.

**Reimbursement** - Submit your own expenses and track the status of your own reimbursements. Scoped to the individual, not the team. This role does not grant access to corporate card features — users who also need card access must be assigned the **Cardholder** role separately.

**Report Viewer** - Read-only access to financial reports and dashboards. Ideal for stakeholders who need visibility without transaction access.

**Purchase Requester** - Access to create and manage purchase orders. Limited to procurement workflows.

**Auditor** - Read-only access to all company data for audit purposes. Auditors can view documents, transactions, reports, and configuration across the platform but cannot create, edit, approve, or post anything.

> **Important:** The **Cardholder** and **Reimbursement** roles are independent. A user with only the Cardholder role cannot access reimbursement features, and a user with only the Reimbursement role cannot access card features. If a user needs both, assign both roles.

## How Permissions Work

You can view the full permissions matrix by navigating to **Business partners → Users** and selecting the **Access roles** tab. This shows every permission grouped by feature area (e.g., Accounting Documents, Accounting Periods, AI Config, API Keys) and which roles have access to each.

Permissions are cumulative, meaning a user with multiple roles has the combined permissions of all their roles. If a role doesn't explicitly grant a permission, the user cannot perform that action.

## MCP (Model Context Protocol) Permissions

Light's MCP integration uses the same role-based access controls as the rest of the platform. When a user connects to Light via MCP, their permissions are determined by their assigned roles—the same roles that control their access in the Light web app.

This means:

- **Role-bound access** - MCP users can only perform actions their roles permit. A user with the **AP Clerk** role can access accounts payable functions via MCP, but not AR or admin functions.
- **Tool visibility** - Users only see MCP tools that are available to their role. Tools for features outside their permissions are not exposed.
- **No elevated privileges** - MCP does not grant any additional permissions beyond what the user already has in Light.

MCP access is currently an early-access feature. It must be turned on for your company before anyone can connect. Once enabled, access within MCP is still governed entirely by existing roles.

## Entities and Permissions

Roles in Light are company-wide and apply across all entities. It is not currently possible to scope a user's role or permissions to specific entities. For example, if a user has the **AP Clerk** role, they will have AP Clerk permissions in all entities within the company.

> **Note:** If you need to restrict users to specific entities, consider creating separate Light companies for each business unit that requires isolated access.

## Assigning and Modifying Roles

Only people with the Admin role can assign or change roles for others.

To assign or update someone's role:

1. Open the Light app and go to **Users** in the left navigation
2. Open the **Users** tab
3. Click the person's row
4. Edit the **Access role** field (multi-select)
5. Click **Save**

The person receives a welcome email when their access roles change.

A person can hold any number of roles at once. There's no system-enforced limit, and no combination of roles is blocked, including Cardholder and Reimbursement. Treating those two as a deliberate pairing (assign both if someone needs both) is a recommended practice, not a restriction the platform enforces.

Follow the principle of least privilege: assign only the roles a person needs to do their job. Reviewing roles periodically (for example, quarterly) is good practice for keeping access aligned with people's actual responsibilities, though this isn't a scheduled or automated feature in Light. The **Access roles** tab (see "How Permissions Work" above) is available any time you want to check current access.

## Related Articles

- [Inviting and removing users](3-2-inviting-removing-users.md)
- [Understanding and managing workflow automation](3-4-workflow-automation.md)
- [Setting up approval workflows](3-3-approval-workflows.md)
- [Two-factor authentication and security](3-5-two-factor-auth.md)

---

*Also searched as: user permissions, access control, role management, user access levels, team permissions, admin roles, permission settings in Light.*
