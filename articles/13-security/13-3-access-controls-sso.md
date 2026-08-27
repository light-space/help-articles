# Access Controls and SSO

Light provides role-based access controls, entity-level scoping, and approval guardrails to protect your financial data. Single Sign-On (SSO) is available through Light's managed authentication layer and is configured in coordination with Light's team.

## What is this page about

This page covers how you manage users, roles, groups, and entity assignment in Light, how approval guardrails and workflows control financial actions, and how to set up Single Sign-On. Read it when you are structuring who can do what across your finance team.

**On this page**

- User Management
- Approval Guardrails
- Workflows
- Policies
- Multi-Factor Authentication (MFA)
- Session Management
- Account Lockout and Brute-Force Protection
- Password Policy
- Single Sign-On (SSO)
- Related Articles

## User Management

User management lives under **Business partners > Users** in the main sidebar navigation. This page has three tabs: **Users**, **Groups**, and **Access roles**.

### Managing Users

The **Users** tab lists all users in your organisation, showing **Full name**, **Status**, **Email**, **City**, **Roles**, and **Groups**. You can search and filter the list, customise which columns are shown via the **Columns** button, and create new users with **+ Create user**.

Clicking on a user opens their detail form, where an admin can view or edit:

- **First name** and **Last name**
- **Email**
- **Address**, **Country**, **State**, **City**, and **Zip / postcode**
- **Phone number**
- **Entity**: the legal entity (company) the user belongs to, selected from a dropdown.
- **Communication channel**: how the user receives notifications, such as Slack.
- **Access role**: one or more roles assigned to the user, selected from a multi-select dropdown.
- **Manager**: the user's direct manager, used for approval routing.
- **Groups**: any groups the user belongs to.

### Access Roles

Each user is assigned one or more access roles that determine what they can see and do across the platform. Light includes the following predefined roles:

- **Admin**: full system access, including settings, user management, and all modules.
- **Controller**: broad access to financial oversight, reporting, and reconciliation.
- **AP clerk**: manages accounts payable tasks such as processing and viewing bills.
- **AP preparation**: prepares accounts payable records for review and posting.
- **AR clerk**: manages accounts receivable tasks such as invoicing.
- **Invoice approver**: reviews and approves invoices within the approval workflow.
- **Purchase requester**: submits purchase requests for approval.
- **Cardholder**: manages their assigned corporate card and related transactions.
- **Reimbursement**: submits and tracks expense reimbursements.
- **Vendor management**: manages vendor records and onboarding.
- **Report viewer**: read-only access to reports and dashboards.
- **Auditor**: read-only audit access to all data across the platform.

To assign roles, open a user's detail form from **Business partners > Users**, then select the desired role(s) from the **Access role** dropdown.

You can also view your own assigned roles in **Settings > Profile > Organization details**.

### Permissions Matrix

The **Access roles** tab on the Users page displays a full permissions matrix. Each row represents a specific permission (grouped by category), and each column represents a role. A checkmark indicates the role has that permission.

The matrix covers around 38 permission categories in total. Some examples:

- **Accounting Documents**: viewing accounting document pages.
- **Accounting Periods**: viewing accounting periods.
- **AI Config**: viewing and editing AI configuration.
- **API Keys**: viewing and editing API keys.
- **Cards**: editing cards, posting transactions to ledger, viewing card accounts and transactions, viewing own cards.
- **Company Settings**: editing and viewing company settings.
- **Contracts**: contract-related permissions.
- **Ledger**: viewing accounts, accrual templates, intercompany configurations and journal entries, journal entries, ledger transactions, reports, and tax codes.
- **Payables**: approving bills, creating and editing bills, managing credit entries, processing payments, and viewing bills.
- **Vendor Portal**: editing own vendor portal form.
- **Vendors**: adding new vendors, editing vendor bank details and details, requesting vendor onboarding, viewing vendors.
- **Workflows**: editing and viewing workflows.
- **Budget**, **Reimbursements**, **Policies**, **Tasks**, **Bank Reconciliation**, **Integration Settings**, and more.

This matrix is read-only and reflects the system-defined permissions for each role. Open the Access roles tab directly to see the complete list for your account.

### Groups

The **Groups** tab lets you organise users into groups. Each group has a name, an optional description, and a member count. Groups can be used to scope access, route approvals, or organise teams.

You can create new groups using the **+ Create group** button at the top of the Users page.

### Entity Assignment

Light supports multi-entity organisations. Each user is assigned to an entity (legal company) via the **Entity** dropdown on their user detail form.

Available entities are configured under **Settings > Entities**, where each entity has a code, legal name, display name, local currency, and VAT number.

## Approval Guardrails

Light uses **Guardrails** to enforce approval requirements on financial transactions. Guardrail settings are found under **Settings > Guardrails > Payables**.

### Bills

Under the **Bills** tab, you can view the approval rules that apply to bill payments. For example, a guardrail might require approval from a minimum number of approvers before a bill can be processed.

### Reimbursements

Under the **Reimbursements** tab, similar approval rules apply to expense reimbursements. Guardrails are configurable, so your organisation can set its own approval requirements, such as a minimum number of approvers, before a reimbursement is paid out.

> **Note:** Guardrail configurations are managed by Light. If you need to update your approval rules, contact your Light representative. The guardrails page shows a **Contact Light for update** prompt.

## Workflows

Light includes a visual **Workflow** builder for automating processes that involve approvals and other actions. Workflows are accessed from **Settings > Workflows**.

Each workflow is triggered by an event and can include approval steps, conditional logic, and automated actions. Pre-built workflows include:

- **Bill payment**: triggered when bill data changes.
- **Credit entry**: triggered when credit entry data changes.
- **Journal entry**: triggered when journal entry data changes.
- **Expense reimbursement**: triggered when an expense report is submitted.
- **Purchase request approval**: triggered when a purchase request is submitted.
- **Vendor card request**: triggered when a card request is created.
- **Dunning**: triggered as part of the collections process for overdue invoices.
- **Vendor onboarding**: triggered when a vendor is created or bank data changes.
- **Employee record updates**: triggered when an HRM system update is received.
- **Sync from HubSpot** and **Sync to HubSpot**: HubSpot syncs in both directions, with a separate workflow for each.
- **Sync from Salesforce** and **Sync to Salesforce**: Salesforce also syncs both ways.
- **Sync from Stripe**: Stripe data flows into Light.

Workflows are configured using a drag-and-drop node editor with **Action** and **Condition** blocks. Each workflow can be published, and the Workflows page shows the trigger, publication date, publisher, and version number.

## Policies

Under **Settings > Guardrails > Policies**, you can create and manage spend policies that are scoped to specific entities. Policies can be uploaded or created from scratch using the **+ Create policy** and **Upload** buttons. Each policy is associated with one or more entities and tracks the last edit date and editor.

## Multi-Factor Authentication (MFA)

MFA for your own users is governed by your identity provider. If your team signs in to Light through SSO, set your MFA policy in that provider and it applies to everyone signing in through it. MFA adds a second layer of verification beyond a password, protecting accounts even when a password is compromised.

Separately, Light requires MFA for its own staff whenever they access production systems and management consoles.

## Session Management

Light's authentication layer enforces session controls to limit exposure from unattended or hijacked sessions:

- **Inactivity timeout**: Sessions expire after a period of inactivity, requiring the user to re-authenticate.
- **Absolute session lifetime**: Sessions have a maximum lifetime regardless of activity, after which a fresh sign-in is required.
- **Sign-out propagation**: Signing out in Light revokes the active session at the identity layer.

Customers using SSO inherit session controls from their identity provider; values configured in the IdP take precedence over Light's defaults.

## Account Lockout and Brute-Force Protection

To protect against credential stuffing and brute-force attacks, Light's authentication layer applies:

- **Failed login throttling**: Repeated failed sign-in attempts trigger progressive delays.
- **Account lockout**: After repeated failures, the account is temporarily locked and the user is notified.
- **Anomaly detection**: Sign-in attempts from unusual locations, devices, or IPs are flagged for additional verification or blocked.
- **Bot and credential-stuffing protection**: Automated abuse signals are detected and blocked at the authentication layer.

Customers using SSO have these protections enforced by their own identity provider in addition to Light's perimeter controls.

## Password Policy

For customers signing in with a Light-managed password (rather than SSO), passwords are subject to:

- **Minimum length and complexity** requirements at the time of creation.
- **Common-password screening**, rejecting known breached or weak passwords.
- **Secure storage**, with passwords salted and hashed using a modern algorithm. Light staff cannot view customer passwords.
- **Reset on suspicion of compromise**, with a self-service reset flow and audit logging on the change.

For customers using SSO, password policy is governed by their identity provider.

## Single Sign-On (SSO)

Light supports Single Sign-On so that employees can log in using their company's identity provider rather than managing a separate username and password. Light's SSO is powered by a managed authentication layer.

### How SSO Works

Light's team configures SSO at the organisation level, so setup happens through your Light representative rather than in the app. To enable SSO, contact them and provide:

1. Your identity provider type (e.g., Okta, Azure AD, Google Workspace, OneLogin).
2. The relevant connection details for your provider:
   - For **SAML 2.0** providers: Entity ID, SSO URL, and signing certificate.
   - For **OpenID Connect (OIDC)** providers: Client ID, Client Secret, and discovery endpoint.
3. The user attributes you'd like mapped (e.g., email, first name, last name).

Light's team will configure the connection on Light's side and test it with you before going live.

### SAML Configuration

When setting up SAML-based SSO, you'll need to configure a new SAML application in your identity provider (e.g., Okta, Azure AD, OneLogin). Use the following callback URL:

- **Assertion Consumer Service (ACS) URL**: `https://light-inc-prod.eu.auth0.com/login/callback`

This callback URL is the same for all identity providers. Share your SAML metadata (Entity ID, SSO URL, and signing certificate) with your Light representative, and they will complete the configuration on Light's side.

> **Important:** When sharing your SAML certificate, use a secure method such as a 1Password shared link, an encrypted email, or another trusted secret-sharing tool. Do not send certificates as plain-text email attachments.

## Related Articles

- Security Architecture
- Data Encryption and Storage
