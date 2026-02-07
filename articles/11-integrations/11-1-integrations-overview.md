# Integrations Overview

Light's strength lies in its ability to connect seamlessly with other business systems. Integrations eliminate manual data entry, reduce errors, and keep your financial data synchronized across your technology stack. Light provides native integrations with CRM, HRM, payments, tax, banking, and messaging platforms.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration types

Light supports three types of integrations:

**Data sync integrations**: Automatically synchronize data between Light and other systems.
- Examples: Salesforce → Light (opportunities to AR invoices), Stripe → Light (payments to ledger)
- Real-time or scheduled (typically hourly or daily)

**API integrations**: Custom integrations via REST API.
- Examples: Custom workflow tools, proprietary systems, specialized applications
- Requires technical setup but maximum flexibility

**Workflow integrations**: Trigger actions in other systems based on Light events.
- Examples: Send Slack notification when invoice is overdue, create Jira ticket for dispute
- Connects Light to communication and project management tools

## Pre-built integrations

Light provides native integrations with popular platforms:

**CRM & Sales**:
- Salesforce: Sync opportunities, accounts, contacts
- HubSpot: Sync deals, contacts, companies

**HRM & Payroll**:
- Finch: Sync headcount, payroll data, company structure

**Payments**:
- Stripe: Sync transactions, payouts, refunds

**Tax & Compliance**:
- AvaTax (US): Automated sales tax calculation and reporting
- Avalara E-Invoicing: Peppol compliance and transmission
- HMRC (UK): VAT returns and filings

**Messaging**:
- Slack: Notifications and alerts
- Microsoft Teams: Notifications and alerts

**Banking**:
- Bank APIs: Direct account feeds, balance updates

## Setting up integrations

For most integrations, the process is:

1. Navigate to **Settings (gear icon) > Integrations**
2. Find the integration you want (Salesforce, Stripe, Slack, etc.)
3. Click **Connect**
4. You're redirected to the third-party system to authorize
5. You grant Light permission to access your data
6. Light confirms the connection is active
7. Configure sync settings (frequency, data to sync, mappings)

Once configured, the integration runs automatically.

> Good to know: Light stores integration credentials securely and never displays them. You can disconnect any time.

## OAuth and secure authentication

Light uses industry-standard OAuth for secure authentication. When you connect an integration:

1. Light redirects you to the third-party system
2. You log in (Light never sees your password)
3. You review what Light is requesting permission to do
4. You authorize the connection
5. Third-party system provides Light a secure token
6. Light uses the token to access data on your behalf

This is the same authentication method major tech companies use. Your credentials are never shared with Light.

## Data mapping and synchronization

For each integration, configure what data to sync:

**Salesforce integration**:
- Sync opportunities to AR invoices
- Map Salesforce opportunity fields to Light invoice fields
- Configure: Account → Company Entity, Amount → Invoice Total, etc.
- Sync frequency: Real-time (as opportunity closes) or nightly

**Stripe integration**:
- Sync successful payments to cash receipts
- Sync refunds to credit notes
- Map Stripe data to Light: Customer ID, Amount, Currency
- Sync frequency: Daily

**HubSpot integration**:
- Sync deals to AR invoices
- Sync contact creation to customer master data
- Map fields appropriately

## Testing integrations

Before relying on an integration, test it:

1. Set up the integration in test mode
2. Create test data in the source system
3. Sync and verify data appears correctly in Light
4. Check field mappings and calculations
5. Once confident, enable for production use

Light provides test mode for most integrations.

## Monitoring integration health

Light tracks integration status:

1. Navigate to **Settings (gear icon) > Integrations** to check status
2. View each integration's status:
   - Connected: Active and working
   - Paused: Disabled but can be re-enabled
   - Error: Connection failed, needs attention
3. Click any integration to see:
   - Last successful sync
   - Last error (if failed)
   - Number of records synced
4. Manually trigger a sync if needed

If an integration shows error, investigate and reconnect.

## Syncing historical data

When first connecting an integration, decide whether to sync historical data:

- **Start fresh**: Only sync new data from today forward (faster setup)
- **Import history**: Sync all historical data (may take longer, but complete data set)

For most integrations, starting fresh is recommended. You can manually import old data if needed.

## Conflict resolution

If the same data exists in both systems, decide which takes priority:

- **Source-preferred**: Updates in source system overwrite Light
- **Light-preferred**: Updates in Light overwrite source system
- **Manual review**: Conflicts flagged for human review before sync

Configure conflict resolution per integration. Most commonly, source system is preferred (Light acts as ledger receiving data).

## Rate limiting and performance

Integrations respect platform rate limits:

- Don't sync too frequently (every 5 minutes is reasonable; every 30 seconds is excessive)
- Batch operations to reduce API calls
- Light automatically handles retries if rate limits are hit

Configure sync frequency to balance currency with system performance.

## Audit trail on integrations

Light logs all integration activity:

- Sync timestamp and duration
- Number of records synced
- Errors or warnings
- User who triggered the sync (if manual)

Navigate to **Settings (gear icon) > Integrations** to review activity logs.

## Common integration workflows

**Lead-to-cash**:
Salesforce → Light → Bank
1. Close an opportunity in Salesforce
2. Integration automatically creates AR invoice in Light
3. Customer pays
4. Payment appears in bank feed
5. Bank integration matches payment to invoice
6. Cash posting completes the lead-to-cash cycle

**Payroll integration**:
HRM (Finch) → Light
1. Employees paid by payroll processor
2. Finch integration syncs payroll data to Light
3. Light automatically creates JE to record payroll expense
4. GL reflects latest headcount and expense

**Tax compliance**:
Light → AvaTax → Tax Authority
1. Create AR invoice in Light with tax codes
2. AvaTax integration calculates applicable tax
3. Light posts tax to GL
4. AvaTax integration prepares tax return
5. Light submits to tax authority

## Common integration issues and troubleshooting

**Connection failures**: Verify credentials, check if third-party system is online, re-authorize.

**Sync errors**: Check data mapping, verify required fields are populated, review error log.

**Missing data**: Verify sync scope (is this data type configured to sync?), check date filters.

**Duplicate data**: Verify conflict resolution settings, check if manual sync created duplicates.

**Field mapping issues**: Verify field names match, check data types (text vs. number vs. date), test with sample data.

Light provides detailed error messages to help diagnose issues.

## API rate limits

When syncing large data sets, respect API rate limits:

- Most vendors allow 1,000-10,000 API calls per hour
- Light batches operations to minimize calls
- If rate limited, Light queues requests and retries

Configure sync frequency appropriately for your data volume.

## Webhook integrations

For real-time data flow, use webhooks:

Webhooks allow third-party systems to push data to Light immediately, rather than Light polling (asking) for data.

Example: When a customer pays in Stripe, Stripe webhook immediately notifies Light, which records the payment.

Light supports webhooks for:
- Stripe (payment notifications)
- Salesforce (opportunity updates)
- HubSpot (deal updates)
- Bank feeds (transaction notifications)

## Related articles

- [Salesforce integration](11-2-salesforce.md)
- [HubSpot integration](11-3-hubspot.md)
- [Slack integration](11-4-slack.md)
- [Microsoft Teams integration](11-5-microsoft-teams.md)
- [Stripe integration](11-6-stripe.md)
- [HRM integration (Finch)](11-8-hrm-finch.md)
- [API access and custom integrations](11-12-api-access.md)
