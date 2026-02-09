# Access Controls and SSO

Light provides role-based access controls, entity-level scoping, and approval guardrails to protect your financial data. Single Sign-On (SSO) is available through Light's Auth0-based authentication layer and is configured in coordination with Light's team.

## User Management

User management lives under **Business partners > Users** in the main sidebar navigation. This page has three tabs: **Users**, **Groups**, and **Access roles**.

### Managing Users

The **Users** tab lists all users in your organization, showing their full name, email, roles, groups, and city. You can search and filter the list, customize which columns are shown via the **Columns** button, and create new users with **+ Create user**.

Clicking on a user opens their detail form, where an admin can view or edit:

- **First name** and **Last name**
- **Email**
- **Address**, **Country**, **State**, **City**, and **Zip / postcode**
- **Phone number**
- **Entity** — the legal entity (company) the user belongs to, selected from a dropdown.
- **Communication channel** — how the user receives notifications (e.g., Slack).
- **Access role** — one or more roles assigned to the user, selected from a multi-select dropdown.
- **Manager** — the user's direct manager, used for approval routing.
- **Groups** — any groups the user belongs to.

Users can be archived from this form using the **Archive** button.

### Access Roles

Each user is assigned one or more access roles that determine what they can see and do across the platform. Light includes the following predefined roles:

- **Admin** — Full system access, including settings, user management, and all modules.
- **Controller** — Broad access to financial oversight, reporting, and reconciliation.
- **AP clerk** — Manages accounts payable tasks such as processing and viewing bills.
- **AP preparation** — Prepares accounts payable records for review and posting.
- **AR clerk** — Manages accounts receivable tasks such as invoicing.
- **Invoice approver** — Reviews and approves invoices within the approval workflow.
- **Purchase requester** — Submits purchase requests for approval.
- **Cardholder** — Manages their assigned corporate card and related transactions.
- **Reimbursement** — Submits and tracks expense reimbursements.
- **Vendor management** — Manages vendor records and onboarding.
- **Report viewer** — Read-only access to reports and dashboards.

To assign roles, open a user's detail form from **Business partners > Users**, then select the desired role(s) from the **Access role** dropdown.

You can also view your own assigned roles in **Settings > Profile > Organization details**.

### Permissions Matrix

The **Access roles** tab on the Users page displays a full permissions matrix. Each row represents a specific permission (grouped by category), and each column represents a role. A checkmark indicates the role has that permission.

Permission categories include:

- **Accounting Documents** — viewing accounting document pages.
- **Accounting Periods** — viewing accounting periods.
- **AI Config** — viewing and editing AI configuration.
- **API Keys** — viewing and editing API keys.
- **Cards** — editing cards, posting transactions to ledger, viewing card accounts and transactions, viewing own cards.
- **Company Settings** — editing and viewing company settings.
- **Contracts** — contract-related permissions.
- **Ledger** — viewing accounts, accrual templates, intercompany configurations and journal entries, journal entries, ledger transactions, reports, and tax codes.
- **Payables** — approving bills, creating and editing bills, managing credit entries, processing payments, and viewing bills.
- **Vendor Portal** — editing own vendor portal form.
- **Vendors** — adding new vendors, editing vendor bank details and details, requesting vendor onboarding, viewing vendors.
- **Workflows** — editing and viewing workflows.

This matrix is read-only and reflects the system-defined permissions for each role.

### Groups

The **Groups** tab lets you organize users into groups. Each group has a name, an optional description, and a member count. Groups can be used to scope access, route approvals, or organize teams.

You can create new groups using the **+ Create group** button at the top of the Users page.

### Entity Assignment

Light supports multi-entity organizations. Each user is assigned to an entity (legal company) via the **Entity** dropdown on their user detail form. This controls which entity's transactions and data they can access.

Available entities are configured under **Settings > Entities**, where each entity has a code, name, base currency, and VAT number.

### Levels

Users may also be assigned a **Level**, visible under **Settings > Profile > Organization details**. Levels can be used to further scope access or define approval hierarchies.

## Approval Guardrails

Light uses **Guardrails** to enforce approval requirements on financial transactions. Guardrail settings are found under **Settings > Guardrails > Payables**.

### Bills

Under the **Bills** tab, you can view the approval rules that apply to bill payments. For example, a guardrail might require approval from a minimum number of approvers before a bill can be processed.

### Reimbursements

Under the **Reimbursements** tab, similar approval rules apply to expense reimbursements — such as requiring approval from at least two approvers before a reimbursement is paid out.

> **Note:** Guardrail configurations are managed by Light. If you need to update your approval rules, contact your Light representative — you'll see a **Contact Light for update** prompt on the guardrails page.

## Workflows

Light includes a visual **Workflow** builder for automating processes that involve approvals and other actions. Workflows are accessed from **Settings > Workflows**.

Each workflow is triggered by an event and can include approval steps, conditional logic, and automated actions. Pre-built workflows include:

- **Bill payment** — triggered when bill data changes.
- **Expense reimbursement** — triggered when an expense report is submitted.
- **Vendor card request** — triggered when a card request is created.
- **Invoice-to-cash** — triggered when an invoice is posted.
- **Vendor onboarding** — triggered when a vendor is created or bank data changes.
- **Employee record updates** — triggered when an HRM system update is received.
- **Sync from HubSpot** / **Sync to Salesforce** / **Sync from Salesforce** — triggered by data changes in external systems.

Workflows are configured using a drag-and-drop node editor with **Action** and **Condition** blocks. Each workflow can be published, and the Workflows page shows the trigger, publication date, publisher, and version number.

## Policies

Under **Settings > Guardrails > Policies**, you can create and manage spend policies that are scoped to specific entities. Policies can be uploaded or created from scratch using the **+ Create policy** and **Upload** buttons. Each policy is associated with one or more entities and tracks the last edit date and editor.

## Single Sign-On (SSO)

Light supports Single Sign-On so that employees can log in using their company's identity provider rather than managing a separate username and password. Light's SSO is powered by Auth0.

### How SSO Works

SSO is configured at the organization level in coordination with Light's team — there is no self-service SSO setup screen in the Light app. To enable SSO, contact your Light representative and provide:

1. Your identity provider type (e.g., Okta, Azure AD, Google Workspace, OneLogin).
2. The relevant connection details for your provider:
   - For **SAML 2.0** providers: Entity ID, SSO URL, and signing certificate.
   - For **OpenID Connect (OIDC)** providers: Client ID, Client Secret, and discovery endpoint.
3. The user attributes you'd like mapped (e.g., email, first name, last name).

Light's team will configure the connection on the Auth0 backend and test it with you before going live.

### SAML Configuration

When configuring your identity provider for SAML-based SSO:

1. In your identity provider (e.g., Okta, Azure AD, OneLogin), create a new SAML application for Light.
2. Set the **Assertion Consumer Service (ACS) URL** (also called the Callback URL or Reply URL) to: `https://light-inc-prod.eu.auth0.com/login/callback`
3. Set the Single Sign-On URL to your Light instance.
4. Download the SAML certificate.
5. In Light, upload the certificate and enter the SSO URL.
6. Test the connection by logging in with your identity provider credentials.

> **Note:** The callback URL `https://light-inc-prod.eu.auth0.com/login/callback` is the same for all identity providers (Okta, Azure AD, OneLogin, etc.).

### Just-In-Time Provisioning

When SSO is enabled, new users can be provisioned automatically on their first login. Their name and email are pulled from the identity provider, and they receive a default role. Admins can then adjust roles and entity assignments as needed from **Business partners > Users**.

### Multi-Factor Authentication (MFA)

If your organization requires multi-factor authentication, this is configured through your identity provider. Light's Auth0 layer respects the MFA requirements set by your IdP, so users will be prompted for MFA during the SSO login flow if your provider enforces it.

### Session and Security

Light enforces session timeouts for inactive users.

## Related Articles

- [Security Architecture](/articles/13-security/13-1-security-architecture)
- [Data Encryption and Storage](/articles/13-security/13-2-data-encryption-storage)
