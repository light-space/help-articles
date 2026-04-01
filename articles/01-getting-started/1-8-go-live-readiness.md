# Go-live readiness

This article outlines the minimum viable setup for going live with Light and helps you prepare for a successful transition from your legacy financial system.

[Open in Light →](https://app.light.inc/dashboard)

## Key concepts

Before starting, align your team on these terms:

**Cutoff Date** — The last day you operate in your legacy system (end of day). This is the reference point for your Trial Balance, open items, and releases. All transactions before this date stay in the legacy system for historical reference.

**Go-Live Date** — The first day you operate in Light. From this date forward, Light is your system of record. All new transactions are created and managed in Light.

**Migration Suspense Account** — A temporary balance sheet account used in Light to offset migrated AP and AR balances during the cutover import. After all cutover imports are complete, this account must net to zero.

## Before you go live

Successful go-live requires careful planning and testing. This article helps you verify that Light is ready for production use and that your organization is prepared for the transition.

## Minimum viable setup

Your Light instance is ready for go-live when it includes:

**User and permissions**
- At least one Finance Admin user who understands settings and can manage the system
- Finance Manager or Specialist users for each functional area (AR, AP, GL, Bank)
- Approval authority clearly defined with limits set per role
- Test users to verify workflows before go-live

**Organization structure**
- Company created with correct name, base currency, and emails
- All legal entities configured (subsidiaries, regional offices, etc.)
- Currency configuration matches your operating footprint
- Chart of accounts created with accounts for all major GL balances

**Bank connectivity**
- At least one primary bank account connected and verified
- Bank account mapped to correct GL account
- Transaction feed confirmed working (check last updated timestamp)
- Backup bank connection if using multiple banks

**Financial workflows**
- Invoice creation and approval workflow configured
- Bill processing and approval workflow configured
- Expense submission and approval workflow configured
- Payment processing workflow configured
- Default GL accounts set for common transactions

**Integration connectivity**
- Authentication configured (Auth0 for SSO, if applicable)
- Slack or Microsoft Teams connected for notifications
- Salesforce or HubSpot connected (if you use them)
- Any other critical integrations tested and verified

**Additional setup**
- Tax codes configured
- Reimbursement category → GL mapping defined
- Invoice template configured
- AI assistant rules configured (optional)

**Cards (if applicable)**
- Adyen GL account created in Light before go-live
- Adyen account funding and spending limits configured

**Master data**
- Vendors created: those present in open AP, plus those used in last year's postings
- Customers created: those present in open AR, plus those used in last year's postings
- Products/services created for any active contracts
- Open contracts uploaded so recurring sales invoices work from day one

## Legacy system preparation

Before cutover, complete the following in your legacy system. These steps reduce migration issues more than anything else.

**1. Reconcile subledgers to GL**
- Reconcile AP subledger ↔ AP control account in the General Ledger
- Reconcile AR subledger ↔ AR control account in the General Ledger
- Reconcile fixed assets register ↔ FA / accumulated depreciation accounts (if applicable)

If differences exist, correct them in the legacy system. Do not attempt to patch differences in Light.

**2. Clean up open items**
- Apply vendor credit notes to open invoices
- Apply customer credits to open invoices
- Allocate prepayments where possible

The goal is to migrate clean, consistent data.

**3. Confirm prior year close**
Ensure the previous year-end close (e.g. 2024) is completed in the legacy system — especially important if importing only current-year journals.

**4. Complete COA mapping**
Every account used in the agreed historical period must be mapped to a Light account code. Missing mappings are a common cause of migration delays.

**5. Prepare accruals schedule**
Document all ongoing accruals to carry forward operationally:
- Deferred revenue and prepaid expenses
- Start date, end date, frequency, and remaining balance for each

## Data migration requirements

If you're transitioning from a legacy system (NetSuite, SAP, Xero, QuickBooks, etc.), follow these steps in order. Completing them out of sequence can cause reconciliation problems.

> **Good to know:** Light provides CSV import templates for most entities. Ask your implementation specialist for templates that match your legacy system's export format.

### Step 0 — Lock snapshot exports

Once month-end close is complete in the legacy system, prepare frozen data packages and hand them to the implementation team:
- Final trial balance as of the cutoff date
- Open AP aging report
- Open AR aging report
- Fixed asset register (if applicable)
- Historical GL journals for the agreed import period

Do not post further transactions in the legacy system after this point.

### Step 1 — Import open AP and open AR

Import all unpaid invoices and bills into Light using the **Migration Suspense Account** (not P&L accounts). After import:
- Verify totals match between the legacy export and Light
- Resolve any exceptions
- Open invoices now appear in Light and can be collected or paid normally

> **Important:** Do not process payments or run bank reconciliation in Light until this step is complete. Doing so before migration is finished risks incorrect open balances.

### Step 2 — Import opening trial balance and historical GL journals

Post the opening trial balance as of the cutoff date via:
- Manual journal entry per account, or
- A single "Opening balances" journal entry, or
- CSV bulk journal entry import

After all imports in Steps 1 and 2 are complete, verify that the **Migration Suspense Account nets to zero**. A non-zero balance indicates an import discrepancy that must be resolved before go-live.

### Step 3 — Upload fixed assets and ongoing releases

Upload depreciation schedules and deferred revenue using the provided templates. Confirm that amortization logic matches your operational process.

### Step 4 — Validate foreign currency accounts and FX revaluation

If your entity operates in multiple currencies:
- Verify opening balances for all foreign currency accounts
- Confirm revaluation settings are configured correctly
- Run a test revaluation and confirm no unexpected FX gains or losses appear

## Operating rules during cutover

Follow these rules to maintain clean books during the transition period.

**Transactions and journals**
- Finalize all transactions in the legacy system as part of the final month-end close before cutoff
- From go-live forward, record all new transactions directly in Light
- If a correction is discovered after cutoff that relates to a legacy period: post the adjustment in the legacy system first to preserve historical accuracy, then mirror it in Light as a "Prior Period Adjustment" with a reference to the legacy entry for audit purposes

**Supplier and customer invoices**
- Invoices dated before cutoff: create and manage in the legacy system; these are migrated to Light as part of the initial upload
- Invoices dated on or after go-live: process directly in Light (via AP intake email or manual entry)

**Payments and bank reconciliation**
- Do not process payments or run bank reconciliation in Light until Open AP and Open AR migration (Step 1) is fully complete and verified

## Legacy system parallel run

Before fully cutting over to Light, run both systems in parallel:

**Parallel run timeline (typically 2-4 weeks)**
- **Week 1:** Run processes in both systems, compare results daily
- **Week 2:** Investigate any reconciliation differences
- **Week 3:** Minor adjustments, team confidence building
- **Week 4:** Final verification, prepare for cutover

**Processes to parallel run:**
1. Invoice creation and AR aging reports
2. Bill processing and AP aging reports
3. Expense submission and approval workflows
4. Bank reconciliation
5. GL posting and trial balance

**Reconciliation checklist:**
- [ ] Total AR in both systems matches
- [ ] Total AP in both systems matches
- [ ] GL trial balance matches
- [ ] Bank balances reconcile
- [ ] Expense totals by category match
- [ ] Approval workflows complete successfully in Light

If any variance exists, investigate and resolve before cutover. Most discrepancies come from:
- Different timing of transaction posting (normal, expected)
- Currency conversion rounding (normal for multi-currency)
- Transactions recorded in legacy system but not yet in Light (identify and recreate)

## Go-live checklist

**1 week before go-live**
- [ ] Verify all team members have Light access and have completed training
- [ ] Run final parallel reconciliation—all figures match
- [ ] Complete bank account reconciliation in Light
- [ ] Test all approval workflows with real data
- [ ] Verify email notifications are routing correctly
- [ ] Confirm Slack/Teams integration is working
- [ ] Export final data from legacy system for archive
- [ ] Notify all stakeholders of go-live date and time
- [ ] Document any workarounds or known issues
- [ ] Prepare rollback plan (in case of critical issues)

**Day of go-live**
- [ ] Post opening GL balances if not already done
- [ ] Disable invoicing, bill entry, and payments in legacy system
- [ ] Enable full access in Light for all users
- [ ] Send team communication confirming go-live
- [ ] Post-close legacy system
- [ ] Have Finance Admin on standby for 2-3 hours
- [ ] Monitor for critical issues

**First week post-go-live**
- [ ] Daily verification of GL posting
- [ ] Review bank reconciliation for accuracy
- [ ] Monitor approval workflows for bottlenecks
- [ ] Gather team feedback and address issues
- [ ] Create internal FAQ from common questions
- [ ] Fine-tune workflows based on actual usage

## Common go-live pitfalls to avoid

**Trying to perfect everything before go-live**
Light can evolve post-go-live. Focus on core AR, AP, and bank functions first. Optimize reporting, revenue recognition, and multi-entity consolidation after you're stable.

**Insufficient user training**
Users need hands-on practice before go-live. Schedule training 1-2 weeks before cutover so people remember what they learned.

**Inadequate testing of approval workflows**
Test with real amounts and real approvers. Test edge cases: what happens if an approver is on vacation? What if an expense exceeds all thresholds?

**No backup plan**
Have the legacy system accessible (read-only) for at least 30 days post-go-live. If a critical issue emerges, you may need to reference historical data.

**Poor data quality in legacy system**
Spend time cleaning data before import. Bad customer names, duplicate vendors, or incorrect account codes will cause problems in Light.

**Cutting over too quickly**
A 2-4 week parallel run is standard. Cutting over in days is risky unless you have a very simple financial structure.

## Post-go-live optimization

After go-live stabilizes (typically 2-4 weeks), optimize:

**Workflow efficiency**
- Review approval patterns—are approvals completing quickly?
- Adjust approval limits if too many escalations occur
- Consider parallel approvals for non-dependent items

**Automation**
- Set up recurring invoices for regular customers
- Automate bill matching and payment scheduling
- Configure recurring expense reports

**Reporting and dashboards**
- Create custom dashboards for executives
- Build automated reports for stakeholders
- Schedule weekly/monthly report distribution

**AI configuration**
- Monitor expense categorization accuracy
- Refine category definitions for better AI accuracy
- Review bank transaction reconciliation suggestions

**Team capability building**
- Advanced training on multi-entity consolidation
- Revenue recognition workflows
- Custom API integrations for third-party systems

## Post-cutover system maintenance

**Weeks 1-4 post-go-live (Stabilization)**
- Finance Admin actively monitoring
- Daily GL reconciliation
- Weekly meeting to discuss issues and learnings
- Defer non-critical enhancements

**Weeks 4-12 post-go-live (Optimization)**
- Move to normal monitoring cadence
- Implement efficiency improvements
- Train new team members
- Start building advanced features

**Months 3+ (Sustaining)**
- Move to standard operational mode
- Periodic system reviews and updates
- Continuous staff training
- Decommission legacy systems (after 90+ day archive period)

## Success metrics

Track these metrics post-go-live to measure success:

| Metric | Target | Measurement |
| --- | --- | --- |
| Invoices processed daily | All > 0 days | Day count to process new invoice |
| Bills paid on time | 95%+ | Percentage paid before due date |
| Expense approval SLA | 24-48 hours | Average time from submission to approval |
| GL reconciliation completion | Daily | Days to achieve clean GL trial balance |
| Bank reconciliation | Daily/weekly | Days to complete reconciliation |
| Approval bottlenecks | < 1 per month | Escalations blocked by missing approvals |
| System uptime | 99.5%+ | Monitor dashboard availability |

## Get help during go-live

Light provides support during go-live:
- **Go-live support line:** Available 24/7 during your go-live week
- **Slack support channel:** Real-time assistance in your workspace
- **Implementation specialist:** Dedicated support lead for your organization
- **Documentation and video:** Extensive resources for your team

## Next steps

After successful go-live:
- [Creating and sending invoices](#)
- [Processing bills and payments](#)
- [Submitting and approving expenses](#)
- [Bank reconciliation](#)
- [Financial reporting](#)

## Related articles

- [Quick-start checklist](#)
- [Setting up your organization](#)
- [Adding team members and roles](#)
- [Connecting your first bank account](#)
