# Audit-Ready Record Keeping

Audit readiness is the practice of maintaining financial records in a format that external auditors and tax authorities can easily review and verify. Light is designed with audit requirements at its core, providing complete documentation, audit trails, and exportable reports that satisfy regulatory requirements across jurisdictions.

[Open in Light →](https://app.light.inc/journal-entries)

## Audit requirements overview

External auditors review your financial records to provide an independent opinion on the fairness of your financial statements. Tax authorities review records to verify you've complied with tax laws. Audit readiness requires:

- **Complete ledger records**: All transactions recorded with full supporting detail
- **Audit trail**: History of who created each record, when, and any modifications
- **Source documentation**: Original invoices, receipts, and supporting documents
- **Consistent policies**: Documented accounting policies applied uniformly
- **Timely records**: Financial records prepared during the reporting period, not afterwards
- **Control evidence**: Documentation of internal controls and review procedures

Light maintains all these elements automatically.

## Ledger completeness and accuracy

Light records all transactions in the general ledger with complete detail:

- **Document origination**: AP, AR, JE, FX, CN, CT, BP, YC, DE, CC transactions recorded with full supporting information
- **Dual-entry posting**: Every transaction posts to at least two accounts (general accounting principle)
- **Amounts in multiple currencies**: Transaction, local, and group currency amounts preserved
- **Account mappings**: Clear traceability from transaction to general ledger account
- **Balance verification**: Trial balance always balances (assets = liabilities + equity)

Your audit team can access the complete ledger with drill-down capability from summary financial statements to individual transactions.

> Good to know: Light maintains a transaction-immutable ledger. Once posted, transactions cannot be deleted (only reversed with an offsetting entry), providing strong audit evidence.

## Audit trail functionality

Light logs all financial activities with full audit trail:

**Posted transactions** show:
- Who created the transaction (user ID)
- When created (timestamp)
- Original amounts and accounts
- Post date and status

**Modified transactions** show:
- Original posting details
- Each modification (edit date, user, changes made)
- Reason for modification (if required)
- Final current state

**Approvals and authorizations** show:
- Who approved each transaction
- Date/time of approval
- Evidence of segregation of duties (creator ≠ approver)

Navigate to any transaction and view **Audit Log** to see complete history.

## Document supporting evidence

Attach supporting documents to transactions in Light:

1. Create an AP, AR, or JE document
2. Click **Attachments**
3. Upload original invoices, receipts, contracts, or other supporting documents
4. Light stores documents with full metadata:
   - Uploaded by (user ID)
   - Upload date/time
   - File name and size
   - Content hash (for verification)
5. Retrieved documents display as read-only (preventing tampering)

Your audit team can access original documents directly from Light without hunting through email or file systems.

## Inter-company transaction documentation

Multi-entity organizations with inter-company transactions require clear documentation:

1. Create inter-company transactions with clear labeling
2. Link the original transaction to its corresponding inter-company mirror entry
3. Document the business purpose and pricing methodology
4. Maintain supporting inter-company agreements

Light reports inter-company transactions separately and provides elimination documentation during consolidation.

## Bank reconciliation documentation

Reconcile bank accounts regularly:

1. Navigate to **Accounting > Bank reconciliation** (in Platform section)
2. Upload your bank statement
3. Match transactions to bank statement lines
4. Light documents:
   - Date of reconciliation
   - Who performed the reconciliation
   - Exceptions identified and resolved
   - Timing differences explained
5. Sign off the reconciliation
6. Archive the signed reconciliation

Maintain monthly reconciliations. Your audit team will request these.

## Tax transaction documentation

Light maintains specific documentation for tax compliance:

**VAT/Sales Tax**:
- Tax authority registrations and identification numbers
- Tax returns filed (with filing confirmations)
- Tax payment records
- Exemption certificates
- Tax calculation methodologies documented

**Income Tax**:
- Tax identification numbers (EINs, company registrations)
- Correspondence with tax authorities
- Tax positions taken and supporting documentation
- Transfer pricing documentation (if applicable)

Navigate to **Planning & Reports > Reports** to access all tax-related records.

## Accounting policy documentation

Document your accounting policies:

1. Navigate to **Settings** and document your policies
2. Document your policies for each area:
   - Revenue recognition (IFRS 15 vs. ASC 606 compliance)
   - Depreciation methods and useful lives
   - Inventory valuation method
   - Foreign exchange treatment
   - Consolidation and elimination methodologies
   - Deferred tax policies
3. Record effective dates
4. Document any changes and reasons for changes
5. Archive prior-period policies

Provide your auditor with this documentation early in the audit. Consistency is key.

> Tip: Create a formal "Accounting Policies and Procedures Manual" in Light detailing all significant accounting judgments and estimates.

## Spreadsheet-free financial processes

Maintain records in Light rather than spreadsheets:

- Excel variance analysis calculations are hard to audit
- Manual adjustments lack audit trail
- Version control in spreadsheets is unreliable
- Consolidation spreadsheets are prone to formula errors

Use Light's reporting features for all analysis. Export to Excel for presentation, but maintain calculations and supporting detail in Light's audit-trail system.

> Good to know: Your auditors expect to audit transactional detail in Light, not formulas in spreadsheets.

## Month-end close documentation

Prepare comprehensive month-end documentation:

1. Close out GL accounts for the month
2. Document accruals, prepayments, and deferred revenue
3. Prepare bank reconciliation
4. Calculate and document FX impacts
5. Review and document significant transactions
6. Create a month-end close summary
7. Archive in Light

This documentation provides auditors with clear evidence of your close process and financial controls.

## Year-end audit preparation

As year-end approaches, prepare audit documentation:

1. **Complete trial balance**: Ensure all accounts are reconciled
2. **Turnover** (first and last transaction dates per account): Demonstrate account activity
3. **Account detail schedules**: List all transactions per account for materiality
4. **Consolidation working papers**: Inter-company transactions and eliminations
5. **Account reconciliations**: Match GL to subledgers (AP aging, AR aging, fixed asset register)
6. **Review of estimates**: Document judgments on accruals, allowances, reserves
7. **Subsequent events**: Document and disclose events after year-end but before audit

Light's reporting suite can generate all these schedules automatically.

## Multi-jurisdiction compliance documentation

For multinational organizations:

- Document tax positions taken in each jurisdiction
- Maintain local entity trial balances and balance sheets
- Preserve local regulatory reporting documentation
- Keep evidence of consolidation and elimination procedures
- Archive local statutory audit reports

Light's multi-entity capabilities maintain separate audit trails per entity and consolidated records.

## Retention and archiving

Maintain financial records according to legal requirements:

- US: 7 years (IRS statute of limitations)
- UK: 6 years (HMRC requirement)
- EU: Varies by country but typically 6-10 years

Light maintains immutable records in a secure archive. Periodically export and archive historical records per your organization's retention policy.

> Good to know: Document your retention policy and ensure IT systems backup data according to your policy. Your auditor will ask about record retention practices.

## Audit readiness checklist

Before your external audit:

- All transactions are recorded in Light with complete detail
- Supporting documents are attached where required
- Month-end and year-end close procedures are documented
- Bank and inter-company reconciliations are complete
- All estimates (allowances, accruals, deferred items) are documented
- Accounting policies are current and applied consistently
- Prior-year audit findings have been addressed
- Management representation letter can be prepared

Light enables all these requirements.

## Related articles

- [Tax compliance — HMRC (UK) and VAT](9-7-hmrc-vat.md)
- [Tax compliance — AvaTax (US)](9-8-avatax-us.md)
- [Balance sheet](../10-reporting/10-2-balance-sheet.md)
- [Trial balance](../10-reporting/10-5-trial-balance.md)
