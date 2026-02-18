# Gmail Integration

Gmail is Google's email platform used by millions of businesses worldwide. Light's Gmail integration connects your email directly to your financial workflow, automatically linking email threads to invoices, bills, and customer records so your team never loses context on financial communications.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

The Gmail integration enables:

- **Email linking**: Associate email threads with invoices, bills, and other financial documents
- **Automatic context**: View relevant email conversations alongside transactions
- **Secure OAuth connection**: Connect your Gmail account with Google's secure authorization flow
- **Company-wide access**: Enable email fetching across your organization with a single toggle
- **Token management**: Automatic credential refresh keeps your connection active without manual intervention

This creates a seamless link between financial records and the email conversations behind them.

## Setting up Gmail integration

To connect Gmail:

1. Navigate to **Settings (gear icon) > Integrations > Gmail**
2. Click **Connect**
3. You're redirected to Google to authorize access
4. Sign in with the Google account you use for business email
5. Review the permissions Light is requesting (read and label access)
6. Click **Allow**
7. Light confirms the connection and redirects you back to the integrations page

Your Gmail account is now linked to your Light user profile.

> Good to know: Each user in your organization connects their own Gmail account. This ensures Light only accesses emails for users who have explicitly authorized the connection.

## Enabling email fetching for your company

After connecting your personal Gmail account, an admin can enable email fetching at the company level:

1. Navigate to **Settings (gear icon) > Integrations > Gmail**
2. Toggle **Enable Email Fetching** to on
3. Light performs a connectivity check to verify access
4. If successful, email fetching is now active for your organization

Once enabled, Light can retrieve email threads associated with your financial documents.

> Good to know: Email fetching requires your Google Workspace admin to configure domain-wide delegation for Light's service account. This allows Light to securely access emails on behalf of authorized users. Contact your IT administrator if the connectivity check fails.

## How email linking works

Once Gmail is connected and email fetching is enabled:

1. Light scans for email threads relevant to your financial documents
2. Matching emails are linked to the corresponding invoice, bill, or customer record
3. You can view linked email threads directly from the transaction detail page
4. Email context is available to anyone on your team with access to that transaction

This means when reviewing an invoice, you can instantly see the email conversation that preceded it — no more searching your inbox for context.

## Viewing linked emails

To view emails linked to a financial document:

1. Open any invoice, bill, or customer record in Light
2. Look for the **Email** section or tab on the detail view
3. See linked email threads with subject, date, and participants
4. Click a thread to expand and read the conversation

This keeps all communication context in one place alongside your financial data.

## Managing your Gmail connection

You can manage your personal Gmail connection at any time:

1. Navigate to **Settings (gear icon) > Integrations > Gmail**
2. View your connection status (Connected or Not Connected)
3. To disconnect, click **Disconnect**
4. To reconnect, click **Connect** and re-authorize with Google

Disconnecting removes Light's access to your Gmail. Previously linked emails remain visible on transactions but no new emails will be fetched for your account.

## Google Workspace requirements

The Gmail integration works with Google Workspace (formerly G Suite) accounts. For full functionality:

- **Individual connection**: Any Google account can authorize via OAuth for personal email linking
- **Company-wide fetching**: Requires Google Workspace with domain-wide delegation configured for Light's service account
- **Admin setup**: A Google Workspace admin must grant Light's service account read-only access to Gmail for your domain

If your organization uses Google Workspace, ask your IT administrator to configure domain-wide delegation. Light's support team can provide the service account details needed for setup.

## Security and privacy

Light takes email security seriously:

- **OAuth 2.0**: Industry-standard authorization — Light never sees or stores your Google password
- **Encrypted storage**: All access credentials are encrypted at rest using AES encryption
- **Automatic token refresh**: Credentials refresh automatically so you don't need to re-authorize
- **Read-only fetching**: Company-wide email fetching uses read-only access — Light cannot send, delete, or modify your emails
- **Per-user authorization**: Each user must individually authorize Gmail access
- **Company isolation**: Email data is strictly isolated between companies

You can revoke Light's access at any time from your Google Account permissions page or from within Light.

## Troubleshooting Gmail integration

**Connection fails during authorization**: Verify you're signing in with the correct Google account, check that third-party app access is enabled in your Google Workspace admin console, and try clearing your browser cookies before retrying.

**Email fetching toggle won't enable**: This typically means domain-wide delegation hasn't been configured for Light's service account. Contact your Google Workspace admin to set this up, then retry.

**Emails not appearing on transactions**: Confirm email fetching is enabled at the company level, verify your personal Gmail account is connected, and check that relevant emails exist in the connected account's mailbox.

**Connection shows "Not Connected" unexpectedly**: Your Google credentials may have expired or been revoked. Navigate to Settings > Integrations > Gmail and click **Connect** to re-authorize.

**Access denied error during OAuth**: Your Google Workspace admin may have restricted which third-party apps can access your organization's data. Ask your admin to allowlist Light in the Google Admin Console under Security > API Controls.

## Disabling the integration

To disable Gmail integration entirely:

1. Navigate to **Settings (gear icon) > Integrations > Gmail**
2. Toggle **Enable Email Fetching** to off (disables company-wide fetching)
3. Individual users can disconnect their accounts separately

Previously linked emails remain on transactions for historical reference.

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [Slack integration](11-4-slack.md)
- [API access and custom integrations](11-12-api-access.md)
