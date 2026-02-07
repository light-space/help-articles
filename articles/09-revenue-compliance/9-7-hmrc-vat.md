# Tax Compliance — HMRC (UK) and VAT

Value Added Tax (VAT) is a consumption tax applied at each stage of production and distribution in the UK and EU. As the VAT framework is complex with multiple rates, exemptions, and reverse-charge mechanisms, Light automates VAT calculation, reporting, and HMRC submissions to ensure compliance.

[Open in Light →](https://app.light.inc/invoice-receivables)

## Understanding VAT

VAT is collected from customers on sales and can be reclaimed on purchases. A business collects VAT from customers, reclaims VAT from suppliers, and remits the net difference to HMRC.

**VAT rates in the UK**:

- **Standard rate**: 20% (most goods and services)
- **Reduced rate**: 5% (fuel, children's car seats, energy-saving materials)
- **Zero rate**: 0% (food, books, newspapers, children's clothing)
- **Exempt**: No VAT charged or recoverable (insurance, financial services, postage stamps)

Within the EU, digital services are subject to the customer's country VAT rate, creating complexity for e-commerce and SaaS businesses.

> Good to know: VAT is calculated on invoice amounts after discounts but before freight (unless freight is separately invoiced).

## VAT configuration in Light

Light requires configuration of your VAT treatment:

1. Navigate to **Settings** (gear icon in bottom-left sidebar) > **Tax codes** or **Tax Tables**
2. Select **United Kingdom** as your primary jurisdiction
3. Configure your VAT registration number (begins with GB)
4. Set your VAT registration date
5. Indicate if you're VAT-registered or below threshold
6. Save configuration

Once configured, Light automatically applies VAT rules to all transactions.

## Tax codes and VAT treatment

In Light's ledger, each tax code maps to a VAT treatment:

**Standard Rate (20%)**:
- Most supplies of goods and services
- Commercial rent
- Construction services

**Reduced Rate (5%)**:
- Fuel and power
- Children's car seats and safety seats
- Installation of energy-saving materials

**Zero Rate (0%)**:
- Food and food ingredients
- Books and printed matter
- Children's clothing and footwear
- Newspapers and periodicals

**Exempt**:
- Insurance
- Financial services
- Postage stamps
- Education (by eligible institutions)
- Health services (by eligible providers)

**Reverse Charge** (no VAT on purchase, VAT deferred):
- Services from EU businesses under reverse-charge rules
- Construction services (domestic reverse charge)

Configure each tax code to map to these categories. Light then automatically applies the correct rate to transactions using that code.

## VAT on purchases (Input Tax)

When you purchase goods or services, VAT is charged. You can recover this VAT (input tax) if:

1. The purchase is for business purposes (not personal use)
2. The supplier is VAT-registered and charged VAT
3. You have a valid invoice from the supplier
4. The invoice includes the supplier's VAT number

In Light, when you record a purchase (AP invoice) with a VAT tax code, the VAT is automatically categorized as recoverable input tax. This appears on your VAT return as a reduction in VAT owed.

> Tip: Keep all supplier invoices. HMRC requires supporting invoices for all VAT claims. Light maintains a complete audit trail of all VAT transactions.

## VAT on sales (Output Tax)

When you make a sale, you charge VAT (output tax). This VAT is owed to HMRC. In Light, when you create an AR invoice with a VAT tax code, the VAT is automatically categorized as output tax.

Your VAT liability = Output Tax (from sales) - Input Tax (from purchases)

If input tax exceeds output tax (common for exporters or businesses with many exempt supplies), you receive a VAT refund.

## Intrastat and the reverse charge

When selling to customers in other EU countries, specific rules apply:

**Distance selling**: If you sell goods to private consumers in the EU, you charge your own country's VAT. When sales exceed EUR 35,000 to a country, you must charge that country's VAT instead.

**Reverse charge for services**: Services supplied to non-VAT-registered consumers in other EU countries are reverse-charged (the customer pays VAT in their country).

**Reverse charge for goods from EU**: When you purchase from EU suppliers, you may be charged VAT but use reverse-charge treatment (record as no VAT, with the VAT deferred until you resell).

Light applies reverse-charge automatically when you configure the customer or supplier as being in another EU country. You can manually override reverse-charge treatment if your specific transaction requires it.

## VAT returns

HMRC requires VAT returns quarterly (or monthly if you prefer). Light prepares your VAT return automatically:

1. Navigate to **Planning & Reports > Reports**
2. Select the return period (quarter or month)
3. Light calculates:
   - Total output tax (Box 1)
   - Total input tax (Box 4)
   - Net VAT owed or refundable (Box 5)
4. Review the calculation and supporting details
5. Click **Prepare Return** to generate the official HMRC form
6. Submit via MTD (Making Tax Digital) portal or light's integration

> Good to know: Light stores all supporting calculations so you can audit the return line-by-line before submission.

## MTD integration for VAT

The UK implemented Making Tax Digital (MTD), requiring digital filing of VAT returns. Light integrates with HMRC's MTD system:

1. Set up your HMRC credentials in **Settings** (gear icon in bottom-left sidebar) > **Integrations**
2. Authorize Light to access your MTD account
3. Light maintains connection to your HMRC account
4. When you file a VAT return in Light, it automatically submits to HMRC

Light maintains a record of all submissions and acknowledgments from HMRC.

## Multi-entity VAT

For companies with multiple UK entities, each entity has its own VAT registration and VAT liability. Light:

- Tracks VAT separately for each entity
- Consolidates VAT reporting across entities only if you have a VAT group registration
- Maintains separate VAT returns per entity

If you have a VAT group (one consolidated VAT liability across entities), configure this in Light's multi-entity settings. Light then combines VAT calculations across entities for group returns.

## EU transactions and VAT

Transactions with EU counterparties involve specific VAT rules:

**Purchases from EU suppliers**: Request their VAT number (starts with their country code, e.g., DE, FR). If they provide a VAT number, reverse-charge applies (no VAT on purchase).

**Sales to EU businesses**: If the buyer provides a VAT number, supply is zero-rated (no VAT charged). Ask the customer for their VAT number before invoicing.

**Sales to EU consumers**: Charge your own VAT unless distance selling thresholds apply.

Light assists by requesting VAT numbers from customers and suppliers. If provided, it applies the correct VAT treatment automatically.

## VAT exemption management

If you make exempt supplies (e.g., financial services, insurance), you cannot reclaim VAT on related purchases. Configure accounts as:

- **Exempt supply accounts**: VAT-zero-rated on invoices
- **Exempt input accounts**: VAT is not recoverable on purchases

Light then prevents recovery of VAT on transactions tagged to exempt categories.

## Audit documentation

Maintain comprehensive VAT documentation:

- All invoices (sales and purchases) with VAT detail
- VAT returns submitted to HMRC
- Bank statements showing VAT payments
- Supporting schedules for major transactions

Light maintains this automatically. Export for auditor review:

1. Navigate to **Planning & Reports > Reports**
2. Select period
3. Click **Export Audit Package**
4. Download PDF with all VAT transactions and calculations

## Related articles

- [Tax compliance — AvaTax (US)](9-8-avatax-us.md)
- [Audit-ready record keeping](9-9-audit-ready-records.md)
- [HMRC connection (UK)](../11-integrations/11-9-hmrc-uk.md)
