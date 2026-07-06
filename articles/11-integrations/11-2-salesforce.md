# Salesforce Integration

Salesforce is the leading CRM platform managing customer relationships and sales pipelines. Light's Salesforce integration creates a seamless connection from sales opportunity closure to financial accounting, automatically converting closed deals into contracts and accounts receivable invoices.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration overview

The Salesforce integration enables:

- **Opportunity sync**: When you close an opportunity in Salesforce, Light automatically creates a corresponding contract (or AR invoice, depending on your workflow configuration)
- **Account sync**: Salesforce accounts synchronize to Light customer master data
- **Product sync**: Salesforce products synchronize to Light products, including standard price book pricing
- **Field mapping**: Configure which Salesforce fields map to Light fields in the **Salesforce to Light** workflow
- **Filtering**: Choose which records to sync using SOQL filters (by default, only Closed Won opportunities)

This eliminates manual data entry and ensures contracts and invoices match CRM data.

## Setting up the Salesforce integration

To connect Salesforce:

1. Navigate to **Settings (gear icon) → Integrations → Salesforce**
2. Click **Connect**
3. Choose your Salesforce environment (**Production** or **Sandbox**)
4. You're redirected to Salesforce to authorize
5. Enter your Salesforce username and password
6. Review the permissions Light is requesting
7. Click **Authorize**
8. Light confirms the connection is active

Next, configure what data to sync in the **Salesforce to Light** workflow.

## Configuring opportunity sync

Define how opportunities become contracts or invoices:

1. Navigate to **Settings (gear icon) → Workflows** and open the **Salesforce to Light** workflow
2. Configure the opportunity filter node. This is a SOQL filter — by default only closed-won opportunities sync (`IsClosed = TRUE AND IsWon = TRUE`). You can extend the filter with additional conditions, for example by stage, amount, or close date
3. Configure field mappings in the mapping nodes. By default, opportunities map to Light contracts:
   - **Salesforce Account** → **Light Customer**
   - **Salesforce Opportunity Amount** → **Light Contract Estimated Amount**
   - **Salesforce Opportunity Description** → **Light Contract Description**
   - **Salesforce Opportunity Currency** → **Light Contract Currency**
   - **Salesforce Opportunity Line Items** → **Light Contract Lines** (product, quantity, discount)
4. Publish the workflow to activate the sync

Light validates the workflow to ensure data consistency.

## Opportunity to contract or invoice transformation

When a Salesforce opportunity matches your sync criteria:

1. Light reads the opportunity data (including its account and line items)
2. If the related customer doesn't exist in Light yet, it is created from the Salesforce account
3. By default, Light creates a contract populated with:
   - Customer (from the Salesforce account)
   - Estimated amount and currency (from the opportunity)
   - Contract lines (from the opportunity line items)
4. The workflow can instead (or additionally) be configured to create an AR (accounts receivable) invoice or, for negative amounts, a customer credit
5. You review the resulting record before finalizing it

This gives you a chance to review before committing to GL.

> Tip: Have finance review the first several synced invoices to ensure mapping is correct. After that, you can configure auto-posting if comfortable.

## Account and product sync

Beyond opportunities, sync Salesforce accounts and products:

1. Navigate to **Settings (gear icon) → Workflows** and open the **Salesforce to Light** workflow
2. Configure the account mapping node. By default:
   - **Salesforce Account Name** → **Light Customer Name**
   - **Salesforce Account Website** → **Light Customer Domain**
   - **Salesforce Account Description** → **Light Customer Description**
   - **Salesforce Billing Address** (street, city, state, postal code, country) → **Light Customer Address**
3. Publish the workflow

Similarly for products, active (non-archived) Salesforce products sync to Light products by default:

- **Salesforce Product Name** → **Light Product Name**
- **Salesforce Standard Price Book Entries** → **Light Product Pricing** (currency and unit price)

## Duplicate handling

What if the same customer exists in both Salesforce and Light?

Light matches records automatically using the Salesforce record ID, which is stored on the Light record as its external ID:

- If a Light customer, contract, or product with the same Salesforce ID already exists, the sync updates the existing record instead of creating a new one
- If no match is found, a new record is created with the Salesforce ID as its external ID

This prevents duplicate records without any additional configuration.

## Sync frequency

Once the **Salesforce to Light** workflow is published, Light automatically polls Salesforce for new and changed records on a recurring schedule. The sync frequency is managed by Light and does not require configuration.

You can also trigger a sync manually at any time (see below) if you don't want to wait for the next scheduled run.

## Monitoring Salesforce sync

Track integration activity:

1. Navigate to **Settings (gear icon) → Workflows** and open the **Salesforce to Light** workflow
2. Each synced record is processed as a workflow run, where you can see:
   - Which specific records were processed
   - Which were successfully synced
   - Which failed and why

This helps identify issues quickly.

## Manual sync trigger

Manually trigger a sync if you don't want to wait for scheduled sync:

1. Navigate to **Settings (gear icon) → Integrations → Salesforce**
2. Initiate a sync
3. Light imports the matching Salesforce records and runs them through the **Salesforce to Light** workflow

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
2. In the workflow's mapping nodes, add custom field mappings:
   - **Salesforce Project Code** → **Light Project Cost Center**
   - **Salesforce Product Category** → **Light Invoice Line Item Product**
3. Light syncs these custom fields to Light custom properties
4. Use these properties for reporting and cost allocation

## Multi-line items

If an opportunity includes multiple products (line items in Salesforce), how are they synced?

Salesforce opportunity line items (opportunity products) sync automatically:

1. Add products to the opportunity in Salesforce as opportunity line items
2. The workflow's line-item mappings apply to each line:
   - **Salesforce Product** → **Light Product**
   - **Salesforce Quantity** → **Light Quantity**
   - **Salesforce Discount** → **Light Discount**
3. Light creates the contract or invoice with multiple lines matching the Salesforce structure

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
