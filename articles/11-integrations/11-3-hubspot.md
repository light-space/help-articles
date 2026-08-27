# HubSpot Integration

HubSpot is a comprehensive platform managing sales, marketing, and customer service. Light's HubSpot integration connects your sales pipeline directly to financial accounting, automatically converting closed deals into contracts and accounts receivable invoices.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

The HubSpot integration enables:

- **Deal sync**: Closed-won deals automatically create contracts (or AR invoices, depending on your workflow configuration) in Light
- **Contact sync**: HubSpot contacts synchronize to Light customer master
- **Company sync**: HubSpot companies synchronize to Light customers
- **Product sync**: Active HubSpot products synchronize to Light products, including multi-currency pricing
- **Deal value tracking**: Monitor deal progression and associated revenue
- **Custom property mapping**: Map HubSpot custom properties to Light fields
- **Invoice sync to HubSpot**: Light sales invoices can sync back to HubSpot as HubSpot invoices

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

Next, configure what data to sync in the **HubSpot to Light** workflow.

## Configuring deal sync

Define how HubSpot deals become Light contracts or invoices:

1. Navigate to **Settings (gear icon) → Workflows** and open the **HubSpot to Light** workflow
2. Configure the deal filter node. By default only deals that are closed and won sync (`hs_is_closed_won = true`). You can extend the filter with additional conditions, for example by pipeline, amount, or close date
3. Configure field mappings in the mapping nodes. By default, deals map to Light contracts:
   - **HubSpot Associated Company** → **Light Customer**
   - **HubSpot Deal Amount** → **Light Contract Estimated Amount**
   - **HubSpot Deal Close Date** → **Light Contract Start Date**
   - **HubSpot Deal Currency** → **Light Contract Currency**
   - **HubSpot Deal Description** → **Light Contract Description**
   - **HubSpot Deal Line Items** → **Light Contract Lines** (product, quantity, discount, billing period)
4. Publish the workflow to activate the sync

If the related customer doesn't exist in Light yet, it is created automatically from the HubSpot company associated with the deal. If the deal has file attachments in HubSpot, Light can also attach the deal's document (preferring PDF attachments) to the created contract.

The workflow can instead (or additionally) be configured to create or update AR invoices from deals.

> **Good to know**: When configuring advanced mappings, you can access deal owner properties as nested fields. For example, if you need the deal owner's email on an invoice field, use `owner.email` in your mapping expression. Other owner properties like `owner.firstName` and `owner.lastName` are also available.

## Company and contact sync

HubSpot companies and contacts associated with synced deals are read as part of deal processing, and companies sync to Light customer data. Default company field mappings in the **HubSpot to Light** workflow:

- **HubSpot Company Name** → **Light Customer Name**
- **HubSpot Company Domain** → **Light Customer Domain**
- **HubSpot Company Description** → **Light Customer Description**
- **HubSpot Company Address** (street, city, state, zip, country) → **Light Customer Address**

Customers created from HubSpot are marked with HubSpot as their external source and keep the HubSpot record ID as their external ID.

## Deal filtering and revenue stages

Light syncs only deals matching the filter configured in the **HubSpot to Light** workflow. By default this is deals that are closed and won, so deals still in proposal or negotiation stages don't create records in Light, and lost deals are excluded.

This ensures you don't record revenue prematurely.

## Handling multiple deal lines

If a HubSpot deal includes multiple line items:

1. Create line items in HubSpot (via Products or custom configuration)
2. The workflow's line-item mappings apply to each line:
   - **HubSpot Product** → **Light Product**
   - **HubSpot Quantity** → **Light Quantity**
   - **HubSpot Discount** (amount or percentage) → **Light Discount**
   - **HubSpot Recurring Billing Start/End Dates** → **Light Billing Period**
3. Light creates the contract or invoice with matching line structure

This preserves product detail from HubSpot. Similarly, active HubSpot products sync to Light products by default, including prices in each currency configured on the HubSpot product.

## Syncing Light invoices to HubSpot

The integration also works in the reverse direction. When the **Light to HubSpot** workflow is published, Light sales invoices sync to HubSpot as HubSpot invoices:

- If a matching HubSpot invoice already exists (matched by external ID), it is updated
- Otherwise, a new HubSpot invoice is created with the invoice's line items

This sync runs on the same automatic schedule as the import sync.

## Sync frequency

Once the **HubSpot to Light** workflow is published, Light automatically polls HubSpot for new and changed records on a recurring schedule (roughly hourly). The sync frequency is managed by Light and does not require configuration.

If you need specific records imported immediately, contact Light support, who can trigger a sync on demand.

## Monitoring sync activity

Track HubSpot sync history:

1. Navigate to **Settings (gear icon) → Workflows** and open the **HubSpot to Light** workflow
2. Each synced record is processed as a workflow run, where you can see:
   - Which specific records were processed
   - Which successfully synced
   - Which failed and why

This helps identify issues and track data flow.

## Handling sync errors

If deals fail to sync:

1. Check the error message in the workflow run
2. Common errors:
   - **Missing required field**: Deal missing a mapped field
   - **Invalid amount**: Deal amount not a valid number
   - **Duplicate deal**: Deal already synced (matched by its HubSpot ID and updated instead of duplicated)
3. Fix the issue in HubSpot
4. The record is picked up again on the next sync

> Tip: Create HubSpot validation rules to require fields before closing a deal. This prevents sync failures.

## Custom property mapping

Map HubSpot custom properties to Light:

1. Create custom properties in HubSpot (e.g., "Project Code", "Customer Segment")
2. In the workflow's mapping nodes, add custom property mappings:
   - **HubSpot Project Code** → **Light Cost Center**
   - **HubSpot Customer Segment** → **Light Customer Segment Custom Property**
3. Light syncs these properties for reporting and cost allocation

## Deal renewal and re-sync

If you renew a HubSpot deal (e.g., annual contract renewed):

1. HubSpot creates a new deal record for the renewal
2. Light syncs the new deal as a new contract
3. Or, if you modify the existing deal, Light updates the existing Light contract (matched automatically by the HubSpot deal ID stored as its external ID)

Matching by external ID happens automatically and prevents duplicate records.

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

**Duplicate invoices**: Check workflow runs to see if the deal was already synced, adjust sync filters if needed.

**Connection failed**: Re-authorize HubSpot integration, verify your HubSpot account has API access.

## Exporting synced deals

Export synced deals and associated invoices:

1. Navigate to **Planning & Reports → Reports**
2. Filter by date range, customer, or rep
3. Export to Excel or PDF
4. Analyze deal activity and revenue impact

## Deal attribution and reporting

Track which deals drive revenue:

1. Light contracts and invoices created from HubSpot deals store the source deal ID as their external ID
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
