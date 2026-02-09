# Two-Factor Authentication and Security

Two-factor authentication (2FA) adds an extra security layer by requiring users to provide two forms of identification before accessing Light. This article explains 2FA and other security features.

[Open in Light →](https://app.light.inc/settings/profile)

## What is Two-Factor Authentication?

2FA requires two independent verification methods to log in:

1. **Something you know** - Your password
2. **Something you have** - A code from your phone (authenticator app or SMS)

Even if someone obtains your password, they cannot access your account without the second factor. This significantly reduces the risk of unauthorized account access.

## Enabling 2FA

Light uses a secure authentication provider to manage login and 2FA. Two-factor authentication is configured through the login flow rather than from within the Light application settings. Contact your company administrator to enable 2FA requirements for your organization.

Once 2FA is enabled for your account, you will be prompted for a verification code each time you log in with your email and password.

## Password Reset

If you forget your password:

1. Click **Forgot password?** on the login page
2. Enter your email address
3. Click the link in the email you receive
4. Set a new password
5. Log in with your new password

If you're locked out and cannot reset via email, contact your company administrator.

## API Keys

Light uses API keys for programmatic access and integrations. API keys are managed under **Settings → API keys** ([Open in Light →](https://app.light.inc/settings/api-keys)).

The API keys page shows all keys with their name, key prefix, assigned role, status, and creation date.

To create an API key:

1. Go to **Settings → API keys**
2. Click **+ Create key**
3. Enter a **Name** for the key (e.g., "Salesforce Integration")
4. Select an **Access role** to define what permissions the key has
5. Optionally specify **Allowed IP patterns** to restrict which IPs can use the key
6. Click **Create**
7. Copy the key and store it securely — you'll only see the full key once

API keys can have one of two statuses:

**Active** - The key is valid and can be used for API calls.

**Revoked** - The key has been deactivated and can no longer be used.

> Important: The full key is only displayed once at creation. If lost, revoke the key and generate a new one.

## API Key Best Practices

- **Use minimal permissions** - Assign only the access role the integration needs
- **Restrict by IP** - Use allowed IP patterns to limit where keys can be used from
- **Rotate regularly** - Revoke and recreate keys every 90 days
- **Never commit to code** - Use environment variables or secure vaults
- **Revoke immediately** if a key is compromised

## Profile Settings

Your personal profile is managed under **Settings → Profile** ([Open in Light →](https://app.light.inc/settings/profile)), which includes:

**Contact Information** - Your name, email, phone number, and address details.

**User Settings** - Preferences for appearance (light/dark mode), numeric format, CSV data separator, and sidebar behavior.

**Reimbursement Details** - Bank information for expense reimbursements (bank country, IBAN, BIC/SWIFT, account details).

**Organization Details** - Read-only view of your assigned access roles, entity, level, and groups.

## Best Practices

- **Use strong passwords** - Mix of character types and sufficient length
- **Rotate API keys** - Every 90 days minimum
- **Report incidents** - Immediately report suspicious activity to your admin
- **Restrict API key IPs** - Limit API key usage to known IP ranges

## Related Articles

- [User roles and permissions overview](/mnt/help-articles/articles/03-user-management/3-1-roles-permissions-overview.md)
- [Inviting and removing users](/mnt/help-articles/articles/03-user-management/3-2-inviting-removing-users.md)
- [Audit log and activity history](/mnt/help-articles/articles/03-user-management/3-6-audit-log.md)
