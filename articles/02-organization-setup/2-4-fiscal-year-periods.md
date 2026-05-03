# Fiscal Year and Accounting Periods

This article explains how to configure fiscal years, accounting periods, and period closing tasks in Light. Proper period configuration ensures accurate closing procedures and period-based reporting.

[Open in Light →](https://app.light.inc/accounting/accounting-periods)

## Understanding fiscal years and accounting periods

A **fiscal year** is your organization's accounting year, which may differ from the calendar year. An **accounting period** is a subdivision of the fiscal year (typically monthly) during which transactions are grouped for reporting and closing purposes.

Light supports fiscal years that start and end in any month, including:
- **Calendar years** (January–December)
- **Non-calendar fiscal years** (e.g., April–March, October–September)
- **Partial years** (e.g., January–July for a company's first year)

## Navigating accounting periods

1. Go to [**Accounting → Accounting periods**](https://app.light.inc/accounting/accounting-periods) in the sidebar
2. The page displays fiscal years as collapsible sections, with labels that reflect your fiscal year structure:
   - **Calendar years**: `2025`, `2026`, `2027`
   - **Non-calendar fiscal years**: `FY2025/2026`, `FY2026/2027` (e.g., for April–March or October–September)
   - **Partial years**: `2025 Jan-Jul`, `2026 Apr-Sep`
3. Expand a fiscal year to see its accounting periods
4. Each period shows columns for **Period** (month name), **Start date**, **End date**, and **Status**

The status column shows how many closing tasks have been completed (e.g., "2/4 tasks done", "0/4 tasks done").

## Generating accounting periods

### Creating your first fiscal year

1. Navigate to [**Accounting → Accounting periods**](https://app.light.inc/accounting/accounting-periods)
2. Click **+ Generate next period**
3. In the dialog that appears:
   - Use the **month range picker** to select your fiscal year start and end months
   - The picker displays two consecutive calendar years side by side
   - Select the starting month in the left panel and ending month in the right panel
   - Your fiscal year must span exactly 12 consecutive months
4. Review the **label preview** below the picker:
   - `2026` for calendar years (January–December)
   - `FY2026/2027` for fiscal years that cross calendar year boundaries
   - `2026 Jan-Jul` for partial years (less than 12 months or non-standard ranges)
5. Select the **duration** (typically Monthly)
6. Click **Generate period**

### Generating subsequent fiscal years

Once you have at least one fiscal year configured:

1. Click **+ Generate next period**
2. The month range picker will default to the next 12-month period following your last period
3. Adjust the range if needed, or accept the default
4. Click **Generate next period**

Light automatically creates the next set of periods based on your fiscal year configuration.

## Configuring non-calendar fiscal years

To set up a fiscal year that doesn't align with the calendar year (e.g., April 2025 to March 2026):

1. Open the period generation dialog
2. In the month range picker:
   - Select **April** in the left panel (2025)
   - Select **March** in the right panel (2026)
3. The label preview will show: **FY2025/2026**
4. Select **Monthly** as the duration
5. Click **Generate period**

Light will create 12 monthly periods spanning your fiscal year, with the year labeled as `FY2025/2026` in the accounting periods list.

## Period closing tasks

Each accounting period has a set of closing tasks that must be completed before the period can be closed. To view and manage tasks:

1. Click on a period in the accounting periods list
2. The **Tasks** view opens, showing the required closing tasks:
   - **Account Payables**: Close or reopen accounts payable for the period
   - **Journal Entries**: Close or reopen journal entry posting for the period
   - **FX revaluation**: Run foreign exchange revaluations for the period
   - **Account Receivables**: Close or reopen accounts receivable for the period
3. Each task shows a **Required** badge and an action button:
   - **Close**: Locks the task area for the period
   - **Reopen**: Unlocks a previously closed task area
   - **Run revaluations**: Executes FX revaluation calculations

## Closing a period

Once all four closing tasks are completed:

1. Navigate to the period's Tasks view
2. Ensure all tasks show **Reopen** buttons (meaning they've been closed)
3. Click the **Close period** button at the bottom of the page
4. Confirm the closing

A closed period prevents new transactions from being posted.

## Reopening tasks

If corrections are needed after closing a task:

1. Navigate to the period's Tasks view
2. Click **Reopen** on the relevant task
3. Make the necessary corrections
4. Close the task again when complete

## Fiscal year structure

Fiscal years are displayed in reverse chronological order on the Accounting periods page. Each fiscal year's status depends on the progress of its accounting periods and their closing tasks.

## Best practices

- Complete all four closing tasks promptly after month-end to enable timely reporting
- Run FX revaluations before closing Account Payables and Account Receivables
- Plan period closing tasks in advance and assign responsibilities
- Reopen periods only for legitimate corrections
- Close periods in chronological order to maintain accounting integrity
- When configuring your first fiscal year, ensure the start and end months align with your organization's accounting calendar

## Related articles

- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
- [Chart of Accounts Setup](/articles/02-organization-setup/2-2-chart-of-accounts)
- [Tax and VAT Configuration](/articles/02-organization-setup/2-5-tax-vat-configuration)
