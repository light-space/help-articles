# Gmail Integration

Gmail is Google's email platform used by millions of businesses. Light's Gmail integration automatically fetches receipt emails from your team's inboxes and matches them to corporate card transactions, using AI to extract merchant details, amounts, and dates — then auto-populates the accounting data on each transaction.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

The Gmail integration enables:

- **Automatic receipt fetching**: Light scans connected Gmail accounts for emailed receipts related to card transactions
- **AI-powered receipt matching**: Receipts are analyzed using AI to extract merchant name, transaction amount, and date, then matched to the corresponding card transaction
- **Auto-populated accounting**: Once a receipt is matched, Light automatically fills in the ledger account, tax code, and custom properties on the transaction
- **Secure OAuth connection**: Each user connects their own Gmail account through Google's OAuth 2.0 flow
- **Company-wide email access**: Admins can enable domain-wide email fetching via Google Workspace service account delegation

This eliminates manual receipt chasing and data entry for corporate card spend.

## Setting up Gmail integration

To connect your Gmail account:

1. Navigate to **Settings (gear icon) > Integrations > Gmail**
2. Click **Connect**
3. You're redirected to Google to authorize access
4. Sign in with the Google account you use for business email
5. Review the permissions Light is requesting
6. Click **Allow**
7. Light confirms the connection and redirects you back to the integrations page

Your Gmail account is now linked to your Light user profile.

> Good to know: Each user in your organization connects their own Gmail account individually. This ensures Light only accesses emails for users who have explicitly granted permission.

## Enabling email fetching for your company

After individual users connect their Gmail accounts, an admin can enable receipt fetching at the company level:

1. Navigate to **Settings (gear icon) > Integrations > Gmail**
2. Click **Activate** or toggle **Enable Email Fetching** to on
3. Light performs a connectivity check to verify it can access emails via your domain's service account
4. If the check passes, email fetching is now active for your organization

Once enabled, Light begins scanning connected Gmail accounts for receipt emails that match card transactions.

> Good to know: Company-wide email fetching requires your Google Workspace admin to configure domain-wide delegation for Light's service account. This grants Light read-only access to Gmail on behalf of authorized users in your domain. Contact your IT administrator if the connectivity check fails.

## How receipt matching works

Once Gmail is connected and email fetching is enabled:

1. Light fetches emails from connected Gmail accounts on a recurring basis
2. Emails containing receipt attachments (typically PDFs) are identified
3. AI analyzes each receipt to extract the merchant name, transaction amount, and date
4. Light matches the extracted data against your company's card transactions
5. When a match is found, the receipt is attached to the transaction and accounting fields are auto-populated — including ledger account, tax code, and any custom properties

This runs automatically in the background. Your team doesn't need to manually upload receipts or fill in transaction details for matched spend.

## Reviewing matched receipts

After Light matches a receipt to a card transaction:

1. Open the card transaction in Light
2. The matched receipt is attached to the transaction
3. Review the auto-populated accounting data (ledger account, tax code, custom properties)
4. Adjust any fields if needed, or approve the transaction as-is

If Light couldn't find a match or the AI extraction needs correction, you can manually upload a receipt or edit the transaction details.

## Google Workspace requirements

The Gmail integration supports two levels of access:

- **Individual OAuth connection**: Any Google account can connect via OAuth. This links your personal Gmail to your Light user profile and allows Light to access your emails with the permissions you granted.
- **Company-wide service account delegation**: For automatic receipt fetching across your organization, a Google Workspace admin must configure domain-wide delegation for Light's service account. This grants Light read-only Gmail access on behalf of users in your domain.

To set up domain-wide delegation:

1. Contact Light support to obtain the service account email and client ID
2. Your Google Workspace admin adds these credentials in the Google Admin Console under **Security > API Controls > Domain-wide Delegation**
3. Grant the `https://www.googleapis.com/auth/gmail.readonly` scope
4. Return to Light and activate the integration

## Connection status

You can check the status of your Gmail integration at any time:

1. Navigate to **Settings (gear icon) > Integrations > Gmail**
2. View your personal connection status: **Connected** or **Not Connected**
3. View the company-wide fetching status: **Enabled** or **Disabled**

Each user manages their own connection independently. The company-wide toggle is controlled by admins.

## Security and privacy

Light takes email security seriously:

- **OAuth 2.0**: Industry-standard authorization — Light never sees or stores your Google password
- **Encrypted credentials**: All access tokens and refresh tokens are encrypted at rest
- **Automatic token refresh**: Credentials refresh automatically so you don't need to re-authorize periodically
- **Read-only access**: Company-wide email fetching uses Gmail read-only scope — Light cannot send, delete, or modify your emails
- **Per-user authorization**: Each user must individually authorize Gmail access
- **Company isolation**: Email data and credentials are strictly isolated between companies

You can revoke Light's access at any time from your Google Account permissions page or from within Light's integration settings.

## Troubleshooting Gmail integration

**Connection fails during authorization**: Verify you're signing in with the correct Google account, check that third-party app access is enabled in your Google Workspace admin console, and try clearing your browser cookies before retrying.

**Connectivity check fails when activating**: This means domain-wide delegation hasn't been configured correctly for Light's service account. Verify the service account email, client ID, and granted scopes with your Google Workspace admin.

**Receipts not being matched to transactions**: Confirm email fetching is enabled at the company level, verify your personal Gmail account is connected, and check that receipt emails exist in the connected account's inbox. Matching depends on AI extraction — if the receipt format is unusual, the match may not be automatic.

**Connection shows "Not Connected" unexpectedly**: Your Google credentials may have expired or been revoked. Navigate to **Settings > Integrations > Gmail** and click **Connect** to re-authorize.

**Access denied error during OAuth**: Your Google Workspace admin may have restricted which third-party apps can access your organization's data. Ask your admin to allowlist Light in the Google Admin Console under **Security > API Controls**.

## Disabling the integration

To disable Gmail integration:

1. Navigate to **Settings (gear icon) > Integrations > Gmail**
2. Toggle **Enable Email Fetching** to off to stop company-wide receipt fetching
3. Individual users can disconnect their personal Gmail accounts separately

Previously matched receipts and auto-populated accounting data remain on transactions for historical reference.

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [Slack integration](11-4-slack.md)
- [API access and custom integrations](11-12-api-access.md)
