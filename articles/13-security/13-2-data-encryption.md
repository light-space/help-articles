# Data Encryption and Storage

This article explains how Light encrypts and stores your financial data to keep it secure and private.

[Open in Light →](https://app.light.inc/settings)

## Encryption Overview

Light protects all your financial data through encryption. Every piece of information—from bank transactions to invoices to custom configurations—is encrypted using industry-standard algorithms.

## Encryption at Rest

### Database Encryption

Light encrypts all data stored in its databases:

- **Algorithm**: AES-256 encryption, the same standard used by the US government for classified information
- **Scope**: All financial records, company data, user information, and audit logs
- **Key Management**: Encryption keys are stored separately from encrypted data in a dedicated key management service
- **Automatic**: Encryption happens automatically; you don't need to configure or manage it

All data in Light's databases is unreadable without the correct encryption key.

### Storage Encryption

Beyond database encryption, Light adds additional protection:

- **File Storage**: Documents (invoices, receipts, etc.) uploaded to Light are encrypted before storage
- **Backup Encryption**: Database and file backups are encrypted immediately upon creation
- **Archive Encryption**: Older data moved to long-term archives remains encrypted

### Backup Security

Light maintains encrypted backups for disaster recovery:

- **Frequency**: Full backups daily, incremental backups hourly
- **Retention**: Backups are retained for at least 30 days, and recovery-ready backups for 7 years
- **Encryption**: All backups are encrypted with AES-256
- **Testing**: Recovery procedures are tested regularly to ensure backups are reliable
- **Location**: Backups are stored across multiple availability zones within the same region for redundancy

> Good to know: Even if someone gained access to Light's backup systems, the encrypted data would be useless without the encryption keys.

## Encryption in Transit

### HTTPS/TLS Encryption

All communication between your browser or mobile app and Light uses HTTPS:

- **Protocol**: TLS 1.2 or higher (the same encryption used by banks)
- **Certificates**: Valid SSL/TLS certificates signed by trusted certificate authorities
- **Ciphers**: Only strong encryption ciphers are enabled; weak ones are disabled
- **Perfect Forward Secrecy**: Even if an encryption key is compromised in the future, historical communication remains secure

### API Encryption

Light's APIs use encrypted communication:

- **Protocol**: HTTPS/TLS for all API requests
- **Authentication**: API keys or OAuth 2.0 tokens, always transmitted over TLS
- **Validation**: Requests are validated to prevent tampering
- **Logging**: API requests are logged with sensitive headers and query parameters redacted; credentials are never written to logs

### Integration Security

When Light communicates with external services (banks, payment processors, CRM systems):

- **End-to-End**: Data is encrypted from Light to the external service
- **Validation**: Outbound connections use TLS with full certificate validation, and inbound webhooks are verified with signatures before processing
- **Audit Trail**: All integration communication is logged and audited

## Data in Use

### Application-Level Encryption

Even while data is being processed, sensitive information remains encrypted:

- **Sensitive Fields**: Highly sensitive data (API keys, credentials, SSN numbers if any) are encrypted at the application level
- **Processing**: The application only decrypts data when necessary to perform operations
- **No Logging**: Sensitive data is never logged in plaintext

## Encryption Key Management

### Key Rotation

Light rotates encryption keys regularly:

- **Frequency**: Master keys are rotated annually
- **New Keys**: Keys used for new data are different from those used for older data
- **Seamless**: Keys can be rotated without downtime and without affecting your access

### Key Access Control

Encryption keys are protected:

- **Limited Access**: Only the encryption service has access to keys, not even Light engineers
- **Separation**: Keys are stored separately from encrypted data
- **Monitoring**: All key access is logged and monitored

### Backup Key Protection

Keys used for backup recovery:

- **Separate Protection**: Backup encryption keys are kept in separate secure storage
- **Tested**: Recovery procedures are regularly tested to ensure keys work when needed
- **Long-Term**: Keys are maintained for the duration of backup retention (7+ years)

## Regional Data Storage

Light stores your data in the European Union:

- **Data Location**: All customer data is hosted on AWS infrastructure in the EU (Ireland, eu-west-1)
- **Replication**: Backups and failover copies are kept across multiple availability zones within the region for disaster recovery
- **Compliance**: EU data storage supports GDPR requirements

## Field-Level Encryption

Certain sensitive fields receive additional encryption layers:

- **API Keys & Tokens**: OAuth tokens and API credentials for third-party integrations (such as Gmail, Salesforce, HubSpot, and HR or tax providers) are encrypted at the application level before storage
- **Card Security Data**: Card 3-D Secure credentials are encrypted with versioned keys, so keys can be rotated without downtime while older data stays readable

## Data Disposal

When you delete data or accounts, Light securely disposes of it:

- **Immediate Deletion**: Deletion requests are processed immediately
- **Cascade Deletion**: Related data is also deleted
- **Crypto Erasure**: Data is removed from backups as they expire and are replaced
- **Verification**: Deleted data cannot be recovered from the system

> Tip: Light maintains an audit log of all deletions for 7 years. This helps verify that data has been properly disposed of.

## Transparency

Light is transparent about encryption:

- **Security Audit Reports**: Third-party SOC 1 and SOC 2 audits verify encryption implementation
- **Documentation**: Full technical documentation of encryption methods is available under NDA
- **Testing**: Regular penetration testing verifies encryption cannot be bypassed

## Related Articles

- Light's security architecture
- Access controls and SSO
- Compliance certifications
- Data retention and deletion
