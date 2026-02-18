# AR Aging Reports

AR aging reports analyze outstanding invoices by how overdue they are. These reports are essential for collection management, financial planning, and assessing credit risk.

[Open in Light →](https://app.light.inc/invoice-receivables)

> **Important:** AR aging reports group transactions by the customer's UUID (unique identifier). For accurate aging data, ensure all customers have a UUID assigned. Transactions linked to customers without a UUID may appear under a blank partner or be grouped incorrectly.

## Understanding Aging Buckets

Invoices are grouped into aging buckets based on days past due:

- **Current (0-30 days)**: Due within next 30 days or not yet due
- **1-30 Past Due (31-60 days)**: 31 to 60 days overdue
- **1-60 Past Due (61-90 days)**: 61 to 90 days overdue
- **60+ Past Due (90+ days)**: More than 90 days overdue

The aging date is calculated from the invoice due date (if available) or document date.

## Running an AR Aging Report

1. Navigate to **Reports** > **AR Aging**
2. Set the **Reporting Date** (defaults to today)
3. Select **Report Options**:
   - **Group By**: Customer, Currency, Entity, or None
   - **Include**: Active customers only, or include archived
   - **Currencies**: Specific currencies or all
   - **Entities**: Specific entities or consolidated

4. Click **Generate**

Light displays the aging report with summary and detail sections.

## Reading the Aging Report

### Summary Section

The summary shows:

- **Total Outstanding**: Total amount due across all buckets
- **By Aging Bucket**: Amounts and percentages for each bucket
- **Totals by Currency**: If multi-currency selected
- **Collections Status**: Percentage in each bucket (helps track improving or deteriorating AR)

### Detail Section

Detailed listing by customer showing:

- **Customer Name**
- **Amounts by Bucket**: Breaking out the customer's total by aging
- **Total Outstanding**: Customer's total across all invoices
- **Number of Invoices**: Count of open invoices per customer

Click on a customer to see all individual invoices and their aging.

## Filtering and Drilling Down

### Customer Filtering

Apply filters to narrow the report:

1. Click **Add Filter**
2. Select filter type:
   - **Customer Name**: Search by name or ID
   - **Customer Type**: Business, Consumer, Government
   - **Customer Status**: Active, Archived
   - **Country**: Customer's billing country
   - **Industry**: If customer has industry classification

3. Enter filter value
4. Click **Apply**

### Aging Bucket Drilling

1. Click on an aging bucket amount
2. Light shows all invoices in that bucket
3. View:
   - Invoice number and date
   - Invoice amount
   - Days past due
   - Customer name

4. Click an invoice to see full details including dunning history and payment status

### High-Risk Customer Identification

To find your most problematic customers:

1. Generate the aging report
2. Look at the **60+ Past Due** bucket
3. Identify the top N customers by amount
4. Sort by days past due (longest first)
5. These are your priority collections cases

## Currency and Entity Analysis

### Multi-Currency Aging

When customers owe in multiple currencies:

1. Select **Group By: Currency** (if not already set)
2. Aging report breaks down totals by currency
3. See which currencies represent largest exposure
4. Useful for FX hedging decisions

### Entity-Specific Aging

For multi-entity companies:

1. Select **Group By: Entity**
2. View aging by entity (each has its own GL)
3. See which entity has largest collections challenge
4. Useful for accountability and resource allocation

## Exporting and Sharing Reports

### Export Formats

1. Generate the aging report
2. Click **Export**
3. Choose format:
   - **Excel**: Detailed data with sorting/filtering
   - **PDF**: Formatted report with summary and detail
   - **CSV**: Raw data for analysis tools

4. Click **Export** to download

### Emailing Reports

1. After generating, click **Share**
2. Enter **Email Recipients**
3. Optionally, add **Message**
4. Click **Send**

Recipients receive the report as a PDF or Excel file depending on format selected.

## Scheduling Recurring Reports

Set up automatic report generation:

1. Navigate to **Reports** > **Scheduled Reports**
2. Click **Schedule New Report**
3. Select **AR Aging**
4. Set **Scheduling Options**:
   - **Frequency**: Daily, Weekly, Monthly
   - **Day/Date**: Which day to run
   - **Time**: What time to run
   - **Recipients**: Who receives the report
   - **Format**: PDF or Excel

5. Click **Create Schedule**

Light automatically generates and emails reports on schedule.

## Collection Workflow Integration

Link aging data to collection activities:

1. Generate the aging report
2. Click into a customer with overdue invoices
3. Click **Create Collection Task**
4. Light creates a reminder for your collections team
5. Team can mark tasks complete after following up

Track collection effectiveness by monitoring improvements in aging buckets over time.

## Trend Analysis

Monitor AR health over time:

1. Generate aging reports for multiple dates (e.g., monthly)
2. Compare bucket percentages:
   - Growing **0-30 bucket** (good): Invoices being collected
   - Growing **60+ bucket** (bad): Collections deteriorating

3. Calculate metrics like:
   - **Days Sales Outstanding (DSO)**: Average days to collect
   - **Collection Rate**: % of invoices collected within 30 days

Use trend data to identify collection problems early.

## Advanced Aging Options

### Adjusting Reporting Date

Use date other than today:

1. In the Reporting Date field, enter a past or future date
2. Light recalculates aging based on that date
3. Useful for:
   - Month-end closing analysis
   - What-if scenarios
   - Reconciling to period-end AR balance

### Excluding Certain Invoices

Remove invoices from aging:

1. Open the aging report
2. Click **Filters**
3. Add filter for invoice status:
   - CLEARED or ARCHIVED: Already collected or closed
   - Include only OPEN or PARTIALLY_CLEARED

4. Apply filter

Helps focus on current collection priorities.

## Related Articles

- [Tracking payments and outstanding balances](/articles/06-accounts-receivable/6-8-tracking-payments.md)
- [Sending invoices and payment reminders](/articles/06-accounts-receivable/6-7-sending-invoices.md)
- [Multi-entity AR operations](/articles/06-accounts-receivable/6-11-multi-entity-ar.md)
