# Fiscal Year and Accounting Periods

> **What is this page about:** How to configure fiscal years and accounting periods in Light, generate periods on any month boundary, complete closing tasks in the required order (some tasks must precede others), and close periods for accurate reporting.

## On this page

- Understanding fiscal years and accounting periods
- Navigating accounting periods in Light
- Configuring fiscal years in Light
- Generating accounting periods in Light
- Period closing tasks in Light
- Closing a period in Light
- Reopening tasks in Light
- Fiscal year structure in Light
- Best practices for fiscal years and accounting periods in Light
- Related articles

[Open in Light →](https://app.light.inc/accounting/accounting-periods)

## Understanding fiscal years and accounting periods

A **fiscal year** is your organization's accounting year, which may differ from the calendar year. An **accounting period** is a subdivision of the fiscal year (typically monthly) during which transactions are grouped for reporting and closing purposes.

## Navigating accounting periods in Light

1. Go to [Accounting → Accounting periods](https://app.light.inc/accounting/accounting-periods) in the sidebar
2. The page displays fiscal years as collapsible sections
3. Expand a fiscal year to see its accounting periods
4. Each period shows columns for **Period** (month name), **Start date**, **End date**, and **Status**

The fiscal year labels reflect your configuration:
- **Calendar year**: "2025" (Jan 1 – Dec 31, 2025)
- **Fiscal year**: "FY2025/2026" (e.g., Apr 1, 2025 – Mar 31, 2026)
- **Partial year**: "2025 Jan–Jul" (e.g., Jan 1 – Jul 31, 2025)

The status column shows how many closing tasks have been completed (e.g., "2/4 tasks done", "0/4 tasks done").

## Configuring fiscal years in Light

When generating accounting periods, you can configure your fiscal year to start and end on any month boundary.

1. Click **+ Generate next period** on the Accounting periods page
2. Use the **month range picker** to select your fiscal year start and end months
   - The picker spans two adjacent calendar years, and you can select up to 12 consecutive months within that range
   - Shorter, partial fiscal years (e.g., a 3-month stub year when changing your fiscal year end) are fully supported
   - As you select months, the live preview shows how your fiscal year will be labeled
3. Choose your period interval (typically **Monthly**)
4. Click **Generate next period** to confirm (this button reads **Generate period** only the first time, before any periods exist)

**Examples:**
- **April to March fiscal year**: Select Apr 2025 – Mar 2026 → labeled "FY2025/2026"
- **Calendar year**: Select Jan 2025 – Dec 2025 → labeled "2025"
- **Partial year**: Select Jan 2025 – Jul 2025 → labeled "2025 Jan–Jul"

## Generating accounting periods in Light

1. Navigate to [Accounting → Accounting periods](https://app.light.inc/accounting/accounting-periods)
2. Click **+ Generate next period**
3. Select your fiscal year start and end months using the month range picker
4. Light automatically generates monthly periods based on your selection

Your fiscal year can start in any month—not just January. For example, you can generate an April to March fiscal year or an October to September fiscal year.

## Period closing tasks in Light

Each accounting period has a set of closing tasks that must be completed before the period can be closed. To view and manage tasks:

1. Click on a period in the accounting periods list
2. The **Tasks** view opens, showing the required closing tasks:
   - **Account Payables**: Close or reopen accounts payable for the period
   - **Account Receivables**: Close or reopen accounts receivable for the period
   - **Journal Entries**: Close or reopen journal entry posting for the period
   - **FX revaluation**: Run foreign exchange revaluations for the period
3. Each task shows a **Required** badge and an action button:
   - **Close**: Locks the task area for the period
   - **Reopen**: Unlocks a previously closed task area
   - **Run revaluations**: Executes FX revaluation calculations (shows as **Re-run revaluations** once revaluations have already been run for the period)

Account Payables, Account Receivables, and Journal Entries can be closed in any order relative to each other. **FX revaluation** is the exception—it can only be run after all three of those are closed, and after the previous period's FX revaluation is done.

## Closing a period in Light

Once all four closing tasks are completed:

1. Navigate to the period's Tasks view
2. Ensure all tasks show **Reopen** buttons (meaning they've been closed)
3. Click the **Close period** button at the bottom of the page
4. Confirm the closing

The previous accounting period must already be closed before you can close a period—periods are closed in chronological order.

A closed period prevents new transactions from being posted.

## Reopening tasks in Light

If corrections are needed after closing a task:

1. Navigate to the period's Tasks view
2. Click **Reopen** on the relevant task
3. Make the necessary corrections
4. Close the task again when complete

Reopening a task may also reopen the FX revaluation task for later periods you've already run, so revaluations must be run again before those periods can be closed.

## Fiscal year structure in Light

Fiscal years are displayed in reverse chronological order on the Accounting periods page. Each fiscal year's status depends on the progress of its accounting periods and their closing tasks.

## Best practices for fiscal years and accounting periods in Light

- Complete all four closing tasks promptly after month-end to enable timely reporting
- Close Account Payables, Account Receivables, and Journal Entries before running FX revaluations—revaluations can only run once those three are closed and the prior period's revaluation is done
- Plan period closing tasks in advance and assign responsibilities
- Reopen periods only for legitimate corrections
- Close periods in chronological order to maintain accounting integrity

## Related articles

- [Managing Entities](https://light.inc/help/organization-setup/managing-entities)
- [Chart of Accounts Setup](https://light.inc/help/organization-setup/chart-of-accounts)
- [Tax and VAT Configuration](https://light.inc/help/organization-setup/tax-vat-configuration)
