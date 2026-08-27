# Gmail Integration

> **What's this page about: **The Gmail integration connects your company's Gmail to the Light app so it can find receipt emails on its own, match them to corporate card transactions, and fill in the accounting details, the ledger account, tax code, and any custom properties, without anyone re-entering the data by hand.

**On this page**

- What the Gmail integration does
- Setting up the Gmail integration
- How receipt matching works
- Forwarding receipts manually
- Reviewing matched receipts
- Checking connection status
- Security and data access
- Troubleshooting
- Disabling the integration

## What the Gmail integration does

Gmail is Google's email platform. Light's Gmail integration scans your company's Gmail for receipt emails, matches each one to the right corporate card transaction using AI, and posts the accounting entries automatically.

[Open Gmail settings in Light →](https://app.light.inc/settings/integrations)

The integration handles:

- **Automatic receipt fetching.** Light scans connected Gmail accounts for receipt emails tied to card transactions, so nobody has to go looking for them.
- **Manual receipt forwarding.** Anyone on the team can forward a receipt email to your company's dedicated Light receipts address to get it matched, useful for receipts that land in a personal inbox or don't get picked up automatically. Find your company's exact address under **Settings > Integrations > Gmail** in the Light app.
- **AI-powered receipt matching.** Light reads each receipt (including PDF attachments) to pull out the merchant name, amount, currency, and date, then matches it to the corresponding card transaction.
- **Auto-populated accounting.** Once a receipt is matched, Light fills in the ledger account, tax code, and any custom properties on the transaction, the same fields your accounting team would otherwise enter by hand.
- **Company-wide setup.** One admin connects Gmail once for the whole company. Individual team members don't need to do anything.
- **Read-only, encrypted access.** Light connects using Google OAuth 2.0 with read-only Gmail access, and stores encrypted, auto-refreshing access tokens rather than any Google password.

This removes the manual chasing and re-keying that corporate card spend usually creates: no forwarding receipts around, no typing merchant names or amounts into the ledger by hand.

## Setting up the Gmail integration

One admin sets up the Gmail integration for the whole company. No one else needs to take any action.

To connect Gmail:

1. In the Light app, go to **Settings (gear icon) > Integrations > Gmail**.
2. Click **Connect**.
3. Light redirects you to Google to authorize access.
4. Sign in with the Google account that should connect to Gmail for your company. For company-wide receipt scanning, this is usually your Google Workspace admin, since domain-wide mailbox access is normally authorized at that level.
5. Review the permissions Light is requesting, then click **Allow**.
6. Light confirms the connection and redirects you back to the integrations page in the Light app.
7. Toggle **Enable Email Fetching** on. Light runs a connectivity check first and only activates fetching once that check passes.

Once this finishes, the Gmail integration is connected and active for your company.

## How receipt matching works

Once the integration is active, for every corporate card transaction:

1. Light searches the cardholder's Gmail inbox for a matching receipt email.
2. It identifies emails with receipt attachments, typically PDFs.
3. AI compares each candidate receipt against the transaction's merchant name, amount, currency, and date.
4. On a match, Light attaches the receipt to the transaction and auto-populates the accounting fields: ledger account, tax code, and any custom properties.
5. If no match turns up right away, Light keeps retrying automatically, since receipt emails often land a little after the transaction itself. Retries space out over time, starting around 2 minutes apart and stretching to as long as 15 minutes between attempts.

This runs in the background. Your team doesn't need to upload receipts or fill in transaction details by hand for anything Light matches.

## Forwarding receipts manually

Alongside automatic fetching, anyone on the team can forward a receipt directly to Light for matching:

1. Forward the receipt email to your company's dedicated Light receipts address. You'll find the exact address under **Settings > Integrations > Gmail** in the Light app.
2. Light receives the forwarded email and extracts the receipt data using AI.
3. Light matches the receipt to the corresponding card transaction by merchant, amount, and date.
4. Once matched, Light auto-populates the accounting fields on the transaction.

This is worth using when:

- A receipt email wasn't picked up automatically.
- The receipt landed in a personal email account instead of a company inbox.
- You want a specific receipt processed right away, without waiting on the automatic scan.

## Reviewing matched receipts

After Light matches a receipt to a card transaction:

1. Open the transaction in the Light app.
2. The matched receipt is attached to it.
3. Review the auto-populated accounting data: ledger account, tax code, and any custom properties.
4. Adjust any field if it needs a correction, or approve the transaction as-is.

If Light couldn't find a match, or the AI extraction needs correction, upload the receipt manually or edit the transaction details directly.

## Checking connection status

Admins can check the Gmail integration's status at any time:

1. In the Light app, go to **Settings (gear icon) > Integrations > Gmail**.
2. Check the connection status: **Connected** or **Not Connected**.
3. Check the email fetching status: **Enabled** or **Disabled**.

## Security and data access

- **OAuth 2.0.** Light never sees or stores your Google password.
- **Encrypted tokens.** Access and refresh tokens are encrypted at rest.
- **Automatic token refresh.** Credentials refresh on their own; no manual re-authorization.
- **Read-only access.** Email fetching uses Gmail's read-only scope. Light can't send, delete, or modify anything in your Gmail.
- **Per-user and domain-level access.** Light stores an encrypted access token for the connecting user, and, where your Workspace admin has configured domain-wide delegation, Light can access mailboxes across the domain under that same read-only scope.
- **Company isolation.** Email data and credentials are kept separate between companies. One company's connection can't see another's data.

Your Google Workspace admin can revoke Light's access at any time, either from the Google Admin Console or from the integration settings inside the Light app.

## Troubleshooting the Gmail integration

**Connection fails during authorization.** Confirm you're signing in with the Google account intended for this integration, check that third-party app access is enabled in your Google Admin Console, and clear your browser cookies before retrying.

**Connectivity check fails when activating.** This usually means domain-wide delegation hasn't been configured correctly for Light's service account. Verify the service account email, client ID, and granted scopes with your Google Workspace admin.

**Receipts aren't matching to transactions.** Confirm email fetching is enabled for the company, and check that the receipt emails actually exist in the relevant inbox. Matching depends on AI reading the receipt, so an unusual receipt format can occasionally miss an automatic match.

**Connection shows "Not Connected" unexpectedly.** The OAuth credentials have likely expired or been revoked. Go to **Settings > Integrations > Gmail** in the Light app and click **Connect** to re-authorize.

## Disabling the integration

To turn off the Gmail integration:

1. In the Light app, go to **Settings (gear icon) > Integrations > Gmail**.
2. Toggle **Enable Email Fetching** off. This stops receipt fetching across the company.

Receipts already matched, and the accounting data already posted from them, stay on their transactions. Nothing already matched gets undone.

## Related articles

- [Integrations overview](https://help.light.inc/integrations/integrations-overview)
- [Slack integration](https://help.light.inc/integrations/slack)
- [API access and custom integrations](https://help.light.inc/integrations/api-access)

---

*Also searched as: connect Gmail to Light, sync Gmail receipts, auto-fetch receipts from email, forward receipts to Light, Gmail OAuth setup, disconnect Gmail integration, Gmail integration troubleshooting.*
