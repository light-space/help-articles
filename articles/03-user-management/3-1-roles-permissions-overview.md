# User Roles and Permissions Overview

> **What is this page about:** How user roles and permissions work in Light, from the roles you can assign to how access adds up, where to review it, and who can make changes.

[Open in Light →](https://app.light.inc/users?tab=roles)

## On this page

- Understanding Light user roles
- Available Light user roles
- How Light permissions work
- MCP permissions in Light
- Entities and permissions in Light
- Assigning and modifying user roles in Light

## Understanding Light User Roles

A role is a bundle of permissions. You assign one or more roles to each person in the Light app, and their access is the combination of everything those roles allow. Roles apply company-wide: once someone has a role, it works the same way across every entity in your company.

## Available Light User Roles

- **Admin**: full system access, with control over every feature, configuration, and user in the company. Reserve this for people who need unrestricted access.
- **Controller**: for your finance controller or accounting manager. Grants access to financial reports, ledger management, and closing accounting periods.
- **AP Clerk**: covers day-to-day accounts payable work, including entering, editing, and submitting invoices, and managing payments. Also grants access to view financial reports and to view and post card transactions. Does not include invoice approval. That's handled by whoever is assigned as the Invoice Approver on a given document.
- **AP Preparation**: a lighter version of AP Clerk for staff who prepare invoices and documents but don't need approval authority.
- **Invoice Approver**: authority to approve invoices and payments up to a configured threshold. Works with your approval workflows to control how documents move forward.
- **AR Clerk**: handles accounts receivable, including creating invoices, managing customers, and registering payments.
- **Cardholder**: access to corporate card features in Light. Includes viewing and disputing your own card transactions. Scoped to the cardholder's own activity, not company-wide card usage. Does not include expense reimbursement; assign the Reimbursement role for that.
- **Vendor Management**: create, edit, and approve changes to vendor records and payment details.
- **Reimbursement**: submit your own expenses and track the status of your own reimbursements. Scoped to the individual, not the team. Does not include corporate card access; assign the Cardholder role for that.
- **Report Viewer**: read-only access to financial reports and dashboards. For stakeholders who need visibility but shouldn't touch transactions.
- **Purchase Requester**: create and manage purchase orders. Scoped to procurement workflows only.
- **Auditor**: read-only access to documents, transactions, reports, and configuration across the platform. Can view everything but can't create, edit, approve, or post.

**Cardholder and Reimbursement are independent roles.** Someone with only Cardholder can't touch reimbursements. Someone with only Reimbursement can't touch card features. Assign both roles if a person needs both.

## How Light Permissions Work

To see what each role can and can't do:

1. Open the Light app and go to **Business partners → Users**
2. Open the **Access roles** tab

This lists every permission by feature area (for example, Accounting Documents, Accounting Periods, AI Config, API Keys) and shows which roles have access to each one.

Permissions stack. If a person has more than one role, they get the combined permissions of all of them. If none of a person's roles grant a permission, they can't do that thing. There is no partial or implied access.

## MCP (Model Context Protocol) Permissions in Light

If your team connects to Light through MCP, the same role-based rules apply there. Going through MCP grants no extra access beyond the Light app.

- **Role-bound access**: a person using MCP can only do what their roles already allow in Light. For example, an AP Clerk connected via MCP can work with accounts payable, but not AR or admin functions.
- **Tool visibility**: people only see the MCP tools that match their role. A tool outside their permissions won't appear.
- **No shortcuts**: MCP never grants privileges beyond what a person already has inside Light.

MCP access is currently an early-access feature. It must be turned on for your company before anyone can connect. Once enabled, access within MCP is still governed entirely by existing roles.

## Entities and Permissions in Light

Roles apply across your whole company, not to individual entities. There is currently no way to grant a role for one entity only (for example, AP Clerk access for Entity A but not Entity B). Wherever a role applies, it applies everywhere.

To limit certain people to specific parts of the business, set up separate Light companies for each business unit that needs isolated access.

## Assigning and Modifying User Roles in Light

Only people with the Admin role can assign or change roles for others.

To assign or update someone's role:

1. Open the Light app and go to **Users** in the left navigation
2. Open the **Users** tab
3. Click the person's row
4. Edit the **Access role** field (multi-select)
5. Click **Save**

The person receives a welcome email when their access roles change.

A person can hold any number of roles at once. There's no system-enforced limit, and no combination of roles is blocked, including Cardholder and Reimbursement. Treating those two as a deliberate pairing (assign both if someone needs both) is a recommended practice, not a restriction the platform enforces.

Follow the principle of least privilege: assign only the roles a person needs to do their job. Reviewing roles periodically (for example, quarterly) is good practice for keeping access aligned with people's actual responsibilities, though this isn't a scheduled or automated feature in Light. The **Access roles** tab (see "How Light Permissions Work" above) is available any time you want to check current access.

## Related Articles

- [Inviting and Removing Users](https://help.light.inc/user-management/inviting-removing-users)
- [Understanding and Managing Workflow Automation](https://help.light.inc/user-management/workflow-automation)
- [Setting Up Approval Workflows](https://help.light.inc/user-management/approval-workflows)
- [Two-Factor Authentication and Security](https://help.light.inc/user-management/two-factor-auth)

---

*Also searched as: user permissions, access control, role management, user access levels, team permissions, admin roles, permission settings in Light.*
