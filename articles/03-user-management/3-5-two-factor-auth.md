# Two-Factor Authentication and Security

Two-factor authentication (2FA) adds an extra security layer by requiring users to provide two forms of identification before accessing Light. This article explains 2FA and other security features.

[Open in Light →](https://app.light.inc/settings/profile)

## What is Two-Factor Authentication?

2FA requires two independent verification methods to log in:

1. **Something you know** - Your password
2. **Something you have** - A code from your phone (authenticator app or SMS)

Even if someone obtains your password, they cannot access your account without the second factor. This significantly reduces the risk of unauthorized account access.

## Enabling 2FA for Your Account

To enable two-factor authentication on your user account:

1. Go to **Settings (gear icon) > Profile** ([Open in Light →](https://app.light.inc/settings/profile))
2. Click **Enable Two-Factor Authentication**
3. Choose your preferred method:
   - **Authenticator app** (recommended) - Use an app like Google Authenticator or Microsoft Authenticator
   - **SMS** - Receive codes via text message
4. Follow the setup wizard to configure your chosen method

For authenticator apps, scan the QR code presented or enter the setup key manually. Save the backup codes in a secure location—use them if you lose access to your authenticator.

> Important: Back up your recovery codes immediately. If you lose your phone, you'll need these codes to regain access to your account.

## Using 2FA to Log In

Once 2FA is enabled:

1. Log in with your email and password as usual
2. When prompted, enter the 6-digit code from your authenticator app or SMS
3. Click **Verify**

Each code is valid for 30 seconds. If your code expires, a new one is generated automatically.

## Managing Your 2FA Method

You can change or disable 2FA anytime:

1. Go to **Settings (gear icon) > Profile**
2. Click **Manage Two-Factor Authentication**
3. Choose to **change method** (switch between app and SMS) or **disable 2FA**
4. Confirm your identity with your current 2FA code

> Good to know: Company admins can require all users to enable 2FA as a security policy.

## Recovery Codes

Recovery codes are backup codes generated when you set up 2FA:

- **10 single-use codes** that can substitute for your 2FA code
- **Use when** you don't have access to your authenticator or phone
- **Save securely** - Store in a password manager or print and secure physically
- **Never share** - Treat recovery codes like passwords

Each recovery code can only be used once. Once used, it's deleted.

## API Keys and Secure Access

In addition to user authentication, Light uses API keys for programmatic access:

**Service Accounts** - Non-human accounts used for integrations and automations

**API Keys** - Long-lived credentials for service accounts that authenticate external systems

API keys should be:

- **Created with minimal permissions** - Grant only necessary roles
- **Rotated regularly** - Update to new keys every 90 days
- **Never committed to code** - Use environment variables or secure vaults
- **Immediately deactivated** if compromised

To create an API key:

1. Go to **Settings (gear icon) > API keys**
2. Click **+ Create service account** and name it (e.g., "Salesforce Integration")
3. Assign necessary roles
4. Click **Generate API Key**
5. Copy the key and store securely (you'll only see it once)

> Important: Display the key only once for security. If lost, deactivate and generate a new one.

## Session Security

Light automatically manages user sessions for security:

**Session timeout** - Users are logged out after 30 minutes of inactivity to prevent unauthorized access on unattended devices

**Device trust** - Sensitive actions may require additional verification even for logged-in users

**Concurrent sessions** - Users can have multiple active sessions across devices

If you see unfamiliar sessions or locations, log out other sessions from **Settings (gear icon) > Profile** and reset your password.

## Password Requirements

Passwords must meet these criteria:

- Minimum 12 characters (longer is better)
- Include uppercase, lowercase, numbers, and special characters
- Cannot match previous passwords
- Cannot contain your username or email

> Tip: Use a passphrase (multiple words) for memorable yet secure passwords.

## Suspicious Activity

Light monitors for suspicious activity:

- **Multiple failed login attempts** - Account temporarily locked after 5 failed attempts
- **Login from unusual location** - Additional verification may be required
- **Unusual data access patterns** - Admins are notified

If your account is locked, contact your company admin or use a recovery code to regain access.

## Password Reset

If you forget your password:

1. Click **Forgot Password** on the login page
2. Enter your email address
3. Click the link in the email you receive
4. Set a new password
5. Log in with your new password

Password reset links expire after 24 hours. If yours expires, request another reset.

If you're locked out and cannot reset via email, contact your company administrator.

## Security Audit Trail

Light maintains audit logs of user access and sensitive actions:

- **Who logged in** and when
- **API calls** made by service accounts
- **Permission changes** applied to users
- **Data access** by external systems

Admins can review logs in **Settings (gear icon) > Audit Logs** to detect unauthorized activity.

## Best Practices

- **Enable 2FA** - Recommended for all users, required for admins
- **Use strong passwords** - Mix of character types and sufficient length
- **Rotate API keys** - Every 90 days minimum
- **Secure recovery codes** - Store offline in a safe location
- **Monitor sessions** - Periodically review active sessions and log out unfamiliar ones
- **Report incidents** - Immediately report suspicious activity to your admin

## Related Articles

- [User roles and permissions overview](/mnt/help-articles/articles/03-user-management/3-1-roles-permissions-overview.md)
- [Inviting and removing users](/mnt/help-articles/articles/03-user-management/3-2-inviting-removing-users.md)
- [Audit log and activity history](/mnt/help-articles/articles/03-user-management/3-6-audit-log.md)
