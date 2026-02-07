# Data Migration from QuickBooks

QuickBooks is widely used accounting software. If you're migrating from QuickBooks (Online or Desktop) to Light, this guide covers the migration process including data export, transformation, import, and validation.

[Open in Light →](https://app.light.inc/settings/integrations)

## Migration overview

Migrating from QuickBooks involves:

1. **Prepare**: Plan migration timeline and scope
2. **Export**: Export QuickBooks data (accounts, customers, transactions)
3. **Transform**: Convert QuickBooks format to Light format
4. **Import**: Import transformed data to Light
5. **Validate**: Verify migrated data accuracy
6. **Cutover**: Switch to Light as primary system
7. **Archive**: Maintain QuickBooks for audit trail

The process typically takes 3-6 weeks depending on data volume and complexity.

## What transfers from QuickBooks

Light can import from QuickBooks:

- **Chart of accounts**: GL accounts, structure, and balances
- **Customers**: Names, addresses, contact info, payment terms, credit limits
- **Vendors**: Names, addresses, contact info, payment terms
- **Invoices**: Outstanding AR invoices (unmatched payments recommended)
- **Bills**: Outstanding AP bills (unpaid)
- **Payments**: Customer payments and vendor payments (optional)
- **Journal entries**: Adjusting entries as needed
- **Fixed assets**: Asset register with cost, accumulated depreciation
- **Budgets**: Budget data (if using QuickBooks budgeting)
- **Classes/Cost centers**: For allocation to departments

What typically doesn't transfer:

- Historical transactions > 1-2 years (migrated via GL opening balances)
- Closed invoices/bills (migrated to GL totals)
- QuickBooks reports (recreate in Light)
- Time tracking data (if not integrated with GL)

## Pre-migration preparation

Before starting migration:

1. **Close prior year**: Ensure all prior-year transactions are finalized
2. **Reconcile accounts**: Complete all bank reconciliations
3. **Validate GL**: Trial balance must balance
4. **Cleanup data**: Remove duplicate customers/vendors, inactive records
5. **Document**: Note QuickBooks-specific settings that need rebuilding
6. **Decide cutover date**: Plan to migrate at month-end (preferred)
7. **Notify users**: Alert team of upcoming migration and training

Proper prep prevents post-migration issues.

## Exporting from QuickBooks Online

If using QuickBooks Online:

1. **Chart of Accounts**: Reports → Account List → Export to Excel
2. **Customer list**: Customers → Export to Excel
3. **Vendor list**: Vendors → Export to Excel
4. **Invoices**: Reports → Sales → Open Invoice Report → Export
5. **Bills**: Reports → Expenses → Unpaid Bills Report → Export
6. **Trial Balance**: Reports → Accounting → Trial Balance → Export (as of cutover date)
7. **Fixed Asset list**: If using QB fixed assets, export asset register

Store all exports safely.

## Exporting from QuickBooks Desktop

If using QuickBooks Desktop:

1. **Chart of Accounts**: Lists → Chart of Accounts → Export
2. **Customer list**: Lists → Customer:Job List → Export
3. **Vendor list**: Lists → Vendor List → Export
4. **Invoices**: Reports → Sales → Customer Invoices → Export
5. **Bills**: Reports → Purchases → Bill Reports → Export
6. **Trial Balance**: Reports → Company & Financial → Trial Balance → Export
7. **Year-End Backup**: File → Backup Company → (stores entire company)

QB Desktop exports to Excel or IIF (QuickBooks Interchange Format).

## QuickBooks-to-Light account mapping

QuickBooks uses account types (Asset, Liability, Income, Expense, etc.). Map to Light:

**Example mapping**:

| QB Account Type | QB Account | Light Code | Light Account Name |
|--|--|--|--|
| Bank | Checking Account | 1010 | Bank Checking |
| Asset | Accounts Receivable | 1200 | Accounts Receivable |
| Liability | Accounts Payable | 2010 | Accounts Payable |
| Income | Product Sales | 4100 | Product Revenue |
| Expense | Rent Expense | 6100 | Rent Expense |

Create mapping for all accounts before transformation.

## Data transformation

Transform QuickBooks data to Light format:

1. **Accounts**: Convert QB account types and names to Light account codes and structure
2. **Customers**: Extract QB customer master (name, address, contact, terms) into Light format
3. **Vendors**: Extract QB vendor master into Light format
4. **Invoices**: Transform QB invoices to Light format:
   - Map QB account to Light account
   - Preserve line item detail
   - Include tax information
5. **Bills**: Transform QB bills similarly
6. **Opening balances**: Create GL balances for accounts as of cutover date

Use Excel, Python, or specialized QB migration tools to automate transformation.

> Tip: Don't migrate detailed historical transactions. Instead:
> - Keep QB for historical reference
> - In Light, record opening GL balances as of cutover date
> - Only migrate current-period AR/AP that's still outstanding

## Creating transformation templates

Build Excel templates for data transformation:

**Template 1: Account Mapping**

| QB Account | QB Type | Light Code | Light Name | Opening Balance |
|--|--|--|--|--|
| Checking | Bank | 1010 | Cash | 50000 |
| AR | AR | 1200 | AR | 25000 |
| AP | AP | 2010 | AP | 10000 |

**Template 2: Customer Import**

| QB Customer ID | Name | Contact | Email | Address | Terms | Credit Limit |
|--|--|--|--|--|--|--|
| ACME-001 | Acme Corp | John | john@acme.com | 123 Main | Net 30 | 10000 |

**Template 3: Invoice Import**

| QB Invoice # | Customer ID | Amount | Tax | Due Date | Description |
|--|--|--|--|--|--|
| INV-1001 | ACME-001 | 10000 | 2000 | 3/7/2025 | Services |

Use these as transformation guides.

## Handling QB classes and cost centers

QuickBooks uses Classes for allocation:

1. Export QB Class list
2. In Light, create corresponding cost centers
3. When importing invoices/bills, assign to appropriate cost center
4. Light then allocates expenses to departments

This preserves allocation structure.

## QBO to Light account reconciliation

If you exported from QB Online, reconcile accounts before import:

1. Get QB final trial balance (as of cutover date)
2. Sum light accounts in transformation
3. Verify totals match (assets = liabilities + equity)
4. Fix discrepancies before importing

This ensures GL balances are correct.

## Importing to Light

Once transformed, import data:

1. Follow Light's data import process (**Settings (gear icon) > Import Data**)
2. Import in order:
   - Chart of accounts first
   - Customers
   - Vendors
   - Opening balances (GL)
   - Outstanding invoices (AR)
   - Outstanding bills (AP)
   - Fixed assets (if applicable)
   - Budgets (if applicable)
3. Validate each import before proceeding
4. Review Light's import preview carefully

Light validates data during import.

## Validation after import

Thoroughly validate migrated data:

1. **Trial balance**: Compare Light GL to QB GL (should match as of cutover date)
2. **Account balances**: Spot-check major accounts
3. **AR aging**: Compare Light AR aging report to QB AR aging
4. **AP aging**: Compare Light AP aging report to QB AP aging
5. **Customer counts**: Verify customer list counts match
6. **Vendor counts**: Verify vendor list counts match
7. **Invoice detail**: Sample check 10-20 invoices for accuracy

Discrepancies indicate transformation errors to correct.

## Handling QB-specific features

Some QB features may need rebuilding:

**QB Classes**: Replicate using Light cost centers or custom properties.

**QB sub-accounts**: Maintain hierarchical GL structure in Light.

**QB custom fields**: Use Light custom properties for similar functionality.

**QB automatic calculations**: Rebuild in Light where needed (e.g., depreciation via releases).

**QB attachments**: Upload supporting documents to Light invoices/bills.

**QB workflows**: May not transfer; recreate in Light if needed.

## Parallel running (optional)

Run both systems in parallel for confidence:

1. Continue posting to QB for 1-2 weeks after Light go-live
2. Post same transactions to Light
3. Compare results between systems
4. Once confident Light is accurate, archive QB
5. Switch fully to Light

This adds 2 weeks but reduces risk.

## Cutover execution

Execute the migration:

1. **Final QB close**: Complete final month-end in QB
2. **Final exports**: Export GL, AR, AP, invoices, bills
3. **Final validation**: Import to Light and validate
4. **Announce cutover**: Notify team Light is now primary
5. **Disable QB posting**: Stop posting to QB (archive for reference)
6. **Begin Light posting**: All new transactions in Light

Schedule cutover for month-end to align with close cycle.

## Post-cutover reconciliation

After cutover, reconcile:

1. **Bank reconciliation**: Match cash accounts to bank statements
2. **AR reconciliation**: Verify AR subsidiary ledger to GL
3. **AP reconciliation**: Verify AP subsidiary ledger to GL
4. **Customer verification**: Contact sample of customers to verify balances
5. **Vendor verification**: Contact sample of vendors to verify balances

This confirms migration accuracy.

## Maintaining QB archive

Keep QB available for reference:

1. Export final QB data to Excel and PDFs
2. Store QB backup file securely (encrypted, off-site)
3. Keep QB login available if needed
4. Document QB export date and purpose
5. Maintain for 7+ years per retention policy

This preserves historical data for audit.

## Team training

Train on Light before and after cutover:

1. **Before cutover**: Train on Light's interface, invoice entry, reporting
2. **During cutover**: Support for transition week
3. **After cutover**: Ongoing training on Light-specific features

Good training ensures smooth adoption.

## Common QB migration challenges

**Multi-currency**: QB and Light handle FX differently. Test conversions.

**Inventory**: If using QB inventory, evaluate Light's approach (Light focuses on P&L, not inventory tracking).

**Payroll integration**: QB Payroll may not transfer. Redirect to Finch or other payroll integrations.

**Loan tracking**: QB's loan tracking may require custom GL structure in Light.

**Budgets**: QB budgets don't directly transfer. Recreate in Light if needed.

## Related articles

- [Data import and migration tools](11-13-data-import.md)
- [Data migration from E-Conomic](11-14-migration-economic.md)
- [Cutover fundamentals and execution](11-16-cutover.md)
- [Audit-ready record keeping](../09-revenue-compliance/9-9-audit-ready-records.md)
