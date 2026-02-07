# Data Migration from E-Conomic

E-Conomic is a cloud accounting system used primarily in Nordic countries. If you're migrating from E-Conomic to Light, this guide walks through the migration process, covering data export, transformation, import, and cutover validation.

[Open in Light →](https://app.light.inc/settings/integrations)

## Migration overview

Migrating from E-Conomic involves:

1. **Prepare**: Understand what data transfers to Light
2. **Export**: Export data from E-Conomic
3. **Transform**: Convert E-Conomic format to Light format
4. **Import**: Import transformed data to Light
5. **Validate**: Verify migrated data is accurate
6. **Cutover**: Switch to Light as primary system

The process typically takes 2-4 weeks depending on data volume and complexity.

## What transfers from E-Conomic

Light can import from E-Conomic:

- **Chart of accounts**: GL accounts and structure
- **Customers**: Contact information, payment terms
- **Suppliers**: Vendor information, payment terms
- **Invoices**: Outstanding AR invoices (unmatched payments)
- **Bills**: Outstanding AP bills (unpaid)
- **Payments**: Customer payments and supplier payments (if needed for audit trail)
- **Fixed assets**: Asset register with depreciation
- **Budgets**: Budget data (if applicable)

What typically doesn't transfer:

- Historical transactions >1 year old (migrated via opening balances instead)
- Closed invoices/bills (migrated via GL balances)
- Internal notes (not easily portable)

## Pre-migration steps

Before exporting from E-Conomic:

1. **Close prior year**: Close all prior-year transactions in E-Conomic
2. **Reconcile**: Complete all bank reconciliations
3. **Validate GL**: Ensure trial balance balances
4. **Document processes**: Note E-Conomic-specific processes that will change in Light
5. **Set cutover date**: Decide when to switch to Light (typically month-end)
6. **Prepare team**: Train team on Light before cutover

This ensures clean migration.

## Exporting from E-Conomic

Export all necessary data:

1. Log into E-Conomic
2. Navigate to **Settings (gear icon) > Data > Export**
3. Export each module:
   - **Chart of Accounts**: General → Account (export structure, names, balances as of cutover date)
   - **Customers**: CRM → Customers (names, addresses, terms, contact info)
   - **Suppliers**: Suppliers (names, addresses, terms, payment methods)
   - **Invoices**: Sales → Invoices (outstanding AR only)
   - **Bills**: Purchases → Bills (outstanding AP only)
   - **Fixed Assets**: Assets (asset register with cost, depreciation, book value)
4. Export as CSV or Excel format
5. Store exports safely

## Preparing E-Conomic data for Light

E-Conomic and Light have different data structures. Transform E-Conomic exports:

**Chart of Accounts mapping**:

E-Conomic uses 4-level account structure (Main Group, Main Type, Sub Type, Group). Light uses flat account codes.

- E-Conomic: 4.5000.1 (liability, payables, trade payables, individual)
- Light: 2010 (Accounts Payable)

Create mapping between E-Conomic and Light account structure.

**Customer mapping**:

E-Conomic exports customer data in its format. Light needs:
- Customer ID, Name, Contact, Email, Address, Terms

Transform using Excel or Python script to match Light requirements.

**Invoice and bill migration**:

E-Conomic invoices have line item detail. Transform to:
- Document number, customer/vendor, date, total amount, tax
- Line items with account coding and amounts

## Creating mapping templates

Create Excel templates for transformation:

**Template 1: Account Mapping**
| E-Conomic Account | Light Account Code | Light Account Name | Transfer? |
|--|--|--|--|
| 4.5000.1 | 2010 | Accounts Payable | Yes |

**Template 2: Customer Mapping**
| E-Conomic ID | Customer Name | Contact | Email | Light Terms |
|--|--|--|--|--|
| ACME-DK | Acme Corp | John | john@acme.com | Net 30 |

**Template 3: Invoice Mapping**
| E-Conomic # | Customer | Amount | Tax | Light Account |
|--|--|--|--|--|
| INV-100 | Acme | 10000 | 2000 | 1200 |

Use these templates to guide transformation.

## Data transformation process

Transform E-Conomic data to Light format:

1. **Accounts**: Map E-Conomic accounts to Light account codes based on nature (asset, liability, etc.)
2. **Customers**: Create Light customer records from E-Conomic customer exports
3. **Suppliers**: Create Light vendor records
4. **Invoices**: Transform E-Conomic invoice format to Light format
5. **Bills**: Transform E-Conomic bill format to Light format
6. **Opening balances**: Create JE for opening balances as of cutover date

> Tip: Use Python, Excel, or specialized migration tools to automate transformation. Manual transformation is error-prone for large datasets.

## Importing to Light

Once transformed, import to Light:

1. Follow Light's data import process (**Settings (gear icon) > Import Data**)
2. Import in this order:
   - Chart of accounts (so accounts exist for other data)
   - Customers and vendors
   - Opening balances (GL accounts initialized)
   - Outstanding invoices (AR)
   - Outstanding bills (AP)
   - Fixed assets (if using Light asset tracking)
   - Budgets (if applicable)
3. Validate each import before proceeding to next
4. Use Light's import preview to verify data looks correct

Light guides you through each import type.

## Validation after import

After importing, validate data is accurate:

1. **Trial balance**: Compare Light GL trial balance to E-Conomic trial balance (should match)
2. **AR aging**: Compare Light AR aging to E-Conomic AR aging
3. **AP aging**: Compare Light AP aging to E-Conomic AP aging
4. **Account balances**: Spot-check major accounts (cash, AR, AP, equity)
5. **Customer/vendor counts**: Verify number of active customers/vendors matches

Discrepancies indicate transformation errors to fix.

## Parallel running period

Optionally run both systems in parallel for verification:

1. Continue posting to E-Conomic for 1-2 weeks
2. Also post to Light
3. Compare results between systems
4. Once confident Light is accurate, switch over
5. Archive E-Conomic as backup

This reduces cutover risk but requires duplicate data entry.

## Cutover execution

When ready to switch to Light:

1. **Final E-Conomic close**: Close E-Conomic for the cutover month (month-end typical)
2. **Final GL balances**: Export GL as of cutover date from E-Conomic
3. **Final import to Light**: Import final GL balances and any last-minute invoices/bills
4. **Announce cutover**: Notify team Light is now primary system
5. **Disable E-Conomic posting**: Stop posting to E-Conomic (archive only)
6. **Begin Light posting**: All new transactions post to Light

Cutover typically happens on a Friday to allow full week of Light before next close.

## Post-cutover reconciliation

After cutover, reconcile accounts:

1. **Bank reconciliation**: Reconcile cash accounts to bank statements
2. **AR reconciliation**: Reconcile AR subsidiary ledger to GL
3. **AP reconciliation**: Reconcile AP subsidiary ledger to GL
4. **Fixed asset verification**: Verify asset register integrity
5. **Customer contact verification**: Contact customers to verify AR balances

This ensures migration accuracy.

## Handling E-Conomic-specific features

Some E-Conomic features may not transfer directly:

**E-Conomic workflows**: May need to be rebuilt in Light using different tools.

**E-Conomic integrations**: Redirect integrations from E-Conomic to Light.

**E-Conomic custom fields**: Map to Light custom properties.

**E-Conomic approval workflows**: Implement similar workflows in Light.

Document these changes and update processes accordingly.

## Common migration challenges

**Multi-currency**: E-Conomic uses different currency handling than Light. Test FX conversion carefully.

**Custom accounts**: E-Conomic may have accounts not matching standard GL structure. Create corresponding Light accounts.

**Complex tax**: E-Conomic's tax handling may differ. Test VAT calculations in Light.

**Dimensional accounting**: E-Conomic supports dimensions. Use Light cost centers and custom properties to replicate.

## Team training

Train your team on Light before cutover:

1. **Accounting basics**: How transactions work in Light
2. **Invoice processing**: Creating AP and AR invoices
3. **Reconciliation**: Bank and account reconciliation in Light
4. **Reporting**: Generating reports in Light
5. **Month-end close**: Light's close process

Invest in training to ensure smooth adoption.

## Ongoing E-Conomic archive

Keep E-Conomic available for reference:

1. Export final state of all E-Conomic data
2. Archive securely (cloud storage, archive server)
3. Keep login available for password-protected access
4. Maintain for historical reference (audits may require it)
5. Eventually decommission (typically after 7+ years per retention policy)

This preserves historical data if needed.

## Related articles

- [Data import and migration tools](11-13-data-import.md)
- [Data migration from QuickBooks](11-15-migration-quickbooks.md)
- [Cutover fundamentals and execution](11-16-cutover.md)
- [Audit-ready record keeping](../09-revenue-compliance/9-9-audit-ready-records.md)
