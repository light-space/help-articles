# Integrations Overview

Light's strength lies in its ability to connect seamlessly with other business systems. Integrations eliminate manual data entry, reduce errors, and keep your financial data synchronized across your technology stack. Light provides native integrations with CRM, HRM, payments, tax, banking, and messaging platforms.

[Open in Light →](https://app.light.inc/settings/integrations)

**On this page**

- Integration types
- Pre-built integrations
- Non-prebuilt integrations
- Setting up integrations
- OAuth and secure authentication
- Data mapping and synchronization
- Testing integrations
- Monitoring integration health
- Syncing historical data
- Conflict resolution
- Rate limiting and performance
- Audit trail on integrations
- Common integration workflows
- Common integration issues and troubleshooting
- API rate limits
- Webhook integrations
- Related articles

## Integration types

Light supports three types of integrations:

**Data sync integrations**: Automatically synchronize data between Light and other systems.
- Examples: Salesforce → Light (opportunities to AR invoices), Stripe → Light (payments to ledger)
- Real-time or scheduled (typically hourly or daily)

**API integrations**: Custom integrations via REST API.
- Examples: Custom workflow tools, proprietary systems, specialized applications
- Requires technical setup but maximum flexibility

**Workflow integrations**: Trigger actions in other systems based on Light events.
- Example: Send a Slack notification when an invoice is overdue
- Connects Light to communication tools

## Pre-built integrations

Light provides native integrations with popular platforms:

**CRM & Sales**:
- Salesforce: Sync opportunities, accounts, contacts
- HubSpot: Sync deals, contacts, companies

**FP&A**:
- Abacum: Sync balance sheet, trial balance and ledger trx .csv files into the FP&A tool via S3 bucket for financial planning and analysis. Client can define backfilling dates.

**HRM & Payroll**:
- Finch: Syncs users, manager relationship, and entities into Light keeping your Users list current. See HRM Integration (Finch) for exactly what syncs

**Payments**:
- Stripe: Sync transactions, payouts, refunds for the AR side
- Airwallex: Outgoing payments from your Airwallex virtual bank accounts

**Tax & Compliance**:
- AvaTax (US): Automated sales tax calculation and reporting
- Sphere (US): Automated sales tax calculation and reporting
- E-Invoicing via Invopop: E-invoicing compliance and transmission across Europe and more regions. Contact Light for full scope.
- HMRC (UK): VAT returns and filings
- Skattestyrelsen (DK): VAT returns and filings

**Messaging**:
- Slack: Notifications and alerts
- Microsoft Teams: Notifications and alerts

**Email**:
- Gmail: Automatic receipt fetching and matching for card transactions

**Banking**:
- Bank feed: Direct account feeds, balance updates via GoCardless, Plaid, and Stripe's APIs. Payments are not prebuilt so it requires project and configuration (talk with your Light sales on this topic).

## Non-prebuilt integrations

**Payments via your banks**
- AP and Reimbursement Payments: connects to AMC Banking, which handles the connection to your bank (SEB, J.P. Morgan HSBC, and others) on Light's behalf.

## Setting up integrations

For most integrations, the process is:

1. Navigate to **Settings (gear icon) > Integrations**
2. Click **Add integration** and find the one you want (Salesforce, Stripe, Slack, etc.)
3. You're redirected to the third-party system to authorize (for OAuth-based integrations), or asked to enter credentials directly (for API-key based ones)
4. You grant Light permission to access your data
5. Light confirms the connection is active
6. For integrations that support it, configure sync settings (frequency, data to sync, mappings), simpler integrations like Slack, Teams, and Gmail just need to be connected or enabled, with no further configuration

Once set up, the integration runs automatically.

> Good to know: Light stores integration credentials securely and never displays them. You can disconnect any time.

## OAuth and secure authentication

Most integrations use industry-standard OAuth for secure authentication. When you connect one of these integrations:

1. Light redirects you to the third-party system
2. You log in (Light never sees your password)
3. You review what Light is requesting permission to do
4. You authorize the connection
5. Third-party system provides Light a secure token
6. Light uses the token to access data on your behalf

This is the same authentication method major tech companies use. Your credentials are never shared with Light.

A few integrations authenticate differently: AvaTax connects using an app-managed OAuth client (no browser sign-in step involved), and Sphere connects using an API key. Your Light representative sets these up as part of onboarding that integration.

## Data mapping and synchronization

For each integration, configure with your Light representative what data to sync:

**Salesforce integration**:
- Sync opportunities to AR invoices
- Map Salesforce opportunity fields to Light invoice fields
- Configure: Account → Customer, Amount → Invoice Total, etc.
- Sync frequency: Real-time (as opportunity closes) or nightly

**Stripe integration**:
- Sync successful payments to cash receipts
- Sync refunds to credit notes
- Map Stripe data to Light: Customer ID, Amount, Currency
- Sync frequency: Real-time (via webhook) or daily

**HubSpot integration**:
- Sync deals to AR invoices
- Sync contact creation to customer master data
- Map fields appropriately

**HRM integration**:
- Default Base Role = *e.g. Reimbursement Only*
- HRM field Entity = Entity in Light
- HRM field Sub-department = e.g. User Group in Light

## Testing integrations

Before relying on an integration for critical data, it's worth confirming it's working as expected:

1. Connect the integration
2. Sync a small amount of data first
3. Check field mappings and calculations against the source system
4. Once confident, rely on it for ongoing syncs

Testing support varies by integration. A few providers, like Avalara and Airwallex, offer their own sandbox environments, check the specific integration if this matters to you.

## Monitoring integration health

Light tracks integration status:

1. Navigate to **Settings (gear icon) > Integrations** to check status
2. View each integration's status. Status values vary by integration, for example Stripe shows Active/Inactive, Slack/Teams/Gmail show Connected/Not connected, and sync-based integrations like Finch show states such as Syncing, Paused, or Initial sync running
3. Click any integration to see:
   - Last successful sync
   - Last error (if failed)
   - Number of records synced
4. Manually trigger a sync if needed

If an integration shows error, investigate and reconnect.

## Syncing historical data

Historical data handling varies by integration. Most integrations (like Salesforce) start syncing from the moment you connect them, without a historical import. Some, like Finch, let you set a start date for how far back to sync. Check the specific integration's setup for what's available.

## Conflict resolution

Most sync workflows run in a single direction (for example, Salesforce → Light or Stripe → Light), with Light acting as the ledger receiving data. HubSpot is an exception, it syncs in both directions (Light ↔ HubSpot). Check the specific integration's documentation for its sync direction before relying on it for two-way data consistency.

## Rate limiting and performance

Each integration syncs on a fixed schedule set by Light (for example, Salesforce roughly every 20 minutes, HubSpot hourly), tuned to respect that platform's API rate limits. If a rate limit is hit, Light automatically retries.

## Audit trail on integrations

Light tracks the timestamp of each integration's last successful sync. Syncs run on a schedule (cron-driven) rather than being manually triggered by a user in most cases.

Navigate to **Settings (gear icon) → Integrations** to see each integration's last sync time.

## Common integration workflows

**Lead-to-cash**:
Salesforce → Light → Bank
1. Close an opportunity in Salesforce
2. Integration automatically creates AR invoice in Light
3. Customer pays
4. Payment appears in bank feed
5. Bank integration matches payment to invoice
6. Cash posting completes the lead-to-cash cycle

**HRM and Payroll integration**:
Finch syncs employee and organizational data (not payroll) into Light, keeping your Users list current as employees join, change roles, or leave.

For the payroll expense itself:
1. Employees paid by payroll processor
2. Most companies record payroll expense with a simple monthly journal entry upload
3. GL reflects the latest payroll expense

See HRM integration (Finch) for exactly what data does sync.

**Tax compliance**:
Light → AvaTax or Sphere → GL
1. Create AR invoice in Light with tax codes
2. AvaTax or Sphere calculates the applicable tax
3. Light posts the tax to your GL

AvaTax and Sphere calculate and record tax, they don't file returns with a tax authority. For UK VAT, Light's HMRC integration is the one that actually files returns directly with HMRC, see HMRC connection (UK).

## Common integration issues and troubleshooting

**Connection failures**: Verify credentials, check if third-party system is online, re-authorize.

**Sync errors**: Check data mapping, verify required fields are populated, review error log.

**Missing data**: Verify sync scope (is this data type configured to sync?), check date filters.

**Duplicate data**: Verify conflict resolution settings, check if manual sync created duplicates.

**Field mapping issues**: Verify field names match, check data types (text vs. number vs. date), test with sample data.

Light provides detailed error messages to help diagnose issues.

## API rate limits

Light's API enforces rate limits of 300 requests per minute per user and 100,000 requests per day per company (both configurable per company on request). Light batches operations to minimize calls, and automatically queues and retries requests that hit a limit.

## Webhook integrations

For real-time data flow, use webhooks:

Webhooks allow third-party systems to push data to Light immediately, rather than Light polling (asking) for data.

Example: When a customer pays in Stripe, Stripe webhook immediately notifies Light, which records the payment.

Light supports webhooks for:
- Stripe (payment notifications)
- Bank feeds (transaction notifications)

Salesforce and HubSpot data syncs run on a schedule rather than via webhooks.

## Related articles

- [Salesforce integration](https://light.inc/help/integrations/salesforce)
- [HubSpot integration](https://light.inc/help/integrations/hubspot)
- [Slack integration](https://light.inc/help/integrations/slack)
- [Microsoft Teams integration](https://light.inc/help/integrations/microsoft-teams)
- [Stripe integration](https://light.inc/help/integrations/stripe)
- [Airwallex integration](https://light.inc/help/integrations/airwallex)
- [HRM integration (Finch)](https://light.inc/help/integrations/hrm-finch)
- [HMRC connection (UK)](https://light.inc/help/integrations/hmrc-uk)
- [AvaTax integration (US)](https://light.inc/help/integrations/integrations-avatax-us)
- [Bank integrations overview](https://light.inc/help/integrations/bank-integrations)
- [Gmail integration](https://light.inc/help/integrations/gmail)
- [Abacum integration](https://light.inc/help/integrations/abacum)
- [API access and custom integrations](https://light.inc/help/integrations/api-access)
