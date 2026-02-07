# Stripe Integration

Stripe is the leading online payment processor for e-commerce and SaaS businesses. Light's Stripe integration automatically syncs payments, refunds, and subscription data directly to your ledger, creating a complete audit trail and eliminating manual payment entry.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

The Stripe integration enables:

- **Payment sync**: Successful customer payments automatically post to cash receipts
- **Refund sync**: Customer refunds automatically post as reversals
- **Subscription tracking**: Recurring subscription payments tracked for revenue recognition
- **Currency handling**: Multi-currency payments automatically converted
- **Reconciliation**: Bank deposits matched to Stripe settlements

This creates an automated payment-to-cash-receipt workflow.

## Setting up Stripe integration

To connect Stripe:

1. Navigate to **Settings (gear icon) > Integrations > Stripe**
2. Click **Connect**
3. You're redirected to Stripe to authorize
4. Sign in to your Stripe account
5. Review permissions Light is requesting
6. Click **Authorize**
7. Light confirms connection and enables sync

Next, configure what data to sync.

## Configuring payment sync

Define how Stripe payments become Light cash receipts:

1. Navigate to **Settings > Integrations > Stripe > Payment Mapping**
2. Select **Sync Payments**: Toggle on
3. Configure mapping:
   - **Stripe Charge Amount** → **Light Receipt Amount**
   - **Stripe Customer ID** → **Light Customer** (match Stripe customer to Light customer)
   - **Stripe Invoice ID** → **Light AR Invoice** (link payment to invoice if exists)
   - **Stripe Metadata** → **Light Custom Properties** (if using Stripe metadata)
4. Configure filters:
   - Payment status: Only sync successful payments (exclude pending)
   - Currency: Only sync specific currencies (or all)
   - Amount threshold: Only sync payments above minimum (e.g., > $1)
5. Save configuration

Light validates the mapping.

## Payment matching and reconciliation

When a Stripe payment syncs:

1. Light reads the payment amount and customer
2. Light searches for a matching AR invoice (by customer and amount)
3. If found, Light automatically applies payment to invoice
4. If not found, Light creates a cash receipt without invoice linkage
5. Payment appears as a line on bank reconciliation
6. You can manually link to invoice if needed

This enables both automatic and manual matching.

## Handling multiple invoices

If a Stripe payment covers multiple customer invoices:

1. Light receives the payment
2. Light attempts to match (may match first invoice only)
3. Create a manual payment allocation:
   - Split the Stripe payment across invoices
   - Light allocates portions to each invoice
   - All invoices marked paid when fully allocated

> Tip: Use Stripe metadata to include invoice numbers with payments, enabling cleaner automatic matching.

## Refund and chargeback handling

When customers are refunded or chargebacks occur:

1. Stripe records the refund
2. Light syncs the refund
3. Light creates a reversal of the original cash receipt
4. AR aging automatically updates (invoice marked unpaid)
5. You can then apply alternative payment or write off

This maintains complete audit trail of all payment activity.

## Subscription and recurring payment tracking

For SaaS with recurring Stripe subscriptions:

1. Configure **Subscription Sync**: Toggle on
2. Light tracks active subscriptions:
   - Subscription ID
   - Customer
   - Monthly recurring value (MRR)
   - Renewal date
3. When subscription renews, Light automatically:
   - Creates new AR invoice (if using invoice-based billing)
   - Records payment as cash receipt
   - Updates revenue recognition (if using deferred revenue)

This automates subscription billing entirely.

## Multi-currency payments

Stripe processes payments in multiple currencies. Light handles:

1. Stripe payment in foreign currency (e.g., EUR 100)
2. Light records transaction in transaction currency (EUR 100)
3. Light calculates local currency using Stripe's FX rate (EUR 100 = GBP 85 at 0.85 rate)
4. Light records to cash account in local currency

This ensures accurate multi-currency reporting.

## Sync frequency

Configure how often Light checks Stripe for new payments:

1. Navigate to **Settings > Integrations > Stripe > Sync Settings**
2. Select frequency:
   - **Real-time**: Via webhook (immediate, as payment completes)
   - **Hourly**: Check hourly
   - **Daily**: Check once daily
3. Save

Real-time (webhook) is ideal for quick cash visibility. Daily is sufficient for most organizations.

## Monitoring Stripe sync

Track integration activity:

1. Navigate to **Settings > Integrations > Stripe > Sync History**
2. View all past syncs:
   - Date/time
   - Number of payments synced
   - Number of refunds synced
   - Errors (if any)
3. Click any sync to see details:
   - Which payments were processed
   - Which invoices were matched
   - Which failed and why

This helps identify issues.

## Manual sync trigger

Sync immediately without waiting for scheduled time:

1. Navigate to **Settings (gear icon) > Integrations > Stripe**
2. Click **Sync Now**
3. Light immediately checks Stripe and syncs new payments
4. See summary of results

Useful when you need to reconcile immediately.

## Bank settlement sync

Stripe typically deposits settlements to your bank account:

1. Stripe accumulates charges throughout the day
2. Stripe deposits net amount to your bank account (typically daily)
3. Bank integration syncs deposit
4. Stripe integration syncs individual charges
5. Reconcile: Stripe charges aggregate to bank deposit

This ensures ledger matches bank statement.

## Handling Stripe fees

Stripe charges processing fees. Configure how to record:

**Option 1 - Record as expense**:
- Each Stripe charge includes the fee
- Light records net amount as cash receipt
- Light records fee as operating expense (merchant fees account)

**Option 2 - Gross recording**:
- Light records gross revenue
- Separately records Stripe fee as expense

Configure in Stripe mapping settings which approach you prefer.

## Testing Stripe sync

Before relying on Stripe integration:

1. Create a test payment in Stripe (test mode)
2. Verify Light receives and syncs the payment
3. Check that amount, customer, and accounts are correct
4. Test refund processing
5. Verify bank reconciliation matches

Once confident, enable for production.

## Troubleshooting Stripe sync

**Payments not syncing**: Check sync status, verify filter criteria, ensure payment status is "completed" (not pending or failed).

**Wrong customer assigned**: Verify customer mapping, check for duplicate customers in Light with similar names.

**Refund not processing**: Verify refund syncing is enabled, check that original payment is marked in Light, test manual refund entry.

**Connection failed**: Re-authorize Stripe integration, verify your Stripe account has API access enabled.

**Currency conversion errors**: Verify FX rate mapping, check Stripe settings for currency handling.

## Subscription management

For SaaS companies using Stripe subscriptions:

1. Light automatically tracks subscription billing
2. Upcoming renewal dates are visible in Light
3. Failed renewals alert for collection follow-up
4. Churn tracking updates automatically
5. MRR and ARR calculations incorporate Stripe subscriptions

This enables full visibility into subscription metrics.

## Reporting on Stripe data

Analyze Stripe payments in Light reporting:

1. Create custom reports showing:
   - Revenue by source (Stripe, other payment methods)
   - Subscription revenue vs. one-time
   - Refund rate and reasons
   - Average payment processing time
2. Export for analysis
3. Benchmark against industry

> Tip: Use Stripe reporting alongside Light reporting for complete financial visibility.

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [Bank integrations overview](11-11-bank-integrations.md)
- [ARR and SaaS metrics](../10-reporting/10-13-arr-saas-metrics.md)
- [Profit and loss](../10-reporting/10-3-profit-loss.md)
