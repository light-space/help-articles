# Light's Security Architecture

This article provides an overview of Light's approach to security, explaining the foundational security measures that protect your financial data.

[Open in Light →](https://app.light.inc/settings)

## Security Principles

Light is built on several core security principles:

- **Defense in Depth**: Multiple layers of security so that no single point of failure exposes your data
- **Encryption by Default**: All data is encrypted at rest and in transit
- **Zero Trust Architecture**: Every user and system component must authenticate and authorize access
- **Least Privilege**: Users and services have minimal access needed to perform their functions
- **Continuous Monitoring**: Real-time monitoring and logging of all system activity
- **Regular Testing**: Penetration testing and security audits to identify vulnerabilities before attackers do

## Infrastructure Security

### Cloud Infrastructure

Light runs on secure, isolated cloud infrastructure with:

- **Network Isolation**: Your financial data is in isolated network segments
- **DDoS Protection**: Advanced DDoS mitigation to prevent service disruption
- **Intrusion Detection**: Real-time monitoring for unauthorized access attempts
- **Web Application Firewall**: Protection against common web attacks (injection, XSS, etc.)

### Data Center Security

Light's infrastructure includes:

- **Physical Security**: Access to data centers is restricted and monitored
- **Environmental Controls**: Redundant power, cooling, and climate monitoring
- **Fire Suppression**: Automatic fire detection and suppression systems
- **Backup Systems**: Multiple redundant systems ensure availability

> Good to know: Light's infrastructure is designed for 99.9% uptime with automatic failover to backup systems.

## Data Encryption

### Encryption at Rest

All financial data stored in Light is encrypted using AES-256 encryption:

- Database data is encrypted at the storage layer
- Backups are encrypted before leaving the data center
- Historical data archives are encrypted
- Encryption keys are managed separately from encrypted data

### Encryption in Transit

All data moving to or from Light is encrypted:

- HTTPS/TLS 1.2+ for web connections
- API requests use OAuth 2.0 token authentication
- Data from integrations (bank feeds, payment processors) is encrypted end-to-end
- Internal service communication is encrypted

## Authentication and Access Control

### User Authentication

Light supports multiple authentication methods:

- **Single Sign-On (SSO)** via Auth0 with SAML or OIDC protocols
- **Multi-Factor Authentication (MFA)** for additional security
- **API Keys** for service-to-service authentication
- **OAuth 2.0** for third-party integrations

### Role-Based Access Control

Light implements role-based access control (RBAC):

- **Global Roles**: Admin, Finance Manager, Accountant, Employee, etc.
- **Data-Level Controls**: Fine-grained permissions on entities, departments, and currencies
- **Function-Level Controls**: Permissions on specific operations like approving expenses or posting journal entries

Your administrators configure roles and permissions based on your company's structure and approval workflows.

## Security Monitoring

### Activity Logging

Light logs:

- All user logins and logouts
- Every data access, modification, or deletion
- All financial transactions and entries
- Integration activities and API calls
- System administrative actions

Logs are retained for 7 years and encrypted for protection.

### Real-Time Monitoring

Light monitors for:

- Unusual access patterns (e.g., accessing data at odd hours or from unusual locations)
- Brute force login attempts
- Large data exports
- Configuration changes by administrators
- Failed security checks or validation errors

Suspicious activity triggers alerts to your security team.

## Vulnerability Management

### Security Testing

Light conducts:

- **Penetration Testing**: Annual third-party penetration tests to find vulnerabilities
- **Security Code Reviews**: Regular code reviews focusing on security
- **Vulnerability Scanning**: Automated scanning for known vulnerabilities in dependencies
- **Threat Modeling**: Regular assessment of potential threats and attack vectors

### Incident Response

Light maintains an incident response plan:

- 24/7 security monitoring to detect breaches quickly
- Rapid response procedures to contain and remediate incidents
- Transparent communication with affected customers
- Post-incident analysis to prevent recurrence

## Compliance and Certifications

Light maintains multiple security certifications:

- **SOC 2 Type II**: Audited controls for security, availability, processing integrity, confidentiality, and privacy
- **GDPR Compliance**: Full compliance with European data protection regulations
- **CCPA Compliance**: Compliance with California privacy requirements
- **ISO 27001**: Information security management standards

> Tip: Request Light's SOC 2 or security audit reports directly from your Light account team for your due diligence.

## Data Isolation

Light ensures strict data isolation between companies:

- Each company's data is logically and physically isolated
- No company can access another company's data, even through administrative access
- Multi-tenancy architecture ensures natural boundaries
- Database-level controls prevent cross-company data leakage

## API Security

Light's APIs are secured with:

- **API Keys**: Unique keys for each integration, rotatable and revocable
- **Rate Limiting**: Protection against brute force or DDoS attacks via API
- **Request Validation**: Strict validation of all API inputs
- **Audit Logging**: All API calls are logged and audited

## Related Articles

- Data encryption and storage
- Access controls and SSO
- Compliance certifications
- Data retention and deletion
