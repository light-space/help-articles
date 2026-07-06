# HMRC Connection (UK)

HMRC (His Majesty's Revenue and Customs) is the UK tax authority. Light's HMRC integration enables automated VAT return filing through a direct connection to HMRC's Making Tax Digital (MTD) system.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

The HMRC integration enables:

- **VAT returns**: Automated VAT return preparation and filing
- **Making Tax Digital (MTD)**: Direct submission to HMRC's digital platform
- **VAT calculations**: Automatic calculation from GL transaction data
- **VAT obligations**: Filing periods and due dates retrieved directly from HMRC
- **Per-entity connections**: Each UK entity connects to HMRC with its own VAT registration

This automates UK VAT compliance and reduces manual filing work.

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

Once connected, Light can retrieve your VAT obligations and file returns. Light never stores your HMRC credentials — only encrypted access tokens, which are refreshed automatically.

> Good to know: The connection is per entity, and the entity must have its VAT registration number set in **Settings (gear icon) > Entities** (with or without the GB prefix — Light formats it correctly when communicating with HMRC).

## VAT return preparation

Light automatically calculates VAT returns:

1. Navigate to **Planning & Reports → Reports**
2. Select the return period — Light retrieves your open VAT obligations (filing periods, due dates, and period keys) directly from HMRC
3. Light calculates all nine boxes of the VAT return, including:
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

Your VAT filing frequency is determined by your registration with HMRC — there is no separate frequency setting in Light. Light retrieves your filing obligations (periods, period keys, and due dates) directly from HMRC, so the return periods you see always match what HMRC expects you to file.

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
2. View your open VAT obligations retrieved from HMRC, including upcoming return due dates
3. Once filed, HMRC records the return against the obligation

This prevents missed deadlines and penalties.

## Adjusting submitted returns

VAT returns are submitted to HMRC as final, so a submitted return cannot be amended through MTD. If you discover an error after filing, follow HMRC's correction rules: errors below HMRC's thresholds are corrected as an adjustment in your next VAT return, while larger errors must be reported to HMRC directly (form VAT652).

## VAT penalties and interest

HMRC charges penalties for late filing and late payment, plus interest on underpayment. Use Light's obligation tracking to see upcoming due dates and file on time — staying current on filings through Light's deadline tracking helps you avoid penalties.

## Troubleshooting HMRC connection

**Connection failed**: Verify Government Gateway credentials, check two-factor authentication is working, ensure HMRC account is active.

**Missing VAT number**: Light requires the entity's VAT registration number to communicate with HMRC — add it in **Settings (gear icon) > Entities**.

**Return calculation incorrect**: Review GL account mappings, verify tax codes are correct, check for manual adjustments needed.

**Filing deadline missed**: Check your open obligations in **Planning & Reports → Reports** and file as soon as possible.

**Error in a submitted return**: Correct it per HMRC's rules — in your next return if below HMRC's thresholds, otherwise report directly to HMRC.

## Exporting HMRC documentation

Prepare documentation package for auditors:

1. Navigate to **Planning & Reports → Reports**
2. Light compiles:
   - VAT returns filed
   - Supporting trial balance by tax code
   - Exceptions and adjustments
3. Export as PDF for auditor review

This provides comprehensive evidence for compliance review.

## Related articles

- [Tax compliance — HMRC (UK) and VAT](../09-revenue-compliance/9-7-hmrc-vat.md)
- [Integrations overview](11-1-integrations-overview.md)
- [E-invoicing compliance (Peppol)](../09-revenue-compliance/9-6-e-invoicing-compliance.md)
