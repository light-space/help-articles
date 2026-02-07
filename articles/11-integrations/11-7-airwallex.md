# Airwallex Integration

Airwallex is a global fintech platform enabling multi-currency payments, virtual accounts, and financial operations for international businesses. Light's Airwallex integration connects your payments and banking data to automatically sync transactions to your ledger.

[Open in Light →](https://app.light.inc/settings/integrations)

## Integration capabilities

The Airwallex integration enables:

- **Payment sync**: Outbound payments from Airwallex automatically post to cash disbursements
- **Inbound transaction sync**: Customer deposits to Airwallex accounts automatically post to cash receipts
- **Multi-currency account management**: Track accounts and balances in multiple currencies
- **FX conversion tracking**: Automatic recording of currency conversion impacts
- **Account balance monitoring**: Real-time visibility into Airwallex balances

This automates international payment and cash management.

## Setting up Airwallex integration

To connect Airwallex:

1. Navigate to **Settings (gear icon) > Integrations > Airwallex**
2. Click **Connect**
3. You're redirected to Airwallex to authorize
4. Sign in to your Airwallex account
5. Review permissions Light is requesting
6. Click **Authorize**
7. Light confirms connection and enables sync

Next, configure what accounts and data to sync.

## Configuring account sync

Map Airwallex accounts to Light cash accounts:

1. Navigate to **Settings > Integrations > Airwallex > Account Mapping**
2. For each Airwallex account, specify:
   - **Airwallex Account** → **Light Bank Account**
   - Currency matching (Airwallex account currency to Light account currency)
   - Reconciliation method (match by date, amount, or description)
3. Save mappings

Light then knows which Airwallex account corresponds to which Light bank account.

## Payment sync configuration

Configure how Airwallex payments become Light cash disbursements:

1. Navigate to **Settings > Integrations > Airwallex > Payment Mapping**
2. Select **Sync Payments**: Toggle on
3. Configure mapping:
   - **Airwallex Payment Amount** → **Light Cash Disbursement Amount**
   - **Airwallex Beneficiary** → **Light Vendor** (match to Light vendor master)
   - **Airwallex Payment Date** → **Light Payment Date**
   - **Airwallex Reference** → **Light Memo** (for audit trail)
4. Configure filters:
   - Payment status: Only sync completed payments
   - Currency: Specific currencies or all
   - Amount threshold: Minimum payment size to sync
5. Save configuration

## Inbound transaction sync

Configure how Airwallex incoming deposits become Light cash receipts:

1. Navigate to **Settings > Integrations > Airwallex > Receipt Mapping**
2. Select **Sync Deposits**: Toggle on
3. Configure mapping:
   - **Airwallex Deposit Amount** → **Light Cash Receipt Amount**
   - **Airwallex Sender** → **Light Customer** (match to customer master)
   - **Airwallex Deposit Date** → **Light Receipt Date**
4. Configure filters (status, currency, minimum amount)
5. Save

Light automatically posts customer payments received in Airwallex accounts.

## Multi-currency account management

Track accounts in different currencies:

1. Navigate to **Settings > Integrations > Airwallex > Multi-Currency Settings**
2. For each currency account:
   - Create Light cash account in that currency
   - Map to corresponding Airwallex account
3. Light maintains separate GL accounts for each currency
4. Reports show balances in each currency

This enables full multi-currency banking visibility.

## FX conversion tracking

When you convert currencies through Airwallex:

1. Airwallex records the conversion (EUR 100 = GBP 85 at 0.85 rate)
2. Light syncs both legs of the conversion:
   - Debit EUR account (reduction in EUR)
   - Credit GBP account (increase in GBP)
3. Light records any FX gain/loss if conversion rate differs from your standard rate

This maintains accurate FX tracking.

## Account balance monitoring

Light displays current Airwallex account balances:

1. Navigate to **Planning & Reports → Reports**
2. View all Airwallex accounts:
   - Account name and currency
   - Current balance
   - Daily activity (deposits, withdrawals)
   - Comparison to prior day
3. Real-time visibility (or configurable refresh frequency)

This helps with cash management and FX optimization.

## Sync frequency

Configure how often Light checks Airwallex:

1. Navigate to **Settings > Integrations > Airwallex > Sync Settings**
2. Select frequency:
   - **Real-time**: Via webhook (immediate sync as transaction occurs)
   - **Hourly**: Check hourly
   - **Daily**: Check once daily
3. Save

Real-time is ideal for visibility into international payments. Daily is sufficient for most organizations.

## Monitoring sync activity

Track Airwallex integration:

1. Navigate to **Settings > Integrations > Airwallex > Sync History**
2. View all past syncs:
   - Date/time
   - Number of transactions synced
   - Payments and deposits processed
   - Errors (if any)
3. Click any sync for details:
   - Which transactions processed
   - Which matched to invoices/vendors
   - Issues encountered

## Bank reconciliation with Airwallex

Reconcile Light GL accounts to Airwallex:

1. Navigate to **Ledger > Bank Reconciliation**
2. Select the Airwallex cash account
3. Upload Airwallex statement (or Light pulls automatically)
4. Match Light transactions to Airwallex statement
5. Identify reconciling items (in-transit payments, processing delays)
6. Complete reconciliation

Light simplifies reconciliation through automated sync.

## Payment approval workflows

Set up approval for international payments:

1. Configure payment approval rules (amount threshold, approver)
2. When payment needs approval, Light notifies approver
3. Approver reviews and approves in Light
4. Payment syncs from Light to Airwallex
5. Airwallex processes the payment
6. Completed payment syncs back to Light

This enables full workflow automation.

## Reporting on Airwallex transactions

Analyze Airwallex activity in Light:

1. Create custom reports showing:
   - Cash by currency
   - Payments by vendor and currency
   - Deposits by customer and currency
   - FX gains/losses
2. Export for analysis
3. Benchmark cash efficiency

## Troubleshooting Airwallex sync

**Payments not syncing**: Check sync status, verify filter criteria, ensure Airwallex payment is completed (not pending).

**Wrong vendor assigned**: Verify vendor mapping, check for duplicate vendor names, manually link if needed.

**Currency mismatch**: Verify account currency matches Airwallex account currency, check FX conversion settings.

**Connection failed**: Re-authorize Airwallex integration, verify your Airwallex account has API access.

**Balance discrepancy**: Check for pending transactions, verify filter criteria, review recent FX conversions.

## Automating international payments

Use Airwallex integration for streamlined global payments:

1. Create payable invoice in Light
2. Schedule payment through Light
3. Light syncs payment details to Airwallex
4. Airwallex processes international payment
5. Completed payment syncs back to Light
6. AP marked paid automatically

This eliminates manual payment entry.

## Multi-entity Airwallex management

For organizations with multiple entities:

1. Configure separate Airwallex accounts per entity (or per currency within entity)
2. Map each Airwallex account to entity-specific Light GL accounts
3. Light consolidates in multi-entity reporting
4. Each entity sees only its own Airwallex activity

This maintains proper separation of entity finances.

## Related articles

- [Integrations overview](11-1-integrations-overview.md)
- [Bank integrations overview](11-11-bank-integrations.md)
- [Stripe integration](11-6-stripe.md)
- [Multi-currency revenue recognition](../09-revenue-compliance/9-4-multi-currency-revenue.md)
