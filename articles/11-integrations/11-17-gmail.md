# Gmail Integration

Gmail is Google's email platform used by millions of businesses. Light's Gmail integration automatically fetches receipt emails from your team's inboxes and matches them to corporate card transactions, using AI to extract merchant details, amounts, and dates — then auto-populates the accounting data on each transaction.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

The Gmail integration enables:

- **Automatic receipt fetching**: Light scans your company's Gmail accounts for emailed receipts related to card transactions
- **AI-powered receipt matching**: Receipts are analyzed using AI to extract merchant name, transaction amount, and date, then matched to the corresponding card transaction
- **Auto-populated accounting**: Once a receipt is matched, Light automatically fills in the ledger account, tax code, and custom properties on the transaction
- **Company-wide setup**: An admin connects and activates the integration once for the entire company — no action required from individual team members
- **Secure access**: Uses Google OAuth 2.0 and Google Workspace service account delegation with read-only Gmail access

This eliminates manual receipt chasing and data entry for corporate card spend.

## Setting up Gmail integration

A company admin sets up the Gmail integration on behalf of the entire organization. No action is required from individual team members.

To connect Gmail:

1. Navigate to **Settings (gear icon) > Integrations > Gmail**
2. Click **Connect**
3. You're redirected to Google to authorize access
4. Sign in with a Google Workspace admin account for your organization
5. Review the permissions Light is requesting
6. Click **Allow**
7. Light confirms the connection and redirects you back to the integrations page

The Gmail integration is now connected for your company.

## How receipt matching works

Once the integration is activated:

1. Light fetches emails from Gmail accounts across your company on a recurring basis
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

## Connection status

Admins can check the status of the Gmail integration at any time:

1. Navigate to **Settings (gear icon) > Integrations > Gmail**
2. View the connection status: **Connected** or **Not Connected**
3. View the email fetching status: **Enabled** or **Disabled**

## Security and privacy

Light takes email security seriously:

- **OAuth 2.0**: Industry-standard authorization — Light never sees or stores any Google passwords
- **Encrypted credentials**: All access tokens and refresh tokens are encrypted at rest
- **Automatic token refresh**: Credentials refresh automatically without manual re-authorization
- **Read-only access**: Email fetching uses the Gmail read-only scope — Light cannot send, delete, or modify emails
- **Service account delegation**: Access is granted at the domain level by your Google Workspace admin, with no credentials stored per individual user
- **Company isolation**: Email data and credentials are strictly isolated between companies

Your Google Workspace admin can revoke Light's access at any time from the Google Admin Console or from within Light's integration settings.

## Troubleshooting Gmail integration

**Connection fails during authorization**: Verify you're signing in with the correct Google Workspace admin account, check that third-party app access is enabled in your Google Admin Console, and try clearing your browser cookies before retrying.

**Connectivity check fails when activating**: This means domain-wide delegation hasn't been configured correctly for Light's service account. Verify the service account email, client ID, and granted scopes with your Google Workspace admin.

**Receipts not being matched to transactions**: Confirm email fetching is enabled for the company and check that receipt emails exist in team members' inboxes. Matching depends on AI extraction — if the receipt format is unusual, the match may not be automatic.

**Connection shows "Not Connected" unexpectedly**: The OAuth credentials may have expired or been revoked. Navigate to **Settings > Integrations > Gmail** and click **Connect** to re-authorize.

**Access denied error during OAuth**: Your Google Workspace admin may have restricted which third-party apps can access your organization's data. Allowlist Light in the Google Admin Console under **Security > API Controls**.

## Disabling the integration

To disable Gmail integration:

1. Navigate to **Settings (gear icon) > Integrations > Gmail**
2. Toggle **Enable Email Fetching** to off to stop receipt fetching across the company

Previously matched receipts and auto-populated accounting data remain on transactions for historical reference.

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [Slack integration](11-4-slack.md)
- [API access and custom integrations](11-12-api-access.md)
