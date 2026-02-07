# HMRC Connection (UK)

HMRC (Her Majesty's Revenue and Customs) is the UK tax authority. Light's HMRC integration enables automated VAT return filing, PAYE reporting, and other UK tax compliance through direct connection to HMRC's Making Tax Digital (MTD) systems.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

The HMRC integration enables:

- **VAT returns**: Automated VAT return preparation and filing
- **Making Tax Digital (MTD)**: Direct submission to HMRC's digital platform
- **VAT calculations**: Automatic calculation from GL transaction data
- **PAYE reporting**: Employee tax and NI withholding tracking
- **CIS returns**: Construction Industry Scheme reporting (if applicable)
- **Penalties and deadlines**: Automatic tracking of filing deadlines

This automates UK tax compliance and reduces manual filing work.

## Setting up HMRC connection

To connect HMRC:

1. Navigate to **Settings (gear icon) > Integrations > HMRC**
2. Click **Connect to HMRC**
3. You're redirected to HMRC to authorize
4. Sign in with your Government Gateway credentials
5. Two-factor authentication required (security code via email or phone)
6. Review permissions Light is requesting to access your tax account
7. Click **Authorize**
8. Light confirms connection is active

Once connected, Light can file returns and access account information.

## VAT return preparation

Light automatically calculates VAT returns:

1. Navigate to **Planning & Reports → Reports**
2. Select return period (quarter typically)
3. Light displays:
   - **Box 1**: VAT due on sales (output tax)
   - **Box 4**: VAT recoverable on purchases (input tax)
   - **Box 5**: Net VAT payable/refundable
   - Supporting detail (transactions included, calculations)
4. Review and validate calculations
5. Click **Submit to HMRC**

Light submits directly to HMRC's system.

## Making Tax Digital (MTD) filing

Light integrates with MTD, the UK's digital tax filing system:

1. Light prepares VAT return with all required data
2. MTD format validation occurs automatically
3. Light submits to HMRC's secure MTD portal
4. HMRC confirms receipt (filing acknowledgment)
5. Light stores filing confirmation for audit trail

This replaces manual VAT form submission.

## PAYE withholding and reporting

Track employee taxes and National Insurance:

1. Light receives payroll data from HRM (via Finch integration)
2. Light calculates employee income tax withholding and NI contributions
3. Light calculates employer NI contributions
4. Light automatically reports to HMRC via Real Time Information (RTI)

## VAT compliance rules

Light enforces UK VAT rules:

**Standard rate (20%)**:
- Applied to most goods and services
- Correctly identified in GL tax codes

**Reduced rate (5%)**:
- Applied to fuel, energy, children's goods, materials
- Correctly identified in GL tax codes

**Zero rate (0%)**:
- Applied to food, books, newspapers, children's clothing
- Correctly identified in GL tax codes

**Exempt**:
- Insurance, financial services, education
- VAT not charged; recovery not allowed

**Reverse charge**:
- Services from EU suppliers (post-Brexit, less common)
- Construction services (domestic reverse charge)

Light enforces these rules in tax configuration.

> Good to know: VAT treatment depends on customer location and nature of supply. Light automatically applies rules based on your configuration.

## Quarterly vs. monthly filing

Configure your VAT filing frequency:

1. Navigate to **Settings > Tax > VAT Filing Frequency**
2. Select:
   - **Quarterly**: File every 3 months (most common)
   - **Monthly**: File monthly (if required)
3. Set filing dates (HMRC typically requires filing within 30 days of quarter-end)
4. Save

Light tracks deadlines and prompts you to file on time.

## Flat rate VAT (if applicable)

Some small businesses use VAT flat rate scheme:

1. Navigate to **Settings > Tax > Flat Rate VAT**
2. If using flat rate, configure:
   - Flat rate percentage for your business type
   - Turnover threshold
3. Light calculates VAT using flat rate method
4. File flat rate return to HMRC

Most growing businesses use standard VAT.

## Construction Industry Scheme (CIS)

If you're in construction, configure CIS:

1. Navigate to **Settings > Tax > CIS**
2. Configure:
   - CIS status (registered, subcontractor)
   - CIS withholding rate
3. When paying subcontractors, Light calculates withholding
4. Light tracks cumulative withholding (offset against payments due)
5. File CIS returns to HMRC

## VAT in multi-entity organizations

For organizations with multiple UK entities:

1. Each entity has separate HMRC registration (VAT number)
2. Each entity files separate VAT return
3. Light maintains VAT tracking per entity
4. Can consolidate for group reporting if you have VAT group registration

Light enables both consolidated and entity-level VAT reporting.

## Monitoring filing deadlines

Light tracks HMRC deadlines:

1. Navigate to **Planning & Reports → Reports**
2. View:
   - Upcoming VAT return due dates
   - PAYE reporting deadlines
   - CIS return deadlines (if applicable)
3. Light sends reminders before deadline
4. Once filed, status updates to "Submitted"

This prevents missed deadlines and penalties.

## Adjusting submitted returns

If you file a return but then discover an error:

1. Create an amended return:
   - Navigate to **Planning & Reports → Reports**
   - Select the original return period
   - Click **Amend Return**
   - Correct the error
   - Submit amended return to HMRC
2. Or use Adjustment Notices (AON) for significant corrections

Light maintains separate records of original and amended returns.

## VAT penalties and interest

HMRC charges penalties for late filing:

Light tracks:
- Filing deadline vs. actual filing date
- Late payment penalties if VAT payment is late
- Interest on underpayment
- Prompts you to pay on time to avoid penalties

Stay current on filings through Light's deadline tracking.

## Documenting VAT positions

Keep detailed documentation:

1. Navigate to **Settings > Tax > VAT Policies**
2. Document your VAT positions:
   - Treatment of supplies
   - Reasoning for zero-rating, exempt, or standard rating
   - Customer location documentation (for distance selling)
   - VAT recovery methodology
3. Light maintains these for audit trail

This supports audit procedures if HMRC questions your treatment.

## Troubleshooting HMRC connection

**Connection failed**: Verify Government Gateway credentials, check two-factor authentication is working, ensure HMRC account is active.

**Return calculation incorrect**: Review GL account mappings, verify tax codes are correct, check for manual adjustments needed.

**Filing deadline missed**: Set calendar reminders, enable Light notifications for deadlines, configure early reminder alerts.

**Amended return needed**: Prepare amended return within HMRC time limits, submit through Light.

## Real Time Information (RTI)

For PAYE, HMRC requires Real Time Information reporting:

1. Each payroll submission, Light reports to HMRC via RTI
2. Light automatically reports:
   - Employee earnings
   - Tax withholding
   - National Insurance
3. HMRC confirms receipt
4. Employee's tax record updates in HMRC system

This happens automatically when payroll processes.

## Exporting HMRC documentation

Prepare documentation package for auditors:

1. Navigate to **Planning & Reports → Reports**
2. Light compiles:
   - All VAT returns filed (original and amended)
   - Supporting trial balance by tax code
   - Exceptions and adjustments
   - PAYE records and RTI confirmations
   - CIS records (if applicable)
3. Export as PDF for auditor review

This provides comprehensive evidence for compliance review.

## Related articles

- [Tax compliance — HMRC (UK) and VAT](../09-revenue-compliance/9-7-hmrc-vat.md)
- [Integrations overview](11-1-integrations-overview.md)
- [E-invoicing compliance (Peppol)](../09-revenue-compliance/9-6-e-invoicing-compliance.md)
