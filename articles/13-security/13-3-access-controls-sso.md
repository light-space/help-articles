# Access Controls and SSO

This article explains how to manage user access in Light using role-based controls and Single Sign-On (SSO) authentication.

[Open in Light →](https://app.light.inc/settings)

## Overview

Light provides flexible access control to ensure users can do their jobs while protecting sensitive financial data. You can grant permissions at the role level and restrict access by entity, department, and data type.

## Role-Based Access Control

Light includes pre-built roles for common job functions:

### Global Roles

- **Admin**: Full system access, can manage users, configure settings, and access all financial data
- **Finance Manager**: Access to all financial modules, can approve transactions and manage bank accounts
- **Accountant**: Can create and post journal entries, access transaction details, run reports
- **Approver**: Can approve expenses and documents up to their approval limit
- **Employee**: Can submit expenses and view their own reimbursement status
- **Viewer**: Read-only access to designated reports and dashboards

### Role Permissions

Each role includes permissions for:

- **Financial Transactions**: Create, edit, approve, post, or view transactions
- **Reconciliation**: Access to bank reconciliation and matching groups
- **Reporting**: Access to financial reports and dashboards
- **Administration**: User management, company settings, integration configuration
- **Data Export**: Permission to export data in bulk

> Good to know: Your Light administrator can create custom roles tailored to your organization's structure.

## Data-Level Access Control

Beyond global roles, Light provides fine-grained controls on specific data:

### Company Entity Access

Restrict users to specific companies or business units:

- **Single Entity**: User sees data only for one company
- **Multiple Entities**: User sees data across multiple selected companies
- **All Entities**: User sees all company data

### Department and Cost Center Access

Limit access by department or cost center:

- User sees only transactions for their department
- Expenses from other departments are hidden
- Reports show only department-relevant data

### Currency Access

Restrict access by currency:

- Users see transactions only in assigned currencies
- Multi-currency reports are filtered
- Exchange rate data is limited to assigned currencies

### Document Type Access

Granular controls on document types:

- Restrict journal entry access to accountants
- Allow employees to view only their own invoices
- Limit bank account access to finance personnel

## Setting Up Access Control

### For Global Roles

1. Navigate to **Admin** > **Users**
2. Select a user to edit
3. Under **Roles**, choose the appropriate role
4. Click **Save**

### For Entity-Level Access

1. Go to **Admin** > **Users**
2. Select a user
3. Under **Data Access**, select **Entities**
4. Choose which companies/entities the user can access
5. Click **Save**

### For Department-Level Access

1. Go to **Admin** > **Users**
2. Select a user
3. Under **Data Access**, select **Departments**
4. Choose which departments the user can access
5. Click **Save**

> Tip: Use department access to control expense visibility, preventing staff from viewing colleagues' sensitive spending.

## Approval Workflows

Light can enforce approval workflows based on user roles and transaction amounts:

### Approval Levels

1. Define approval levels (e.g., $0-$500, $500-$5,000, $5,000+)
2. Assign approvers to each level
3. Transactions automatically route to appropriate approvers

### Delegation

Approvers can temporarily delegate authority:

1. Go to **Settings** > **Delegation**
2. Select who to delegate to and for how long
3. Approvals route to the delegate during the period
4. Delegation automatically expires on the specified date

## Single Sign-On (SSO)

### Overview

Single Sign-On lets employees use their company credentials to access Light without creating separate usernames and passwords. Light supports SSO via Auth0.

### Supported Protocols

Light supports industry-standard SSO protocols:

- **SAML 2.0**: For companies with Okta, Azure AD, OneLogin, or other SAML providers
- **OpenID Connect (OIDC)**: For companies with Google Workspace, Office 365, or OIDC-compatible identity providers
- **OAuth 2.0**: For integration with social and corporate identity providers

### Setting Up SSO

#### Prerequisites

- Access to your company's identity provider (Okta, Azure AD, etc.)
- Light admin access
- Authority to configure SSO at your organization

#### Configuration Steps

1. Go to **Admin** > **Authentication Settings**
2. Select **Enable Single Sign-On**
3. Choose your identity provider (SAML or OIDC)
4. Configure connection details:
   - **Entity ID / Client ID**: Provided by your identity provider
   - **SSO URL**: The login endpoint for your identity provider
   - **Certificate**: SAML certificate (for SAML only)
5. Map user attributes (email, first name, last name, etc.)
6. Click **Test Connection** to verify configuration
7. Click **Enable** to activate SSO

#### SAML Configuration Example

If using Okta:

1. In Okta, create a new SAML application for Light
2. Set the **Assertion Consumer Service (ACS) URL** (also called the Callback URL or Reply URL) to: `https://light-inc-prod.eu.auth0.com/login/callback`
3. Set the Single Sign-On URL to your Light instance
4. Download the SAML certificate
5. In Light, upload the certificate and enter the SSO URL
6. Test the connection by logging in with Okta credentials

> Note: The callback URL `https://light-inc-prod.eu.auth0.com/login/callback` is the same for all identity providers (Okta, Azure AD, OneLogin, etc.).

#### OIDC Configuration Example

If using Azure AD:

1. Register Light as an application in Azure AD
2. Note the Client ID and Client Secret
3. In Light, select OIDC and enter Client ID and Secret
4. Configure the discovery endpoint
5. Test by logging in with Azure AD credentials

### Session Management

Light sessions are secured:

- **Timeout**: Sessions expire after 30 minutes of inactivity (configurable)
- **Logout**: Logging out of Light also logs out from SSO provider
- **Multiple Devices**: Users can be logged in on multiple devices simultaneously
- **Browser Cookies**: Session cookies are encrypted and httpOnly

### Multi-Factor Authentication (MFA)

For additional security, enable MFA:

1. In **Admin** > **Authentication Settings**, select **Require MFA**
2. Users must set up MFA (authenticator app, SMS, or hardware key)
3. MFA is required on every login
4. MFA settings sync with your identity provider if configured

> Good to know: MFA is recommended for all admin users and finance personnel with approval authority.

## Just-In-Time Provisioning

With SSO enabled, users are automatically created in Light on first login:

- **Automatic User Creation**: User accounts are created when they first log in
- **Attributes Mapped**: First name, last name, email are pulled from SSO provider
- **Default Role**: New users are assigned a default role (e.g., Viewer)
- **Manual Override**: Admins can still manually create users with custom roles

## SSO Troubleshooting

### Users Can't Log In

- Verify identity provider configuration is correct
- Check that user exists in identity provider
- Ensure user's email matches in both systems
- Review audit logs in Light for detailed error messages

### Wrong User Data Displayed

- Verify attribute mappings are correct in SSO configuration
- Check that identity provider is returning the correct attributes
- Update attribute mappings if your identity provider structure changed

### MFA Issues

- Users should set up MFA before logging in through the identity provider
- Clear browser cookies and try again
- Contact your IT team if MFA device is lost

## Related Articles

- Light's security architecture
- Data encryption and storage
- Compliance certifications
