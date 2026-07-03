# Compliance Certifications

This article explains Light's security and compliance certifications, demonstrating our commitment to protecting your financial data and meeting regulatory requirements.

[Open in Light →](https://app.light.inc/settings)

## Overview

Light maintains security and compliance assurances backed by independent audit. These provide customers with evidence that Light meets industry standards for security, privacy, and operational handling of financial data.

Light's current compliance posture:

- **SOC 2 Type II**: audited and maintained, renewal audit in progress
- **GDPR compliance**: operational, with a customer-facing DPA
- **PCI DSS 4.0.1 (in progress)**: SAQ-D Service Provider scope, audit closing May 21, 2026

## SOC 2 Compliance

### What is SOC 2?

SOC 2 (System and Organization Controls 2) is a framework for evaluating controls at service providers, conducted by independent auditors. It assesses Light's controls for security, availability, processing integrity, confidentiality, and privacy. SOC 2 reports are issued under the AICPA's SSAE 18 attestation standard.

### Light's SOC 2 Type II

Light maintains **SOC 2 Type II**, with a renewal audit currently in progress:

- **Independent Audit**: Conducted annually by an independent auditing firm
- **Type II Testing Period**: Auditors observe Light's controls in operation over a multi-month period, not at a single point in time
- **Comprehensive Review**: Covers Light's systems, processes, and personnel relevant to the Trust Services Criteria
- **Continuous Compliance**: Light maintains the underlying controls year-round and tracks them on an ongoing basis

### What SOC 2 Covers

SOC 2 evaluates controls over:

- **Security**: Protection against unauthorized access
- **Availability**: Systems remain operational and available
- **Processing Integrity**: Data is processed accurately and completely
- **Confidentiality**: Sensitive data is protected from unauthorized disclosure
- **Privacy**: Data is collected, used, and retained appropriately

> Good to know: Request Light's SOC 2 Type II report directly from your account team. The full audit report is provided under NDA.

## GDPR Compliance

### What is GDPR?

GDPR (General Data Protection Regulation) is the European Union's comprehensive data protection law applying to companies processing European residents' data.

### Light's GDPR Compliance

Light is fully GDPR compliant:

- **Legal Basis**: Processing has legitimate legal basis (customer request, contractual need, etc.)
- **Data Subject Rights**: Users can request access, correction, deletion, and portability of their data
- **Data Protection Officer**: Light maintains a DPO for privacy questions
- **Privacy Policy**: Clear, transparent privacy terms
- **Consent Management**: Explicit consent for processing where required

### Controller and Processor Roles

For customer data processed in the Light service, the customer acts as **Data Controller** and Light acts as **Data Processor** under the Data Processing Agreement (DPA). Light processes the following categories of personal data on the customer's behalf:

- **Identification and contact data**: name, business email address, business phone number, job title, office location
- **Customer-provided content**: documents, images, and other data in electronic form that end users upload, submit, store, or otherwise process through the Light application
- **System and usage data**: authentication data, login events, activity logs, device/IP information, and other metadata necessary for service provision, security, and auditing

The processing concerns customer employees, authorized users, designated administrators, and customer representatives interacting with Light support. Light does not process personal data of the customer's own customers, suppliers, or the general public unless those individuals are intentionally added or included by the customer in the service.

Light does **not** require, request, or intentionally process any special-category personal data (Article 9 GDPR).

### Supervisory Authority

Light is headquartered in Denmark. Its supervisory data protection authority is **Datatilsynet** (the Danish Data Protection Authority). Denmark does not require GDPR controllers or processors to register with the supervisory authority, so no registration number applies.

### Data Subject Access Requests (DSARs)

Light supports customers in fulfilling data subject access requests. Admins can view and update user profile data in the app and export business records (invoices, journal entries, reports, and more) to CSV. Requests to export or delete a specific person's data are handled by Light on request. Under the DPA, Light provides reasonable assistance to the customer. The customer remains the Data Controller and is responsible for responding directly to data subjects.

### Key GDPR Capabilities

Light provides:

- **Data Export**: Admins can export business records to CSV from the app; personal data exports for DSARs are fulfilled by Light on request
- **Right to Deletion**: Deletion of personal data can be requested through Light; admins can deactivate users directly in the app
- **Data Processing Agreements (DPA)**: Standard DPA available for all customers
- **Sub-processor Management**: All sub-processors are listed and compliant
- **Breach Notification**: Light notifies you within 36 hours if a breach occurs

## PCI DSS Compliance (in progress)

### What is PCI DSS?

PCI DSS (Payment Card Industry Data Security Standard) is a set of security requirements that apply to companies that store, process, or transmit cardholder data. PCI DSS 4.0.1 is the current version of the standard.

### Light's PCI Programme

Light is currently undergoing a PCI DSS 4.0.1 audit, scoped as **SAQ-D Service Provider**:

- **Scope**: SAQ-D is the most comprehensive self-assessment questionnaire and applies to service providers handling cardholder data
- **Audit Close**: Targeted for **May 21, 2026**
- **Controls in Place**: Encryption of cardholder data, network segmentation, access controls, vulnerability scanning, and logging are already in operation; remaining work is documentation and evidence collection toward audit close

We will update this article when the audit completes.

## Data Processing Agreements (DPA)

### What is a DPA?

A Data Processing Agreement is a contract between Light and customers specifying how personal data will be processed, protecting both parties legally.

### Light's DPA

Light provides:

- **Standard DPA**: Available for all customers at no additional charge
- **Customization**: DPAs can be customized for specific requirements
- **GDPR Compliant**: Full compliance with GDPR Article 28 requirements
- **Signature**: Executed within 5 business days of request
- **Online Access**: Light's DPA is available at [light.inc/dpa](https://light.inc/dpa)

### Key DPA Terms

- **Processing Scope**: Specifies exactly what data is being processed
- **Purpose**: Defines legitimate purposes for processing
- **Duration**: Specifies how long data is retained
- **Sub-processors**: Lists vendors that may access data
- **Data Subject Rights**: Mechanisms for exercising consumer rights
- **Liability**: Allocation of liability and indemnification

### Subprocessors

Light's DPA lists the following subprocessors and their processing locations:

| Subprocessor | Location |
|---|---|
| Amazon Web Services | Ireland |
| OpenAI Services | Europe |
| AMC Banking | Denmark |
| Google Cloud (Vertex AI) | Europe |
| Adyen | Netherlands |

Customers are notified of new subprocessors with a **30-day notice period** and have the right to object under the DPA.

### International Data Transfers

Where cross-border transfers of personal data occur outside the EEA, Light relies on GDPR Chapter V safeguards, including:

- EU Standard Contractual Clauses (SCCs) where required
- Subprocessor DPAs and contractual safeguards
- Supplementary technical and organizational measures such as encryption, access controls, and data minimization

### Public Legal and Privacy Links

- [Terms of Service](https://light.inc/terms)
- [Privacy Policy](https://light.inc/privacy)
- [Data Processing Agreement](https://light.inc/dpa)
- [Security Overview](https://light.inc/security)

## Penetration Testing and Security Audits

Light maintains security through:

- **Annual Penetration Testing**: Third-party experts attempt to compromise systems
- **Vulnerability Scanning**: Regular scans for known vulnerabilities
- **Code Reviews**: Security-focused code review process
- **Bug Bounty Program**: Security researchers can report vulnerabilities responsibly

## Compliance Audit Process

Light undergoes regular audits:

1. **Planning**: Auditors and Light plan the scope and timeline
2. **Testing**: Auditors examine systems, processes, and documentation
3. **Interviews**: Auditors interview Light personnel
4. **Remediation**: Any findings are addressed
5. **Reporting**: Auditors issue official reports and certifications

## Requesting Compliance Documentation

To request compliance documentation:

1. Contact your Light account manager
2. Specify which document (SOC 2 Type II report, DPA, security overview, PCI status letter, etc.)
3. Indicate if you need the full report or summary
4. Document your organization's need for the information
5. Light delivers documentation under NDA if required

Typical response time is 5 business days.

## Staying Current

Light maintains compliance through:

- **Continuous Monitoring**: Year-round monitoring of compliance status
- **Regular Training**: All personnel receive compliance and security training
- **Policy Updates**: Compliance policies are updated as regulations change
- **Vendor Management**: Sub-processors are audited for compliance

## Related Articles

- Light's security architecture
- Data encryption and storage
- Access controls and SSO
- Data retention and deletion
