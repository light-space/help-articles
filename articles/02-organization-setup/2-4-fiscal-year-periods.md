# Fiscal Year and Accounting Periods

This article explains how to configure fiscal years, accounting periods, and period status management in Light. Proper period configuration ensures accurate closing procedures and period-based reporting.

[Open in Light →](https://app.light.inc/accounting/accounting-periods)

## Understanding fiscal years and accounting periods

A **fiscal year** is your organization's accounting year, which may differ from the calendar year. An **accounting period** is a subdivision of the fiscal year (typically monthly, quarterly, or yearly) during which transactions are grouped for reporting and closing purposes.

> Good to know: Light supports flexible period configurations. You can use monthly, quarterly, or annual periods depending on your reporting requirements.

## Creating a fiscal year

1. Navigate to **Accounting → Accounting periods** ([Open in Light →](https://app.light.inc/accounting/accounting-periods))
2. Click **+ Generate next period**
3. Enter the **Year** (numeric value, e.g., 2024)
4. The system automatically calculates the **Start Date** and **End Date** based on your period interval configuration
5. Click **Create**

The fiscal year status depends on its accounting periods:
- **Open**: At least one period is open
- **Partially Closed**: Some periods are closed, others are open
- **Closed**: All periods are closed

## Configuring accounting periods

Before creating accounting periods, configure your period interval type:

1. Go to **Accounting → Accounting periods**
2. Click **Settings** or **Period Configuration**
3. Select your **Interval Type**:
   - **Monthly**: 12 periods per year (Jan-Dec or other start month)
   - **Quarterly**: 4 periods per year (Q1-Q4)
   - **Yearly**: 1 period per year
4. Click **Save Configuration**

> Tip: This interval type applies to all fiscal years. You cannot mix interval types within a company.

## Creating accounting periods

Once interval configuration is complete, create periods:

1. In **Accounting → Accounting periods**, click **+ Generate next period**
2. Select the **Fiscal Year** to create periods for
3. Light automatically generates periods based on your interval configuration:
   - Monthly creates 12 periods
   - Quarterly creates 4 periods
   - Yearly creates 1 period
4. Review the period dates and labels
5. Click **Create**

Each period includes:
- A unique label (e.g., "Jan 2024", "Q1 2024")
- Start and end dates
- An open status allowing transactions to be posted

## Period status: Open and Closed

Periods can be opened or closed to control transaction posting:

- **Open**: Transactions can be posted to this period
- **Closed**: Transactions cannot be posted; period is locked for reporting

To change a period status:

1. Find the period in the accounting periods list
2. Click the period to view details
3. Click **Edit Status**
4. Change the status to **Open** or **Closed**
5. Click **Save**

Closing a period is typically done after all transactions are recorded, reconciliations are complete, and the period is ready for reporting.

## Opening and closing periods

### Opening a period

Opening a previously closed period allows new transactions to be posted:

1. Navigate to **Accounting → Accounting periods**
2. Find the closed period
3. Click **Reopen Period**
4. Confirm the action

Reopening is useful if corrections are needed after initial closing.

### Closing a period

Closing a period after all transactions and reconciliations are complete:

1. Navigate to **Accounting → Accounting periods**
2. Find the open period
3. Click **Close Period**
4. The system may perform final adjustments if configured (FX revaluation, period closing entries)
5. Confirm the closing
6. The period status changes to **Closed**

## Accounting period tasks

Light tracks closing tasks like LOCK_AP (Accounts Payable), LOCK_AR (Accounts Receivable), LOCK_JE (Journal Entries), and FX_REVALUATION (foreign exchange adjustments). For multi-entity organizations, periods are company-wide but closing tasks are tracked per entity, allowing some entities to complete tasks before others.

## Fiscal year closing

When a complete fiscal year is finished:

1. Ensure all periods within the year are closed
2. Verify all closing tasks are completed for all entities
3. Perform final year-end adjustments (retained earnings, tax provisions)
4. The fiscal year status automatically updates to **Closed**
5. Generate final year-end reports

Closed fiscal years retain all transaction data but prevent new posting in those periods.

## Best practices

- Establish a consistent period structure (monthly periods are most common)
- Close periods promptly after month-end to enable timely reporting
- Plan period closing tasks in advance and assign responsibilities
- Use period closing checklists to ensure all steps are completed
- Maintain audit trails of who closed each period and when
- Archive closed periods' documentation for regulatory compliance
- Consider reopening periods only for legitimate corrections
- Schedule period closings during low-activity periods when possible

## Related articles

- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
- [Chart of Accounts Setup](/articles/02-organization-setup/2-2-chart-of-accounts)
- [Tax and VAT Configuration](/articles/02-organization-setup/2-5-tax-vat-configuration)
