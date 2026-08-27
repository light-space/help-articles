# Light's Security Architecture

This article provides an overview of Light's approach to security, explaining the foundational security measures that protect your financial data.

[Open in Light →](https://app.light.inc/settings)

## What is this page about

This page covers how Light protects your financial data: where it runs, how it is encrypted, how access is controlled, how activity is monitored, and how customers are kept separate from one another. Use it as the starting point for a security review, and see the linked articles for detail on encryption, access controls, and compliance.

**On this page**

- Security Principles
- Infrastructure Security
- Data Encryption
- Authentication and Access Control
- Security Monitoring
- Change Management
- Security Awareness Training
- Endpoint Security
- Vulnerability Management
- Compliance and Certifications
- Data Isolation
- API Security
- Business Continuity and Disaster Recovery
- Related Articles

## Security Principles

Light is built on several core security principles:

- **Defence in Depth**: Multiple layers of security so that no single point of failure exposes your data
- **Encryption by Default**: Your data is encrypted at rest, and encrypted in transit between you and Light
- **Enforced Access Control**: Every user and integration authenticates, and every operation is checked against authorisation policies
- **Least Privilege**: Users and services have the minimum access needed to perform their functions
- **Continuous Monitoring**: Activity logging across the platform, with automated threat detection on the underlying infrastructure
- **Regular Testing**: Penetration testing and security audits to identify vulnerabilities before attackers do

## Infrastructure Security

### Cloud Infrastructure

Light is hosted on **Amazon Web Services (AWS)** and runs on secure, isolated cloud infrastructure with:

- **Network Isolation**: Your financial data sits in isolated network segments
- **DDoS Protection**: A CloudFront distribution, AWS Shield Standard, and web application firewall rate limiting absorb volumetric attacks
- **Threat Detection**: Amazon GuardDuty monitors Light's AWS infrastructure, covering storage access events, cluster audit logs, database login events, and network traffic flows
- **Web Application Firewall**: Rate-based rules block excessive request volumes, and AWS managed rule sets monitor for common web attack patterns such as injection and cross-site scripting

### Data Center Security

Light runs in AWS data centres, which provide:

- **Physical Security**: Access to data centres is restricted and monitored
- **Environmental Controls**: Redundant power, cooling, and climate monitoring
- **Fire Suppression**: Automatic fire detection and suppression systems
- **Backup Systems**: Multiple redundant systems ensure availability, with encrypted backups performed daily

> Good to know: Light's infrastructure is designed for 99.9% uptime with automatic failover to backup systems.

## Data Encryption

### Encryption at Rest

All financial data stored in Light is encrypted using AES-256 encryption:

- Database data is encrypted at the storage layer
- Backups are encrypted before leaving the data centre
- Historical data archives are encrypted
- Encryption keys are managed separately from encrypted data

### Encryption in Transit

Traffic between you and Light is encrypted:

- HTTPS with TLS 1.2 or higher for web connections
- API requests authenticate with OAuth 2.0 tokens or API keys
- Traffic from integrations such as bank feeds and payment processors travels over encrypted connections

## Authentication and Access Control

### User Authentication

Light supports multiple authentication methods:

- **Single Sign-On (SSO)** via your identity provider with SAML or OIDC protocols
- **Multi-Factor Authentication (MFA)**, enforced through your identity provider
- **API Keys** for service-to-service authentication
- **OAuth 2.0** for third-party integrations

### Role-Based Access Control

Light implements role-based access control (RBAC):

- **Roles**: Company admin, Controller, AP clerk, AR clerk, Invoice approver, AP preparation, Vendor management, Purchase requester, Cardholder, Reimbursement, Report viewer, and Auditor
- **Entity-Level Controls**: Roles can be scoped to specific company entities, so users only access the entities they are assigned to
- **Function-Level Controls**: Every operation is checked against resource-specific authorisation policies, such as approving expenses or posting journal entries

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

- Configuration changes by administrators
- Failed security checks or validation errors
- Repeated failed authentication attempts, through rate limiting and your identity provider

Suspicious activity alerts Light's security team.

## Change Management

Light follows a formal change management process for all production changes. Changes go through identification and logging, impact and risk assessment, peer review and approval, testing in non-production environments, controlled deployment through CI/CD pipelines, and post-deployment monitoring with rollback capability.

## Security Awareness Training

All Light employees complete security awareness training as part of onboarding. Periodic refresher training is provided to keep employees up to date on evolving threats and security best practices.

## Endpoint Security

All employee devices are enrolled in an endpoint management program that continuously monitors for compliance, including verification that antivirus and endpoint protection software is installed and active.

## Vulnerability Management

### Security Testing

Light conducts:

- **Penetration Testing**: Annual third-party penetration tests to find vulnerabilities
- **Security Code Reviews**: Regular code reviews focusing on security
- **Vulnerability Scanning**: Automated scanning for known vulnerabilities in dependencies
- **Threat Modeling**: Regular assessment of potential threats and attack vectors

### Incident Response

Light maintains an incident response plan:

- Continuous automated security monitoring and alerting tools running 24/7
- Rapid response procedures to contain and remediate incidents
- Transparent communication with affected customers. Light will notify customers in writing **within 36 hours** of identifying a potential or actual breach of personal data
- Post-incident analysis to prevent recurrence

## Compliance and Certifications

Light's compliance posture is anchored on:

- **SOC 2 Type II**: Audited controls for security, availability, processing integrity, confidentiality, and privacy. Renewal audit in progress.
- **GDPR Compliance**: Operational compliance with EU data protection regulations, with a customer-facing DPA and a documented subprocessor list.
- **PCI DSS 4.0.1 (in progress)**: SAQ-D Service Provider scope.

See Compliance Certifications for the full breakdown, including the DPA, subprocessor list, and supervisory authority.

> Tip: Request Light's SOC 2 Type II report or other security documentation directly from your Light account team for your due diligence.

## Data Isolation

Light keeps strict data isolation between companies:

- Each company's data is **logically separated** using tenant identifiers in a shared database. Light enforces that separation by scoping every query to a single company, and applies row-level security as a further layer on analytics access
- No customer can access another customer's data. Authorised Light support staff can access customer data through audited internal tooling in order to provide support
- Tenant scoping applies to every read and write path in the application

## API Security

Light's APIs are secured with:

- **API Keys**: Unique keys for each integration, rotatable and revocable
- **Rate Limiting**: Per-minute and per-day limits on external API and API key traffic, checked together on every request. Exceeding a limit returns an HTTP 429 response with a Retry-After header.
- **Request Validation**: Strict validation of all API inputs
- **Audit Logging**: All API calls are logged and audited

## Business Continuity and Disaster Recovery

Light leverages AWS regional redundancy and failover capabilities for business continuity and disaster recovery. Infrastructure is distributed across multiple availability zones, ensuring that service remains available in the event of localized failures.

## Related Articles

- Data encryption and storage
- Access controls and SSO
- Compliance certifications
- Data retention and deletion
