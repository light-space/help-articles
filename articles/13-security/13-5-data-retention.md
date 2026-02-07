# Data Retention and Deletion

This article explains Light's data retention policies, how long data is kept, and your rights to delete or export your data.

[Open in Light →](https://app.light.inc/settings)

## Data Retention Overview

Light retains your financial data for as long as necessary to serve your account. We also maintain backups and audit logs to meet regulatory requirements and ensure data recovery capabilities.

## Retention Periods by Data Type

### Active Financial Data

**Retention Period**: As long as your account is active, plus 7 years after account termination

Financial data includes:

- Transactions and journal entries
- Invoices and bills
- Bank reconciliations
- Payments and receipts
- Reports and dashboards
- Customer and vendor records

This 7-year retention supports:

- Regulatory compliance (IRS, SEC, and other auditors require 7-year records)
- Tax audits and inquiries
- Legal holds and litigation

### User and Access Logs

**Retention Period**: 7 years minimum

Light retains detailed logs of:

- User logins and logouts
- Data access (who viewed what and when)
- Changes to financial records (who changed what)
- Administrative actions
- API requests and integrations
- Failed security checks

These logs support audit trails and compliance requirements.

### Backup Data

**Retention Period**: 30+ days

Backups are:

- Maintained for disaster recovery
- Encrypted and stored geographically distributed
- Tested regularly to ensure recoverability
- Eventually purged after 30+ days

If you need to recover data from a specific point in time, Light can often restore data from backups within 30 days.

### Deleted Data

**Retention Period**: Data removed per your deletion requests follows these rules:

- **Immediate Removal**: Data is marked for deletion immediately
- **Backup Cycle**: Data remains in backups until backup is rotated out
- **Crypto Erasure**: Deletion is cryptographic (encryption keys are removed)
- **Complete Removal**: After backup retention expires, data is permanently unrecoverable

## Your Data Rights

Light respects your ownership of your data. You have the right to:

### 1. Access Your Data

You can export or view your data at any time.

### 2. Correct Your Data

You can update and correct your financial records. Light maintains a change history so corrections are auditable.

### 3. Delete Your Data

You can request deletion of your data through Light's data deletion procedures (see below).

### 4. Download Your Data

You can download a complete export of your company's data at any time.

### 5. Port Your Data

If you switch from Light, you can export all data in standard formats (CSV, PDF, JSON) for use in another system.

## Data Deletion Procedures

### Deleting Individual Records

To delete individual transactions, documents, or records:

1. Navigate to the record you want to delete
2. Click **Delete** or the delete icon
3. Confirm the deletion (reversals may be required instead of deletion)
4. The record is marked for deletion
5. Data is removed from backups as they expire

### Deleting User Data

To delete a user's personal data (not company data):

1. Go to **Admin** > **Users**
2. Select the user
3. Click **Delete User**
4. Confirm the action
5. User account is deactivated and personal data is flagged for deletion

Note: User's financial activity records remain for audit compliance.

### Complete Account Deletion

To delete an entire company's account and data:

1. Contact your Light account manager or support
2. Verify authorization to request deletion
3. Submit a formal deletion request
4. Light provides a 30-day notice period (for compliance with regulations)
5. After 30 days, all data is marked for deletion
6. Data is permanently removed from backups as retention periods expire

> Good to know: Deletion is final and cannot be undone. Light recommends exporting a data backup before requesting account deletion.

### GDPR Right to Erasure

Under GDPR, you have the right to erasure (the "right to be forgotten"):

1. Identify personal data that needs to be deleted
2. Submit erasure request in **Settings** > **Privacy**
3. Specify reason for deletion
4. Light processes erasure within 30 days
5. Personal data is deleted while retaining necessary financial records

Note: Some financial data may need to be retained for legal or tax compliance, even with erasure requests.

## Data Export

### Exporting Your Company Data

To export all company data:

1. Go to **Admin** > **Data Export**
2. Click **Request Export**
3. Select what to include (transactions, invoices, customers, etc.)
4. Choose format (CSV, Excel, JSON, or PDF)
5. Light prepares your export (typically within 24 hours)
6. Download your data
7. Export is available for 7 days, then deleted

### Exporting Specific Reports

To export individual reports:

1. Run the report you want to export
2. Click **Export** in the report header
3. Choose format (Excel, PDF, CSV)
4. Download the file
5. Save it to your computer

### Requesting Custom Exports

For complex exports not available in Light:

1. Contact Light support with your request
2. Describe the data you need and desired format
3. Light prepares a custom export
4. Usually completed within 5 business days
5. Download your export file

## Data Portability

Light supports data portability, allowing you to move your data to another system:

### Standard Formats

Light exports data in widely-supported formats:

- **CSV**: For spreadsheets and databases
- **Excel**: For analysis and modeling
- **JSON**: For system integration
- **PDF**: For documentation and archival

### Mapping Tools

Light provides documentation:

- Field mappings explain how Light data maps to standard formats
- Transformation guides help adapt data for other systems
- Integration templates support moving to common platforms

### Data Migration Support

For complex migrations, Light offers:

- **Consultation**: Help planning your data migration
- **Custom Exports**: Specialized exports for specific needs
- **Validation**: Ensuring data integrity in destination system
- **Technical Support**: Assistance during the migration process

Contact your account team for migration support.

## Data Retention Compliance

### Regulatory Requirements

Light retains data to comply with:

- **IRS Requirements**: 7-year retention of financial records
- **Tax Regulations**: State and local tax requirements
- **Audit Requirements**: SEC, SOX, and other regulatory audits
- **Legal Holds**: Court orders and litigation

### Retention Policies by Region

Light adjusts retention based on regional requirements:

- **United States**: 7 years for tax compliance
- **European Union**: GDPR rights to erasure considered; 7-year audit retention
- **United Kingdom**: UK tax and audit requirements (6 years typically)
- **Australia**: Australian tax requirements (5-7 years)

> Tip: If you're subject to specific retention requirements (e.g., public company audits), inform Light so retention can be configured appropriately.

## Accessing Deleted Data

### Recovery from Backups

If you accidentally delete data:

1. Contact Light support immediately
2. Request data recovery from backup
3. Specify the timeframe and data needed
4. Light can restore from backups within 30 days
5. Restored data is placed back in your account

Recovery is typically available for 30 days; older backups may not be available.

### Audit Trail

Even after deletion, the audit trail shows:

- What data was deleted
- Who deleted it
- When it was deleted
- Why it was deleted (if documented)

This provides accountability and traceability.

## Third-Party Data Access

Light shares your data with sub-processors and integrations:

### Sub-Processors

Light uses vendors for essential services:

- Cloud infrastructure providers
- Payment processors
- Bank integrations
- Analytics services

All sub-processors are:

- Listed in Light's Data Processing Agreement
- Bound by confidentiality and security obligations
- Regularly audited for compliance

### Integrations

When you enable integrations:

- Third-party services may access specific data
- You control what data is shared
- Permissions can be revoked at any time
- Data shared is governed by the third-party's privacy policy

## Related Articles

- Light's security architecture
- Data encryption and storage
- Compliance certifications
