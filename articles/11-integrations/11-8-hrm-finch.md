# HRM Integration (Finch)

Finch is a unified HRM and payroll API connecting all major payroll providers (ADP, Gusto, Rippling, BambooHR, etc.) to a single integration point. Light's Finch integration automatically syncs headcount, payroll data, and employee information from your HRM system.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

The Finch integration enables:

- **Headcount sync**: Employee count and changes automatically update in Light
- **Payroll data sync**: Payroll expenses automatically post to GL after processing
- **Employee location tracking**: Track employees by location for multi-entity reporting
- **Benefit tracking**: Track benefits cost for accurate expense allocation
- **Department and cost center**: Assign employees to cost centers for departmental expense analysis

This automates payroll accounting and ensures HR data stays current.

## Setting up Finch integration

To connect Finch:

1. Navigate to **Settings (gear icon) > Integrations > Finch**
2. Click **Connect**
3. Finch displays your list of connected payroll providers (ADP, Gusto, etc.)
4. Select the HRM system where your employees are managed
5. You're redirected to that system to authorize
6. Sign in and authorize Finch to access employee data
7. Light confirms connection is active

Next, configure what data to sync.

## Configuring headcount sync

Map employee data to Light:

1. Navigate to **Settings > Integrations > Finch > Headcount Mapping**
2. Select **Sync Employees**: Toggle on
3. Configure mapping:
   - **Employee Name** → **Light Employee Record**
   - **Employee ID** → **Light Employee ID**
   - **Department** → **Light Cost Center**
   - **Location** → **Light Entity** (for multi-entity companies)
   - **Salary/Wage** → **Light Salary Amount**
4. Configure filters:
   - Employment status: Active employees only (exclude terminated)
   - Employee type: Full-time, part-time, contractors
5. Save mappings

Light tracks current employee roster.

## Configuring payroll expense sync

Automate payroll posting to GL:

1. Navigate to **Settings > Integrations > Finch > Payroll Mapping**
2. Select **Sync Payroll**: Toggle on
3. Configure mapping:
   - **Gross Salary** → **Light Payroll Expense Account**
   - **Taxes Withheld** → **Light Payroll Tax Liability Account**
   - **Employee Benefits** → **Light Benefits Expense Account**
   - **Employer Taxes** → **Light Employer Tax Expense Account**
   - **Deductions** → **Light Deduction Liability Account**
4. Configure by:
   - Pay frequency (weekly, biweekly, monthly)
   - Post-pay date (immediately or offset by N days)
5. Save configuration

Light automatically posts payroll after processing by your payroll provider.

## Department and cost center allocation

Allocate payroll expenses by department:

1. Ensure employees are assigned to departments/cost centers in your HRM
2. Light syncs department information from HRM
3. Payroll expenses are allocated to each employee's department
4. Reporting shows salary and benefit costs by department

This enables departmental P&L analysis.

## Multi-entity payroll

For organizations with employees in multiple entities:

1. Configure location/entity mapping in Finch integration
2. Sync employees with their entity/location
3. Light posts payroll expenses to entity-specific GL accounts
4. Consolidated P&L shows payroll across entities

This maintains proper entity accounting.

## Employee benefits tracking

Track benefit expenses separately:

1. Configure benefit mapping (health insurance, retirement, etc.)
2. Light syncs benefit costs from HRM
3. Benefits post as separate expense lines
4. Enables benefit cost analysis by employee, department, or type

This supports cost management and budgeting.

## Headcount metrics and reporting

Generate headcount reports:

1. Navigate to **Planning & Reports → Reports**
2. View:
   - Current employee count
   - Headcount by department
   - Headcount by location (if multi-location)
   - Headcount changes (new hires, terminations)
3. Trend headcount over time
4. Calculate revenue per employee

This integrates HR data with financial reporting.

## Sync frequency

Configure how often Light checks for new payroll:

1. Navigate to **Settings > Integrations > Finch > Sync Settings**
2. Select frequency:
   - **Manual**: Only sync when you trigger
   - **Post-payroll**: Sync immediately after payroll processes
   - **Daily**: Check daily
   - **Weekly**: Check weekly
3. Save

Most companies sync daily or after each payroll run.

## Manual sync trigger

Sync immediately without waiting for scheduled time:

1. Navigate to **Settings (gear icon) > Integrations > Finch**
2. Click **Sync Now**
3. Light immediately checks your payroll system for new data
4. See summary of synced payroll and headcount

Useful if you need updated payroll in GL immediately.

## Monitoring Finch sync

Track integration activity:

1. Navigate to **Settings > Integrations > Finch > Sync History**
2. View all syncs:
   - Date/time
   - Headcount synced
   - Payroll periods processed
   - Errors (if any)
3. Click any sync to see details:
   - Employees added, updated, terminated
   - Payroll amounts processed
   - GL accounts posted to

## Handling payroll corrections

If payroll needs to be corrected (e.g., missed deduction):

1. Correct the data in your HRM system
2. Request a re-run or correction from payroll provider
3. Light syncs the corrected payroll
4. Light reverses the prior payroll entry
5. Posts the corrected payroll entry

This maintains audit trail of corrections.

## Integrating with tax systems

Light combines Finch payroll with tax compliance:

1. Light tracks payroll by employee and department
2. Tax systems (HMRC, AvaTax) use Light payroll data
3. Employer taxes, employee taxes calculated correctly
4. Tax returns prepared with complete payroll data

This ensures tax compliance.

## Troubleshooting Finch sync

**Payroll not syncing**: Check sync status, verify payroll was processed in HRM system, check filter criteria.

**Wrong department assigned**: Verify department mapping, ensure employees are assigned to departments in HRM.

**Salary amounts incorrect**: Verify mapping (gross vs. net), check for deductions that should post separately.

**Connection failed**: Re-authorize Finch and HRM system, verify API access is enabled.

**Duplicate employees**: Check for duplicate employee records in Light, merge if needed.

## Terminating employee access

When employees are terminated:

1. HRM marks employee as terminated
2. Finch syncs termination status
3. Light updates employee status
4. Future payroll does not include terminated employee
5. Historical payroll remains for reporting

This prevents accidental re-entry of terminated employees.

## Salary and wage updates

When employee salary changes:

1. HRM records salary change
2. Finch syncs updated salary
3. Light updates employee record and applies to future payroll
4. Previous salary used for retroactive payroll corrections

This keeps salary data current.

## Reporting headcount and payroll

Create reports combining headcount and payroll:

1. Navigate to **Planning & Reports → Reports**
2. View:
   - Headcount and changes
   - Payroll expense by department
   - Revenue per employee
   - Payroll as % of revenue
   - Salary cost trends
3. Export for analysis and budgeting

> Tip: Compare payroll budget to actual using Finch sync data. This helps with workforce planning and cost control.

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [Budget scenarios](../10-reporting/10-10-budget-scenarios.md)
- [Custom reports and filters](../10-reporting/10-9-custom-reports.md)
