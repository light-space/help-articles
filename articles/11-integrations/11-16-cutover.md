# Cutover Fundamentals and Execution

Cutover is the process of switching from your legacy accounting system to Light as the primary system. It's a critical milestone requiring careful planning, validation, and execution. This guide covers best practices for a smooth cutover.

[Open in Light →](https://app.light.inc/settings/integrations)

## Cutover overview

Cutover involves:

1. **Planning**: Define scope, timeline, risks
2. **Data migration**: Export, transform, import data to Light
3. **Validation**: Verify migrated data is accurate
4. **Preparation**: Train team, establish Light processes
5. **Execution**: Switch to Light on cutover date
6. **Stabilization**: Monitor and resolve post-cutover issues
7. **Closure**: Ensure legacy system is properly archived

Cutover typically takes 4-8 weeks total.

## Cutover planning

Plan your cutover:

1. **Identify cutover date**: Typically a month-end (preferred) or quarter-end
2. **Define scope**: What data transfers? What stays behind?
3. **Identify dependencies**: What other systems depend on accounting data?
4. **Assess risks**: What could go wrong? What's the impact?
5. **Create timeline**: Work backwards from cutover date
6. **Assign owners**: Who's responsible for each step?
7. **Allocate resources**: Budget time and people needed

Document the plan and socialize with stakeholders.

## Cutover risks and mitigation

Common cutover risks:

| Risk | Impact | Mitigation |
|--|--|--|
| Data accuracy | Wrong GL balances | Thorough validation before cutover |
| Missing data | Incomplete records | Comprehensive data mapping |
| Downtime | No access to accounting | Parallel running period |
| Staff resistance | Poor adoption | Early training, change management |
| Integration issues | Systems misaligned | Test all integrations pre-cutover |
| Performance | Slow system | Load testing before go-live |

Create a risk register and mitigation plan.

## Data migration (covered in detail in other articles)

Migrate data to Light:

1. **Prepare**: Clean up legacy system data, close prior periods
2. **Export**: Export all data from legacy system
3. **Transform**: Convert to Light format
4. **Import**: Import to Light in structured order
5. **Validate**: Verify GL, AR, AP, customers, vendors
6. **Reconcile**: Ensure balances match legacy system

See data migration articles (QuickBooks, E-Conomic) for detailed steps.

## Validation checklist

Before cutover, validate:

**GL Account Validation**:
- Trial balance balances (debits = credits)
- All accounts have correct opening balances
- Account structure matches business organization

**Customer/Vendor Validation**:
- All active customers and vendors imported
- Contact information correct
- Payment terms and credit limits set

**AR/AP Validation**:
- AR aging matches legacy system
- AP aging matches legacy system
- All outstanding invoices/bills present

**Account Balances**:
- Cash matches bank statements
- AR total matches GL
- AP total matches GL

**Fixed Asset Validation**:
- Fixed assets entered via journal entries, bills, or sales invoices with release templates
- Book values match legacy system

Use Light's reconciliation reports to validate.

## Establishing Light processes

Before cutover, document new processes:

1. **Invoice processing**: How to create AP/AR invoices in Light
2. **Payment processing**: How to record customer payments, vendor payments
3. **Bank reconciliation**: Light's reconciliation process (monthly)
4. **GL posting**: Journal entry procedures
5. **Month-end close**: Light's close process and procedures
6. **Reporting**: How to access and generate reports in Light
7. **System access**: Who has access to what data
8. **Change management**: How to request new features or process changes

Document these and share with team.

## Team training and readiness

Train your team thoroughly:

1. **Leadership training**: CFO/finance manager understands full scope
2. **Core team training**: Daily accounting staff (invoice entry, reconciliation)
3. **User training**: Anyone who enters data into Light
4. **Support training**: Who to contact with questions
5. **Train-the-trainer**: Identify super-users who can help others
6. **Practice sessions**: Hands-on exercises before cutover
7. **FAQs**: Document common questions and answers

Schedule training 2-4 weeks before cutover.

## Cutover decision criteria

Before pulling the trigger, ensure:

- All data migration validation completed successfully
- GL trial balance balances
- AR and AP aging reports match legacy system
- All integrations tested and working
- Team trained and confident
- Legacy system data backed up
- Stakeholders (auditors, lenders) notified
- IT infrastructure ready

Create a go/no-go checklist.

## Executing the cutover

On cutover day:

1. **Final data exports**: Export final data from legacy system (as of cutover date)
2. **Final import to Light**: Import any final transactions
3. **Freeze legacy system**: Stop posting new transactions to legacy system
4. **Announce cutover**: Notify team cutover is happening
5. **Begin Light posting**: All new transactions post to Light
6. **Monitor closely**: Watch for issues throughout the day
7. **Support hotline**: Have team available to help users
8. **Communicate status**: Keep stakeholders informed

Cutover typically happens late Friday to allow full week for stabilization.

## Post-cutover stabilization (first week)

In the week following cutover:

1. **Monitor system performance**: Ensure Light is responsive
2. **Track issues**: Log all problems reported by users
3. **Prioritize issues**: Critical issues resolved immediately
4. **Communicate**: Daily updates to team on status
5. **Validate transactions**: Sample-check transactions posted in Light
6. **Train on-the-job**: Address questions as they arise
7. **Document workarounds**: If issues exist, document temporary workarounds

Most issues surface in first week.

## First month-end in Light

Your first close in Light:

1. **Month-end procedures**: Follow Light's established processes
2. **Reconciliations**: Bank, AR, AP, GL
3. **Accruals**: Record accruals per Light process
4. **Close**: Post closing entries, prepare trial balance
5. **Reporting**: Generate management and statutory reports
6. **Validation**: Compare results to legacy system results (if available)
7. **Adjustments**: Record any adjustments needed

This validates that Light processes work correctly.

## Parallel running (optional but recommended)

Run both systems in parallel for 1-4 weeks:

1. Post transactions to both systems
2. Compare results
3. Identify discrepancies
4. Resolve before fully archived legacy system
5. Provides confidence before fully switching

This reduces risk but adds work during transition.

## Legacy system archival

Properly archive the legacy system:

1. **Final backup**: Create comprehensive backup of legacy system
2. **Data exports**: Export GL, transactions, reports as PDFs
3. **Documentation**: Collect all system documentation
4. **Access preservation**: Maintain login access if needed
5. **Retention policy**: Plan how long to keep (typically 7+ years)
6. **Secure storage**: Store backups securely (encrypted, off-site)
7. **Decommissioning timeline**: Plan when to fully decommission

Maintain archived system per compliance requirements.

## Handling issues post-cutover

If problems surface after cutover:

1. **Assess severity**: Is this critical or minor?
2. **Communicate**: Notify affected parties
3. **Identify cause**: Root cause analysis
4. **Develop solution**: Fix the issue
5. **Implement**: Deploy fix
6. **Validate**: Verify fix works
7. **Prevent recurrence**: What can we do differently?

Have a rapid response process.

## Communication plan

Maintain regular communication:

1. **Pre-cutover**: Regular updates on progress
2. **Cutover week**: Daily status updates
3. **First month**: Weekly updates
4. **Post-first month**: Monthly updates as issues resolve

Use email, team meetings, or shared dashboards to communicate.

## Stakeholder management

Keep key stakeholders informed:

- **CFO/Controller**: Overall responsibility for cutover success
- **Finance team**: Daily users affected most
- **IT**: Infrastructure and technical support
- **External auditors**: May need to validate migration
- **Lenders**: If required by agreements
- **Investors**: If material to business

Tailor communication to each stakeholder group.

## Post-cutover audit and sign-off

Document cutover completion:

1. **Cutover report**: Document what was migrated, what wasn't, issues encountered
2. **Validation results**: Document all validation performed
3. **Sign-off**: Finance leadership approves cutover completion
4. **Lessons learned**: What went well? What could be better?
5. **Archive documentation**: Store all cutover documentation for audit trail

This provides evidence of proper cutover.

## Measuring cutover success

Evaluate cutover success:

1. **Data accuracy**: Is GL accurate? Do reports match expectations?
2. **System adoption**: Are users comfortable in Light?
3. **Process efficiency**: Are month-end closes faster? More accurate?
4. **Compliance**: Are we meeting audit and regulatory requirements?
5. **Issues**: How many critical issues? How quickly resolved?
6. **Cost**: Was cutover within budget?
7. **Timeline**: Did we hit the planned cutover date?

Document metrics and celebrate wins.

## Related articles

- [Data migration from QuickBooks](11-15-migration-quickbooks.md)
- [Data migration from E-Conomic](11-14-migration-economic.md)
- [Data import and migration tools](11-13-data-import.md)
- [Audit-ready record keeping](../09-revenue-compliance/9-9-audit-ready-records.md)
