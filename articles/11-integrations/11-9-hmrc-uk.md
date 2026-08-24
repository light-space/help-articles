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

1. Navigate to **Settings (gear icon) > Integrations**
2. Find **HMRC** and click to connect, opening the **Create HMRC connection** dialog
3. Click **Create**, then you're redirected to HMRC to authorize
4. Sign in with your Government Gateway credentials
5. Two-factor authentication required (security code via email or phone)
6. Review permissions Light is requesting to access your tax account
7. Authorize on HMRC's site
8. Light confirms connection is active

Once connected, Light can retrieve your VAT obligations and file returns. Light never stores your HMRC credentials — only encrypted access tokens, which are refreshed automatically.

> Good to know: The connection is per entity, and the entity must have its VAT registration number set in **Settings (gear icon) > Entities** (with or without the GB prefix — Light formats it correctly when communicating with HMRC).

## VAT return preparation

Light automatically calculates VAT returns:

1. Navigate to **Planning & Reports → Reports**
2. Light calculates all nine boxes of the VAT return, including:
   - **Box 1**: VAT due on sales (output tax)
   - **Box 4**: VAT recoverable on purchases (input tax)
   - **Box 5**: Net VAT payable/refundable
   - Supporting detail (transactions included, calculations)
3. Review the calculations
4. Click **File with HMRC**, then **Confirm** in the drawer that opens

Light submits directly to HMRC's system.

## Making Tax Digital (MTD) filing

Light integrates with MTD, the UK's digital tax filing system:

1. Light prepares VAT return with all required data
2. Light submits to HMRC's secure MTD portal, where HMRC validates the submission
3. HMRC confirms receipt (a form bundle number, shown as a confirmation in Light)

This replaces manual VAT form submission.

## VAT tax codes

Light seeds these UK VAT tax codes for you to use on your transactions:

**Standard rate (20%)**:
- Applied to most goods and services

**Reduced rate (5%)**:
- Applied to fuel, energy, children's goods, materials

**Zero rate (0%)**:
- Applied to food, books, newspapers, children's clothing

**Exempt**:
- Insurance, financial services, education
- VAT not charged, and recovery isn't allowed

**Reverse charge**:
- Available through the generic EDIFACT **AE** code, rather than one of the seeded UK defaults
- Used for services from EU suppliers and for domestic construction services under the reverse charge scheme

Light checks that a tax code is used correctly at a structural level, such as balanced postings and rejecting a manual tax amount on a reverse-charge line. Choosing the right code for a given transaction, based on VAT law, is down to you.

> Good to know: VAT treatment depends on the customer's location and the nature of the supply. Select the tax code that matches your transaction on the invoice or bill line.

## Quarterly vs. monthly filing

Your VAT filing frequency is determined by your registration with HMRC — there is no separate frequency setting in Light.

## VAT in multi-entity organizations

For organizations with multiple UK entities:

1. Each entity has separate HMRC registration (VAT number)
2. Each entity files a separate VAT return
3. Light tracks VAT per entity
4. Light has no VAT group feature. If your entities hold an actual VAT group registration with HMRC, talk to your Light representative about how to handle group filing, since it isn't a self-service configuration in the product today

Light supports entity-level VAT reporting and general financial consolidation across entities, but not VAT group filing specifically.

## Monitoring filing deadlines

Light tracks HMRC deadlines:

1. Navigate to **Planning & Reports → Reports**
2. View your open VAT obligations retrieved from HMRC, including upcoming return due dates
3. Once filed, HMRC records the return against the obligation

This prevents missed deadlines and penalties.

## Adjusting submitted returns

VAT returns are submitted to HMRC as final, so a submitted return cannot be amended through MTD. If you discover an error after filing, follow HMRC's correction rules: errors below HMRC's thresholds are corrected as an adjustment in your next VAT return, while larger errors must be reported to HMRC directly (form VAT652). Rules and thresholds here are HMRC's, not Light's, and they can change, so confirm your own position with your tax adviser rather than relying on this summary.

## VAT penalties and interest

HMRC charges penalties for late filing and late payment, plus interest on underpayment.

## Troubleshooting HMRC connection

**Connection failed**: Verify Government Gateway credentials, check two-factor authentication is working, ensure HMRC account is active.

**Missing VAT number**: Light requires the entity's VAT registration number to communicate with HMRC — add it in **Settings (gear icon) > Entities**.

**Return calculation incorrect**: Review GL account mappings, verify tax codes are correct, check for manual adjustments needed.

**Filing deadline missed**: Check your open obligations in **Planning & Reports → Reports** and file as soon as possible.

**Error in a submitted return**: Correct it per HMRC's rules — in your next return if below HMRC's thresholds, otherwise report directly to HMRC.

## Exporting reports for auditors

Light doesn't compile a single dedicated HMRC documentation package. Instead, export the underlying reports individually as CSV:

1. Navigate to **Planning & Reports → Reports**
2. Open the report you need (filed VAT returns, trial balance by tax code, or exceptions/adjustments)
3. Use the report's Export action to download it as CSV

Combine the individual CSV exports as needed for auditor review.

## Related articles

- [Tax compliance — HMRC (UK) and VAT](../09-revenue-compliance/9-7-hmrc-vat.md)
- [Integrations overview](11-1-integrations-overview.md)
- [E-invoicing compliance (Peppol)](../09-revenue-compliance/9-6-e-invoicing-compliance.md)
