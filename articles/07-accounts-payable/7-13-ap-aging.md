# AP Aging Reports

AP aging reports analyze outstanding vendor payables by how overdue they are. These reports are essential for cash flow planning, vendor management, and meeting payment deadlines.

[Open in Light →](https://app.light.inc/payables)

## Understanding AP Aging Buckets

Vendor bills are grouped into aging buckets based on how overdue they are:

- **Current (0-30 days)**: Due within next 30 days or not yet due
- **1-30 Past Due (31-60 days)**: 31 to 60 days overdue
- **1-60 Past Due (61-90 days)**: 61 to 90 days overdue
- **60+ Past Due (90+ days)**: More than 90 days overdue

The aging date is calculated from the bill's due date (if available) or posting date.

## Running an AP Aging Report

1. Navigate to **Reports** > **AP Aging**
2. Set the **Reporting Date** (defaults to today)
3. Select **Report Options**:
   - **Group By**: Vendor, Currency, Entity, or None
   - **Include**: All vendors, or only active
   - **Currencies**: Specific currencies or all
   - **Entities**: Single entity or consolidated

4. Click **Generate**

Light displays the aging report with summary and detail sections.

## Reading the AP Aging Report

### Summary Section

The summary shows:

- **Total Payable**: Total amount due across all buckets
- **By Aging Bucket**: Amounts and percentages for each bucket
- **Totals by Currency**: If multi-currency selected
- **Payment Status**: Percentage due immediately vs. future

Key metric: **Days Payable Outstanding (DPO)** shows average days to pay vendors.

### Detail Section

Detailed listing by vendor showing:

- **Vendor Name**
- **Amounts by Bucket**: Breaking out vendor's total by aging
- **Total Outstanding**: Vendor's total across all bills
- **Number of Bills**: Count of open bills per vendor
- **Payment Terms**: Vendor's payment terms for reference

Click on a vendor to see all individual bills and their aging.

> Good to know: A healthy AP aging typically shows most bills in the Current bucket, with minimal past-due amounts.

## Filtering and Analysis

### Vendor Filtering

Apply filters to focus on specific vendors:

1. Click **Add Filter**
2. Select filter type:
   - **Vendor Name**: Search by name
   - **Vendor Type**: External or User (employees)
   - **Payment Method**: Wire, check, ACH, etc.
   - **Currency**: Specific currencies
   - **Entity**: Specific entities

3. Enter filter values
4. Click **Apply**

### High-Priority Vendor Identification

Identify vendors most likely to complain about late payment:

1. Generate aging report
2. Look for vendors in **Current bucket** with significant amounts
3. These vendors are about to become overdue
4. Prioritize their payment
5. Send payment confirmation so they know when to expect it

Alternatively, focus on **Past Due bucket** to address complaints.

### Payment Timing Analysis

Analyze your actual payment pattern:

1. View the **Current bucket** amount
2. Divide by total monthly vendor spend
3. This shows how many days' worth of payables you carry
4. Compare to vendor payment terms (e.g., if terms are Net 30):
   - If carrying 40 days: You're paying slightly late
   - If carrying 20 days: You're paying early
   - If carrying 30 days: You're following terms exactly

Adjust payment timing to optimize cash flow while maintaining relationships.

## Multi-Entity and Multi-Currency Analysis

### Entity-Specific Aging

View payables by entity:

1. Select **Group By: Entity**
2. Aging report breaks down totals by entity
3. See which entity carries more payables
4. Identify which entity has cash flow concerns
5. Compare payment practices across entities

### Currency Exposure Analysis

View payables by currency:

1. Select **Group By: Currency**
2. See total exposure in each currency
3. Helps with:
   - FX risk assessment
   - Currency liquidity planning
   - Payment sequencing by currency

4. Large exposure in weakening currency: Consider early payment

## Cash Flow Planning with AP Aging

### Payment Forecasting

Use AP aging to forecast cash needs:

1. Generate aging report
2. Look at Current bucket: How much is due within 30 days?
3. Calculate weekly payment needs:
   - Current bucket / 4 weeks = weekly average
   - This is baseline weekly payment obligation

4. Add expected new bills (based on historical volume)
5. Total shows cash needed for payables over next month

### Seasonal Adjustments

For businesses with seasonal patterns:

1. Generate aging reports for same month in prior years
2. Compare aging amounts
3. Historical pattern shows expected cash needs
4. Use to build cash reserves in strong months

## Vendor Performance Analysis

### Payment Compliance

Track whether vendors are reminding about overdue payments:

1. View vendors in **Past Due** bucket
2. Note which vendors have contacted (check comments or task history)
3. Separate "bad vendor relationships" from "bad cash management"
4. Address cash issues with CFO; fix vendor relationships with procurement

### Early Payment Discounts

Identify opportunities to save money:

1. Generate aging report
2. Look for vendors offering early payment discounts:
   - Check vendor terms (e.g., "2/10 Net 30" = 2% discount if paid in 10 days)
   - Cross-reference bills in Current bucket that are under 10 days old

3. Calculate discount benefit (2% of amount)
4. If discount > cost of borrowing, pay early

Light can highlight discounts available if configured.

## Exporting and Reporting

### Export Formats

1. Generate the aging report
2. Click **Export**
3. Choose format:
   - **Excel**: Detailed data with sorting/filtering
   - **PDF**: Formatted report with summary and chart
   - **CSV**: Raw data for analysis tools

4. Click **Export** to download

### Scheduled Reports

Set up automatic report generation:

1. Navigate to **Reports** > **Scheduled Reports**
2. Click **Schedule New Report**
3. Select **AP Aging**
4. Set scheduling:
   - **Frequency**: Daily, Weekly, Monthly
   - **Day/Date**: Which day to run
   - **Time**: What time to run
   - **Recipients**: Who receives the report
   - **Format**: PDF or Excel

5. Click **Create**

Light automatically generates and emails reports on schedule.

## Vendor Communication

### Payment Confirmation Emails

Inform vendors when payment is due:

1. Navigate to vendors with large outstanding amounts
2. Click **Send Payment Confirmation**
3. Optionally, attach aging report showing vendor's payables
4. Vendors appreciate transparency about payment schedule
5. Reduces inquiry volume to Finance

### Aging by Vendor Statement

Send aged payables statement to each vendor:

1. Open vendor
2. Click **Generate Aged Statement**
3. Light produces PDF showing:
   - All open bills
   - Aging (how overdue each is)
   - Total outstanding

4. Email to vendor's AP department
5. Helps them with their AR reconciliation

## Dispute Resolution

### Disputed Bills

Handle bills vendors claim are incorrect:

1. In aging report, look for vendors with past-due amounts
2. Contact vendor to discuss disputes
3. If vendor claims bill is incorrect:
   - Review invoice and receipt
   - Check if credit note should be issued
   - Verify GL account coding

4. If agreeable to dispute, hold payment pending resolution
5. Light can mark bill as "Disputed" to track

### Deduction Analysis

Track deductions vendors take from your payments:

1. When receiving payment confirmation from bank:
   - Expected: Bill amount
   - Actual: Less than expected
   - Difference: Deduction taken by vendor

2. Investigate deduction reason:
   - Vendor credit? (Apply to future bills)
   - Unauthorized? (Dispute with vendor)
   - Discount taken? (Valid if earned)

3. Record in Light comments for next negotiation

## Related Articles

- [Adding and managing vendors](/articles/07-accounts-payable/7-2-managing-vendors.md)
- [Scheduling and executing payments](/articles/07-accounts-payable/7-7-scheduling-payments.md)
- [Multi-entity AP operations](/articles/07-accounts-payable/7-12-multi-entity-ap.md)
