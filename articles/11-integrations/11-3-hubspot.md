# HubSpot Integration

HubSpot is a comprehensive platform managing sales, marketing, and customer service. Light's HubSpot integration connects your sales pipeline directly to financial accounting, automatically converting closed deals into accounts receivable invoices.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

The HubSpot integration enables:

- **Deal sync**: Closed deals automatically create AR invoices in Light
- **Contact sync**: HubSpot contacts synchronize to Light customer master
- **Company sync**: HubSpot companies synchronize to Light customers
- **Deal value tracking**: Monitor deal progression and associated revenue
- **Custom property mapping**: Map HubSpot custom properties to Light fields

This creates a unified sales-to-accounting workflow.

## Setting up HubSpot integration

To connect HubSpot:

1. Navigate to **Settings (gear icon) > Integrations > HubSpot**
2. Click **Connect**
3. You're redirected to HubSpot to authorize
4. Enter your HubSpot login credentials
5. Review the permissions Light is requesting
6. Click **Authorize**
7. Light confirms the connection is active

Next, configure what data to sync.

## Configuring deal sync

Define how HubSpot deals become Light invoices:

1. Navigate to **Settings > Integrations > HubSpot > Deal Mapping**
2. Select **Sync Deals**: Toggle on
3. Configure deal stage filters:
   - Select which deal stages trigger invoice creation (typically "Closed Won")
   - Only deals in these stages will sync
4. Configure field mappings:
   - **HubSpot Deal Name** → **Light Invoice Description**
   - **HubSpot Deal Amount** → **Light Invoice Total**
   - **HubSpot Deal Close Date** → **Light Invoice Document Date**
   - **HubSpot Associated Company** → **Light Customer**
   - **HubSpot Deal Owner** → **Light Sales Rep** (for reporting)
5. Save mappings

Light validates mappings for consistency.

## Company and contact sync

Sync HubSpot companies and contacts to Light customer data:

1. Navigate to **Settings > Integrations > HubSpot > Company Mapping**
2. Select **Sync Companies**: Toggle on
3. Configure field mappings:
   - **HubSpot Company Name** → **Light Customer Name**
   - **HubSpot Company Domain** → **Light Website**
   - **HubSpot Company Industry** → **Light Industry**
   - **HubSpot Company Phone** → **Light Phone**
4. Save

For contacts:

1. Navigate to **Contact Mapping**
2. Select **Sync Contacts**: Toggle on
3. Configure mappings for contact information

## Deal pipeline and revenue stages

Configure which deal stages generate revenue recognition:

1. Navigate to **Deal Mapping > Stage Configuration**
2. Define stages and their revenue impact:
   - **Proposal**: No invoice yet (deal not won)
   - **Negotiation**: No invoice yet
   - **Closed Won**: Create invoice (recognized revenue)
   - **Closed Lost**: No invoice
3. Light syncs only deals in stages you've configured to generate revenue

This ensures you don't record revenue prematurely.

## Handling multiple deal lines

If a HubSpot deal includes multiple line items:

1. Create line items in HubSpot (via Products or custom configuration)
2. In Light mapping, configure line-item syncing:
   - **HubSpot Product Name** → **Light Product**
   - **HubSpot Quantity** → **Light Quantity**
   - **HubSpot Unit Price** → **Light Unit Price**
3. Light creates Light invoices with matching line structure

This preserves product detail from HubSpot.

## Sync frequency

Configure how often Light checks HubSpot for new deals:

1. Navigate to **Settings > Integrations > HubSpot > Sync Settings**
2. Select frequency:
   - **Real-time**: Check continuously (as deals move to closed won)
   - **Hourly**: Check hourly
   - **Daily**: Check daily at specified time
   - **Manual**: Only sync when you click "Sync Now"
3. Save

Real-time is ideal for tracking closed deals immediately. Daily is sufficient for most organizations.

## Monitoring sync activity

Track HubSpot sync history:

1. Navigate to **Settings > Integrations > HubSpot > Sync History**
2. View all past syncs:
   - Date/time
   - Number of deals processed
   - Number created, updated, skipped
   - Errors (if any)
3. Click any sync to see detail:
   - Which specific deals were processed
   - Which successfully synced
   - Which failed and why

This helps identify issues and track data flow.

## Manual sync trigger

Trigger a sync immediately (don't wait for scheduled sync):

1. Navigate to **Settings (gear icon) > Integrations > HubSpot**
2. Click **Sync Now**
3. Light immediately checks HubSpot and syncs new deals
4. You see summary of results

Useful when you close a large deal and need the invoice immediately.

## Handling sync errors

If deals fail to sync:

1. Check the error message in sync history
2. Common errors:
   - **Missing required field**: Deal missing a mapped field
   - **Invalid amount**: Deal amount not a valid number
   - **Company not found**: HubSpot company doesn't match a Light customer
   - **Duplicate deal**: Deal already synced (filtered out to prevent duplicates)
3. Fix the issue in HubSpot
4. Manually retry the sync

> Tip: Create HubSpot validation rules to require fields before closing a deal. This prevents sync failures.

## Custom property mapping

Map HubSpot custom properties to Light:

1. Create custom properties in HubSpot (e.g., "Project Code", "Customer Segment")
2. In Light mapping, add custom property mappings:
   - **HubSpot Project Code** → **Light Cost Center**
   - **HubSpot Customer Segment** → **Light Customer Segment Custom Property**
3. Light syncs these properties for reporting and cost allocation

## Deal renewal and re-sync

If you renew a HubSpot deal (e.g., annual contract renewed):

1. HubSpot creates a new deal record for the renewal
2. Light syncs the new deal as a new invoice
3. Or, if you modify the existing deal amount, Light updates the Light invoice

Configure whether Light should create new or update existing invoices on deal changes.

## Forecasting and revenue tracking

Use synced deals for revenue forecasting:

1. HubSpot deals represent future revenue (pipeline)
2. Light invoices represent recognized revenue (booked)
3. Compare HubSpot pipeline (forecast) to Light AR (actual bookings)
4. Track deal progression: Pipeline → Closed → Invoiced → Paid

This provides full visibility from opportunity to cash.

## Reporting on synced data

Create reports analyzing synced deals:

1. Navigate to **Planning & Reports → Reports**
2. View revenue by:
   - Customer (HubSpot company)
   - Sales rep (HubSpot deal owner)
   - Deal stage progression
   - Close date trends
3. Compare HubSpot forecast to Light recognized revenue

Light's custom reporting integrates HubSpot data for full analysis.

## Troubleshooting sync issues

**Deals not syncing**: Check that deals are in the correct stage, verify required fields are populated, check filter criteria.

**Wrong customer assigned**: Verify company mapping, check for duplicate customer names in Light.

**Incorrect amounts**: Check field mapping, ensure HubSpot deal amount is being read correctly.

**Duplicate invoices**: Check sync history to see if deal was already synced, adjust sync filters if needed.

**Connection failed**: Re-authorize HubSpot integration, verify your HubSpot account has API access.

## Exporting synced deals

Export synced deals and associated invoices:

1. Navigate to **Planning & Reports → Reports**
2. Filter by date range, customer, or rep
3. Export to Excel or PDF
4. Analyze deal activity and revenue impact

## Deal attribution and reporting

Track which deals drive revenue:

1. Light invoices created from HubSpot deals include the source deal ID
2. Use custom reporting to analyze:
   - Revenue by deal size
   - Revenue by deal source/channel
   - Revenue by sales rep
3. Understand which types of deals drive profitability

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [Salesforce integration](11-2-salesforce.md)
- [API access and custom integrations](11-12-api-access.md)
- [Custom reports and filters](../10-reporting/10-9-custom-reports.md)
