# Salesforce Integration

Salesforce is the leading CRM platform managing customer relationships and sales pipelines. Light's Salesforce integration creates a seamless connection from sales opportunity closure to financial accounting, automatically converting closed deals into accounts receivable invoices.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration overview

The Salesforce integration enables:

- **Opportunity sync**: When you close an opportunity in Salesforce, Light automatically creates a corresponding AR invoice
- **Account sync**: Salesforce accounts synchronize to Light customer master data
- **Contact sync**: Contacts synchronize to contact information
- **Field mapping**: Configure which Salesforce fields map to Light invoice fields
- **Filtering**: Choose which opportunities to sync (by stage, amount, date)

This eliminates manual invoice creation and ensures invoices match CRM data.

## Setting up the Salesforce integration

To connect Salesforce:

1. Navigate to **Settings (gear icon) > Integrations > Salesforce**
2. Click **Connect**
3. You're redirected to Salesforce to authorize
4. Enter your Salesforce username and password
5. Review the permissions Light is requesting
6. Click **Authorize**
7. Light confirms the connection is active

Next, configure what data to sync.

## Configuring opportunity sync

Define how opportunities become invoices:

1. Navigate to **Settings > Integrations > Salesforce > Opportunity Mapping**
2. Select **Sync Opportunities**: Toggle on
3. Configure filters:
   - Opportunity Stage: Only "Closed Won" or other completed stages
   - Minimum Amount: Only sync opportunities above a threshold (avoid small deals)
   - Date Range: Sync only recent opportunities (avoid re-syncing old data)
4. Configure field mappings:
   - **Salesforce Account** → **Light Customer Entity**
   - **Salesforce Opportunity Amount** → **Light Invoice Total**
   - **Salesforce Opportunity Name** → **Light Invoice Description**
   - **Salesforce Close Date** → **Light Invoice Document Date**
5. Save mappings

Light validates the mappings to ensure data consistency.

## Opportunity to invoice transformation

When a Salesforce opportunity matches your sync criteria:

1. Light reads the opportunity data
2. Light creates a new AR (accounts receivable) invoice
3. Invoice is populated with:
   - Customer (from Salesforce account)
   - Invoice amount (from opportunity amount)
   - Invoice description (from opportunity name)
   - Invoice date (from opportunity close date)
4. Invoice is created in draft status (not yet posted to GL)
5. You review the invoice and click Post to finalize

This gives you a chance to review before committing to GL.

> Tip: Have finance review the first several synced invoices to ensure mapping is correct. After that, you can configure auto-posting if comfortable.

## Account and contact sync

Beyond opportunities, sync Salesforce accounts and contacts:

1. Navigate to **Settings > Integrations > Salesforce > Account Mapping**
2. Select **Sync Accounts**: Toggle on
3. Configure mappings:
   - **Salesforce Account Name** → **Light Customer Name**
   - **Salesforce Account Industry** → **Light Customer Industry**
   - **Salesforce Billing Address** → **Light Billing Address**
   - **Salesforce Phone** → **Light Phone**
4. Save mappings

Similarly for contacts:

1. Navigate to **Account Mapping**
2. Select **Sync Contacts**: Toggle on
3. Configure mappings for contact information

## Duplicate handling

What if the same customer exists in both Salesforce and Light?

Configure duplicate handling:

1. Navigate to **Settings > Integrations > Salesforce > Duplicate Settings**
2. Select approach:
   - **Match by name**: If customer name matches, update existing Light customer
   - **Match by external ID**: If you have a customer ID in both systems, use it to match
   - **Create new**: Always create new Light customer (may create duplicates)
3. Save

Typically, match by name or external ID to avoid duplicate customer records.

## Sync frequency

Configure how often to check Salesforce for new opportunities:

1. Navigate to **Settings > Integrations > Salesforce > Sync Settings**
2. Select frequency:
   - **Real-time**: Check continuously (as opportunities close)
   - **Hourly**: Check hourly
   - **Daily**: Check daily (at specific time)
   - **Manual**: Only sync when you click "Sync Now"
3. Select time zone for scheduled syncs
4. Save

Real-time is ideal for fast-moving sales. Daily is sufficient for most organizations.

## Monitoring Salesforce sync

Track integration activity:

1. Navigate to **Settings > Integrations > Salesforce > Sync History**
2. View all past syncs:
   - Date/time of sync
   - Number of opportunities synced
   - Number created, updated, skipped
   - Errors (if any)
3. Click any sync to see detail:
   - Which specific opportunities were processed
   - Which were successfully synced
   - Which failed and why

This helps identify issues quickly.

## Manual sync trigger

Manually trigger a sync if you don't want to wait for scheduled sync:

1. Navigate to **Settings (gear icon) > Integrations > Salesforce**
2. Click **Sync Now**
3. Light immediately checks Salesforce and syncs new opportunities
4. You see a summary of what was synced

Useful when you close a large deal and need the invoice immediately.

## Handling sync failures

If opportunities fail to sync:

1. Check the error message (displayed in sync history)
2. Common errors:
   - **Missing required field**: Salesforce opportunity is missing a mapped field
   - **Invalid amount**: Opportunity amount is not a valid number
   - **Customer not found**: Salesforce account doesn't match a Light customer
3. Fix the issue in Salesforce
4. Manually retry the sync

Light logs all errors for troubleshooting.

> Tip: Create a Salesforce validation rule to prevent opportunities closing without required fields. This prevents sync failures.

## Advanced field mappings

Beyond basic fields, map custom fields:

1. Create custom fields in Salesforce (e.g., "Project Code", "Cost Center")
2. In Light mapping, add custom field mappings:
   - **Salesforce Project Code** → **Light Project Cost Center**
   - **Salesforce Product Category** → **Light Invoice Line Item Product**
3. Light syncs these custom fields to Light custom properties
4. Use these properties for reporting and cost allocation

## Multi-line items

If an opportunity includes multiple products (line items in Salesforce), how are they synced?

Configure line-item sync:

1. Create invoice line items in Salesforce (typically via a related object or custom setup)
2. In Light mapping, configure line-item mappings:
   - **Salesforce Product** → **Light Product**
   - **Salesforce Quantity** → **Light Quantity**
   - **Salesforce Unit Price** → **Light Unit Price**
3. Light creates Light invoice with multiple lines matching Salesforce structure

## Forecasting and reporting

Use synced data for reporting:

1. Sync Salesforce opportunities to Light to create invoices
2. Use Light's custom reporting to analyze revenue:
   - Revenue by customer
   - Revenue by product
   - Revenue by sales rep (synced from Salesforce owner field)
3. Compare Salesforce pipeline to Light recognized revenue

This provides full visibility from pipeline to cash collection.

## Troubleshooting common issues

**Opportunities not syncing**: Check filter criteria, verify opportunities are in correct stage, ensure amounts are populated.

**Wrong customer assigned**: Verify account mapping, check for duplicate customer names in Light.

**Incorrect amounts**: Check field mapping, verify Salesforce amount field is being synced.

**Duplicate invoices**: Verify sync filters prevent re-syncing old opportunities.

**Connection failed**: Re-authorize Salesforce integration, verify your Salesforce account has API access enabled.

## Unsyncing data

If you accidentally synced incorrect data:

1. Navigate to the Light invoice created from Salesforce
2. Click **Delete** (if in draft status) or **Create Reversal** (if posted)
3. Light removes or reverses the invoice
4. Data sync can be re-attempted after correcting in Salesforce

Light provides audit trail of deleted/reversed items.

## Exporting synced data

Export synced invoices for analysis:

1. Navigate to **Planning & Reports → Reports**
2. Filter by date, customer, amount
3. Export to Excel or PDF
4. Analyze revenue by customer, product, region

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [HubSpot integration](11-3-hubspot.md)
- [API access and custom integrations](11-12-api-access.md)
- [Profit and loss](../10-reporting/10-3-profit-loss.md)
