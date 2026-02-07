# Go-live readiness

This article outlines the minimum viable setup for going live with Light and helps you prepare for a successful transition from your legacy financial system.

[Open in Light →](https://app.light.inc/dashboard)

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

## Data migration requirements

If you're transitioning from a legacy system (NetSuite, SAP, Xero, QuickBooks, etc.):

### Chart of accounts
- Export your complete chart of accounts from the legacy system
- Import into Light or manually recreate
- Verify account codes and balances match
- Test GL posting from invoices, bills, and expenses

### Customer and vendor data
- Extract customer master file from legacy system
- Import into Light with account history
- Set credit limits and payment terms
- Verify customer GL mapping for revenue recognition

- Extract vendor master file with payment terms
- Import with vendor reference numbers and tax IDs
- Configure payment methods (bank transfer, check, card)
- Set up AP aging reports for transition period

### Open transactions
- Identify all open invoices, bills, and purchase orders
- Export outstanding AR aging report
- Export outstanding AP aging report
- Plan how to transition these to Light:
  - Create as new transactions in Light, or
  - Import as batch in native format, or
  - Manually recreate high-priority items

- Decide on cutover date (e.g., "Go live with Light on March 1st")
- All transactions before cutover date stay in legacy system for historical reference
- New transactions post to Light starting on cutover date

### Bank account history
- Determine how much historical transaction data to import (typically last 90 days)
- Export bank statements in CSV format if automated feed won't provide history
- Plan to import via bulk CSV or Plaid sync

### GL opening balances
- Run trial balance from legacy system as of cutover date
- Verify all GL accounts are created in Light
- Post opening balances via:
  - Manual journal entry for each account, or
  - Single "Opening balances" journal entry, or
  - Import via CSV bulk journal entry tool

> **Good to know:** Light provides CSV import templates for most entities. Ask your implementation specialist for templates that match your legacy system's export format.

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
