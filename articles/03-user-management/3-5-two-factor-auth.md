# Two-Factor Authentication and Security

> **What's this page about:** How sign-in security works in Light, including two-factor authentication, password resets, API keys, and where your profile and security settings live.

[Open in Light →](https://app.light.inc/settings/profile)

**On this page:**

- Two-factor authentication and password reset
- API keys
- Profile settings
- Security best practices

Light protects your account with two-factor authentication (2FA) and delegates sign-in to a dedicated authentication provider, so your credentials never sit inside Light's own systems.

## Two-factor authentication and password reset

Light handles sign-in, 2FA, and password reset through its authentication provider, separate from Light's application settings. You won't find a 2FA toggle inside Light itself.

With 2FA turned on, signing in takes two steps: your password, plus a one-time code from an authenticator app (SMS may also be available, depending on your organization's setup).

If your organization wants 2FA enabled, contact Light support. This is configured at the organization level by Light, not by a local admin setting inside the product.

**To reset your password:**

1. Open Light and select **Log in**
2. On the sign-in screen, choose the password reset option
3. Enter your email address
4. Open the email you receive and select the reset link
5. Set a new password and log in to Light

If you're locked out and can't complete this by email, contact Light support.

## API keys

Light uses API keys for programmatic access and integrations. Manage them in Light under **Settings → API keys** ([Open in Light →](https://app.light.inc/settings/api-keys)).

The API keys page lists, for each key: name, an obfuscated version of the key, Roles, status, creation date, who created it, and who revoked it (if applicable).

**To create an API key:**

1. In Light, go to **Settings → API keys**
2. Select **Create key** (shown with a plus icon)
3. Enter a **Name** (for example, "Salesforce Integration")
4. Select the **Access role** the key needs
5. Optionally, set **Allowed IP patterns** to restrict which IPs can use the key
6. Select **Create**
7. Copy the key and store it securely. Light shows the full key only once.

A key's status is either **Active** (valid and usable) or **Revoked** (deactivated, can no longer be used).

If you lose a key, use **Rotate** to generate a new one. This invalidates the previous key immediately.

**Recommended practice:** rotate keys periodically (for example, every 90 days), restrict IPs where possible, and revoke a key immediately if it's compromised. These are security recommendations, not requirements enforced by Light.

## Profile settings

Manage your profile in Light under **Settings → Profile** ([Open in Light →](https://app.light.inc/settings/profile)). It has seven sections. Six are visible to every authenticated user, with no role restrictions:

- **Contact information**: first name, last name, email, phone number, and address (street, city, state, ZIP/postal code, country)
- **Notifications**: your notification preferences
- **User preferences**: appearance (light/dark mode), numeric format, date format, CSV data separator, and sidebar behavior
- **Claude MCP**: connect Claude to your Light workspace
- **MCP tokens**: manage tokens used for MCP connections
- **Organization details**: read-only view of your assigned access roles, entity, level, and groups

The seventh section, **Reimbursement details** (bank information for expense reimbursements: bank country, IBAN, BIC/SWIFT, account details), only appears for users explicitly assigned the **Reimbursement** access role. This is a literal match on that specific role — having a broad role like Superuser or Company admin doesn't grant access on its own; the Reimbursement role has to be assigned directly.

## Security best practices

- Use a strong, unique password
- Rotate API keys periodically and restrict them by IP where possible
- Report suspicious account activity to your admin immediately
- Revoke any API key you suspect is compromised right away

## Related Articles

- [User roles and permissions overview](https://help.light.inc/user-management/roles-permissions-overview)
- [Inviting and removing users](https://help.light.inc/user-management/inviting-removing-users)
- [Audit log and activity history](https://help.light.inc/user-management/audit-log)

---

*Also searched as: 2FA, two-step verification, MFA, multi-factor authentication, forgot password, reset password, can't log in, login help, API key, API token, revoke API key, rotate API key, create API key, profile settings, account settings, security settings, notification settings, CSV data separator.*
