# Fiscal Year and Accounting Periods

This article explains how to configure fiscal years, accounting periods, and period closing tasks in Light. Proper period configuration ensures accurate closing procedures and period-based reporting.

[Open in Light →](https://app.light.inc/accounting/accounting-periods)

## Understanding fiscal years and accounting periods

A **fiscal year** is your organization's accounting year, which may differ from the calendar year. An **accounting period** is a subdivision of the fiscal year (typically monthly) during which transactions are grouped for reporting and closing purposes.

## Navigating accounting periods

1. Go to [**Accounting → Accounting periods**](https://app.light.inc/accounting/accounting-periods) in the sidebar
2. The page displays fiscal years as collapsible sections (e.g., 2025, 2026, 2027)
3. Expand a fiscal year to see its accounting periods
4. Each period shows columns for **Period** (month name), **Start date**, **End date**, and **Status**

The status column shows how many closing tasks have been completed (e.g., "2/4 tasks done", "0/4 tasks done").

## Generating accounting periods

1. Navigate to [**Accounting → Accounting periods**](https://app.light.inc/accounting/accounting-periods)
2. Click **+ Generate next period**
3. Light automatically generates the next set of monthly periods
4. The periods are created with start and end dates based on your fiscal year configuration

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

## Related articles

- [Managing Entities](/articles/02-organization-setup/2-1-managing-entities)
- [Chart of Accounts Setup](/articles/02-organization-setup/2-2-chart-of-accounts)
- [Tax and VAT Configuration](/articles/02-organization-setup/2-5-tax-vat-configuration)
